# Comandos Git👨🏻‍💻!

Hola👋🏼, mi nombre es Danny Sinoé conocido como **Sinoe9891**, hoy les dejo algunos comandos git que normalmente uso. Espero les sea de provecho. 
*Si algunas descripciones están mal escritas no duden en hacer un request.


## Comandos Básicos 
Una vez instalado en el servidor, para **iniciar git en un proyecto**

    git init

Si quieres **obtener una copia de un proyecto** que se encuentra en un **repositorio público**

    git clone [url]
Si se han hecho cambios en varios archivos, se pueden añadir todos juntos al **staging** 

    git add .

Si se han hecho cambios en un archivo especifico, se pueden añadir al **staging** 

    git add archivo.txt

Para ver los **cambios que se han hecho en el proyecto** 

    git status

Para ver los **cambios de forma más esquematizada**

      git status -s

 Ver el contenido modificado de los archivos

    git diff

Enmendar el commit antes de hacer push

    git commit --amend

Agrega archivos y commit al mismo tiempo

     git commit -am "<mensaje>"

Muestra los archivos que no pertenecen al repositorio

    git clean --dry-run

Elimina los archivos que no pertenecen al repositorio

    git clean -f

Elimina un archivo en especifico.

    git clean -f <path>

Agrega todos los archivos con la misma extensión

    git add ./*svg



### Git Stash Proceso

Volvemos al estado inicial y se guardan los cambios

    git stash

Crea la rama con los cambios guardados

    git checkout -b <nombrebranch>

Nos permite recuperar los cambios recién guardados y borrarlos del stash a la vez

    git stash pop

Nos muestra la lista de stash

    git stash list

Si decides que ya no necesitas algún stash en particular, puedes eliminarlo mediante el comando

    git stash drop
    
Elimina los archivos que están en staging (caché) pero los deja en tu carpeta (disco duro) o es decir que sacamos todo lo que agregamos al staged

    git rm --cached <ruta-archivo-o-carpeta>

Si queremos ignorar una carpeta ya subida en git, y queremos usar = con gitignore, lo sacamos con este y luego subimos de nuevo

    git rm -r --cached <ruta-archivo-o-carpeta>

Trae actualizaciones del repositorio remoto

    git fetch

Trae actualizaciones del repositorio remoto

    git fetch --all

Muestra el ultimo commit, quién lo hizo y dónde.

    git show <archivo>

### Ramas o Branches

Sincronizar las ramas que ya murieron en remoto  o trae actualizaciones de todas las ramas remotas 

    git remote update origin --prune

Sincronizar tu lista de ramas del repositorio

    git fetch -p

Muestra las ramas locales y remotas

    git branch -a
    
Cambia de rama

    git checkout <branch>

Crea y se cambia a la rama creada

    git checkout -b <branch>

Fusiona las ramas pero se debe de ejecutar en la rama a la que se quieren traer los cambios

    git merge <branch>

Creamos una rama con los cambios realizados

    git stash <branch> nombre de rama

Borra una rama local

    git branch -d -f <branch>
    
Borra una rama remota

    git push origin :<rama>

Subimos de forma forzada al repositorio remoto

    git push origin -r <branch>

Envía una rama especifica a repositorio remoto

    git push origin <branch>
    
Envía todas las ramas a remoto

    git push origin --all

Muestra ramas con información existente

    git show-branch

Ver todas las ramas

    git branch --list

Renombrar rama

    git -m nombre-viejo nuevo-nombre

Muestra ramas con más información existente

    git show-branch --all

Abre plataforma de git 

    gitk

> Git Reset y Reflog - Mala practica


Borra un commit en especifico

    git reset IdCommit

    git branch -d IdCommit

Elimina commit

    git reset <commit> --hard

Sube rama con commit eliminados

    git push -f origin <rama>

Muestra todo, incluso lo eliminado se vería algo así f861165

    git reflog

> El resultado se vería algo así HEAD@{388}: commit: Mensaje

Esto nos devolvería al estado del proyecto donde funcionaba para ejecutarlo sería de esta manera sacando el id del commit desde git reflog: 

    git reset HEAD

> **git reset HEAD@{3}**
    
Destruye el commit y vuelve al anterior:

    git reset HEAD^ --hard

Elimina todo incluyendo lo del staging pero regresa ultimo commit

    git reset --hard HEAD@{388}

Te mantiene lo que tengas en el staging

    git reset --soft HEAD@{388}



### Git Log
Muestra los commits

    git log

Muestra todos los commits

    git log --all

Muestra los commits de una mejor manera

    git log --all --graph --decorate --online

Muestra específicamente los cambios que se hicieron en los archivos.

    git log --stat


### Búsqueda
Busca en todo el proyecto una palabra específica.

    git grep <palabra>

Nos dirá en que línea esta

    git grep -n <palabra>

Cuantas veces se repite cada palabra

    git grep -c <palabra>
    git grep -c "<body>"

Busca un commit

    git log -S <palabra>



### Git Brame
Vemos las líneas solicitadas

    git brame <archivo.ext> -L35, 60 -c

Vemos quién hizo exactamente ese cambio.

    git blame -c <archivo.ext>

**Extras sin especificar**
git config --global alias.<nombredelalias> "<comandoaejecutar>"
git remote -v
git remote set-url origin https://github.com/USERNAME/REPOSITORY.git



