# Analisi del Funnel di Richiesta Prestiti per azienda FinTech

Progetto completo di Business Intelligence end-to-end che analizza il comportamento dei clienti, la conversione del funnel e il rischio del portafoglio all’interno di una piattaforma digitale di prestiti.


## Sommario
Gli istituti di credito devono bilanciare acquisizione clienti, conversione e qualità del portafoglio mantenendo allo stesso tempo una crescita sostenibile. Questo progetto presenta un caso studio completo di Business Intelligence per una fittizia società FinTech di prestiti, analizzando l’intero percorso di richiesta del prestito per identificare i punti critici di conversione, comprendere il comportamento dei clienti e valutare le performance del portafoglio. Per simulare un ambiente aziendale realistico, sono stati creati 4 dataset sintetici che rappresentano clienti, richieste di prestito, eventi e risultati. L’analisi combina la preparazione dei dati tramite SQL e l’analisi business con report interattivi sviluppati in Power BI, fornendo insight e supportando decisioni aziendali basate sui dati.


## Problema Aziendale
Una società FinTech di prestiti vuole migliorare le performance del proprio processo digitale di richiesta finanziamenti mantenendo un portafoglio crediti sano. Il team Product Management ha osservato che molti richiedenti abbandonano il processo prima dell’erogazione del prestito, ma le cause di questo comportamento non sono chiare. Allo stesso tempo, il team Risk vuole assicurarsi che un aumento delle approvazioni dei prestiti non comprometta la qualità del portafoglio attraverso un incremento dei tassi di insolvenza (charge-off). Questo progetto analizza l’intero percorso della richiesta di prestito per identificare opportunità di miglioramento della conversione clienti, mantenendo un equilibrio tra rischio creditizio e performance aziendale.

L’analisi mira a rispondere alle seguenti domande:

- Quali segmenti di clientela raggiungono i tassi di approvazione più elevati?
- In quale fase del funnel di richiesta prestito gli utenti abbandonano maggiormente il processo?
- Quali motivazioni di rifiuto contribuiscono maggiormente alla perdita di richieste?
- Quali canali di acquisizione generano il miglior equilibrio tra conversione e qualità del portafoglio?
- Come varia la performance del portafoglio tra diversi segmenti di clientela?
- Quali opportunità aziendali possono migliorare sia la conversione sia la qualità del portafoglio?


## Datasets
Poiché nessun dataset pubblico disponibile rappresentava completamente lo scenario aziendale richiesto, sono stati creati 4 dataset sintetici per simulare le operazioni di una piattaforma digitale di prestiti. I dati sono stati generati con il supporto dell’AI e includono volutamente valori mancanti, formattazioni incoerenti e problemi di qualità dei dati per supportare un workflow analitico end-to-end realistico. L’AI è stata utilizzata esclusivamente per generare dati fittizi. Tutte le attività di pulizia dati, validazione, sviluppo SQL, analisi business, creazione delle misure DAX, progettazione dashboard, visualizzazioni, insight e raccomandazioni sono state progettate, revisionate e implementate autonomamente da me.


## Modello Dati
L’analisi segue un modello dati relazionale centrato sul ciclo di vita della richiesta di prestito:

```
Users
  │
  │ 1 : Molti
  ▼
Loan Applications
  │
  │ 1 : Molti
  ├──────────────► Application Events (aggiornamenti multipli dello stato)
  │                   
  │ 1 : 1
  ▼
Loan Outcomes
```

- **Users** contiene informazioni demografiche sui clienti
- **Loan Applications** contiene i dettagli delle richieste e il rischio creditizio stimato
- **Application Events** registra ogni fase raggiunta durante il processo di richiesta
- **Loan Outcomes** contiene informazioni sui prestiti erogati e metriche relative alla performance del portafoglio


## Metodologia
Questo progetto segue un workflow completo di Business Intelligence, dalla preparazione dei dati grezzi fino alle raccomandazioni aziendali:

```
Dati grezzi
   ↓
Pulizia e validazione dati
   ↓
Analisi esplorativa business
   ↓
Analisi del funnel
   ↓
Dashboard interattiva Power BI
   ↓
Insight aziendali e raccomandazioni
```

Ogni fase del workflow è descritta di seguito.

**Pulizia e Validazione dei Dati** 

I dataset originali sono stati puliti, standardizzati e validati prima dell’analisi per garantire coerenza e affidabilità. I controlli di validazione includevano:

- Verificare che ogni richiesta appartenga ad un cliente esistente
- Assicurarsi che i risultati dei prestiti corrispondano allo stato finale della richiesta
- Confermare che le motivazioni di rifiuto siano presenti solo per richieste respinte
- Verificare che i tassi di interesse siano registrati solo per prestiti approvati
- Controllare la coerenza tra stato del prestito, flag di insolvenza e date di insolvenza
- Rimuovere record duplicati e gestire valori mancanti

