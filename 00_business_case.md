**Entreprise :** Stripe\
**Secteur :** Technologie financière (FinTech)\
**Fondée :** 2010\
**Siège social :** San Francisco, Californie\
**Produit principal :** Plateforme de traitement des paiements pour les entreprises\
**Contexte :** Stripe est une entreprise de technologie financière de premier plan qui propose une suite complète de produits pour gérer les paiements et les opérations financières des entreprises de toutes tailles. L’entreprise traite des milliards de transactions chaque année, soutenant des millions de commerçants à travers le monde. À mesure que Stripe continue de croître, elle est confrontée à une complexité croissante dans la gestion de ses données sur diverses plateformes, notamment les systèmes transactionnels (OLTP), analytiques (OLAP) et les bases de données non relationnelles (NoSQL).

Stripe cherche à construire une infrastructure de données de pointe qui intègre de manière transparente ces différents types de systèmes de données afin de soutenir à la fois l’excellence opérationnelle et l’analyse avancée. L’objectif est de créer une architecture de données unifiée et évolutive capable de gérer de grands volumes de données transactionnelles, de prendre en charge des requêtes analytiques complexes et de gérer des données non structurées pour des cas d’usage avancés tels que la détection de fraude, l’analyse du comportement client et les recommandations en temps réel.

# Scénario commercial

À mesure que Stripe se développe à l’échelle mondiale, l’entreprise rencontre plusieurs défis :

**1. Charges transactionnelles complexes :**

Les systèmes OLTP de Stripe gèrent des millions de transactions quotidiennes, avec des attentes élevées en matière de disponibilité, de cohérence et de rapidité. Ces transactions incluent les paiements, les remboursements, les rétrofacturations et la gestion des abonnements. L’entreprise doit garantir que ces systèmes soient hautement disponibles, évolutifs et capables de prendre en charge de nouvelles fonctionnalités comme la détection de fraude en temps réel.

**2. Exigences analytiques avancées :**

Stripe doit fournir des analyses robustes à ses clients et à ses parties prenantes internes. Cela inclut l’analyse des revenus, la segmentation des clients, les rapports de conformité et le suivi des performances des produits. L’entreprise a besoin d’un système OLAP capable de traiter efficacement des requêtes complexes, de prendre en charge l’analyse ad hoc et de fournir des informations quasi en temps réel.

**3. Gestion des données non structurées et semi-structurées :**

Stripe collecte d’importants volumes de données non structurées et semi-structurées, telles que des journaux, des retours clients et des données d’interaction provenant de son site Web et de ses applications mobiles. Ces données sont essentielles à la construction de modèles d’apprentissage automatique pour la détection de fraude, la personnalisation client et l’analyse prédictive. L’entreprise a besoin d’une base NoSQL capable de stocker et de traiter efficacement ces données, de les intégrer aux données relationnelles et d’offrir des capacités de requêtes flexibles.

**4. Intégration des données entre les systèmes :**

L’intégration des données entre les systèmes OLTP, OLAP et NoSQL constitue un défi majeur. Stripe a besoin d’une architecture de données unifiée permettant un flux de données transparent entre ces systèmes, garantissant la cohérence, la mise à jour et l’accessibilité des données pour différents cas d’usage.

**5. Conformité et sécurité :**

Étant donné la nature sensible des données financières, Stripe doit s’assurer que son architecture de données respecte les réglementations telles que le RGPD, le PCI-DSS et le CCPA. L’entreprise doit également mettre en œuvre des mesures de sécurité robustes pour protéger les données au repos et en transit, gérer les contrôles d’accès et surveiller l’utilisation des données.

# Exigences commerciales

**1. Intégrité transactionnelle (OLTP) :**

Les systèmes OLTP de Stripe doivent gérer un volume élevé de transactions avec une latence minimale. Le système doit respecter les propriétés ACID pour garantir la cohérence et l’intégrité des données dans des environnements distribués. Il doit aussi prendre en charge des fonctionnalités telles que les transactions multi-documents, la synchronisation des données en temps réel et la reprise après sinistre.

**2. Analytique évolutive et efficace (OLAP) :**

