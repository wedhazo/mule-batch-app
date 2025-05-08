pipeline {
    agent any

    environment {
        // Use values from your pom.xml
        ANYPOINT_USERNAME = 'MEKELE1'
        ANYPOINT_PASSWORD = 'beriha@123KB!'
        DEPLOYMENT_TARGET_ID = '<REPLACE_WITH_YOUR_TARGET_ID>'
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/wedhazo/mule-batch-app.git'
            }
        }

        stage('Build & Deploy to CloudHub 2.0') {
            steps {
                sh '''
                    mvn clean deploy \
                    -Danypoint.username=$ANYPOINT_USERNAME \
                    -Danypoint.password=$ANYPOINT_PASSWORD \
                    -Dcloudhub2.deploymentTargetId=$DEPLOYMENT_TARGET_ID
                '''
            }
        }
    }
}
