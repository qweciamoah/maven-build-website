pipeline{
    agent any 

    tools {
        maven "3.9.6"
    }

    stages {
        stage( "git cloning") {
            steps{
                git 'https://github.com/qweciamoah/maven-build-website.git'
            }
        }
        stage ("build , test, Package") {
            steps {
                sh'''
                mvn clean
                mvn test
                mvn package
                sh '''
            }
        }
        stage ("Build with Docker") {
            steps {
                sh "docker build -t maven-build-website ."
            }
        }
    }
}
