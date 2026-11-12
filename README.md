# hornets-su-data
Oeffentliche SwissUnihockey-Resultate/Spielplaene fuer den Hornets Unihockey Planer (Fallback, solange die offizielle API gesperrt ist).

## Struktur
data/9656.json: E Regional Junioren Gruppe 4 (Hornets E-Orange)
data/9692.json: E Regional Junioren Gruppe 9 (Hornets E-Schwarz)
data/9654.json: E Regional Junioren Gruppe 2 (Hornets E-Gelb)

Jede Datei enthaelt {leagueId, groupLabel, season, sourceUrl, updatedAt, games: [...]}.

## Aktualisierung
Die Daten werden manuell per Chrome-Browser-Scraping von myapp.swissunihockey.ch abgerufen, lokal ins obige Schema transformiert und hier committed:
(a) Seite league/<ligaId>/fixtures (zukuenftig) und ?tab=past (vergangen) oeffnen, bis zum Ende scrollen
(b) Spiele per DOM-Extraktion auslesen und ins JSON-Schema umwandeln
(c) Datei unter data/<ligaId>.json committen

## Hinweis
Die App laedt diese Dateien via raw.githubusercontent.com (CORS-frei) als Fallback-Datenquelle, solange die offizielle SwissUnihockey-API gesperrt ist.
