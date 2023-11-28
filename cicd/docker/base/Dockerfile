FROM python:3.9-slim

# Establish a working folder
WORKDIR /app

# Establish dependencies
COPY requirements.txt .
RUN python -m pip install -U pip wheel && \
    pip install -r requirements.txt

RUN rm -rf /app/requirements.txt

# Become non-root user
RUN useradd -m -r service && \
    chown -R service:service /app
USER service
