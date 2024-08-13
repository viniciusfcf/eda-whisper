# ead-arq-whisper

![alt text](image.png)

# Projetos

## Uploader
Disponibiliza a funcionalidade do upload de arquivos de audio utilizando HTTP/REST, envia esses arquivos via AMQP para o ArtemisMQ.
O retorno do REST são 3 atributos: MessageID, Time (tempo que a transcrição deve demorar) e URLRetrieverID (é um atalho que a aplicação pode fazer o GET)

## Translator
Recupera as mensagens com os arquivos de audio do ActiveMQ, submete para o modelo que faz a transcrição e retorna o texto para o ArtemisMQ

## Retriever
Disponibiliza um modo de acessar as transcrições geradas. Nesse exemplo recuperamos as transcrições diretamente do ArtemisMQ pelo ID.

Pode ser alterado para buscar de um banco (Postgres ou MongoDB) ou cache (Redis ou Infinispan).

## WhisperCPP
Modelo de fato que faz a transcrição.