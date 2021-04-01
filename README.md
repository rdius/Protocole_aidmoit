# Protocole de collecte de données textuelles pour la constitution de corpus thématiques
Les différentes étapes du protocoles sont entre autres:

## 1. La constitution de termes experts
La liste de termes experts est obtenue en deux étapes

* tout d'abord, pour une thématique donnée, nous collectons des données (10ère pages) sur wikipédia en utilisant le mot clé thématique (ex: agriculture). Cette étape est réalisé à partir des données de wiki dans le  but d'obtenir des documents bien centrés, telsque des défnitions, historique, etc. Ce qui donnera un large choix aux experts sur les termes qui représenteront au mieux sémantiquement chaque thématique.
* ensuite, pour chaque mini corpus, nous utilisons Biotex pour extraire des ensembles de termes. Les termes obtenus des mésures (f-tfidf-cm, c_value) sont fusionnés pour obtenir un seul ensemble. 
* enfin, avec un avis expert, nous retenons ~100 termes pour chaque thématique. 
Toujours, en se basant sur le principe d'expansion par graine, les termes experts ainsi obtenus, seront utilisés pour la constitution des vocabulaires de concepts.

## 2. La constitution de vocabulaire de concepts
La vocabulaire de concetps est obtenu en 04 étapes
* la premiere consiste à utiliser les termes experts obtenus précédemment pour recolter des données sur Google, dans le but d'obtenir des données plus diversifées, en terme de contenu, que dans les sources.
* deuxiemement, pour chaque thématique, le corpus obtenu est utilisé pour extraire des ensembles de termes en utilisant BioTex comme dans l'étape 1).
* troisiement, afin de s'assurer que ces termes sont sémantiquement valide vis-à-vis de la thématique, nous introduisons une mesure de similarité en utilisant DistilBert. Ce calcul de similarité est évalué entre chacun des termes obtenus avec l'ensemble de la liste de termes experts obtenue en 1).
* le dernier point consite à ordonner par ordre décroissant, les termes suivants score de similarité. Ceux ayant les plus grand score étant les plus proches de la thématique, sémentiquement parlant. Dans notre étude, nous avons retenu les 1000er de chaque thématique, correspondant des seuils > 0.7

## 3. La constitution des corpus thématique



* Item 2
  * Sub Item 1
  * Sub Item 2
