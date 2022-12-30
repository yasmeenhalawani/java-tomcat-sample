pipeline {
    agent any
    tools {
        maven 'maven-tool'
    }   
    stages {
        stage('Build Application') {
            steps {
                sh 'mvn -f pom.xml clean package'
            }
            post {
                success {
                    echo "Now Archiving the Artifacts....."
                    archiveArtifacts artifacts: '**/*.war'
                }
            }
        }
    }
}
