pipeline {
    agent any
    environment {
        STAGING_ENVIRONMENT= "AWS EC2 instance"
    }
    stages {
        stage('Build') {
            steps {
                echo 'Compile and package the source code using Maven.'
            }
        }
    
        stage('Unit and Integration Tests') {
            steps {
                echo 'Run unit tests with JUnit and integration tests with TestNG.'
            }
            post {
                success {
                    emailext subject: 'Build Successful - Unit and Integration Tests',
                        body: 'Your build was successful! ',
                        to: 'salonivinodmehta@gmail.com, art.random.email@gmail.com',
                        attachLog: true
                }
            }
        }
    }
    post {
        always {
            echo 'Cleaning up after pipeline execution.'
        }
    }
}
