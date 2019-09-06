node  {
        
  stage ('Checkout') {
    git branch: '${gitBranch}', credentialsId: 'git-ssdc-kube', url: '${gitUrl}'
  }


  stage('Docker build') {
      
    docker.withRegistry('https://image.docker.ctbiyi.com', 'docker-admin') {

        def customImage = docker.build("${imageName}:${imageVersion}")

        customImage.push()
    }
  }  
}