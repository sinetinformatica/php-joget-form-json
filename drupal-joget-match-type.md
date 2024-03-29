# Drupal webform to Joget Examples

## VALIDATORE (Controlli di coerrenza del campo del form)
### Empty
   "className":"",
   "properties":{}

### Default
```
	"className":"org.joget.apps.form.lib.DefaultValidator"
	"properties":
				{
											VALORI						# 	INDICAZIONI
					"mandatory":			""|"true"					#	Campo obbligatorio
					"type":												#	Tipo di dati accettati
											"alphabet"					-		Alfabetico
											"alphanumeric"				-		Alfanumerico
											"numeric"					-		Numerico
    										"email"						-		Campo email
											"custom"					-		Regular Expression definita in "custom-regex"
					"custom-regex":			Regular Expression			#	Inserire la Regular Expression per type "custom"
					"message":				Stringa						#	Messaggio nel caso in cui fallisca il controllo del Validatore
				}
```

## TEXTFIELD
```
	"className":"org.joget.apps.form.lib.TextField"
	"properties":
				{							VALORI						#	INDICAZIONI
					"label":				Stringa						#	Etichetta del campo per l'interfaccia grafica
					"id":					Stringa senza spazi			#	Nome della colonna del database
					"workflowVariable":		Stringa senza spazi			#	Nome della variabile del workflow mappata
					"value":				Stringa						#	Valore di default del campo
					"readonly": 			""|"true"	 				#	Flag sola lettura (true) oppure inseribile ("")
					"readonlyLabel":		""|"true"	 				#	Flag per visualizzazione come etichetta se in sola lettura
					"size":					""|Numerico					#	Lunghezza del campo in pixel
					"maxlength":			""|Numerico					#	Lunghezza massima del testo
					"validator":			VALIDATORE					#	VEDERE SCHEDA VALIDATORE
				}
```

## DATEPICKER
```
"className":"org.joget.apps.form.lib.DatePicker"
	"properties":
				{							VALORI						#	INDICAZIONI
					"label":				Stringa						#	Etichetta del campo per l'interfaccia grafica
					"id":					Stringa senza spazi			#	Nome della colonna del database
					"workflowVariable":		Stringa senza spazi			#	Nome della variabile del workflow mappata
					"value":				Data nel formato javascript	#	Valore di default del campo
					"readonly": 			""|"true"	 				#	Flag sola lettura (true) oppure inseribile ("")
					"readonlyLabel":		""|"true"	 				#	Flag per visualizzazione come etichetta se in sola lettura
					"yearRange":			""|"c-10:c+10"				#	Valore minimo massimo visualizzati nel picker
					"dataFormat":			"yyyy-MM-dd"				#	Formato data per il DB (java format)
					"format":				"dd/mm/yy"					#	Formato data per la visualizzazione (jquery format)
					"currentDateAs":		""|"minDate"|"maxDate"		#	Definire se la data di oggi è un limite minimo/massimo di valori accettati
					"startDateFieldId":		""							#	Opzione utilizzata con "currentDateAs"
					"endDateFieldId":		""							#	Opzione utilizzata con "currentDateAs"
					"allowManual":			""|"true"					#	Definisce se è possibile scrivere le date a mano anziché tramite calendario
					"validator":			VALIDATORE					#	VEDERE SCHEDA VALIDATORE
				}
```
## RADIO-BUTTON
	"className":"org.joget.apps.form.lib.Radio"
	"properties":
				{							VALORI						#	INDICAZIONI
					"label":				Stringa						#	Etichetta del campo per l'interfaccia grafica
					"id":					Stringa senza spazi			#	Nome della colonna del database
					"workflowVariable":		Stringa senza spazi			#	Nome della variabile del workflow mappata
					"value":				Stringa						#	Valore di default del campo (separare più valori con ;)
					"readonly": 			""|"true"	 				#	Flag sola lettura (true) oppure inseribile ("")
					"readonlyLabel":		""|"true"	 				#	Flag per visualizzazione come etichetta se in sola lettura
					"validator":			VALIDATORE					#	VEDERE SCHEDA VALIDATORE
					"optionBinder":			{"className":"",			#	Non utilizzato, impostare questi parametri
											"properties":{}}
					"controlField":			""							#	Non utilizzato, lasciare vuoto
					"options":				[
												{
													"label":Stringa
													"value":Stringa
													"grouping":""
												}, ...
											]
				}
```
## SELECT-BOX

```
    "className":"org.joget.apps.form.lib.SelectBox"
	"properties":
				{							VALORI						#	INDICAZIONI
					"label":				Stringa						#	Etichetta del campo per l'interfaccia grafica
					"id":					Stringa senza spazi			#	Nome della colonna del database
					"workflowVariable":		Stringa senza spazi			#	Nome della variabile del workflow mappata
					"value":				Stringa						#	Valore di default del campo (separare più valori con ;)
					"readonly": 			""|"true"	 				#	Flag sola lettura (true) oppure inseribile ("")
					"readonlyLabel":		""|"true"	 				#	Flag per visualizzazione come etichetta se in sola lettura
					"multiple":				""|"true"					#	Selectbox a elenco con più scelte
					"size":					""|Numerico					#	Lunghezza del campo in pixel
					"validator":			VALIDATORE					#	VEDERE SCHEDA VALIDATORE
					"optionBinder":			{"className":"",			#	Non utilizzato, impostare questi parametri
											"properties":{}}
					"controlField":			""							#	Non utilizzato, lasciare vuoto
					"options":				[
												{
													"label":Stringa
													"value":Stringa
													"grouping":""
												}, ...
											]
				}
```

## ALFRESCO REPO BUTTON (DevPGS plugin),
da attivare nel caso in cui ci siano documenti collegati alla pratica
```
	"className":"org.joget.alfresco.AlfrescoRepoButton"
	"properties":
				{							VALORI						#	INDICAZIONI
					"processId":			"#assignment.processId#"	#	Prende il processId della pratica 	(lasciare valore default)
					"id":					"documento"					#	Identificativo						(lasciare valore default)
					"label":				Stringa						#	Etichetta del campo per l'interfaccia grafica
				}
```