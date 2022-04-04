pipeline{

    agent any
    environment{
        NEW_VERSION  = '1.3.0'
        USER_CREDENTIALS = credentials('user-credentials')
    }
    parameters {
        choice(name: 'VERSION', choices: ['1.1.0', '1.2.0', '1.3.0'], description: '')
        booleanParam(name: 'executeTests', defaultValue: true, description: '')
    }
    stages {

        stage("build"){

            steps{
                echo 'building the application...'
                echo "building version ${NEW_VERSION}..."
            }
        }


        stage("test"){
            when{
                expression{
                    params.executeTests
                }
            }

            steps{
                echo 'testing the application...'
                echo "deploying with ${USER_CREDENTIALS}"
            }
        }



        stage("deploy"){

            steps{
                echo 'deploying the application...'
                echo "deploying the version ${params.VERSION}"
            }
        }
}