Le système OLAP doit pouvoir exécuter des requêtes complexes sur de grands ensembles de données. Il doit agréger les données selon plusieurs dimensions, prendre en charge l’analyse chronologique et gérer des jointures et sous-requêtes à grande échelle. Le système doit offrir des temps de réponse faibles pour les requêtes critiques et prendre en charge à la fois l’analyse historique et quasi temps réel.

**3. Gestion flexible des données (NoSQL) :**

Stripe a besoin d’un système NoSQL capable de gérer différents types de données, y compris JSON, XML et binaires. Le système doit permettre une conception de schéma flexible, offrir des requêtes efficaces sur des données imbriquées et non structurées, et s’intégrer à d’autres systèmes de données pour offrir une vue holistique.

**4. Intégration et cohérence des données :**

L’architecture de données doit garantir un flux de données cohérent entre les systèmes OLTP, OLAP et NoSQL. Stripe doit mettre en place des pipelines de données capables de gérer le traitement par lots, les flux en continu et la synchronisation en temps réel. L’architecture doit prendre en charge les processus ETL/ELT et permettre la transformation et l’enrichissement des données.

**5. Sécurité et conformité :**

L’architecture doit inclure des mesures de sécurité robustes telles que le chiffrement, le contrôle d’accès et la journalisation des audits. Stripe doit s’assurer que le stockage et le traitement de ses données respectent les exigences réglementaires dans différentes juridictions. Le système doit prendre en charge les rapports de conformité automatisés et la surveillance en temps réel des failles de sécurité.

# Sources de données

**1. Données transactionnelles (OLTP) :**

Capturent toutes les transactions financières traitées par Stripe. Champs inclus :
- ID de transaction
- ID de commerçant
- ID de client
- Montant de la transaction
- Devise
- Méthode de paiement
- Date et heure de la transaction
- Localisation (géolocalisation IP)
- Type d’appareil (mobile, bureau, etc.)
- Statut (réussie, échouée, remboursée)
- Indicateurs de fraude (ex. : scores d’anomalie)

**2. Données analytiques (OLAP) :**

Données agrégées et historiques utilisées pour les rapports et analyses. Champs inclus :
- Indicateurs de revenus (quotidiens, hebdomadaires, mensuels)
- Données de segmentation client
- Indicateurs de performance des produits
- Données d’analyse de fraude
- Journaux de conformité et d’audit

**3. Données non structurées et semi-structurées (NoSQL) :**

Données collectées à partir de diverses sources, telles que journaux, interactions clients et données générées par les machines. Champs inclus :
- Données de journaux (erreurs, accès)
- Données d’interaction utilisateur (clickstream, sessions)
- Caractéristiques pour l’apprentissage automatique (données d’entrée des modèles)
- Retours clients (avis, réponses à des sondages)

**4. Données de référence :**

Données statiques ou peu changeantes utilisées dans plusieurs systèmes :
- Codes pays et régions
- Taux de change
- Informations sur les commerçants
- Catalogues de produits

# Exigences techniques

**1. Conception du modèle de données (OLTP, OLAP, NoSQL) :**

Vous devez concevoir des modèles de données pour chaque type de système :
- OLTP : se concentrer sur la normalisation, l’intégrité transactionnelle et l’optimisation des performances.  
- OLAP : concevoir des schémas en étoile ou en flocon de neige pour des requêtes et agrégations efficaces. Inclure des tables pré-agrégées pour les requêtes courantes.  
- NoSQL : concevoir des schémas flexibles prenant en charge les données non structurées et permettant des requêtes efficaces.

**2. Architecture du pipeline de données :**

Développer un pipeline de données intégrant les systèmes OLTP, OLAP et NoSQL. Il doit prendre en charge le traitement par lots et en temps réel, la transformation et l’enrichissement des données. Envisager des outils comme Apache Kafka pour le streaming et Apache Airflow pour l’orchestration des processus ETL.

**3. Scalabilité et optimisation des performances :**

