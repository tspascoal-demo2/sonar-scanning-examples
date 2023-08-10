node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    def mvn = tool 'Default Maven';
    withSonarQubeEnv() {
      dir("sonarqube-scanner-maven/maven-basic") {
        sh "${mvn}/bin/mvn clean verify sonar:sonar -Dsonar.projectKey=tspascoal-demo2_sonar-scanning-examples_AYnfO7-5qQBUWseO844w"
      }
    }
  }
}
