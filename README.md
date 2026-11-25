# Chatbot de Atendimento — Projeto Nadar Mais (UERN)

Protótipo de assistente virtual construído com **n8n** e **Gemma 4 (Google AI Studio)** para atendimento automatizado sobre horários, faixas etárias, valores de contribuição e regras do Projeto Nadar Mais.

## Pré-requisitos
1. **Docker Desktop** instalado e em execução.
2. Uma chave de API gratuita do **Google AI Studio** (`aistudio.google.com` ➔ *Get API key*).

## Como rodar localmente

### 1. Subir o ambiente n8n
Abra o terminal dentro desta pasta e execute:
\`\`\`bash
docker compose up -d
\`\`\`
Aguarde cerca de 15 segundos e acesse **http://localhost:5678** no navegador (na primeira vez, crie um usuário e senha locais).

### 2. Importar o fluxo do chatbot
1. No painel do n8n, clique em **Create Workflow**.
2. Clique no menu **`...`** (canto superior direito) ➔ **Import from File...**
3. Selecione o arquivo **`workflow-nadar-mais.json`** desta pasta.

### 3. Configurar a chave da IA (Gemma 4)
1. Dê um duplo clique no sub-nó **Google Gemini Chat Model** (conectado na parte inferior do *AI Agent*).
2. Em **Credential to connect with**, clique em **Create New Credential**.
3. Cole sua **API Key** do Google AI Studio, clique em **Save** e feche a janela.

### 4. Abrir e testar o Chat
1. Clique no botão **Publish** no canto superior direito da tela.
2. Dê um duplo clique no nó inicial **Chat Trigger** (`On chat message`), copie a **Chat URL** e abra em uma nova aba do navegador.