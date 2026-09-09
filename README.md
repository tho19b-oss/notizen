# Notizen — Aufgaben und Notizen nach Tagen

Eine Notizen-App als **einzelne HTML-Datei**. Kein Build-Schritt, keine
Abhängigkeiten, kein CDN, keine einzige Netzwerkanfrage. Doppelklick auf
`notizen.html` genügt, sie läuft offline im Browser und speichert alles lokal.

Gedacht für den Arbeitsalltag: alles, was am Tag anfällt, landet in einer Zeile.
Was offen bleibt, nimmt die App am nächsten Tag von selbst mit, verrät aber
weiterhin, von wann es ursprünglich stammt.

## Loslegen

1. `notizen.html` herunterladen.
2. Doppelklick. Fertig.

Es gibt nichts zu installieren und nichts einzurichten. Die App läuft in Chrome,
Edge und Firefox. Erscheint oben ein roter Hinweis auf fehlenden Speicher, blockiert
der Browser den lokalen Speicher für Dateien; die App bleibt dann benutzbar, vergisst
aber beim Schließen alles. In dem Fall hilft es, die Datei über einen beliebigen
lokalen Webserver auszuliefern statt sie direkt zu öffnen.

## Was die App kann

- **Nach Tagen sortiert**, neuester Tag oben, die Geschichte bleibt durchblätterbar.
- **Klick hakt ab.** Der Durchstrich zeichnet sich, die Zeile bleibt an ihrem Platz.
  Ein zweiter Klick öffnet sie wieder.
- **Volltextsuche über alle Tage**, mit deutscher Umlautbehandlung in beide
  Richtungen: `mueller` und `muller` finden beide *Müller*. Wortteile in Komposita
  werden gefunden, `rechnung` trifft *Rechnungsprüfung*. Mehrere Begriffe sind
  UND-verknüpft, `"in Anführungszeichen"` sucht die genaue Wortfolge.
- **Filter** für alle, offene oder erledigte Einträge, dazu ein Schalter für
  „nur wichtige".
- **Hell, dunkel oder Systemeinstellung**, umschaltbar über das Symbol in der Kopfzeile.
- **Mit eingeschalteten Kürzeln vollständig über die Tastatur bedienbar**, mit
  Live-Ansagen für Vorlesesoftware. Schaltest du die Kürzel ab, verschwindet auch
  die Pfeiltasten-Navigation der Liste, siehe unten.

## Übernahme auf heute

Das ist der Kern der App. Ein offener Eintrag von gestern steht am nächsten Morgen
unter *Heute*, mit einem kleinen Abzeichen wie **von gestern**, **vom Montag** oder
**vom 3. Sept.**

Wichtig dabei:

- Der **Ursprungstag bleibt erhalten**, auch wenn ein Eintrag zehnmal mitgenommen
  wurde. Das Abzeichen sagt weiterhin die Wahrheit.
- **Erledigtes bleibt an seinem Tag.** Nur Offenes wandert mit.
- Ab acht mitgenommenen Einträgen klappt die Gruppe **Übernommen** ein, damit die
  vier Dinge, die du heute geschrieben hast, nicht unter zwanzig alten verschwinden.
- Ein bereits mitgenommener Eintrag lässt sich über das Zeilenmenü mit **Am
  Ursprungstag lassen** zurückschicken. Er bleibt dort liegen und wird nicht mehr
  übernommen, bis du **Wieder mitnehmen** wählst. Vorbeugend anheften geht nicht:
  solange ein Eintrag an seinem Ursprungstag steht, bietet das Menü diese Aktion
  nicht an.
- Öffnest du einen erledigten Eintrag von einem früheren Tag wieder, kommt er nach
  heute. Ein Hinweis mit **Rückgängig** sagt es dir.
- Die Übernahme ist abschaltbar, im Menü hinter den drei Punkten.
- Sie ist unabhängig davon, wie lange du weg warst. Drei Wochen Urlaub kosten die
  App genauso viel wie ein Wochenende.

Tage, von denen alles weggewandert ist, bleiben als schmale Zeile in der Geschichte
stehen, etwa **Dienstag, 8. September · 4 mitgenommen**. Sonst läse sich der Verlauf
wie der eines Menschen, der jeden Tag alles geschafft hat.

## Tags und Wichtig

Beides schreibst du direkt in den Text, es gibt keine Extra-Felder.

