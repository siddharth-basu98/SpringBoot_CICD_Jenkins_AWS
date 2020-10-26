pipeline {
   agent any

   stages {
      stage('Build') {
        steps {
          echo 'Building...'
          echo "Running ${env.BUILD_ID} ${env.BUILD_DISPLAY_NAME} on ${env.NODE_NAME} and JOB ${env.JOB_NAME}"
	  sh "mvn clean package"
        }
   }
   stage('Test') {
     steps {
        echo 'Testing...'
	sh "mvn test"
     }
   }
   stage('Deploy') {
     steps {
       echo 'Deploying...'
       sh "mvn install"
       sh "spring-boot:run"			
     }
   }
  }
}
