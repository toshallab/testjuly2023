pipeline {
    agent any
    tools {nodejs "mynodejs"}
    environment {
        NODE_ENV= "producation" 
            }
    stages {
        stage('Dev') {
            steps {
                git 'https://github.com/toshallab/testjuly2023.git'
                echo "file1.txt file content "
                sh 'cat file1.txt'
            }
        }
        stage ('build') {
            steps {
            echo NODE_ENV
            withCredentials([string(credentialsId: '66a5f84e-61e7-4f17-bc28-8648023ddf0e', variable: 'sec123')]) {
            // some block
            echo sec123 
        }
             sh 'npm install'    
            }
        }
                stage('saveartifacts') {
            steps {
                archiveArtifacts artifacts: '**', followSymlinks: false
            }
        }
    }
}