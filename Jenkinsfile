pipeline {
    agent any
    stages {
        stage('Git Checkout') {
            steps {
                script {
                    git branch: 'main',
                        url: 'https://github.com/roman-noah/qa-cypress-demoblaze.testing.git'
                }
            }
        }
        stage('Install dependencies') {
            steps {
                script {
                    bat 'npm install'
                }
            }
        }
        stage('Run tests') {
            steps {
                script {
                    bat 'npm run cy:run-ci'
                }
            }
        }
    }
    post {
        always {
            archiveArtifacts artifacts: 'cypress/reports/**'
        }
    }
}