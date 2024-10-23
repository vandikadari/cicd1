pipeline {
    agent any
    stages {
        stage('Checkout Code') {
            steps {
                git 'https://github.com/vandikadari/cicd1.git'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean package' // For Java
                // For Node.js, you might use: sh 'npm install'
            }
        }
        stage('Unit Testing') {
            steps {
                sh 'mvn test' // For Java
                // For Node.js, you might use: sh 'npm test'
            }
        }
        stage('Docker Build') {
            steps {
                sh 'docker build -t your-docker-image-name .'
            }
        }
        stage('Push Docker Image') {
            steps {
                sh 'docker login -u vandik -p Badullakgp@11'
                sh 'docker push your-docker-image-name'
            }
        }
        stage('Deploy to AWS') {
            steps {
                // Add deployment commands here, e.g., AWS CLI commands
            }
        }
    }
}
