pipeline {
    agent any

    stages {
        stage('clone') {
            steps {
                checkout scmGit(branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/satyapujari06/teerdhaa9500.git']]) 
            }
        }
        stage('docker') {
            steps {
                script {
                   withDockerRegistry(url: 'https://hub.docker.com/') {
                         sh 'docker build -t satyapujari/candystore .'
                         sh 'docker push satyapujari/candystore:latest'
                   }
               }
            }
        }
    }
}
