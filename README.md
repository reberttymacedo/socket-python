# PythonUDPTCP

Aluno: Rebertty Macedo da Silva



# Passos


## Efetuando o clone do repositório:
```
git clone http://github.com/othonb/pythonUDPTCP.git
```
## Entrando na pasta do projeto:
```
cd pythonUDPTCP/TCP
```
## Criando arquivo Dockerfile:
```
nano Dockerfile
```
Inserindo passos para definições da imagem:

```
LABEL version="1.0.0" description="Exemplo de Servidor TCP do Kurose" maintainer="Edilayne Salgueiro <edilayne@dcomp.ufs.br>"

FROM python:3-slim

WORKDIR /usr/src/tcpcapital

COPY . .

EXPOSE 12000

CMD [ "python3", "./TCPServer.py" ]
```

Buildando imagem:
```
docker build -t  tcpcapital .
```
Verificando portas utilizadas:
```
docker ps
```
Rodando imagem:
```
docker run -d -p 33388:12000 -it --rm --name TCP-Rebertty tcpcapital
```
Obtendo ID do container que foi inicializado:
```
docker ps | grep Rebertty
```
Conferindo logs da aplicação:
```
docker logs "id do container"
```

















PROJETO UTILIZADO COMO BASE: https://github.com/othonb/pythonUDPTCP
