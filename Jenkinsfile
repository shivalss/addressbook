pipeline {
    agent any
    stages {
        stage('Compile') {
            steps { 
                sh 'mvn compile'
            }
        }
        stage('test') {
            steps { 
                sh 'mvn test'
            }
        }
        stage('Code Review') {
            steps { 
                sh 'mvn cobertura:cobertura'
            }
        }
        stage('Metrics') {
            steps { 
                sh 'mvn -P metrics PMD:PMD'
            }
        }
        stage('package') {
            steps { 
                sh 'mvn package'
            }
        }
        stage('Deploy') {
            steps { 
                sh 'mvn deploy'
            }
        }
    }
}
