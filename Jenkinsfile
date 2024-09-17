## pipeline with multiple stages
pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "MVN3"
    }

    stages {
        stage('pull') {
            steps {
                // Get some code from a GitHub repository
                git credentialsId: 'git', url: '{your repo details}'
                }
        }
        
        stage('build') {
            steps {
                sh "mvn -Dmaven.test.failure.ignore=true -f api-gateway/ clean package"
            }
        }
