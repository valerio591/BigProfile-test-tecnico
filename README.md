# BigProfile-test-tecnico
API per l'ingestion di informazioni

1. Introduzione
La repository contiene il codice necessario ad eseguire un'applicazione che gestisca una API
per l'ingestion di informazioni.
L'applicazione non è completa in quanto la restituzione in forma aggregata delle informazioni
inviate tramite l'endpoint di ingestion. Lo sviluppo è terminato nella fase di esecuzione dei 
comandi per aggregare i risultati salvati sul database MongoDB tramite la libreria pymongo.
La repository è provvista di un ambiente virtuale che è necessario attivare per eseguire l'applicazione.
Il componente principale è il file main.py, che si trova all'interno del percorso '.\backend' come
specificato nella consegna.
Per eseguire l'applicazione è necessaria l'installazione dell'ultima versione di MongoDB.

2. Avvio di mongoDB
Affinchè le informazioni inviate all'endpoint di riferimento per la ricezione delle richieste GET siano salvate
su un database MongoDB è necessario eseguire il seguente comando nel terminale:

'''mongodb'''

Nel caso in cui si decida di modifcare la porta di default nella quale viene lanciato mongodb
è necessario inserire la porta selezionata nel codice del file main.py nella cartella backend alla riga 29. 

3. Avvio dell'ambiente virtuale
Per avviare l'ambiente virtuale nel quale verrà eseguito il codice si può digitare il seguente comando 
nel terminale dopo aver selezionato il percorso in cui si trova la cartella bigprofiles.

'''.\Scripts\activate'''

4. Esecuzione dell'applicazione tramite il framework uvicorn
Per eseguire l'applicazione si può digitare il seguente comando nel terminale, dopo aver
selezionato la directory "backend" come current directory.

'''uvicorn main:app'''

L'applicazione sarà a questo punto avviata. Il root endpoint di riferimento per l'invio delle richieste è
"http://127.0.0.1:8000"

4.Struttura del codice in main.py
Il codice è suddiviso in 7 sezioni: import delle librerie, connessione e creazione del database mongodb,
definizione di un custom middleware per registrare il tempo di risposta del server e la data di creazione delle singole
istanze nel database, definizione degli argomenti delle path operations, definizione di alcune classi utili
nelle fasi successive del codice, definizione dell'endpoint di ingestion e definizione dell'endpoint retrieve.

Il codice è comprensivo di commenti che descrivono i passaggi principali e le scelte effettuate in fase di programmazione

5. Risultati raggiunti
L'endpoint ingestion funziona correttamente, ad eccezione dell'ultima instanza inserita nel database che risulta parzialmente
priva di alcune informazioni. Le informazioni ricevute vengono caricate nel database creato nella seonda sezione del codice.
Per quanto rigurda l'enpoind retrieve lo sviluppo è terminato in fase di implementazione delle operazioni di aggregazione da
eseguire. La variabile pipeline rappresenta l'argomento da passare al metodo aggregate della collezione "requests". Non è stato
possibile effettuare dei test del comando in python in quanto le richieste inviate all'endpoint restituiscono uno status_code 500.
