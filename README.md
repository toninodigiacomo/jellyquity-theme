# Thème Jellyfin pour Ubooquity 3

Un thème sombre inspiré de l'interface de **Jellyfin**, conçu pour Ubooquity 3.x.

---

## Aperçu visuel

| Élément          | Valeur                          |
|------------------|---------------------------------|
| Fond principal   | `#101010` (noir profond)        |
| Surface des cards| `#1c1c1c`                       |
| Couleur accent   | `#00a4dc` (bleu Jellyfin)       |
| Typographie      | Nunito (Google Fonts)           |
| Coins des cards  | Arrondis (10px)                 |
| Effet hover      | Élévation + bordure bleue       |

---

## Installation

1. Dans l'administration Ubooquity, allez dans **Paramètres généraux**
2. Cliquez sur **"Créer un nouveau thème…"** et nommez-le `jellyfin`
3. Copiez les fichiers de ce dossier dans le dossier du thème créé
4. Sélectionnez le thème `jellyfin` dans la liste déroulante et appliquez
5. Redémarrez Ubooquity

> **Important** : Les thèmes Ubooquity 3 sont incompatibles avec Ubooquity 2.x.

---

## Structure des fichiers

```
jellyfin/
├── common/
│   ├── style.css          ← CSS principal (toutes les pages)
│   ├── inc-header.html    ← En-tête commun (logo, nav, recherche)
│   └── themeScript.js     ← (facultatif, vide par défaut)
├── home/
│   └── page-home.html     ← Page d'accueil (catégories)
├── library/
│   ├── page-library.html                    ← Grille livres/dossiers
│   └── page-library-category-root-dirs.html ← Racine d'une catégorie
└── login/
    └── page-login.html    ← Page de connexion
```

Les fichiers non présents dans ce thème sont automatiquement récupérés du thème par défaut d'Ubooquity.

---

## Personnalisation

Toutes les couleurs sont des variables CSS dans `common/style.css` :

```css
:root {
  --jf-bg:       #101010;   /* Fond global */
  --jf-surface:  #1c1c1c;   /* Cards, panels */
  --jf-accent:   #00a4dc;   /* Bleu Jellyfin */
  --jf-text:     #ffffff;   /* Texte principal */
  --jf-text-muted: #aaaaaa; /* Texte secondaire */
}
```

### Changer la couleur d'accent (ex. violet Plex)
```css
--jf-accent: #e5a00d;
--jf-accent-hover: #cc8f0b;
--jf-accent-glow: rgba(229,160,13,0.25);
```

---

## Notes

- La police **Nunito** est chargée depuis Google Fonts. En cas de réseau fermé,
  remplacez l'import par une police locale ou système (`font-family: 'Segoe UI', sans-serif`).
- Les cards utilisent `aspect-ratio: 2/3` pour les couvertures — idéal pour BD et romans.
- La barre de progression de lecture s'affiche automatiquement si Ubooquity fournit
  la variable `{{readingProgress}}`.


> **Important** : Il faut que dans les parèmètres d'administration d'ubooquity que **Enable folder metadata display** soit activé !
> **Important** : Il faut que dans les parèmètres **Display title from metadata instead of file name** soit activé pour avopoir les titres qui se trouvent dans les metadatas !
