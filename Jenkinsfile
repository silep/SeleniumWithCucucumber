pipeline {
  agent any
  stages {
    stage('Test') {
      parallel {
        stage('Maven') {
          steps {
            echo 'Running from Jenkins file'
            withMaven(maven: 'mvn-3.6.3') {
              sh(script: 'mvn compile', label: 'maven')
            }

          }
        }

        stage('Cucumber') {
          steps {
            cucumber '**/*.json'
          }
        }

      }
    }

    stage('finish') {
      steps {
        echo 'finished'
      }
    }

  }
}