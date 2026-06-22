# Loto Togo - Application Android

Application mobile regroupant les 12 jeux de Loto 5/90 du Togo en une seule app.
Fonctionne **100% hors-ligne** : tous les résultats sont stockés directement sur
le téléphone, pas besoin d'internet pour l'utiliser au quotidien.

## Les 12 jeux intégrés

| Jour      | 13:00          | 18:00          |
|-----------|----------------|----------------|
| Lundi     | Lotto Diamant  | Loto Gold      |
| Mardi     | Loto Cash      | Loto Boom      |
| Mercredi  | Loto Benz      | Loto Prestige  |
| Jeudi     | Loto Million   | Loto Super     |
| Vendredi  | Loto Kadoo     | Loto King      |
| Samedi    | Loto Sam       | Loto Bingo     |

## Comment utiliser l'application

1. **Écran d'accueil** : les 12 jeux groupés par jour, avec le dernier
   résultat connu pour chacun.
2. **Bouton crayon (en haut à droite)** : ouvre l'écran de saisie. Choisis
   le jeu, la date, entre les 5 numéros gagnants, puis valide.
3. **Toucher un jeu** dans la liste : affiche l'historique complet des
   résultats enregistrés pour ce jeu.

---

## ÉTAPE 1 — Installer Flutter sur ton ordinateur

Va sur https://docs.flutter.dev/get-started/install et suis les instructions
pour Windows/Mac/Linux. Une fois fait, vérifie avec :
```
flutter doctor
```

## ÉTAPE 2 — Préparer le projet

1. Décompresse ce fichier zip n'importe où sur ton ordinateur. Tu obtiens un
   dossier `loto_togo/` avec ce contenu :
   ```
   loto_togo/
     pubspec.yaml
     assets/icon/icon.png
     lib/
       main.dart
       models.dart
       storage.dart
       home_screen.dart
       game_detail_screen.dart
       admin_screen.dart
   ```
2. Ouvre un terminal **dans le dossier qui contient `loto_togo/`** (pas dedans)
   et lance :
   ```
   flutter create loto_togo_app
   ```
   Cela génère un projet Flutter complet avec tous les fichiers Android
   nécessaires (qui ne sont pas inclus dans ce zip pour rester léger).
3. Copie les fichiers `lib/`, `assets/`, et `pubspec.yaml` de `loto_togo/`
   dans le nouveau dossier `loto_togo_app/`, en remplaçant les fichiers
   existants.

## ÉTAPE 3 — Installer les dépendances et appliquer le logo

Dans le dossier `loto_togo_app/` :
```
flutter pub get
flutter pub run flutter_launcher_icons
```

## ÉTAPE 4 — Tester l'application sur ton téléphone

1. Active le mode développeur sur ton téléphone Android (Paramètres >
   À propos du téléphone > taper 7 fois sur "Numéro de build").
2. Active le débogage USB (Paramètres > Options pour développeurs).
3. Branche le téléphone en USB à ton ordinateur.
4. Dans le dossier du projet :
   ```
   flutter run
   ```

## ÉTAPE 5 — Générer le fichier APK installable

```
flutter build apk --release
```
Le fichier sera ici :
```
build/app/outputs/flutter-apk/app-release.apk
```
Ce fichier .apk est celui que tu peux envoyer à n'importe qui pour installer
l'application sur un téléphone Android (pas besoin de Play Store).

## ÉTAPE 6 — Mettre l'APK sur GitHub (simple, sans automatisation)

1. Crée un compte sur https://github.com si besoin.
2. Crée un nouveau dépôt (bouton vert "New repository").
3. Sur la page du dépôt, clique sur **"Releases"** (colonne de droite) puis
   **"Create a new release"**.
4. Donne un nom à la version (ex: "v1.0"), puis dans la zone "Attach binaries"
   glisse-dépose directement ton fichier `app-release.apk`.
5. Clique sur **"Publish release"**.

Les gens pourront télécharger l'APK directement depuis cette page de Release,
sans que tu aies besoin de configurer quoi que ce soit d'automatique.

## Le logo

Le logo "LT 5/90" se trouve dans `assets/icon/icon.png`. Pour le changer,
remplace ce fichier par ta propre image carrée (1024x1024px de préférence),
puis relance :
```
flutter pub run flutter_launcher_icons
```

## Prochaines améliorations possibles

- Ajouter une protection par mot de passe sur l'écran de saisie
- Synchroniser les résultats sur Firebase pour que plusieurs personnes
  voient les mêmes résultats en temps réel
- Ajouter des notifications à l'heure de chaque tirage
- Permettre aux utilisateurs d'enregistrer leurs propres grilles jouées
  et de vérifier automatiquement s'ils ont gagné
