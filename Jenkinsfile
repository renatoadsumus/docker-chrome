pipeline {
    agent any     
    stages {		
		
        stage('Build image') { 
            steps {
                echo "Construindo a imagem Docker com Chrome e ChromeDriver" 	
				sh "docker build -t renatoadsumus/chrome_standart:latest ."                
            }
        }
		
		stage('Push image') { 
			steps {			
			echo "Deploy nova imagem Docker Hub"				
			sh "docker login --username=renatoadsumus --password=${DOCKER_HUB_PASS}"
			sh "docker push renatoadsumus/chrome_standart:latest"
						
			}			
		}	
        
    }
 }