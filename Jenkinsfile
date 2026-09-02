pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                echo 'Getting source code...'
                checkout scm
            }
        }
        stage('Build') {
            steps {
                echo 'Building the Python application...'
                sh 'python3 -m py_compile app.py'
            }
        }
        stage('Test') {
            steps {
                echo 'Running automated tests...'
                sh 'python3 -m unittest test_app.py'
            }
        }

    }
    post {
        success {
            echo 'BUILD SUCCESSFUL - All tests passed!'
        }
        failure {
            echo 'BUILD FAILED - Please check the errors.'
        }
    }
}
