# Beardemo

demo web application for beardeese group.

## install

lancer mongodb

```
docker run -e MONGO_INITDB_DATABASE=strapi \
           -v `pwd`/db/:/data/db \
           --name beardemo-mongo \
           -d mongo
```

lancer strapi

```
docker run -e APP_NAME=strapi-app \
           -e DATABASE_CLIENT=mongo \
           -e DATABASE_HOST=beardemo-mongo \
           -e DATABASE_PORT=27017 \
           -e DATABASE_NAME=strapi \
           -v `pwd`/strapi-app:/usr/src/api/strapi-app \
           --link beardemo-mongo:mongo \
           -p 1337:1337 \
           --name beardemo-strapi -d strapi/strapi
```

```sh
#1. creer un environnement d'exection appele beardemo
docker build -t beardemo .

#2. alias pour facilement lancer un shell au sein d'un container instanci'e
#   d'apres mon environnement beardemo ayant acces aux dossiers avec le code
#   dans /app
alias drun='docker run -it -u $(id -u):$(id -g) --rm -v $(pwd):/app --workdir=/app --net=host beardemo'

# $(pwd) => /home/rvion/dev/beardemo
#
# -it       => interactive tty
# --rm      => deletete container on exit
# -v        => <host_folder>:<container_folder>
# --workdir => place toi par defaut dans le dossier donne
# --net=host => partage l'interface reseau du container avec le host
```

```
git clone ...
```

---

javascript
client: react, angular, ionic
server:

javacript : interpete

---

node : interpreter js
npm : node package manager
parcel: bundler
