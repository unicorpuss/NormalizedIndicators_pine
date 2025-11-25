# RSPS Trading Systems - TradingView Pine Script

Dieser Codespace enthält eine Sammlung von Trading-Tools, die vollständig in **Pine Script** geschrieben sind – der proprietären Programmiersprache von TradingView für technische Analyse und Strategieentwicklung.

**NormalizedIndicators Library auf TradingView**: https://www.tradingview.com/script/3Cqpb8Jr-NormalizedIndicators/

## 📚 Übersicht

Das Projekt besteht aus drei Hauptkomponenten:

1. **NormalizedIndicators Library** - Eine Bibliothek normalisierter Trend-Momentum-Indikatoren
2. **RSPS Systems** - Beispielhafte Relative-Stärke-Systeme für verschiedene Anlageklassen
3. **RSPS Combiner** - Ein Tool zum Kombinieren mehrerer RSPS-Strategien

---

## 🔧 NormalizedIndicators Library

### Beschreibung

Die `NormalizedIndicators.pine` ist eine umfassende Bibliothek mit **normalisierten technischen Indikatoren**, die speziell für **Trend-Momentum-Analyse** entwickelt wurden.

### Hauptmerkmale

- **Normalisierte Signale**: Alle Indikatoren liefern standardisierte Werte im Bereich von **-1 bis +1** (einige unterstützen auch 0 für neutrale Zustände)
- **Trend-Following-Fokus**: Die Indikatoren werden mit trendfolgenden Methoden gelesen und signalisieren Trend-Momentum
- **Momentum-Basiert**: Alle Indikatoren basieren auf Momentum-Konzepten

### Enthaltene Indikatoren

#### Stationäre Indikatoren
- **TSI** (True Strength Index) - Momentum-Oszillator
- **SMI** (Stochastik Momentum Index) - Kombiniert Stochastik mit Momentum
- **BBPct** (Bollinger Bands Percent) - Positionierung innerhalb der Bollinger Bänder
- **RSI** (Relative Strength Index) - Klassischer Momentum-Indikator

#### Nicht-stationäre Trend-Indikatoren
- **NorosTrendRibbon** (SMA & EMA Versionen) - Trendband-System
- **TrendBands** - Mehrfaches Bandsystem für Trendidentifikation
- **Vidya** (Variable Index Dynamic Average) - Adaptiver Moving Average
- **VZO** (Volume Zone Oscillator) - Volumen-basierter Indikator
- **TrendContinuation** - Trendfortsetzungssignale
- **LeonidasTrendFollowingSystem** - Trendfolgensystem
- **ysanturtrendfollower** - Adaptives Trendfolgensystem
- **TRAMA** (Trend Regularity Adaptive Moving Average) - Regelbasierter adaptiver MA
- **HullSuite** - Auf Hull Moving Average basierend
- **STC** (Schaff Trend Cycle) - Verbesserter MACD

#### Berechnungsindikatoren
- **Korrelationsindikatoren** (Lang- und Mittelfrist)
- **Beta-Berechnung** - Für Asset-Vergleiche
- **TPI Kalibrierungen** - Spezielle Kalibrierungen für verschiedene Assets

### Verfügbarkeit

Die Bibliothek ist öffentlich auf TradingView verfügbar:
**https://www.tradingview.com/script/3Cqpb8Jr-NormalizedIndicators/**

### Signal-Interpretation

- **+1** = Bullisches Signal (Aufwärtstrend/Momentum)
- **-1** = Bearisches Signal (Abwärtstrend/Momentum)
- **0** = Neutrales Signal (bei Indikatoren, die diesen Zustand unterstützen)

---

## 📊 Basic RSPS Systems (Ordner: `basic_rsps_systems/`)

### Was sind RSPS-Systeme?

RSPS steht für **Relative Strength Portfolio Systems** - technische Handelssysteme, die auf relativer Stärke basieren.

### Zweck

Die Dateien in diesem Ordner sind **Nutzungsbeispiele** der NormalizedIndicators Library. Sie demonstrieren, wie die normalisierten Indikatoren in praktischen Trading-Systemen angewendet werden können.

### Enthaltene Sektoren & Anlageklassen

Der Ordner enthält RSPS-Beispiele für verschiedene Märkte:

#### Traditionelle Märkte
- `bonds_rsps.pine` - Anleihen
- `commodities_rsps.pine` - Rohstoffe

#### Aktien-Sektoren
- `technology_rsps.pine` - Technologie
- `healthcare_rsps.pine` - Gesundheitswesen
- `financials_rsps.pine` - Finanzen
- `consumer_discretionary_rsps.pine` - Nicht-Basiskonsumgüter
- `consumer_staples_rsps.pine` - Basiskonsumgüter
- `communication_rsps.pine` - Kommunikation
- `energy_rsps.pine` - Energie
- `industrials_rsps.pine` - Industrie
- `materials_rsps.pine` - Materialien
- `utilities_rsps.pine` - Versorgungsunternehmen

