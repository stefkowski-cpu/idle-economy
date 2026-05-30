# Idle Economy - Projektkontext

## Ziel

Wir bauen ein browser-lauffaehiges Single-HTML-Spiel, das ohne Build-Schritt direkt aus `index.html` gestartet werden kann. Am Ende soll das Projekt ueber GitHub Pages aus dem Repository `stefkowski-cpu/idle-economy` erreichbar sein.

Das Spiel ist ein Idle-Wirtschaftsspiel nach dem Gefuehl von Idle Inc. oder Idle Factory: Der Spieler startet klein, automatisiert Einnahmen, schaltet neue Produktionsketten frei, skaliert ueber immer groessere Zahlenbereiche und erlebt Fortschritt durch Upgrades, Multiplikatoren, Prestige und Story-Ereignisse.

## Leitidee

Das Thema ist Fussball als Wirtschaftsuniversum. Der Spieler baut aus einem Bolzplatz einen globalen Fussballkonzern:

- Spieler werden entdeckt, trainiert, verkauft oder zu Stars entwickelt.
- Trainer verbessern Taktik, Trainingseffizienz und Nachwuchsarbeit.
- Zuschauerzahlen treiben Ticketumsatz, Merchandising und Stimmung.
- Werbevertraege, Medienrechte und Sponsoren oeffnen neue Einkommensdimensionen.
- Stadien, Akademien, Scouting-Netzwerke, Datenlabore und Fanplattformen werden zu Produktionslinien.
- Erfolg auf dem Platz erhoeht Reichweite, Reichweite erhoeht Geld, Geld erhoeht sportliche Qualitaet.

Die Story darf mit jeder Stufe groesser werden: Dorfverein, Stadtclub, nationale Liga, Champions-League-Macht, globales Sportimperium, interdimensionale Fussball-Oekonomie.

## Plattform und technische Vorgaben

- Eine Datei: `index.html`.
- Keine serverseitige Logik.
- Direkt im Browser lauffaehig.
- Speicherstand ueber `localStorage`.
- Responsives Layout fuer Desktop und Mobile.
- GitHub Pages kompatibel, bevorzugt ueber Branch `main` und Root-Verzeichnis.
- Externe Libraries nur, wenn sie per CDN stabil eingebunden werden koennen und echten Nutzen bringen.
- Kernspiel muss auch bei sehr grossen Zahlen spielbar bleiben.

## Zahlenmodell

Es gibt keine harte Grenze fuer Potenzen. Das Spiel braucht deshalb ein Grosszahlen-System.

Geplanter Ansatz:

- Intern werden Werte als Mantisse + Exponent zur Basis 10 gespeichert.
- Beispiel: `4.2e57` bedeutet `4.2 * 10^57`.
- Rechenoperationen fuer Addition, Multiplikation, Division, Potenzen und Vergleiche werden ueber Hilfsfunktionen gekapselt.
- Anzeige nutzt kompakte Formate: `1.23K`, `4.56M`, `7.89B`, danach wissenschaftliche Notation oder eigene Fussball-Rangnamen.
- Sehr spaete Spielphasen duerfen mit Exponenten arbeiten, statt echte JavaScript-Zahlen zu ueberfordern.

## Waehrungen und Dimensionen

Das Spiel soll mehrere Waehrungen haben, die in verschiedenen Dimensionen miteinander verzahnt sind. Keine Waehrung ist nur Dekoration; jede soll mindestens eine eigene Rolle im Fortschritt haben.

### Basisdimension: Geld

- `Euro`: Hauptwaehrung fuer Bau, Gehaelter, Upgrades und Vertrage.
- Quellen: Tickets, Merch, Sponsoren, Transfers, Medienrechte.
- Verwendung: Stadionausbau, Personal, Training, Marketing, Automatisierung.

### Sportdimension: Leistung

- `Teamstaerke`: bestimmt Siegchance, Ligafortschritt und Preisgelder.
- Quellen: Spieler, Trainer, Training, Taktik, Akademie.
- Verwendung: Wettbewerbe gewinnen, bessere Sponsoren freischalten.

### Fan-Dimension: Aufmerksamkeit

- `Fans`: dauerhaftes Publikum und Reichweitenbasis.
- `Stimmung`: kurzfristiger Multiplikator durch Siege, Events und Stars.
- Quellen: Spiele, Derbys, Stars, Social Media, Stadionerlebnis.
- Verwendung: Ticketverkauf, Merch-Multiplikator, Sponsorenqualitaet.

### Markt-Dimension: Marke

- `Markenwert`: langfristige Attraktivitaet fuer Sponsoren, Medien und globale Expansion.
- Quellen: Titel, Stars, internationale Touren, PR, Fanplattformen.
- Verwendung: Werbevertraege, TV-Deals, globale Multiplikatoren.

