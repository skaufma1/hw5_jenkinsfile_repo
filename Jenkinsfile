pipeline {
    agent any

    stages {
        stage('File') {
            steps {
                checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'git@github.com:skaufma1/hw5_repo.git']])
                sh 'cat README.md'
                
                script {
                    
                    if (fileExists('README.md')) {
                        echo 'Good news: README.md file exists'
                    }
                    else {
                        echo 'README.md file does NOT Exist'
                    }
                    
                    def content = readFile(file: "README.md")
                    mail to: "shmuel.kaufmann1@gmail.com",
                    subject: "Test Email",
                    replyTo: 'Test.A@gmail.com',
                    body: content
                }
            }
        }
        stage('Branch'){
            steps {
                echo 'Branch is: sub_branch'
            }
        }
    }
}
