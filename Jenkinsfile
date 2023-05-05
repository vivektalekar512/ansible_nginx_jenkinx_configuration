pipeline {
    agent {
        label 'masternodes'
    }
    stages {
        stage('Checkout') {
            steps {
                
                     checkout scmGit(branches: [[name: 'refs/heads/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/vivektalekar512/ansible_nginx_jenkinx_configuration']])
              
            }
        }
        stage('Ansible Playbook Execution') {
            steps {
                sh 'ansible-playbook  $WORKSPACE/master_playbook.yml'
            }
        }
    }
    post {
        always {
            // Clean the workspace after the build
            cleanWs()
        }
    }
}
