
# Simple movieAPI

Eine einfache API für das Abrufen von Informationen über Filme und das Hinzufügen von Bewertungen. Diese API bietet grundlegende Funktionen zum Abrufen von Filmdetails, Durchsuchen von Filmen und Hinzufügen neuer Bewertungen.

## Inhaltsverzeichnis

- [Installation](#installation)
- [Verwendung](#verwendung)
- [API-Endpunkte](#api-endpunkte)
  - [Movie API](#movie-api)
    - [GET /api/v1/movies](#get-apiv1movies)
    - [GET /api/v1/movies/{imdbId}](#get-apiv1moviesimdbid)
  - [Review API](#review-api)
    - [POST /api/v1/reviews](#post-apiv1reviews)
- [Beispiele](#beispiele)
- [Lizenz](#lizenz)

## Installation

1. Klone das Repository:
   ```bash
   git clone https://github.com/saifdarwish/movieAPI.git
   ```

2. Navigiere in das Projektverzeichnis:
   ```bash
   cd movieAPI
   ```

3. Installiere die Abhängigkeiten:
   ```bash
   mvn install
   ```

4. Starte die Anwendung:
   ```bash
   mvn spring-boot:run
   ```

##  Verwendung

Sobald der Server läuft, kannst du die API über `http://localhost:8080` (oder den entsprechenden Port) aufrufen.

##  API-Endpunkte

### Movie API

#### GET /api/v1/movies

Ruft eine Liste aller Filme ab.

- **URL:** `/api/v1/movies`
- **Methode:** `GET`
- **Antwort:** JSON-Array mit allen Filmen.

#### GET /api/v1/movies/{imdbId}

Ruft die Details eines bestimmten Films anhand seiner IMDb-ID ab.

- **URL:** `/api/v1/movies/{imdbId}`
- **Methode:** `GET`
- **Parameter:**
  - `imdbId` - Die IMDb-ID des Films.
- **Antwort:** JSON-Objekt mit den Filmdetails, falls vorhanden.

### Review API

#### POST /api/v1/reviews

Erstellt eine neue Bewertung für einen Film.

- **URL:** `/api/v1/reviews`
- **Methode:** `POST`
- **Daten:** JSON-Objekt mit den Bewertungsdetails.
  - `reviewBody` - Der Text der Bewertung.
  - `imdbId` - Die IMDb-ID des bewerteten Films.
- **Antwort:** JSON-Objekt mit den Details der erstellten Bewertung.

##  Beispiele

### Beispiel 1: Abrufen aller Filme

```bash
curl -X GET http://localhost:8080/api/v1/movies
```

### Beispiel 2: Abrufen eines einzelnen Films

```bash
curl -X GET http://localhost:8080/api/v1/movies/tt0111161
```

### Beispiel 3: Hinzufügen einer neuen Bewertung

```bash
curl -X POST http://localhost:8080/api/v1/reviews \
-H "Content-Type: application/json" \
-d '{"reviewBody": "Great movie!", "imdbId": "tt0111161"}'
```

##  Lizenz

Dieses Projekt ist frei für alle und steht unter einer freien Lizenz.
```
```
