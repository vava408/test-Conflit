#test-conflict

Normalement, dans le développement réel d'une application, des conflits se produiront spontanément. Cependant, pour notre formation, nous allons intentionnellement forcer un conflit dans git.

Dans la plupart des cas, git est capable de mélanger les modifications que différents utilisateurs apportent à différents fichiers, mais si deux utilisateurs apportent des modifications au même fichier localement (surtout si la modification se trouve sur la même ligne), git ne pourra pas savoir quelle modification est la bonne. Produisons un tel conflit :

- Voici une ligne du README.md avec deux (deux) fotes de frape (fautes de frappe) à corriger

- **Athos** corrigera la première faute de frappe (deux) et **Porthos** la seconde Fautes de frappe (fautes de frappe) à corriger 

- Chacun va faire un clone du repositoire et corriger sa faute de frappe localement, puis essayer de faire un `push` du changement.

pQ1: Les noms des compétitions de l’année 2025.

$\pi nomCompétition(\sigma dateDébut = 2025 (competition) $

Q2 : Les noms et pays des stations de plus de 2500 mètres.

$\pi nomStations,pays(\sigma altitude> 2500(stations)$

Q3 : Les noms et prénoms des skieurs suisses.

$\pi nomSkieur,prénomSkieur(\sigma pays = 'Suisses'(skieur) $

Q4 : Les noms, altitudes et pays des stations où a lieu la compétition 'Coupe d’Europe 2023-2024'.

$\pi nomStation, altitude, pays(\sigma nomCompétition = 'Coupe d’Europe 2023-2024')\bowtie {idStation}(lieux)\bowtie {idCompt}Competitions$

Q5 : Les noms, prénoms et rangs des skieurs autrichiens qui ont participé à la compétition
'Saalbach-2025'.

$\pi nomSkieur, prenomSkieur, rang(
    \sigma nomCompetition = 'Saalbach-2025' (COMPÉTITION) 
    \bowtie CLASSEMENT 
    \bowtie SKIEUR 
    \sigma nationalité = 'Autrichien'
)$


Q6 : Les noms, altitudes et pays des stations où n’a eu lieu aucune compétition.

$\pi nomStation, altitude, pays(STATION)
− 
\pi nomStation, altitude, pays(STATION \bowtie STATION.idStation = LIEU.idStation LIEU)$

Q7 : Les noms, prénoms et nationalités des skieurs ayant participé à toutes les compétitions. 

$\pi nomSkieur, prénomSkieur, nationalité(SKIEUR \bowtie CLASSEMENT)
÷ 
\pi idCompt(COMPÉTITION)$
