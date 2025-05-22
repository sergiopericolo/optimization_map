## Ottimizzazione di Posizionamento con Raggio Comune

Questo progetto esegue un'ottimizzazione geometrica per posizionare una serie di **punti** e **centri** nel piano cartesiano, con l'obiettivo di:

- Rispettare le **inclusioni/esclusioni** specificate in una matrice binaria.
- Trovare un **raggio comune ottimale** `r` per tutti i cerchi.
- Evitare **sovrapposizioni** indesiderate tra punti e tra centri.

##  Descrizione del problema

Hai 5 punti (A–E) e 6 centri (c1–c6). Ogni punto può:
- Essere all'interno di uno o più cerchi (`1`)
- Essere fuori da altri cerchi (`0`)

La configurazione valida deve rispettare la seguente matrice:


data = {
    "A": [0, 1, 1, 1, 1, 0],
    "B": [0, 0, 1, 1, 0, 0],
    "C": [1, 1, 0, 0, 0, 1],
    "D": [0, 0, 0, 1, 1, 1],
    "E": [1, 1, 1, 0, 1, 0]
}


## Funzionamento

#Ottimizzazione
Si usano le coordinate (x, y) di punti e centri come variabili.
Si ottimizza anche il raggio comune r.
Viene usata la funzione scipy.optimize.minimize.

# Funzione obiettivo
Penalizza:
Inclusioni/esclusioni sbagliate.
Sovrapposizioni tra punti o centri.

# Validazione
Verifica che:
I punti rispettino la logica di data.
I punti e centri non siano troppo vicini.



## Visualizzazione
I cerchi vengono disegnati con matplotlib.
I punti sono etichettati.
Il titolo indica se la soluzione è valida o meno.



## Output
Il codice stampa e restituisce:

point_coords_dict: dizionario con le coordinate dei punti.
center_coords_dict: dizionario con le coordinate dei centri.
r: valore del raggio comune.
valid_solution: True se tutti i vincoli sono soddisfatti.

# Requisiti
Python ≥ 3.7
Librerie:
numpy
matplotlib
scipy

