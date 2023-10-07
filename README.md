# M1_Memoire_de_recherche
"Analyse de l'impact d'une modification unique de mot sur le sens des requêtes reformulées en français."

<i>Utilisation du modèle CamemBERT, de l'analyse statistique (langage R) et de l'analyse linguistique qualitative pour identifier les facteurs linguistiques et contextuels influençant les changements sémantiques des requêtes reformulées.</i>

<br>
Pour répondre à mes questions de recherche, j'avais seulement besoin de paires de requêtes reformulées, donc le domaine d'expertise des utilisateurs, leur stratégie (exploitation, exploration, etc.) ou le temps qu'ils ont passé sur les pages de résultats (SERP) ou à reformuler leurs requêtes sont sans importance. Ces informations ne sont pas directement liées à mes objectifs de recherche et n'ont donc pas été prises en compte dans mon étude. Mon analyse se concentre uniquement sur les modifications apportées aux requêtes et leur impact sur leur signification. La seule exception à cela était l'annotation du domaine des tâches, que j'ai utilisée pour créer un script Python spécifique. Ce script utilisait l'information sur le domaine des tâches pour effectuer des opérations spécifiques dans le cadre de mon étude. J'expliquerai en détail la fonctionnalité de ce script plus loin dans mon travail.
Pour les besoins de ma recherche, je devais extraire de ce jeu de données uniquement les requêtes dans lesquelles un seul mot était ajouté, supprimé ou modifié. J'ai également décidé d'exclure toutes les requêtes dont les tâches relèvent du domaine de la médecine, car il serait difficile d'analyser correctement ces données compte tenu de mes connaissances limitées dans ce domaine. Enfin, je voulais annoter automatiquement la classification des changements (mot ajouté, supprimé ou modifié), le mot ajouté/supprimé/modifié, la longueur de la requête originale (nombre de mots), ainsi que la position des mots ajoutés/supprimés/modifiés, car cela serait assez simple à faire et permettrait de gagner beaucoup de temps par rapport à l'annotation manuelle.
Afin d'accomplir cela, j'ai écrit un script Python qui effectue les tâches suivantes. Tout d'abord, il lit les données du jeu de données CoST. Ensuite, il compare les requêtes actuelles avec les requêtes suivantes pour repérer les mots qui ont été ajoutés, supprimés ou modifiés. 
Pour ce faire, j'utilise l'algorithme de Levenshtein, qui calcule la distance d'édition entre les mots. Cette distance mesure la similarité entre deux mots en quantifiant le nombre minimal d'opérations nécessaires (ajout, suppression, substitution) pour transformer un mot en un autre. Grâce à cet algorithme, mon script est capable de traiter des requêtes contenant des fautes d'orthographe et d'évaluer les modifications apportées aux mots dans ces requêtes. 
Lorsqu'une seule modification est détectée, le programme enregistre les détails de cette modification, tels que le mot ajouté, supprimé ou modifié, ainsi que la longueur de la requête d'origine et la position de la modification dans la requête. 
Une fois toutes les requêtes traitées, le script génère un jeu de données complet composé de 853 paires de requêtes. Ce jeu de données fournit des informations précieuses sur les modifications, ajouts ou suppressions de mots dans les requêtes, ce qui permet une analyse plus approfondie de la similarité entre les phrases.
