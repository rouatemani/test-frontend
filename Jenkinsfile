pipeline {
  
  agent any
  stages {
    stage('Clone Sources') {
      steps {
        git 'https://github.com/rouatemani/test-frontend.git'
      }
    }
	  stage('Building image') { 
       steps { 
         sh """ 
            docker build -t vuejs-cookbook/dockerize-vuejs-app .
		 """	 
            
        } 
    }
	  stage('run') { 
       steps { 
         sh """ 
            docker run -d vuejs-cookbook/dockerize-vuejs-app
		 """	
        }
    }
	  stage('tag') { 
       steps { 
         sh """ 
            docker tag vuejs-cookbook/dockerize-vuejs-app docker.we-settle.com:5000/xxx:yyy
		      """	
        }
    }
    stage('push') { 
       steps { 
         sh """ 
            docker push docker.we-settle.com:5000/xxx:yyy
		      """	
        }
    }
	
  }
}