# cumplidos_root_mf

Root Single-SPA para el microfrontend de cumplidos de contratistas (Universidad Distrital).
Orquesta `@udistrital/cumplidos-mf` y delega autenticación, layout y menú al Core del shell.

## Especificaciones Técnicas

### Tecnologías Implementadas y Versiones

- [Single-SPA](https://single-spa.js.org/) 6.0
- [TypeScript](https://www.typescriptlang.org/) 5.6
- [Webpack](https://webpack.js.org/) 5.94
- [Node](https://nodejs.org/es/) 22.x

### Variables de Entorno

```bash
export const environment = {
    production: [Booleano que indica si está habilitado],
    entorno: [Entorno de ejecucion],
    autenticacion: [Booleano que indica si está habilitada],
    notificaciones: [Booleano que indica si están habilitadas],
    menuApps: [Booleano que indica si está habilitado],
    appname: [Nombre del sistema para los estilos],
    appMenu: [Nombre del sistema para los estilos],
    TOKEN: {
      AUTORIZATION_URL: [URL de Autorización - login],
      CLIENTE_ID: [Token de acceso],
      RESPONSE_TYPE: [Tipo de Respuesta del token],
      SCOPE: [Alcance de la solicitud],
      REDIRECT_URL: [URL de redirección],
      SIGN_OUT_URL: [URL de Cerrar Sesión - logout],
      SIGN_OUT_REDIRECT_URL: [URL de redirección despues de cerrar sesion],
      AUTENTICACION_MID: [URL de API MID Autenticación],
    },
    parcels: {
      "@udistrital/cumplidos-root-config": [URL del bundle del root-config],
      "@udistrital/core-mf": [URL del microfrontend core],
      "@udistrital/cumplidos-mf": [URL del microfrontend de cumplidos],
    },
};
```

### Ejecución del Proyecto

1. Clonar el repositorio:
   ```shell
   git clone https://github.com/udistrital/cumplidos_root_mf.git
   ```
2. Acceder al directorio:
   ```bash
   cd cumplidos_root_mf
   ```
3. Instalar las dependencias:
   ```bash
   npm install
   ```
4. Iniciar el Root:
   ```bash
   npm start
   ```

El Root expone el microfrontend en `http://localhost:4200`.
Para registrar `cumplidos_mf` en desarrollo, usar import-map-override:
`@udistrital/cumplidos-mf → http://localhost:4210/main.js`

### Ejecución Dockerfile

```shell
# Does not apply
```

### Ejecución docker-compose

```shell
# Does not apply
```

### Ejecución Pruebas

```shell
npm test
```

## Estado CI

Pipeline Drone (`cumplidos_root_ci`) configurado en `.drone.yml`:

- Ramas `develop`, `feature/*`, `release/*` → análisis SonarQube
- Rama `release/*` → build de pruebas + despliegue S3 (`cliente-pruebas`)
- Rama `master` → build de producción + despliegue S3 (`cliente-prod`)

## Licencia

This file is part of cumplidos_root_mf.

cumplidos_root_mf is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.

cumplidos_root_mf is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details.

You should have received a copy of the GNU General Public License along with cumplidos_root_mf. If not, see https://www.gnu.org/licenses/.
