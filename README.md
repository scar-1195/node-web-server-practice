# EXPRESS + Handlebars

## Servir contenido estatico
En la carpeta publica se sirve el sitio web

```
app.use(express.static('public'));
```

Si se quiere servir otro archivo se usa de esta manera

```
app.get('*', (req, res) => {
  res.sendFile(__dirname + '/public/404.html');
});
```

## handlebars
Sirve para renderizar vistas de html.

  1° Primero se crea la carpeta de views en la raiz del proyecto.

  2° Se crea un archivo que va a tener el contenido html con la extension `hbs`.

  3° Se manda a llamar de esta manera en las rutas.
  ```
  app.set('view engine', 'hbs');

  app.get('/', (req, res) => {
    res.render('home');
  });
```

### Mandar argumentos atraves de las rutas

```
app.get('/', (req, res) => {
  res.render('home', {
    name: 'Oscar',
    title: 'Curso de Node',
  });
});
```

y ya los mandamos a llamar asi 
```
<title>{{ title }}</title>
```