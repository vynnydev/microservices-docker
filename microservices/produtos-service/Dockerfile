# Dockerfile para o Microserviço de Produtos
FROM python:3.10-slim

# Define o diretório de trabalho na imagem
WORKDIR /app

# Variáveis de ambiente
ENV PYTHONDONTWRITEBYTECODE=1
ENV PYTHONUNBUFFERED=1
ENV FLASK_APP=app.py

# Instala as dependências
RUN pip install --no-cache-dir flask gunicorn

# Copia o código fonte para o diretório de trabalho
COPY app.py .

# Informa em qual porta o container estará escutando
EXPOSE 9001

# Comando para iniciar o aplicativo quando o container for executado
CMD ["gunicorn", "--bind", "0.0.0.0:9001", "app:app"]