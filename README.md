# Сервис учёта доходов и расходов

Учебный проект на FastAPI - сервис учёта доходов и расходов.

## Запуск проекта

1. Клонировать репозиторий
2. Создать файл `.env` в корне проекта (см. ниже пример файла .env)
3. Сгенерировать секретный ключ и добавить его в `.env` (JWT_SECRET).
Это можно сделать в Python Console, выполнив следующий код
```python
from secrets import token_urlsafe
token_urlsafe(32)
```
4. Создать базу данных. По умолчанию используется SQLite3, её можно создать
в Python Console, выполнив следующий код
```python
from src.workshop.database import engine
from src.workshop.tables import Base
Base.metadata.create_all(engine)
```
5. Создать конфигурацию для запуска сервера по образцу
![пример конфигурации](https://i.ibb.co/Jsm470N/2023-04-18-173526.png)

## Пример файла .env

```bash
JWT_SECRET=secret_key
DATABASE_URL='sqlite:///./database.sqlite3'
SERVER_HOST='127.0.0.1'
SERVER_PORT=8000
```

## Пример JWT-payload

```json
{
    "iat": 1516239022,
    "nbf": 1516239022,
    "exp": 1516239022,
    "sub": "1234567890",
    "user": {
        "id": 123,
        "email": "email@example.com",
        "username": "username"
    }
}
```
