pipeline {
    agent any

    stages {

        stage('Clone Repo') {
            steps {
                git branch: 'main', url: 'https://github.com/vamshikrishna0/python-devops-demo.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t python-devops-demo .'
            }
        }

        stage('Stop Old Container') {
            steps {
                sh 'docker stop python-devops-demo || true'
                sh 'docker rm python-devops-demo || true'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 5000:5000 --name python-devops-demo python-devops-demo'
            }
        }
    }
}
