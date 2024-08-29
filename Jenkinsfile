pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo "building the code using maven to compile amd package code"
      }
    }
    stage('Unit and integration tests') {
      steps {
        echo "Run unit and integration tests by using Protractor"
      }
      post {
        success {
          emailext(
            to: "glvsrayudu956@gmail.com",
            subject: "Unit and Integration tests stage wwas completed",
            body: "Unit and Integration Tests stage was successful!",
            attachLog: true
          )
        }
        failure {
          emailext(
            to: "glvsrayudu956@gmail.com",
            subject: "Unit and Integration Tests stage was failed",
            body: "Unit and Integration Tests stage failed",
            attachLog: true
          )
        }
      }
    }
    stage('Code analysis') {
      steps {
        echo "Integrate a code analysis tool by using Jenkins"
      }
    }
    stage('Security Scan') {
      steps {
        echo "Perform a security scan on the code"
      }
      post {
        success {
          emailext(
            to: "glvsrayudu956@gmail.com",
            subject: "Security Scan stage was completed",
            body: "Security Scan stage was successful!",
            attachLog: true
          )
        }
        failure {
          emailext(
            to: "glvsrayudu956@gmail.com",
            subject: "Security Scan stage was Failed",
            body: "Security Scan stage failed!",
            attachLog: true
          )
        }
      }
    }
    stage('Deploy to Staging') {
      steps {
        echo "Deploy the application to a staging server by using EC2"
      }
    }
    stage('Integration Tests on Staging') {
      steps {
        echo "Run integration tests on a staging environment by using TestNG"
      }
    }
    stage('Deploy to Production') {
      steps {
        echo "Deploy the app to a production server using AWS"
      }
    }
  }
  post {
    success {
      echo "Pipeline passed!"
    }
    failure {
      echo "Pipeline failed!"
    }
  }
}