L’architecture doit pouvoir évoluer horizontalement pour gérer l’augmentation du volume de données. Mettre en œuvre des stratégies d’indexation, de partitionnement et de mise en cache pour optimiser les performances. Considérer l’usage de bases distribuées et du sharding pour une haute disponibilité.

**4. Cohérence et synchronisation des données :**

Mettre en place des mécanismes garantissant la cohérence entre OLTP, OLAP et NoSQL. Utiliser des modèles de cohérence éventuelle si nécessaire, avec des stratégies de résolution de conflits. Employer des techniques de capture de changement de données (CDC) pour maintenir la synchronisation en temps réel.

**5. Sécurité et conformité :**

Concevoir un cadre de sécurité incluant le chiffrement des données, le contrôle d’accès basé sur les rôles et la journalisation. Assurer la conformité avec les réglementations (RGPD, PCI-DSS, etc.). Intégrer des contrôles et rapports de conformité automatisés.

**6. Analytique avancée et apprentissage automatique :**

Intégrer des modèles de machine learning dans le système NoSQL pour la détection de fraude et la personnalisation en temps réel. Le pipeline doit supporter l’extraction de caractéristiques et le déploiement des modèles, avec suivi et mise à jour de leurs performances.

# Tâche

En tant que membre de l’équipe d’ingénierie des données de Stripe, votre mission est de concevoir une architecture de données complète intégrant les systèmes OLTP, OLAP et NoSQL. Votre conception doit répondre aux besoins de l’entreprise en matière d’intégrité transactionnelle, d’analytique avancée, de gestion flexible des données et de conformité réglementaire.

**1. Modèle de données OLTP :**
- Concevoir un schéma normalisé pour le traitement transactionnel à grande échelle.  
- Garantir les propriétés ACID et la réplication en temps réel.

**2. Modèle de données OLAP :**
- Concevoir un schéma en étoile ou flocon de neige pour des requêtes et agrégations complexes.  
- Proposer une stratégie pour les jointures, sous-requêtes et analyses temporelles.  
- Prévoir des agrégations ou vues matérialisées pour optimiser les performances.

**3. Modèle de données NoSQL :**
- Concevoir un schéma pour les données non structurées et semi-structurées.  
- Définir des stratégies pour la gestion des relations (imbriquées, référencées, indexées).  
- Assurer l’intégration avec les systèmes OLTP et OLAP.

**4. Architecture d’intégration des données :**
- Développer un pipeline garantissant un flux cohérent et en temps réel entre OLTP, OLAP et NoSQL.  
- Inclure des composants pour le traitement par lots et en continu.  
- Proposer des outils et technologies pour l’orchestration du pipeline.

**5. Sécurité et conformité :**
- Concevoir un cadre de sécurité incluant chiffrement, contrôle d’accès et audit.  
- Garantir la conformité aux réglementations (RGPD, PCI-DSS, etc.).  
- Prévoir des rapports et surveillances automatisés.

**6. Intégration du machine learning :**
- Concevoir un processus d’intégration de modèles ML dans le système NoSQL.  
- Proposer des stratégies pour la détection de fraude, la personnalisation et l’analyse prédictive.  
- Prévoir des mécanismes de suivi et de mise à jour des modèles.

# Livrables

- **Diagramme d’architecture de données complet :** montrant l’intégration OLTP, OLAP et NoSQL, les flux de données, pipelines et modèles.  
- **ERD pour le système OLTP :** diagramme entité-relation du schéma normalisé.  
- **Schéma OLAP :** conception détaillée (étoile/flocon), stratégies d’agrégation et d’optimisation.  
- **Modèle NoSQL :** conception détaillée du schéma, gestion des relations et indexation.  
- **Architecture du pipeline de données :** document technique décrivant outils, technologies et processus d’intégration et de synchronisation.  
- **Plan de sécurité et de conformité :** description des mesures, stratégies et outils de suivi.  
- **Stratégie d’intégration du machine learning :** description du déploiement, de l’extraction des caractéristiques et du suivi des modèles.  
- **Requêtes SQL et NoSQL :** ensemble d’exemples démontrant comment répondre à des questions clés (analyse des revenus, détection de fraude, segmentation client).
