pipeline {
    agent any

    stages {
        stage ('Compile Stage') {

            steps {
                withTerraform(terraform : 'terraform_0_12_28') {
                    sh 'mvn clean compile'
                }
            }
        }

        stage ('Testing Stage') {

            steps {
                withTerraform(terraform : 'terraform_0_12_28') {
                    sh 'mvn test'
                }
            }
        }


        stage ('Deployment Stage') {
            steps {
                withTerraform(terraform : 'terraform_0_12_28') {
                    sh 'mvn deploy'
                }
            }
        }
    }
}