**Analisi Esplorativa Business**
- Analisi delle caratteristiche demografiche dei clienti e del comportamento di richiesta prestiti
- Studio degli esiti delle richieste tra diversi segmenti di clientela
- Valutazione delle performance dei canali di acquisizione, del rischio creditizio e della qualità del portafoglio

**Analisi del Funnel**
- Mappatura dell’intero percorso della richiesta dalla compilazione iniziale fino all’erogazione del prestito
- Calcolo dei tassi di conversione in ogni fase
- Identificazione dei principali punti di abbandono e confronto delle performance del funnel tra segmenti diversi

**Sviluppo Dashboard Interattiva**
- Creazione di una dashboard Power BI interattiva per monitorare performance operative e del portafoglio
- Progettazione di tre pagine di reporting dedicate a KPI principali, performance del funnel e analisi del rischio

**Insight Aziendali e Raccomandazioni**
- Sintesi dei risultati analitici in raccomandazioni operative
- Identificazione di opportunità per migliorare la conversione, mantenendo la qualità del portafoglio


## Risultati

#### Dove abbandonano gli utenti la richiesta del prestito?
La maggiore riduzione del numero di richiedenti avviene prima della fase di caricamento dei documenti, rendendo questa fase il principale ostacolo alla conversione nel percorso cliente.

#### Quali segmenti di clientela hanno maggiori probabilità di approvazione?
I richiedenti con punteggi creditizi stimati più elevati raggiungono tassi di approvazione significativamente superiori. I pattern di approvazione variano inoltre in base ai livelli di reddito e ai canali di acquisizione.

#### Quali canali di acquisizione hanno le migliori performance?
I canali di acquisizione differiscono significativamente sia per volume di richieste sia per tasso di approvazione. Il confronto tra conversione e qualità del portafoglio permette di identificare i canali che generano il maggiore valore aziendale.

#### Quali segmenti presentano il rischio maggiore sul portafoglio?
I tassi di insolvenza (charge-off) variano tra segmenti di clienti e canali di acquisizione, dimostrando che un elevato volume di prestiti non si traduce necessariamente in una migliore performance del portafoglio.

#### Come viene riflesso il rischio creditizio nei prezzi?
I richiedenti con punteggi creditizi stimati inferiori ricevono mediamente tassi di interesse più elevati, indicando l’utilizzo di una strategia di prezzo basata sul rischio.

#### Quali opportunità esistono per migliorare le performance?
Le inefficienze del funnel rappresentano un’opportunità per aumentare il numero di prestiti erogati e i ricavi, migliorando la conversione nelle fasi chiave del percorso cliente.

#### Come può l’azienda migliorare le performance?
Migliorare la conversione degli utenti nel principale punto critico del funnel rappresenta la maggiore opportunità per aumentare i prestiti erogati, mantenendo la qualità del portafoglio.


## Suggerimenti
- **Ridurre l’abbandono prima della fase di caricamento documenti** semplificando l’esperienza di caricamento e identificando i punti di frizione nel processo di richiesta
- **Dare priorità ai canali di acquisizione** che combinano costantemente alti tassi di approvazione e bassi tassi di insolvenza per massimizzare la performance del portafoglio
- **Monitorare continuamente la qualità del portafoglio** tra segmenti cliente e fasce di punteggio creditizio per identificare tempestivamente variazioni nel rischio di credito
- **Migliorare le strategie di valutazione del credito** per i richiedenti borderline, bilanciando tassi di approvazione e performance attesa del portafoglio invece di considerare solo il volume delle richieste
- **Monitorare conversione del funnel e KPI del portafoglio** tramite dashboard interattive per supportare decisioni data driven e miglioramento continuo dei processi


## Competenze

**Business Analysis**
- Analisi esplorativa business
- Analisi del funnel
- Segmentazione clienti
- Analisi del rischio creditizio
- Definizione KPI e monitoraggio performance
- Generazione di insight aziendali

**SQL (PostgreSQL)**
- Pulizia dati
- Validazione dati
- Controlli qualità dati
- CTE
- Window functions
- Join
- Aggregations
- CASE Statement
- Query analitiche orientate al business

**Power BI**
- Modellazione dati
- Misure DAX
- Dashboard interattive
- KPI card e visualizzazioni
- Slicer e filtri incrociati

**Sviluppo Assistito dall’AI**
- Generazione dataset sintetici (Claude)
- Brainstorming e supporto al workflow


## Cartelle e File
- Data: dataset sintetici originali e dataset puliti, pronti per l’analisi

- SQL notebooks: pulizia dati e analisi, inclusivi di query e note

- Power BI: dashboard interattive per analisi funnel, performance e rischio

- Screenshots: anteprime delle dashboard interattive Power BI