| Eingabe | Wirkung |
|---|---|
| `Angebot für #Kunde Meier` | `#Kunde` wird zum anklickbaren Filter-Chip, an Ort und Stelle |
| `! Rückruf Klärungsstelle` | Ein **alleinstehendes** `!` markiert als wichtig und verschwindet aus dem Text |
| `Nicht vergessen!` | Bleibt unverändert, das `!` klebt am Wort |

Ein Tag darf Umlaute, Ziffern, Bindestriche und Unterstriche enthalten und braucht
mindestens einen Buchstaben. `#2026` wird deshalb keiner. Eine Adresse wie
`https://intra.de/seite#anker` ebenfalls nicht, und `C#` auch nicht. Höchstens
zwölf Tags pro Eintrag, höchstens 32 Zeichen je Tag.

Wichtige Einträge bekommen einen Balken am linken Rand, etwas mehr Schriftstärke und
einen gefüllten Stern. Drei Kanäle, weil Schriftstärke allein unter Windows 10
manchmal wirkungslos bleibt.

## Tastenkürzel

Einzelne Tasten wirken nur, wenn kein Textfeld den Fokus hat. Die Feststelltaste
stört nicht.

Im Menü hinter den drei Punkten schaltet **Tastenkürzel aktiv** die Einzeltasten ab,
also alles aus den Tabellen außer den Kombinationen mit Strg und Alt. `Strg+Z`,
`Strg+Umschalt+Z`, `Alt+↑`, `Alt+↓`, `Strg+Pos1`, `Strg+Ende` und sämtliche Tasten
der Eingabezeile wirken weiter. Beachte: der Schalter nimmt dir auch die
Pfeiltasten-Navigation in der Liste, und damit den einzigen Weg zu den Knöpfen und
Tag-Chips einer Zeile.

| Taste | Aktion |
|---|---|
| `N` | Fokus in die Eingabezeile |
| `/` | Fokus ins Suchfeld |
| `1` `2` `3` | Filter Alle / Offen / Erledigt |
| `Umschalt+W` | Nur wichtige anzeigen |
| `Umschalt+D` | Design wechseln |
| `Strg+Z` / `Strg+Umschalt+Z` | Rückgängig / Wiederherstellen |
| `?` | Übersicht der Kürzel |

In der Eingabezeile:

| Taste | Aktion |
|---|---|
| `Eingabe` | Anlegen |
| `Umschalt+Eingabe` | Neue Zeile |
| `Strg+Eingabe` | Anlegen und als wichtig markieren |
| `Esc` | Feld leeren, nochmal `Esc` verlässt es |

In der Liste:

| Taste | Aktion |
|---|---|
| `↑` `↓` oder `j` `k` | Voriger / nächster Eintrag, über Tagesgrenzen hinweg |
| `←` `→` | Innerhalb der Zeile zwischen Kästchen, Tags und Knöpfen |
| `Alt+↑` `Alt+↓` | Voriger / nächster Tag |
| `Pos1` `Ende` | Erster / letzter Eintrag des Tages |
| `Strg+Pos1` `Strg+Ende` | Erster / letzter Eintrag insgesamt |
| `Bild↑` `Bild↓` | Zehn Einträge |
| `Leertaste` | Erledigt umschalten |
| `Eingabe` oder `F2` | Bearbeiten |
| `W` | Wichtig umschalten |
| `Entf` | Löschen, mit Rückgängig |

Sobald die Eingabezeile mehrere Zeilen enthält, eingefügt oder mit
`Umschalt+Eingabe` getippt, erscheint darüber eine Leiste mit **Als N Einträge
anlegen** und **Als einen Eintrag anlegen**. Voreingestellt ist ein Eintrag je
Zeile. Wer nichts anklickt, bekommt beim Absenden die Aufteilung.

## Wo die Daten liegen

Im `localStorage` deines Browsers, unter diesen Schlüsseln:

| Schlüssel | Inhalt |
|---|---|
| `notizen.tb.v1` | Alle Einträge und Einstellungen |
| `notizen.tb.v1.bak` | Sicherung des letzten fehlerfrei gelesenen Standes |
| `notizen.tb.v1.hb` | Lebenszeichen, erkennt einen zweiten offenen Tab |
| `notizen.corrupt.<Zeitstempel>` | Rohkopie eines unlesbaren Standes, wird nur beim Start angelegt, wenn die Daten nicht gelesen werden konnten |

