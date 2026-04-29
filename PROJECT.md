# WWS Advisory — Master Repository

**Domain:** [wwsadvisory.com](https://wwsadvisory.com/) (Hauptdomain, EN-Default)
**Schwesterdomain:** [wws-advisory.de](https://wws-advisory.de/) → leitet auf `wwsadvisory.com/?lang=de` weiter (Repo `wowas007/wws-advisory`)

## Stand
- **Live seit:** 2026-04-29
- **GmbH:** WWS Advisory GmbH, im Handelsregister AG Charlottenburg eingetragen unter **HRB 286558 B**
- **Geschäftsführer:** Wolfgang Schmidt
- **Sitz:** Berlin
- **Postanschrift:** Adalbertstraße 14, 80799 München

## Inhalt
Statische, dreisprachige Landing-Page mit Sprachumschalter:

- `index.html` — Hauptseite (EN-Default, JS wechselt zu DE/ES; URL-Parameter `?lang=de|es` wird respektiert)
- `impressum.html` (DE) / `impressum.en.html` (EN) / `impressum.es.html` (ES)
- `datenschutz.html` (DE) / `datenschutz.en.html` (EN) / `datenschutz.es.html` (ES)
- `legal.css` — gemeinsames Stylesheet für die Rechtsseiten
- `fonts/` — Albert Sans 300/400/600 (lokal, kein Google Fonts CDN)

## Design-Tokens
```css
:root {
  --bg: #fafafa;       /* Hintergrund */
  --fg: #1d1d1f;       /* Text */
  --muted: #86868b;    /* Sekundär */
  --link: #424245;
  --sans: 'Albert Sans', system-ui, sans-serif;
}
```

Layout: Content links unten, Sprachumschalter (DE/EN/ES) oben rechts fixed, Impressum/Datenschutz unten rechts fixed. Mobil: zentriert, Footer wird statisch unter den Content.

## Tracking
**Matomo Site ID 3** (Endpoint: `//schmidt-sabugal.de/matomo/`). Tracker läuft im `<head>` der index.html. Datenschutzerklärung enthält in allen drei Sprachen einen Opt-out (Cookie `mtm_consent_removed`).

## Rechtliche Setup-Entscheidungen
- **Impressum:** WWS Advisory GmbH, Adalbertstr. 14, 80799 München; Geschäftsführer Wolfgang Schmidt; AG Charlottenburg HRB 286558 B; Kontakt office@wws-advisory.de; Postsendungs-Hinweis (vorher per E-Mail Kontakt aufnehmen).
- **Aufsichtsbehörde Datenschutz:** Berliner Beauftragte für Datenschutz und Informationsfreiheit (BlnBDI), Alt-Moabit 59–61, 10555 Berlin (zuständig wegen Sitz Berlin).
- **Hosting:** GitHub Pages (Datenübermittlung in die USA via EU-US Data Privacy Framework).
- **Schriften:** lokal (kein Google-Fonts-CDN, keine IP-Übertragung an Dritte).

## Änderungen am Layout
Die alte Hero-Bild-Variante wurde am 2026-04-29 durch die helle, minimalistische Landing ersetzt. Die dunkle Variante existiert noch als `alternative-dark.html` im Schwester-Repo `wws-advisory`.

## Repo-Struktur in der Domain-Familie

| Repo | Domain | Funktion |
|------|--------|----------|
| **wws-advisory-com** | wwsadvisory.com | Master (diese Repo) |
| wws-advisory | wws-advisory.de | Redirect auf wwsadvisory.com/?lang=de |
| wws-advisory-de | — | Legacy, Pages deaktiviert |
| wws-advisory-preview | — | Sandbox |

## Workflow

```bash
cd ~/Library/CloudStorage/OneDrive-Persönlich/2\ Dokumente/Homepage/wws-advisory-com
# Änderungen machen
git add -A && git commit -m "..." && git push
```

Pages baut automatisch nach Push, Live-Stand nach 1–3 Min auf wwsadvisory.com.

## Verwandte Doku
Die übergreifende Doku zur gesamten Domain-Architektur (privat + GmbH) liegt im Repo `ws-office` als `HOMEPAGE_DOKUMENTATION.md`.
