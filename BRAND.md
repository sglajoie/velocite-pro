# BRAND.md — Vélocité · Charte graphique v7
# Ce fichier est la référence absolue de la marque.
# Claude Code doit le lire et le respecter à la lettre sur chaque tâche.

---

## IDENTITÉ

Vélocité est une offre de conseil privé de Stéphane Gérin-Lajoie.
Clientèle cible : femme 35–50 ans, professionnelle accomplie.
Émotion au premier regard : désir. Elle veut ça, maintenant.
Ton visuel : sobre, tendu, haut de gamme. Loft épuré. Rien de superflu.
Règle d'or : « Moins il y a d'éléments, plus chacun compte. »

---

## PALETTE — COULEURS DE SECTION (ordre fixe et intouchable)

| Token         | Hex       | Section     | Rôle                                    |
|---------------|-----------|-------------|-----------------------------------------|
| $noir         | #0C0A08   | S1 Hero     | Fond principal — jamais #000000         |
| $cannoli      | #F5EDE0   | S2 Statut   | Rupture lumineuse — 1 section MAX       |
| $mocha        | #A07060   | S3 Citation | Chaleur organique · Pantone 17-1230     |
| $sirocco      | #C09080   | S4 CTA      | Brun rosé doux · sortie apaisée         |
| $noir-profond | #080604   | S5 Footer   | Légèrement plus profond que S1          |

RÈGLE EXTENSION (sections 6+) :
- Alterner entre $mocha et $noir uniquement.
- $cannoli NE PEUT PAS être dupliquée. Elle est l'unique rupture lumineuse.

---

## PALETTE — COULEURS DE PRÉCISION (accents ponctuels, jamais en fond)

| Token      | Hex       | Usage                                                      |
|------------|-----------|------------------------------------------------------------|
| $bleu      | #7BAAC8   | Pills · liens footer · CTA contour standard                |
| $bordeaux  | #581828   | Filet wordmark Hero · fond plein CTA haute tension · hover |
| $rouge     | #C03848   | Éléments urgence · appel action maximal · très ponctuel    |

RÈGLE HOVER : tout élément interactif $bleu → $bordeaux au hover.
RÈGLE FILET HERO : filet sous wordmark = TOUJOURS $bordeaux opacity 0.8. Jamais $bleu.

---

## PALETTE — COULEURS SECONDAIRES (transitions & surfaces)

| Token      | Hex       | Usage                        |
|------------|-----------|------------------------------|
| $chocolat  | #3C2010   | Transitions sombres          |
| $baltic    | #4A2C18   | Fonds intermédiaires chauds  |
| $safari    | #B89878   | Transitions mi-ton           |
| $cream-tan | #E8C8B0   | Surfaces claires secondaires |

---

## RÈGLES ABSOLUES COULEURS

- JAMAIS blanc pur #FFFFFF
- JAMAIS noir pur #000000
- $cannoli : UNE seule section par page — jamais répétée
- Couleurs de précision : sur éléments PONCTUELS uniquement — jamais en fond de section
- Ordre des sections S1 à S5 : FIXE — ne pas réorganiser

---

## TYPOGRAPHIE

### Police principale : Cormorant Italic

```css
font-family: 'Cormorant', serif;
font-style: italic;           /* TOUJOURS italic — jamais normal sur le wordmark */
font-weight: 300;             /* graisse officielle — max 400 — jamais 700+ */
letter-spacing: 0.02em;       /* sur titres clairs sur fond noir */
line-height: 1.5;             /* minimum absolu sur tous les blocs */
```

Usage : wordmark · H1 · H2 · accroches · citations

### Police secondaire : Jost

```css
font-family: 'Jost', sans-serif;
font-style: normal;           /* JAMAIS italic */
/* graisses : 200 · 300 · 400 · 500 */
```

Usage : corps · étiquettes · tags · navigation · statuts · boutons
RÈGLE : tout paragraphe > 3 lignes → Jost 400 obligatoire
RÈGLE : Jost < 12px → letter-spacing: 0.18em minimum