**Nichts davon verlässt deinen Rechner.** Die Datei enthält eine
Content-Security-Policy, die ihr jede Netzwerkverbindung verbietet.

Der Haken daran: die Daten hängen am Browser, nicht an der Datei. Ein
„Browserdaten löschen" nimmt sie mit, ohne `notizen.html` anzurühren. Deshalb
liegen im Menü hinter den drei Punkten **Daten exportieren** und **Daten
importieren**, und die Fußzeile erinnert nach sieben Tagen ohne Export daran.
Beim Wechsel auf einen anderen Rechner ist der Export der einzige Weg.

Alle Dateien, die du lokal öffnest, teilen sich einen gemeinsamen Speicherbereich.
Die Schlüssel sind deshalb mit `notizen.` vorangestellt, damit sie sich nicht mit
anderen lokalen Seiten in die Quere kommen.

## Grenzen

Gemessen mit 3.000 Einträgen über 400 Tage:

| Vorgang | Zeit |
|---|---|
| Abhaken | 24 ms |
| Neue Notiz anlegen | 225 ms |
| Suche, erste Eingabe | 197 ms |
| Suche, jede weitere | 4 ms |
| Speichern | 7 ms |

Was daraus folgt:

- **Abhaken bleibt schnell**, weil dabei nur eine Zeile geändert wird, nicht die
  ganze Liste. Anlegen und Löschen zeichnen alles neu und ruckeln bei viel Bestand.
- **Der Browser-Speicher ist die harte Grenze.** Daten und Sicherung zusammen
  belegen bei 3.000 Einträgen rund 1,7 MB von etwa 5 MB. Bei ungefähr 8.000
  Einträgen meldet sich die Speicher-Warnung. Ein Export vorher ist Pflicht.
- **Angezeigt werden die neuesten 30 Tage.** Ältere holt ein Knopf am Ende der
  Liste nach, in sich verdoppelnden Schritten, oder alle auf einmal.
- **Bei sehr vielen Suchtreffern** zeigt die App 300 Zeilen und schreibt darunter,
  wie viele fehlen. Blättern gibt es nicht, nur die Suche verengen.
- **Rückgängig reicht 20 Schritte weit** und liegt nur im Arbeitsspeicher. Ein
  Neuladen leert den Verlauf.

## Am Code arbeiten

Es gibt keinen Build-Schritt. Datei bearbeiten, im Browser neu laden, fertig.

`notizen.html` ist in 21 nummerierte Abschnitte gegliedert, die im Quelltext als
Kommentarblöcke markiert sind. Die tragenden sind:

| Abschnitt | Inhalt |
|---|---|
| 2 Datum | Tagesschlüssel, immer lokal, nie UTC |
| 3 Faltung | Umlautbehandlung der Suche mit Index-Karte |
| 5 Speicher | Bündelt den Zugriff auf `localStorage`. Einzige Ausnahme ist `downloadCorruptBackup` in Abschnitt 16, das die abgelegte Rohkopie direkt liest |
| 8 Übernahme | Der Algorithmus für „auf heute holen" |
| 9 Sortierung | Ein Vergleicher, der eine echte Totalordnung liefert |
| 11 Zeichnen | Aufbau der Liste, ohne Nutzertext jemals zu HTML zu machen |

Drei Regeln, die beim Ändern nicht brechen dürfen:

1. **Nutzertext wird niemals zu HTML.** Kein `innerHTML` mit Eingaben, keine aus
   Text zusammengesetzten Adressen. Alles geht durch `textContent`.
2. **`createdDayKey` wird genau einmal geschrieben und nie wieder.** Daran hängt das
   Abzeichen, das den Ursprungstag anzeigt. `dayKey` dagegen ändert sich an fünf
   Stellen: `runCarryOver` und `undoCarry` in Abschnitt 8, sowie `toggleDone`,
   `setPinned` und `pullToToday` in Abschnitt 13. Angelegt wird er in `addItems`.
   Wer eine sechste Stelle braucht, sollte zuerst prüfen, ob es nicht eine der
   fünf schon tut.
3. **Tagesschlüssel entstehen nur aus `getFullYear`, `getMonth` und `getDate`.**
   `toISOString()` ist UTC und schöbe jede Notiz zwischen Mitternacht und zwei Uhr
   auf den Vortag.

## Lizenz

Privates Projekt, keine Lizenz vergeben.
