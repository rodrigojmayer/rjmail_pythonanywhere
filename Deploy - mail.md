## Deploying This Project

-> Clone repository
``` bash
git clone https://github.com/rodrigojmayer/rjmail_pythonanywhere.git
```

-> Create a Virtual environment using
``` bash

cd rjmail

mkvirtualenv --python=/usr/bin/python3.8 venv


```

-> Install all requirements using
``` bash

pip install -r requirements.txt


```

-> Add a new web app (select the last option to configure manually, no Django. And then the Python 3.8 version)

```
-> Setting up your Web app and WSGI file 

```
Source code: /home/rjmail/rjmail_pythonanywhere

Working directory: /home/rjmail/

Virtual     /home/rjmail/.virtualenvs/venv

# Paths
/static/    /home/rjmail/rjmail_pythonanywhere/mail/static

/media/	    /home/rjmail/rjmail_pythonanywhere/mail/static/assets

```

Force HTTPS: ENABLE

```
-> WSGI
```

import os
import sys

# Change this to the path to your project directory
path = '/home/rjmail/rjmail_pythonanywhere'
if path not in sys.path:
    sys.path.append(path)

# Ensure the settings file is imported correctly
os.environ['DJANGO_SETTINGS_MODULE'] = 'project3.settings' # <<< This must match your project folder name

from django.core.wsgi import get_wsgi_application
application = get_wsgi_application()

# If using StaticFilesHandler, it might look like:
# from django.contrib.staticfiles.handlers import StaticFilesHandler
# application = StaticFilesHandler(get_wsgi_application())

```