pipeline {
    agent any
   
    environment{
        SCANNER_HOME= tool 'sonar-scanner'
    }

    stages {
        stage('git-checkout') {
            steps {
                git branch: 'main', changelog: false, poll: false, url: 'https://github.com/vishalmothey/to-do-app.git'
            }
        }

   stage('Sonar Analysis') {
            steps {
                   sh ''' $SCANNER_HOME/bin/sonar-scanner -Dsonar.url=http://13.235.27.6:9000/ -Dsonar.login=squ_12ef2129037e410cfaf726da18f782234eaf0af2 -Dsonar.projectName=to-do-app \
                   -Dsonar.sources=. \
                   -Dsonar.projectKey=to-do-app '''
               }
            } 
           
	/*	stage('OWASP Dependency Check') {
            steps {
               dependencyCheck additionalArguments: '--scan ./', odcInstallation: 'DP'
                    dependencyCheckPublisher pattern: '**/dependency-check-report.xml'
            }
        } */
     

       /*  
       stage('Docker Build') {
            steps {
               script{
                   withDockerRegistry(credentialsId: '9ea0c4b0-721f-4219-be62-48a976dbeec0') {
                    sh "docker build -t  todoapp:latest -f docker/Dockerfile . "
                    sh "docker tag todoapp:latest username/todoapp:latest "
                 }
               }
            }
        } 
	*/

       /* 
       stage('Docker Push') {
            steps {
               script{
                   withDockerRegistry(credentialsId: '9ea0c4b0-721f-4219-be62-48a976dbeec0') {
                    sh "docker push  username/todoapp:latest "
                 }
               }
            }
        } 
*/

       /* stage('trivy') {
            steps {
               sh " trivy username/todoapp:latest"
            }
        } 
*/

	/*	stage('Deploy to Docker') {
            steps {
               script{
                   withDockerRegistry(credentialsId: '9ea0c4b0-721f-4219-be62-48a976dbeec0') {
                    sh "docker run -d --name to-do-app -p 4000:4000 username/todoapp:latest "
                 }
               }
            }
        }
*/

    }
}
