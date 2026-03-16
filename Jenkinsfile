pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                git 'https://github.com/username/nodejs-devops-project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t username/devops-node-app:v1 .'
            }
        }

        stage('Push Docker Image') {
            steps {
                sh 'docker push username/devops-node-app:v1'
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                sh 'kubectl apply -f deployment.yaml'
                sh 'kubectl apply -f service.yaml'
            }
        }
    }
}