### Zukunftsdimension: Talent

- `Talente`: Nachwuchsressource.
- Quellen: Jugendakademie, Scouting, Datenanalyse.
- Verwendung: neue Spieler, Transfergewinne, dauerhafte Teamstaerke.

### Prestige-Dimension

- `Legendenpunkte`: Reset-Waehrung nach grossen Meilensteinen.
- Quellen: Saisonabschluesse, Titel, Rekorde, globale Meilensteine.
- Verwendung: permanente Boni, neue Mechaniken, Automatisierung, Zahlenbeschleunigung.

## Kernmechaniken

### Produktionslinien

Jede Linie erzeugt Ressourcen passiv und kann verbessert werden.

- Bolzplatz: kleine Ticket- und Fan-Einnahmen.
- Jugendteam: erzeugt Talente.
- Amateurstadion: erhoeht Zuschauerlimit.
- Fanshop: erzeugt Merch-Umsatz.
- Trainerstab: erhoeht Trainingseffizienz.
- Scouting-Abteilung: findet Spieler und Talente.
- Medienbuero: erzeugt Markenwert.
- Sponsoring-Team: verbessert Werbevertraege.
- Datenlabor: optimiert alles ueber Multiplikatoren.
- Globales Netzwerk: spaete Spielphase mit extremen Skalierungen.

### Spieler

Spieler sind sammelbare Wirtschafts- und Sporteinheiten.

- Attribute: Position, Talent, Popularitaet, Form, Marktwert.
- Effekte: Teamstaerke, Fans, Merch-Umsatz, Sponsorenbonus.
- Seltenheiten: Lokal, Profi, Star, Weltstar, Legende.
- Entscheidungen: behalten, trainieren, verkaufen, zum Kapitaen machen.

### Trainer

Trainer veraendern Wachstum und Automatisierung.

- Jugendtrainer: mehr Talente.
- Taktiktrainer: mehr Teamstaerke pro Spieler.
- Fitnesstrainer: bessere Form.
- Mediencoach: mehr Markenwert.
- Cheftrainer: globaler Multiplikator.

### Zuschauer und Stadion

Zuschauer sind sichtbarer Fortschritt.

- Stadionkapazitaet begrenzt Ticketeinnahmen.
- Stimmung beeinflusst kurzfristige Einnahmen.
- Komfort, Catering und Fanshop erhoehen Umsatz pro Zuschauer.
- Ausverkaufte Spiele geben Bonusereignisse.

### Werbevertraege und Medienrechte

Vertraege sind wiederkehrende Einkommenspakete.

- Lokaler Sponsor: frueh, stabil, klein.
- Trikotsponsor: skaliert mit Fans.
- Ausruester: skaliert mit Spielern und Merch.
- TV-Rechte: skaliert mit Liga und Teamstaerke.
- Streaming-Plattform: skaliert mit globaler Marke.
- Mega-Deal: spaete Phase, hohe Exponenten.

### Wettbewerbe

Wettbewerbe geben aktive Ziele und groessere Spruenge.

- Freundschaftsspiel
- Stadtliga
- Regionalliga
- Nationale Liga
- Pokal
- Europapokal
- Weltturnier
- Galaktische Liga als spaete, humorvolle Eskalation

## Progression

### Phase 1: Dorfverein

- Klick- oder Button-Einnahme: Eintritt sammeln.
- Erste Zuschauer, erste Spieler, kleiner Fanshop.
- Ziel: regelmaessiges passives Einkommen.

### Phase 2: Profibetrieb

- Trainer, Sponsoren, Stadionausbau.
- Automatisierung wird wichtig.
- Erste Wettbewerbe und Tabellenfortschritt.

### Phase 3: Nationale Macht

- Medienrechte, grosse Transfers, Scouting.
- Mehrere Waehrungen greifen ineinander.
- Prestige wird freigeschaltet.

### Phase 4: Globaler Konzern

- Internationale Fans, Markenwert, Weltstars.
- Sehr grosse Zahlen und exponentielle Kostenkurven.
- Mehrere parallele Produktionsdimensionen.

### Phase 5: Fussball-Multiversum

- Keine harte Potenzgrenze.
- Absichtlich uebertriebene spaete Upgrades.
- Legendenpunkte und globale Multiplikatoren dominieren.

## Grafik- und UI-Plan

Grafiken sind wichtig und gehoeren von Anfang an zur Identitaet des Spiels.

### Visueller Stil

