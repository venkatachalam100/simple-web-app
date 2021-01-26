pipeline {
  agent any
  stages {
    stage ( 'Git Clone') {
      steps {
        git 'https://github.com/venkatachalam100/simple-web-app.git'
      }
    }
    stage ( 'Maven Build') {
      steps {
        bat 'mvn clean install'
      }
    }
    stage ( 'unit test') {
      steps {
        echo 'unittest'
      }
    }
    stage ( 'deploy') {
      steps {
        deploy adapters: [tomcat8(credentialsId: 'admin', path: '', url: 'http://localhost:9595')], contextPath: '/simple-web-app', war: '**/*.war'
      }
    }
  }
}