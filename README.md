# Requisitos:

- Python >= 3.3 
- Python < usar [virtualenv](https://github.com/pypa/virtualenv)

> En el caso de no usar otro gestor de entornos como puede ser anaconda.

# Crear entorno virtual

```
py -m venv env
```

# Activar el entorno virutal

```
.\env\Scripts\activate
```

# Instalar [Flake8](https://flake8.pycqa.org/en/latest/)

Comprueba el código con las guías de estilo de [PEP 8](https://peps.python.org/pep-0008/)

```
py -m pip install flake8
```

Ahora ya podemos ejecutar flake8:

```
flake8 main./py
```

```
(env) flake8 .\main.py
.\main.py:8:1: E302 expected 2 blank lines, found 1
.\main.py:10:1: W293 blank line contains whitespace
.\main.py:11:5: E303 too many blank lines (2)
.\main.py:14:29: W291 trailing whitespace
.\main.py:16:12: E225 missing whitespace around operator
.\main.py:17:11: W292 no newline at end of file
```

# Configuración flake8

Fichero `.flake8`

# Instalar [Black](https://github.com/psf/black)

Black nos permite arreglar los errores de forma automática

```
black ./main.py
```

## VSCode

- ms-python.flake8: Extension para flake8
- ms-python.black-formatter: Extension para black

# [Configurar hooks](https://pre-commit.com/)

```
py -m pip install pre-commit
```

> Cada vez que se realian modificaciones en `pre-commit` es necesario ejecutar `pre-commit install` para actualizar los scripts.

Fichero de configuración `.pre-commit-config.yaml` donde vamos añadiendo las acciones a realizar, en este caso que nos formatee automáticamente y los cambios los añada al commit.

# [Commitlint](https://pypi.org/project/commitizen/)

```
py -m pip install commitizen
```

- Añadir el hook para que realize la comprobación antes de hacer el `commit`

```
pre-commit install --hook-type commit-msg
```
