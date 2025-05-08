pipeline {
    agent any

    environment {
        SONARQUBE_SCANNER_HOME = tool 'SonarQube Scanner'
    }

    stages {
        stage('Clone') {
            steps {
                git 'git@github.com:rafiimafif/Project2.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the application...'
                // Add your build steps here, e.g. `mvn clean install` or `npm run build`
            }
        }

        stage('Code Quality - SonarQube') {
            steps {
                withSonarQubeEnv('SonarQubeServer') {
                    sh "${env.SONARQUBE_SCANNER_HOME}/bin/sonar-scanner"
                }
            }
        }

        stage('Artifact Upload') {
            steps {
                echo 'Uploading artifacts to Artifactory...'
                // Add Artifactory upload commands here
            }
        }
    }
}
