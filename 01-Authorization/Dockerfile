FROM python:3

WORKDIR /home/app

#If we add the requirements and install dependencies first, docker can use cache if requirements don't change
ADD requirements.txt /home/app
RUN pip3 install --no-cache-dir -r requirements.txt

ADD . /home/app

# Migrate the database
RUN python3 manage.py migrate

CMD python manage.py runserver 0.0.0.0:8000

EXPOSE 8000
