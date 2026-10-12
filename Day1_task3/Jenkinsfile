pipeline {
    agent any

    stages {
        stage('Hello github') {
            steps {
                echo 'Hello github'
            }
        }
        stage('Hello NTI') {
            steps {
                echo 'Hello NTI'
            }
        }
        stage('Hello script') {
            steps {
                sh'''
                chmod +x hello.sh
                ./hello.sh
                '''
            }
        }
    }
    post {
        failure{
            mail(
                subject: "Jenkins Pipeline Failed: ${env.JOB_NAME}",
                body: """
                    The Jenkins pipeline has failed.

                    Job: ${env.JOB_NAME}
                    Build Number: ${env.BUILD_NUMBER}
                    Build URL: ${env.BUILD_URL}

                """,
                to: 'salmaamostafa2005@gmail.com'
            )
        }
    }
}
