# n8n Project

Este repositório configura e roda o [n8n](https://n8n.io/), uma ferramenta de automação de fluxo de trabalho, usando Docker. O projeto está configurado para ser executado localmente com Docker Compose, facilitando o setup e o gerenciamento do ambiente.

## Pré-requisitos

Antes de começar, verifique se você tem o seguinte instalado:

- [Docker](https://www.docker.com/)
- [Docker Compose](https://docs.docker.com/compose/)

## Como rodar localmente

### 1. Clonando o repositório

Clone o repositório para sua máquina local:

```bash
git clone <URL_DO_REPOSITORIO>
cd <DIRETORIO_DO_REPOSITORIO>
```

### 2. Executando o Docker Compose

Com o Docker e o Docker Compose instalados, execute o seguinte comando para iniciar o n8n localmente:

```bash
docker-compose up -d
```

Isso irá:

- Baixar a imagem do Docker do n8n.
- Criar o volume `n8n_data` para persistência de dados.
- Iniciar o n8n na porta `5678`.

Após o comando ser executado, você pode acessar o n8n em [http://localhost:5678](http://localhost:5678).

### 3. Configurações

O fuso horário do n8n é configurado como `America/Sao_Paulo` por padrão. Se desejar modificar o fuso horário, altere a variável `GENERIC_TIMEZONE` e `TZ` no arquivo `docker-compose.yml`.

### 4. Para parar o n8n

Para parar o container, execute:

```bash
docker-compose down
```

Isso irá parar e remover os containers, mas manterá os dados persistentes no volume `n8n_data`.

## Dockerfile

O `Dockerfile` neste projeto utiliza a imagem oficial do n8n para criar um ambiente com as configurações básicas. Para ajustes mais avançados, você pode modificar o `Dockerfile` conforme necessário.

```Dockerfile
FROM n8nio/n8n:latest
```
