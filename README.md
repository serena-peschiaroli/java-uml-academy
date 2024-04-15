## Attori
- **Admin (o utente)**: Gestisce l'intero sistema, può aggiungere e assegnare insegnanti/tutor, creare corsi e classi.
- **Insegnante/Tutor**: Professionisti che possono essere assegnati a classi come insegnanti o tutor.
- **Corso**: Entità che contiene diverse classi e definizioni.
- **Classe**: Sottoinsieme di un corso, contiene studenti e può avere uno o più insegnanti o tutor assegnati.
- **Studente**: Persona che si iscrive ai corsi e partecipa alle classi.

## UC1: Inserimento di un nuovo Insegnante/Tutor
- **Attore principale**: Admin
- **Condizione**: Admin è autenticato.
- **Risultato**: Un nuovo insegnante/tutor è creato con un ID unico.
- **Descrizione**:
  1. L’admin accede al sistema.
  2. L’admin inserisce i dettagli come Nome, Cognome, email, specializzazione.
  3. Il sistema valida i dati e crea un nuovo record nel database con un ID autoincrementale.
  4. Il sistema conferma la creazione al admin.
- **Errore**:
  - Se i dati non sono validi, il sistema mostra un errore e richiede la correzione.

## UC2: Assegnazione di un insegnante/tutor ad una classe
- **Attore principale**: Admin
- **Condizioni**: La classe esiste e è collegata ad un corso, l’insegnante/tutor è nel sistema.
- **Risultato**: Insegnante/tutor è assegnato a una classe con un ruolo specifico.
- **Descrizione**:
  1. L’admin accede alla sezione di gestione delle classi.
  2. L’admin seleziona una classe specifica all'interno di un corso.
  3. L’admin sceglie dall’elenco un Insegnante e assegna il ruolo (insegnante o tutor).
  4. Il sistema aggiorna il database.
  5. Il sistema conferma l'operazione.
- **Errore**:
  - Errore nel database o dati non validi impediscono il salvataggio.

## UC3: Creazione di un nuovo corso
- **Attore principale**: Admin
- **Descrizione**:
  1. L’admin inserisce i dettagli del corso come Id, Titolo, Tipologia, Ore totali, Certificazione, Costo.
  2. Il sistema valida i dati e crea un nuovo corso nel database.
  3. Il sistema conferma l'operazione.

## UC4: Creazione di una nuova classe
- **Attore principale**: Admin
- **Condizione**: Il corso esiste nel sistema.
- **Descrizione**:
  1. L’admin accede alla gestione dei corsi
    2. L’admin seleziona il corso.
  3. L’admin sceglie di aggiungere una nuova classe al corso.
  4. L’admin inserisce i dettagli della classe come orario di lezione, tipologia aula (virtuale o in presenza), e numero massimo di studenti.
  5. Il sistema valida i dati e inserisce la nuova classe nel database.
  6. Il sistema conferma l'operazione.

## UC5: Iscrizione di studenti al corso
- **Attore principale**: Admin
- **Precondizioni**: Il corso e lo studente devono essere già presenti nel sistema.
- **Flusso principale**:
  1. L’admin accede alla sezione di gestione degli studenti.
  2. L’admin seleziona lo studente che ha fatto domanda di iscrizione.
  3. L’admin seleziona il corso cui lo studente si è iscritto.
  4. Il sistema aggiorna il database con l'iscrizione.
  5. Il sistema conferma l'operazione o invia un messaggio di errore in caso di problemi.

## UC6: Aggiunta di studenti ad una classe
- **Attore principale**: Admin
- **Condizione**: Classe, corso e studenti devono già essere presenti nel sistema; gli studenti devono essere già iscritti o aver fatto domanda di iscrizione al corso.
- **Descrizione**:
  1. L’admin seleziona una classe all'interno di un corso.
  2. L’admin seleziona uno o più studenti all'interno di quel corso.
  3. Il sistema verifica la disponibilità ed aggiorna il database.
  4. Il sistema conferma l'operazione avvenuta con successo o segnala un errore.

