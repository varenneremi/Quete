pipeline {
    agent any
    stages {
        stage('Titre') {
            steps {
                sh 'echo "La Team Spirit" > livre.md'
            }
        }
        stage('Introduction') {
            steps {
                sh "cat -n Readme.md >> livre.md"
            }
        }
        stage('Histoire') {
	    parallel {
		stage('Scene1'){
            	    steps {
		     	sh "cat -n Intrigue1.md >> livre.md"
		    }
		}
		stage('Scene2'){
                    steps { 
                        sh "cat -n Intrigue2.md >> livre.md"
                    }
                }
		stage('Scene3'){
                    steps { 
                        sh "cat -n Intrigue3.md >> livre.md"
                    }
                }
            }
        }
        stage('Fin') {
            steps {
                sh 'echo "Fin..." >> livre.md'
            }
        }
	stage('Impression') {
	    steps {
		sh 'more livre.md'
		archiveArtifacts artifacts: 'livre.md', fingerprint: true
	    }
	}
    }
}
