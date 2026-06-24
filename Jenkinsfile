pipeline {
    agent any

    stages {

        stage('Clone'){
            steps{
                git 'https://github.com/sam-mendhe/new_app_jen.git'
            }
        }

        stage('Build'){
            steps{
                sh 'docker build -t my-web-app .'
            }
        }

        stage('Deploy'){
            steps{
                sh '''
                docker stop my-web-app || true
                docker rm -f my-web-app || true
                docker run -d --name my-web-app -p 8081:80 my-web-app
                '''
            }
        }
    }
}