### Import Google Fonts

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Cormorant:ital,wght@1,300;1,400;1,500&family=Jost:wght@200;300;400;500&display=swap" rel="stylesheet">
```

---

## ÉLÉMENTS GRAPHIQUES

```css
/* Filet wordmark Hero S1 — BORDEAUX v7 */
.rule-hero {
  width: 36px; height: 1px;
  background: #581828;  /* $bordeaux — JAMAIS $bleu sur le Hero */
  opacity: 0.8;
}

/* Filet structure S3/S4 — NOIR PROFOND */
.rule-section {
  width: 32px; height: 1px;
  background: #080604;  /* $noir-profond */
  opacity: 0.4;
}
```

INTERDIT : gradients · box-shadow · text-shadow · illustrations · icônes
AUTORISÉ : espace vide — c'est un élément graphique à part entière

---

## HIÉRARCHIE TYPOGRAPHIQUE CSS

```css
.eyebrow {
  font-family: 'Jost', sans-serif;
  font-size: 9px; font-weight: 400;
  letter-spacing: 0.32em; text-transform: uppercase;
  color: #907060;
}

h1 {
  font-family: 'Cormorant', serif;
  font-style: italic; font-weight: 300;
  font-size: clamp(3.6rem, 9vw, 5.2rem);
  color: #F0E6DC; letter-spacing: 0.02em; line-height: 1;
}

.tagline {
  font-family: 'Cormorant', serif;
  font-style: italic; font-weight: 300;
  font-size: clamp(1.5rem, 4vw, 2.1rem);
  color: #C8B8A0; line-height: 1.5;
}

.statut-text {
  font-family: 'Cormorant', serif;
  font-style: italic; font-weight: 300;
  font-size: clamp(1.4rem, 3.5vw, 1.9rem);
  color: #0C0A08;  /* CONTRASTE MAX sur $cannoli */
  line-height: 1.5;
}

.quote {
  font-family: 'Cormorant', serif;
  font-style: italic; font-weight: 300;
  font-size: clamp(1.6rem, 4vw, 2.2rem);
  color: #F5EDE0; line-height: 1.5;
}

