pipeline {
    agent any

    stages {
        stage('clonando repositório') {
            steps {
                git branch: 'main', url: 'https://github.com/valdenirrt/jk-public-gh.git'
            }
        }
        stage('criando imagem docker') {
            steps {
                 sh 'docker build -t webapp:${BUILD_NUMBER} .'
                }
        }
        stage('implanto a aplicação') {
            steps {        
                   sh 'docker run --rm -d -p 3000:3000 --name webapp_ctr webapp:${BUILD_NUMBER}'
                }
        }
    }
    
}
