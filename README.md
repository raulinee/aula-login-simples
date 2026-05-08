# Iniciando o alembic

no terminal:
```bash
python -m alembic init migrations
```

# Apagar o valor de linha 89 - no arquivo alembic.ini
deive assim:
sqlalchemy.url =

# Edite o arquivo migrations/env.py:

from dotenv import load_dotenv
import os
import database
from database import Base

load_dotenv()

config.set_option("sqlalchemy.url", os.getenv("DATABASE_URL"))

terget_metadata = Base.metadata

# Gere a migrations com autogenerate
```bash
python -m alembic revision --autogenerate -m "Cria tabela usuario"
```

# Aplicar o micrations
```bash
python -m alembic upgrade head
```