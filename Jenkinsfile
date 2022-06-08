pipeline {
  agent any
  stages {
    stage('test') {
      parallel {
        stage('test') {
          steps {
            echo 'hello phase de test'
            sh 'echo " On fait genre Maven "'
          }
        }

        stage('build') {
          steps {
            git(url: 'https://github.com/kliakos/sparkjava-war-example.git', branch: 'master')
            sh 'mvn clean install'
            archiveArtifacts 'target/*.war'
          }
        }

      }
    }

    stage('reports') {
      steps {
        sh 'echo " phase de test JUnit"'
      }
    }

    stage('end') {
      steps {
        sh 'echo "Fin des dtaches, OK"'
      }
    }

  }
}