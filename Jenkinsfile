pipeline {
    agent any

    tools {
        maven 'MyMaven'
    }

    stages {

        stage('Checkout SCM') {
            steps {
                git branch: 'main',
                url: 'https://github.com/vikas-1421/MavenAnsibleWebApp1.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean compile'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Archive') {
            steps {
                sh 'mvn package -DskipTests'
            }
        }
    }

    post {

        success {
            echo 'Build Successful'
        }

        failure {
            echo 'Build Failed'
        }
    }
}
