# Django-tenants-SAAS
A simple SAAS using multi tenant architecture


## How to run it ?


1. Create a virtual environment

```bash
python -m venv venv
```

2. Activate the environment

```bash
.\venv\Scripts\activate
```

3. Install packages

```bash
pip install -r requirements.txt
```

4. Run postgres using docker compose 

```bash
docker compose up -d
```

5. make respective DB changes in settings.py

6. Migrate Database

```bash
python .\manage.py migrate
```

7. Create Admin user

```bash
python .\manage.py createsuperuser
```

8. run django server

```bash
python .\manage.py runserver
```

Command to create new migrations script (model history) after new models created

```bash
python .\manage.py makemigrations
python .\manage.py migrate
```

Command to create a new tenant

```bash
python .\manage.py create_tenant
```

Command to create tenant superuser

```bash
python .\manage.py create_tenant_superuser
```

django tenant migrate commands

```bash
python manage.py migrate_schemas --shared # to migrate public schemas
python manage.py migrate_schemas --tenant # to migrate tenant schemas
python manage.py migrate_schemas --schema=tenant_name # to migrate specific tenant schema
python manage.py migrate_schemas --executer=parallel # execute migation parallely
```

django collect static command

```bash
python .\manage.py collectstatic
```

command to open tenant specific django shell (to do CRUD on that specific tenant schema model)

```bash
python .\manage.py tenant_command shell
```