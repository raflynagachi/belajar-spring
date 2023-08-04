pipeline {
    agent {
      node {
        label "linux && java17"
      }
    }

    stages {
        stage("build"){
            steps{
                echo ("building...")
                sh("chmod +x ./mvnw")
                sh("./mvnw clean compile test-compile")
                echo ("successfully built")
            }
        }
        stage("test"){
            steps{
                echo ("testing...")
                echo ("test passed")
            }
        }
        stage("deploy"){
            steps{
                echo ("deploying...")
                echo ("successfully deployed")
            }
        }
    }

    post { // post-action after stages completed
      always { echo ("always action notification") }
      failure { echo ("failure action") }
      regression { echo ("success to error action") }
    }
}