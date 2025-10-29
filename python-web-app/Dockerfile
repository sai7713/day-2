FROM ubuntu
WORKDIR /app
COPY requirements.txt /app
COPY devops /app/devops

# FIX: Use the flag to force installation and combine commands for efficiency/cleanup
RUN apt-get update && \
    apt-get install -y python3 python3-pip && \
    pip install --no-cache-dir --break-system-packages -r requirements.txt && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

WORKDIR /app/devops

ENTRYPOINT ["python3"]
CMD ["manage.py", "runserver", "0.0.0.0:8000"]
