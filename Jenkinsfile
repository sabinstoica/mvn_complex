pipeline {
    agent {label 'builder'}
stages {
            stage ('Get code from GIT') {
                steps {
                    // Get the repo from GitHub
                    git 'https://github.com/sabinstoica/mvn_complex.git'
                       }
            stage('build') {
                     // all tests: other variants: only unit, integration, or all (incl. functional testing)
                     sh 'mvn clean package'
   }
            stage('SonarQube analysis') {
      withSonarQubeEnv('sonar2') {
        sh 'mvn sonar:sonar'
            }
         }
      }
   }
}
