pipeline {
    agent any

    stages {

        stage('Debug') {
            steps {
                sh 'pwd'
                sh 'ls -la'
                sh 'terraform version'
            }
        }

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Terraform Init') {
            steps {
                sh 'terraform init'
            }
        }

        stage('Terraform Validate') {
            steps {
                sh 'terraform validate'
            }
        }

        stage('Terraform Plan') {
            steps {
                sh 'terraform plan'
            }
        }

        stage('Terraform Apply') {
            steps {
                input message: 'Apply Terraform?'
                sh 'terraform apply -auto-approve'
            }
        }
    }
}
