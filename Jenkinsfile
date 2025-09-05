pipeline {
    agent any
    tools {
        gradle 'GRADLE_HOME'   // Use your configured Gradle tool name
        jdk 'JAVA_HOME'        // Use your configured JDK tool name
    }
    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/venkatgip/spring-web-sample-gradle.git', branch: 'master'
            }
        }
        stage('Build') {
            steps {
                bat 'gradle clean build  --warning-mode all'
            }
        }
        stage('Test') {
            steps {
                bat 'gradle test  --warning-mode all'
            }
        }
        stage('Archive') {
            steps {
                archiveArtifacts artifacts: 'build/libs/*.jar', fingerprint: true
            }
        }
    }
}
