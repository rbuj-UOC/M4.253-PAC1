# Respostes a les preguntes teòriques

## Exercici T1

### Ordres necessàries per sincronitzar els canvis a GitHub

Desde la línea d'ordres Dev1:

```console
$ git checkout -b dev1-changes
$ git add index.html
$ git commit -m "File index.html modified by Dev1"
$ git push origin dev1-changes
```

Desde la línea d'ordres Dev2:

```console
$ git checkout -b dev2-changes
$ git add index.html
$ git commit -m "File index.html modified by Dev2"
$ git push origin dev2-changes
```

Després, des de la pàgina web del dipòsit a GitHub, ambdós desenvolupadors faran un Pull Request per fusionar les seves respectives branques amb canvis a la branca principal de desenvolupament.

Un cop incorporats els canvis a GitHub, p. ex. mitjançant Rebase and Merge, es poden eliminar les branques dev1-changes i dev2-changes, si aquesta eliminació no està configurada perquè es faci automàticament.

### Possibles conflictes i resolució

Hi pot haver un [merge conflict](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/addressing-merge-conflicts/about-merge-conflicts) si ambdós desenvolupadors han modificat alhora la mateixa part dal fitxer index.html.

Aquest conflicte es mostrarà en la pàgina del Pull Request en un desenvolupador després que s'hagi fusionat el Pull Request de l'altre, i es pot resoldre des de la [mateixa pàgina](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/addressing-merge-conflicts/resolving-a-merge-conflict-on-github) o bé des de la [línea d'ordres](https://docs.github.com/en/get-started/using-git/resolving-merge-conflicts-after-a-git-rebase).

## Exercici T2

### Commits que són considerats a la branca front-end

c1, c2, c4 i c8.

### Conflicte i possibles solucions

Hi ha un conflicte en quan s'incorporen els canvis de la branca front-end a la branca màster, ja que en la branca master s'han incorporat abans els canvis de la branca back-end. En cas que s'hagues modificat el mateix fragment de codi en ambdues branques hi hauria un error de fusió.

Una possible solució seria fer un git rebase abans d'incorporar els canvis de la branca back-end a la branca master i solucionar els possibles errors de fusió.

## Exercici T3

El dipòsit és un fork de [rust-lang/rfcbot-rs](https://github.com/rust-lang/rfcbot-rs). A més, l'últim commit al directori src el va fer [Mark Rousskov](https://github.com/Mark-Simulacrum) el 17 de novembre de 2021. Aquest [commit 2bd38f9](https://github.com/rust-lang/rfcbot-rs/commit/2bd38f9fea0eab524f73eeb451b99dec76caef5d) té el mateix nom, autor i data.

Fins al commit 2bd38f9 han col·laborat 17 desenvolupadors al directori src:

```console
iMac-de-Robert:~ robert$ git clone https://github.com/rust-lang/rfcbot-rs
Cloning into 'rfcbot-rs'...
remote: Enumerating objects: 3398, done.
remote: Counting objects: 100% (118/118), done.
remote: Compressing objects: 100% (54/54), done.
remote: Total 3398 (delta 71), reused 89 (delta 61), pack-reused 3280
Receiving objects: 100% (3398/3398), 21.66 MiB | 21.12 MiB/s, done.
Resolving deltas: 100% (2096/2096), done.
iMac-de-Robert:~ robert$ cd rfcbot-rs
iMac-de-Robert:rfcbot-rs robert$ git checkout 2bd38f9
iMac-de-Robert:~ robert$ cd src
iMac-de-Robert:src robert$ git shortlog -sne . | wc -l
      17
```

Llista de desenvolupadors que han contribuït al directori src, ordenats per nombre de commits:

```console
iMac-de-Robert:src robert$ git shortlog -sne .
   128  Adam Perry <adam.n.perry@gmail.com>
    35  Alan Du <alanhdu@gmail.com>
    24  Mazdak Farrokhzad <twingoow@gmail.com>
     9  Mark Rousskov <mark.simulacrum@gmail.com>
     7  Alan Du <alan.h.du@gmail.com>
     5  lzutao <taolzu@gmail.com>
     2  Aaron Turon <aturon@mozilla.com>
     2  Dale Wijnand <344610+dwijnand@users.noreply.github.com>
     2  boats <woboats@gmail.com>
     1  Aleksey Kladov <aleksey.kladov@gmail.com>
     1  Erik Johnston <erikj@jki.re>
     1  Josh Triplett <josh@joshtriplett.org>
     1  Mateusz Mikuła <mati865@users.noreply.github.com>
     1  Pietro Albini <pietro@pietroalbini.org>
     1  Santiago Pastorino <spastorino@gmail.com>
     1  Yuki Okushi <huyuumi.dev@gmail.com>
     1  inquisitivecrystal <22333129+inquisitivecrystal@users.noreply.github.com>
```

[Javier Canovas](https://github.com/jlcanovas) no ha col·laborat al directori src.
