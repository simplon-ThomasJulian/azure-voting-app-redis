# Présentation de la sécurisation du déploiement dans la pipeline

## Analyse du code statique

### Choix d'application : Sonarcloud

- Pas d'infrastructure supplémentaire à provisionner
- intégré avec Azure Devops
- génération de rapport avec tab spécialement dédié au nouveau code implémenté 

### Difficultées rencontrées

- gestion de la quality gate

## Gestion des dépendances

### Choix d'application : Grype
- facilité d'intégration dans la pipeline
- Rend un rapport si des dépendances sont considérées malveillantes d'après la base de données des CVEs

### Difficultées rencontrées

- récupérer la sortie adéquate pour valider ou bloquer le pipeline


## Analyse Application Web

### Choix d'application : OWASP ZAP

- Solution très renommée et régulièrement mis en avant
- fourni un rapport détaillé et scriptable pour trigger un failed si erreur détectée pour l'app

### Difficultées rencontrées

- Intégration difficile avec Azure Devops, utilisation d'un container docker avec OWASP ZAP et d'un script pour afficher les résultats dans un onglet