- Modernes Sport-Management-Dashboard.
- Dunkler Rasen-/Stadionhintergrund mit kontrastreichen UI-Flaechen.
- Akzentfarben: Gruen fuer Wachstum, Gold fuer Prestige, Rot/Blau fuer Wettbewerb.
- Keine reine Tabellenwueste: Zahlen, Icons, Mini-Charts und Stadionvisualisierung sollen Fortschritt spuerbar machen.

### Grafische Elemente

- Stadionansicht als zentrales Fortschrittsbild.
- Zuschauerbalken oder Mini-Tribuene, die mit Fans/Kapazitaet waechst.
- Spieler-Karten mit Position, Seltenheit und Effekt.
- Trainer-Karten mit klaren Bonus-Icons.
- Sponsoren-/Vertragskarten.
- Ressourcenleiste mit Waehrungssymbolen.
- Fortschrittsleisten fuer Liga, Saison, Prestige und Stadionausbau.
- Kleine Charts fuer Einnahmen pro Sekunde und Ressourcenverteilung.

### Umsetzung der Grafiken

Fuer die erste Version reichen HTML, CSS und Canvas/SVG:

- CSS fuer Layout, Karten, Panels und Fortschrittsanzeigen.
- Inline-SVG oder CSS-Formen fuer Icons, falls keine Icon-Bibliothek genutzt wird.
- Canvas fuer animierte Stadion- oder Zuschaueransicht.
- Keine externen Bilddateien noetig fuer Version 1, damit `index.html` wirklich allein laeuft.

Spaeter koennen optional eingebettete Base64-Bitmaps, eigene Icons oder generierte Assets hinzukommen.

## Geplante Screen-Struktur

- Kopfbereich: Clubname, aktuelle Liga, wichtigste Ressourcen.
- Linke/obere Hauptaktion: Spieltag ausrichten oder Einnahmen sammeln.
- Zentral: Stadion-/Clubvisualisierung und Kernfortschritt.
- Rechte/untere Panels: Upgrades, Produktionslinien, Spieler, Trainer, Sponsoren.
- Tabs oder Segmentsteuerung:
  - Club
  - Spieler
  - Stadion
  - Vertrage
  - Wettbewerbe
  - Prestige
  - Statistiken
- Footer/kleiner Bereich: Speicherstatus, Export/Import, Reset.

## Erste spielbare Version

Die erste lauffaehige Version soll nicht alles enthalten, aber den Kern beweisen:

1. Ressourcen: Euro, Fans, Teamstaerke, Markenwert, Talente.
2. Passive Produktion pro Sekunde.
3. Drei bis fuenf Produktionslinien.
4. Upgrades mit exponentiellen Kosten.
5. Stadionkapazitaet und Zuschauerlogik.
6. Einfache Spieler- und Trainerkarten.
7. Sponsorenvertrag als wiederkehrender Bonus.
8. Save/Load ueber `localStorage`.
9. Grosszahlenanzeige.
10. Ein sichtbares Stadion-/Fan-Grafikelement.

## Spaetere Erweiterungen

- Prestige-System mit Legendenpunkten.
- Saison- und Ligamodus.
- Transfermarkt mit zufaelligen Angeboten.
- Ereignisse: Derby, Verletzung, Hype, Sponsorenskandal, Nachwuchswunder.
- Achievements und Meilensteine.
- Offline-Fortschritt.
- Mehr Statistikcharts.
- Balancing-Modus fuer Kostenkurven.
- Export/Import des Speicherstands.

## GitHub-Pages-Plan

1. Lokales Repository initialisieren oder korrekt mit `stefkowski-cpu/idle-economy` verbinden.
2. `index.html` und `context.md` committen.
3. Branch `main` nach GitHub pushen.
4. In GitHub unter Settings -> Pages die Quelle auf `Deploy from a branch`, Branch `main`, Ordner `/root` stellen.
5. Danach ist das Spiel typischerweise unter `https://stefkowski-cpu.github.io/idle-economy/` erreichbar.

## Offene Designentscheidungen

- Soll der Verein einen festen Namen haben oder frei benennbar sein?
- Soll die erste Version eher Management-Dashboard oder eher verspielte Stadionansicht sein?
- Soll Prestige frueh sichtbar, aber gesperrt sein, oder erst nach dem ersten grossen Meilenstein auftauchen?
- Sollen Spieler zufaellig generiert werden oder aus festen Archetypen bestehen?
- Sollen externe Icon-Libraries erlaubt sein, oder bleibt Version 1 komplett ohne externe Abhaengigkeiten?

## Naechster Schritt

Als naechstes erstellen wir `index.html` als erste spielbare Version. Der Fokus liegt auf einem soliden Kernloop: Einnahmen, passive Produktion, Upgrades, Stadionwachstum, Fussball-Story und eine klare grafische Anzeige, die sofort zeigt, dass der Club groesser wird.
