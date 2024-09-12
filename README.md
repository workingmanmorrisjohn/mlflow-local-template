This is an example of creating a local mlflow server on docker that uses minio as the object storage. This is based on: https://blog.min.io/setting-up-a-development-machine-with-mlflow-and-minio/ but the postgresql is removed

1. Create a config.env file containing:
```.env
# MLflow Configuration
MLFLOW_PORT=5000
MLFLOW_BUCKET_NAME=mlflow

# MinIO Access Keys - These are needed by MLflow
MINIO_ACCESS_KEY=XeAMQQjZY2pTcXWfxh4H
MINIO_SECRET_ACCESS_KEY=wyJ30G38aC2UcyaFjVj2dmXs1bITYkJBcx0FtljZ

# MinIO Configuration
MINIO_ROOT_USER=minio_user                # Correct syntax without quotes
MINIO_ROOT_PASSWORD=minio_pwd             # Correct syntax without quotes
MINIO_ADDRESS=:9000                       # Correct syntax without quotes
MINIO_PORT=9000                           # Correct environment variable
MINIO_CONSOLE_PORT=9001                   # Correct environment variable
MINIO_STORAGE_USE_HTTPS=0                 # Use '0' instead of 'False' for compatibility
MINIO_CONSOLE_ADDRESS=:9001               # Correct syntax without quotes
```


2. Run: 
``` bash
docker-compose --env-file config.env up -d --build
```

3. Configure minio and get access keys. See: https://blog.min.io/setting-up-a-development-machine-with-mlflow-and-minio/ for more details

4. Re-run:
``` bash
   docker-compose --env-file config.env up -d --build
```
