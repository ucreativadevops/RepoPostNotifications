pipeline {
    agent any
    
    environment {
        LISTA_CORREOS = 'ucreativadevops@gmail.com;ucreativacursoci@gmail.com'
        CUERPO_CORREO = "El pipeline ${BUILD_URL} tuvo un resultado"
        TITULO_CORREO = "${BUILD_URL} STATUS"
    }

    stages {
        stage('Success') {
            steps {
                echo 'Todo bien'
            }
        }
        stage('Failure') {
            steps {
                echo 'Todo bien'
            }
        }
    }
    
    post {
        success {
            emailext body: "${CUERPO_CORREO} exitoso", subject: "${TITULO_CORREO}", to: "${LISTA_CORREOS}"
        }
        failure {
            emailext body: "${CUERPO_CORREO} fallido", subject: "${TITULO_CORREO}", to: "${LISTA_CORREOS}"
        }
    }
}