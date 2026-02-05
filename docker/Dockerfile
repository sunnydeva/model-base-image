ARG BASE_IMAGE=${BASE_IMAGE}

FROM python:$BASE_IMAGE-slim

WORKDIR /app

RUN apt-get update \
    && apt-get install -y curl build-essential gcc \
    && apt-get clean

RUN pip install --no-cache-dir poetry
RUN poetry config virtualenvs.create false

COPY pyproject.toml poetry.lock* /app/
RUN poetry install --no-root --no-interaction --no-ansi