#### Krypto-Märkte
- `crypto_altcoins_rsps.pine` - Alternative Kryptowährungen
- `memecoins_rsps.pine` - Meme-Coins

#### Kombinierte Systeme
- `sector_rsps.pine` - Sektorübergreifendes System
- `multi_rsps_combiner.pine` - Kombination mehrerer RSPS-Systeme

### Charakteristik

- **Rein technisch**: Alle Systeme basieren ausschließlich auf technischen Indikatoren
- **Beispiel-Charakter**: Dienen als Vorlagen und Lernmaterial
- **Normalisierte Signale**: Nutzen die standardisierten Outputs der NormalizedIndicators Library

---

## 🔀 RSPS Combiner (`rsps_combiner_5strategies.pine`)

### Funktionalität

Der RSPS Combiner ermöglicht die **Kombination von 1 bis 5 verschiedenen RSPS-Strategien** in einem einzigen Portfolio.

### Features

#### Portfolio-Allokation
- Dynamische Gewichtung basierend auf den Strategie-Werten
- Prozentuale Allokationsanzeige
- Optional: Cash-basierte Allokation mit konfigurierbarem Startkapital

#### Visualisierung
- **Interaktive Tabelle** zeigt:
  - Allokation jeder Strategie in Prozent
  - Optionale Cash-Allokation
  - Farbcodierung für jede Strategie (Orange, Aqua, Purple, Yellow, Lime)
- **Portfolio-Wert-Chart**:
  - Zeigt die Entwicklung des Gesamtportfolios
  - Farblich gekennzeichnet nach dominierender Strategie
  - Berechnet auf Basis der Rate of Change (ROC) aller Strategien

#### Eingabeparameter
- **5 Strategien-Inputs**: Jeweils Signal und ROC (Rate of Change)
- **Cash-Modus**: Optional aktivierbar
- **Startkapital**: Konfigurierbarer Startwert für das Portfolio

#### Outputs
- Portfolio Value - Gesamtwert des kombinierten Portfolios
- Portfolio ROC - Gesamtrendite des Portfolios
- Farbindikator - Zeigt welche Strategie dominiert

### Anwendung

Der Combiner ist ideal für:
- **Diversifikation**: Verteilung des Risikos über mehrere Strategien
- **Portfolio-Management**: Tracking der kombinierten Performance
- **Strategie-Vergleich**: Visualisierung der relativen Stärke einzelner Ansätze

---

## 🚀 Verwendung

### Voraussetzungen
- TradingView Account (kostenlos oder Premium)
- Grundkenntnisse in Pine Script (optional, für Anpassungen)

### Installation auf TradingView

1. **NormalizedIndicators Library importieren:**
   - Besuche: https://www.tradingview.com/script/3Cqpb8Jr-NormalizedIndicators/
   - Oder kopiere den Code aus `NormalizedIndicators.pine`

2. **RSPS System nutzen:**
   - Öffne eines der RSPS-Systeme aus dem `basic_rsps_systems/` Ordner
   - Kopiere den Code in den Pine Editor auf TradingView
   - Kompiliere und füge zum Chart hinzu

3. **Strategien kombinieren:**
   - Öffne `rsps_combiner_5strategies.pine`
   - Konfiguriere die Inputs mit deinen gewählten Strategien
   - Aktiviere optional den Cash-Modus

---

## 📖 Technische Details

### Pine Script Version
- Library: `@version=5`
- Combiner: `@version=6`

### Lizenz
Mozilla Public License 2.0 (MPL 2.0)

### Autor
© unicorpusstocks

---

## 💡 Hinweise

- Die RSPS-Systeme sind **Beispiele** und sollten vor Live-Trading gründlich getestet werden
- Alle Indikatoren sind **momentum-basiert** und funktionieren am besten in Trending-Märkten
- Die Normalisierung ermöglicht einfache **Vergleichbarkeit** zwischen verschiedenen Indikatoren
- Der Combiner unterstützt maximal **5 Strategien** gleichzeitig

---

## 📚 Weiterführende Ressourcen

- **TradingView Pine Script Dokumentation**: https://www.tradingview.com/pine-script-docs/
- **NormalizedIndicators auf TradingView**: https://www.tradingview.com/script/3Cqpb8Jr-NormalizedIndicators/

---

**Hinweis**: Dieser Code dient zu Bildungszwecken. Konsultiere einen Finanzberater vor realen Trading-Entscheidungen.
