
pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/vijayjerry/nodejs.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'npm test'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t nodejs-image .'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh 'docker run -d -p 3000:3000 nodejs-image'
            }
        }
    }
}

