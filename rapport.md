## partie 3 : transactions

### code de deux transaction debit-credit dont l'execution entraine une situation d'interblocage.

```sql
-- Session 1, etape 1
UPDATE account SET balance = balance - 100 WHERE name = 'bob';

\prompt 'Appuyez sur Entree pour continuer' dummy

-- Session 2, etape 1
UPDATE account SET balance = balance - 50 WHERE name = 'alice';

\prompt 'Appuyez sur Entree pour continuer' dummy


-- Session 1, etape 2
UPDATE account SET balance = balance + 100 WHERE name = 'alice';

\prompt 'Appuyez sur Entree pour continuer' dummy


-- Session 2, etape 2
UPDATE account SET balance = balance + 50 WHERE name = 'bob';

\prompt 'Appuyez sur Entree pour continuer' dummy
```

### la trace de la console des 2 transactions.

![Alt text](screens/deadlock.png)

## partie 4 :

![Alt text](screens/Screenshot_20241101_012446.png)
![Alt text](screens/Screenshot_20241101_012906.png)
![Alt text](screens/Screenshot_20241101_015501.png)
![Alt text](screens/Screenshot_20241101_015603.png)
![Alt text](screens/Screenshot_20241101_015632.png)
