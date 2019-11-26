# Deep Learning - Instrument Classification

Dieses Projekt entstand im Rahmen der Lehrveranstaltung "Aktuelles Vertiefungsfach / Deep Learning" im 3. Semester des Masterstudiengangs Software Engineering an der FH Hagenberg.

Projektmitglieder: Gregor Rechberger, Stefan Schöberl und Jakob Wundsam

## Ziel

Mit einem CNN (Convolutional Neural Network) sollen Bilder von Klavieren und Schlagzeugen unterschieden werden.

## Erkenntnisse

* Pipeline aufsetzen und initales Setup ist am Anfang etwas zeitaufwändig, sobald es allerdings einmal läuft, sind Anpassungen einfach möglich. Somit kann man dann einfache Modelle relativ schnell zusammenbauen.
* Beim Erstellen des Modells sollte man jeden Schritt in der Pipeline ausprobieren und ausgeben, zum Beispiel: "Sind die Bilder wirklich geladen und nicht schwarz" oder "Machen die Daten (und daraus verarbeitete) Sinn".
* Es ist sehr wichtig, gute und viele Trainingsdaten zu haben. Gegebenfalls kann man die Menge der Daten künstlich vergrößern (img_generator). Die Daten sind essenziell, ohne sie kann selbst das "beste" Modell nichts daraus lernen.
* Es hilft, dass man versteht, was im Modell etwa passiert (welche Funktion haben welche Layer, ...). So hat man beim Erstellen des Modells eine ungefähre Idee, was *funktionieren könnte*, bzw. auf gar keinen Fall *funktionieren kann*.
* Eher Projektengineering-Aspekt, wir sind aber dennoch darauf gestoßen: Die Jupyter-Notebooks lassen sich zwar in Git versionieren, jedoch scheinen sie nicht sehr merge-freundlich zu sein, da sie im Prinzip "generierte" JSON-Dokumente sind, die wir selbst nicht händisch schreiben. Wir würden ungern Merge-Konflikte darin lösen müssen.
* Daten müssen immer aufgeteilt werden (Training und Validierung). Sonst macht das Training keinen Sinn, wenn man später mit Trainingsdaten testen würde.
* Unser primärer Ansatz bei der Architektur des Modells war, möglichst wenig Parameter zu haben. Dies erreichten unter anderem durch mehrere Convolution- und Pooling-Layers, sodass bei den Fully-Connected-Layers am Ende möglichst wenig, aber bereits vorverarbeitete Daten ankommen.