pipeline {
    agent any
    
    stages {
        stage('Clone repository') {
            steps {
                // Ensure 'main' is the branch used, not 'master'
                git branch: 'main', url: 'https://github.com/tayyabsattar042/Simple-Nodejs-application.git'
            }
        }
        
        stage('Build Docker image') {
            steps {
                script {
                    docker.build("my-node-app")
                }
            }
        }
        
        stage('Run Docker container') {
            steps {
                script {
                    docker.image("my-node-app").run('-p 3000:3000')
                }
            }
        }
    }
}