.status  { font-family: 'Jost', sans-serif; font-size: 11px; font-weight: 500; color: #2A2820; }
.tags    { font-family: 'Jost', sans-serif; font-size: 10px; font-weight: 300; color: #9A9490; letter-spacing: 0.1em; }
.body-dense { font-family: 'Jost', sans-serif; font-weight: 400; font-size: 14px; line-height: 1.5; }
```

---

## COMPOSANTS CSS

### Pills

```css
.pill {
  font-family: 'Jost', sans-serif;
  font-size: 9px; font-weight: 400;
  letter-spacing: 0.14em; text-transform: uppercase;
  padding: 6px 14px; border-radius: 100px;
  border: 0.5px solid #7BAAC8; color: #7BAAC8;
  background: transparent;
}
```

### Liens

```css
a {
  font-family: 'Jost', sans-serif;
  font-size: 11px; font-weight: 400;
  color: #7BAAC8;
  text-decoration: underline; text-underline-offset: 3px;
  letter-spacing: 0.06em; transition: color 0.2s;
}
a:hover { color: #581828; }  /* BORDEAUX — règle hover obligatoire */
```

### CTA Haute Tension (fond Bordeaux plein)

```css
/* Sur fonds $noir, $mocha, $sirocco */
.btn-primary {
  display: inline-block;
  font-family: 'Jost', sans-serif;
  font-size: 10px; font-weight: 500;
  letter-spacing: 0.16em; text-transform: uppercase;
  padding: 13px 28px;
  background: #581828; color: #F5EDE0;
  border: none; text-decoration: none;
  transition: opacity 0.2s;
}
.btn-primary:hover { opacity: 0.88; }
```

### CTA Standard (contour Bleu)

```css
.btn-secondary {
  display: inline-block;
  font-family: 'Jost', sans-serif;
  font-size: 10px; font-weight: 500;
  letter-spacing: 0.16em; text-transform: uppercase;
  padding: 13px 28px;
  background: transparent;
  border: 1px solid #7BAAC8; color: #7BAAC8;
  text-decoration: none; transition: border-color 0.2s, color 0.2s;
}
.btn-secondary:hover { border-color: #581828; color: #581828; }
```

---

## SPÉCIFICATIONS SECTION PAR SECTION

### S1 — Hero (fond #0C0A08)
```
eyebrow     : Jost 400 · 9px · #907060 · spacing 0.32em · uppercase
wordmark h1 : Cormorant Italic 300 · clamp(3.6rem,9vw,5.2rem) · #F0E6DC · ls 0.02em
filet v7    : width 36px · 1px · #581828 Bordeaux · opacity 0.8  ← JAMAIS BLEU
accroche    : Cormorant Italic 300 · clamp(1.5rem,4vw,2.1rem) · #C8B8A0 · lh 1.5
sous-titre  : Jost 300 · 13px · #484038 · spacing 0.04em
```

### S2 — Statut (fond #F5EDE0 Cannoli)
```
eyebrow     : Jost 600 · 8px · #B09070 · spacing 0.22em · uppercase
texte       : Cormorant Italic 300 · 1.4–1.9rem · #0C0A08 · lh 1.5  ← CONTRASTE MAX
pill        : border #7BAAC8 · color #7BAAC8
pill hover  : border #581828 · color #581828
```

### S3 — Citation (fond #A07060 Mocha)
```
eyebrow     : Jost 400 · 8px · #E8C8A8 · opacity 0.6 · uppercase
filet       : width 32px · 1px · #080604 · opacity 0.4  ← NOIR PROFOND
citation    : Cormorant Italic 300 · 1.6–2.2rem · #F5EDE0 · lh 1.5
attribution : Jost 300 · 10px · #E8C8A8 · spacing 0.1em
```

### S4 — CTA (fond #C09080 Sirocco)
```
eyebrow     : Jost 400 · 8px · #F5EDE0 · opacity 0.5 · uppercase
titre       : Cormorant Italic 300 · 2rem · #F5EDE0 · lh 1.5
bouton HT   : fond #581828 · texte #F5EDE0 · Jost 500 · 10px · spacing 0.16em
```

### S5 — Footer (fond #080604)
```
wordmark    : Cormorant Italic 300 · 1.8rem · #F0E6DC
signature   : Jost 200 · 8px · #605040 · spacing 0.24em · uppercase
lien        : Jost 400 · 10px · #7BAAC8 · underline · offset 3px
lien hover  : color #581828
```

---

## RÈGLES D'EXTENSION (sections 6+)

Si des sections additionnelles sont nécessaires :
- Alterner UNIQUEMENT entre $mocha (#A07060) et $noir (#0C0A08)
- $cannoli NE PEUT PAS être répétée
- Filets de structure : $noir-profond (#080604) opacity 0.4
- CTA haute tension : $bordeaux fond plein

---

## CHECKLIST AVANT CHAQUE COMMIT

1. [ ] Google Fonts chargées — Cormorant ital + Jost
2. [ ] Cormorant : font-style italic — jamais normal sur le wordmark
3. [ ] Cormorant : font-weight max 400 — jamais 700+
4. [ ] Jost : font-style normal — jamais italic
5. [ ] Filet wordmark : #581828 Bordeaux opacity 0.8 — JAMAIS #7BAAC8
6. [ ] Filets S3/S4 : #080604 opacity 0.4 — JAMAIS bleu
7. [ ] Texte S2 : #0C0A08 — contraste max sur Cannoli
8. [ ] $cannoli : UNE seule fois en fond
9. [ ] Aucun #FFFFFF ni #000000
10.[ ] Hover liens et boutons bleus → #581828 Bordeaux
11.[ ] line-height >= 1.5 sur tous les blocs texte
12.[ ] Jost 400 sur paragraphes > 3 lignes
13.[ ] letter-spacing 0.02em sur Cormorant clair sur fond noir
14.[ ] letter-spacing 0.18em minimum sur Jost < 12px
15.[ ] Ordre S1→S5 respecté

## TEST MENTAL

Avant de committer : « Est-ce que cette cliente de 40 ans,
directrice accomplie, désire ce qu'elle voit au premier regard ? »
Si non ou incertain → simplifier, retirer, épurer. Jamais ajouter.
