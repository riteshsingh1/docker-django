# Django Version : 3.2

# For local development
```bash
docker-compose up

```


# For Production

## Step 1: Copy `.env.prod.sample` to `.env.prod`

## Step 2: Update Prodution Settings to `.env.prod`

## Step 3: Copy `.env.db` to `.env.db.prod`
## Step 4: Update Database Settings to `.env.db.prod`

## Step 5: 
```bash
$ docker-compose -f docker-compose.prod.yml up -d --build

```

# Documentation

## For running migrations -
> On Local
```bash
$ docker-compose exec web python manage.py migrate --noinput
```

> On Production 
```bash
$ docker-compose -f docker-compose.prod.yml exec web python manage.py migrate --noinput
```
## For Static Files

```bash
$ docker-compose -f docker-compose.prod.yml exec web python manage.py collectstatic --no-input --clear
```
# Note:

## In production 1 folder `postgres-data` will be created make sure to keep this folder to `.gitignore`. This folder will be used to store database , so that data can be persisted even when containers are rebuild.



