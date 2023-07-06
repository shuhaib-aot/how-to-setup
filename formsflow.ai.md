# formsflow.ai Development Environment Setup

## Cloning Repositories
- Clone the formsflow.ai repository.
- Clone the formsflow.ai micro-frontend repository.

## Setting up formsflow.ai with Local Development

### formsflow.ai keycloak
1. Go to the formsflow.ai repository.
2. Navigate to `formsflow.ai/formsflow-id/keycloak` directory.
3. Run the command: `docker-compose up -d`.

### Full Docker Deployment in Local
1. Navigate to the `formsflow/docker/deployment` directory.
2. Create a `.env` file or replace `sample.env` with `.env`.
3. If you create a new `.env` file, copy the contents from `sample.env` to `.env`.
4. Replace `{your-ip}` with your IP address in the `.env` file.
5. Uncomment the `NODE_ENV` line and change its value to "development".

### Setting up formsflow.ai with Local formsflow-web or Micro-front-end URLs
1. Go to the micro-front-end repository.
2. Deploy each service through Docker containers or by running `docker` or `npm start` for the desired service.
3. Take note of the URL for the particular service.
4. Go to the `formslow/deployment/docker` directory in the formsflow.ai repository.
5. Locate the environment variables (`env`) file.
6. Update the following variables with the URL of the micro-front-end:
   - `MF_FORMSFLOW_NAV_URL`
   - `MF_FORMSFLOW_SERVICE_URL`
   - `MF_FORMSFLOW_ADMIN_URL`
   - `MF_FORMSFLOW_THEME_URL`
   
   You can provide the local URL as follows:
```
MF_FORMSFLOW_WEB_URL=//localhost:3004/single-spa-build.js
MF_FORMSFLOW_NAV_URL=//{your-ip-address}:3005/forms-flow-nav.js
MF_FORMSFLOW_ADMIN_URL=//{your-ip-address}:3006/forms-flow-admin.js
MF_FORMSFLOW_SERVICE_URL=//{your-ip-address}:3007/forms-flow-service.js
MF_FORMSFLOW_THEME_URL=//{your-ip-address}:3008/forms-flow-theme.js
```

Alternatively, you can provide one URL and use the others from a CDN.

### Setting up formsflow.ai with Local formsflow-root-config
1. Deploy all services locally except for the root config.
2. Go to the `formsflow-web-root-config` folder.
3. Run `npm i` to install dependencies.
4. Open the `public/config` file.
5. Replace the values with your URLs in the following section:
```json
{
    "NODE_ENV": "development",
    "REACT_APP_API_SERVER_URL": "http://192.168.0.101:3001",
    "REACT_APP_API_PROJECT_URL": "http://192.168.0.101:3001",
    "REACT_APP_KEYCLOAK_CLIENT": "forms-flow-web",
    "REACT_APP_KEYCLOAK_URL_REALM": "forms-flow-ai",
    "REACT_APP_KEYCLOAK_URL": "http://192.168.0.101:8080",
    "REACT_APP_WEB_BASE_URL": "http://192.168.0.101:5000",
    "REACT_APP_BPM_URL": "http://192.168.0.101:8000/camunda",
    "REACT_APP_WEBSOCKET_ENCRYPT_KEY": "giert989jkwrgb@DR55",
    "REACT_APP_APPLICATION_NAME": "formsflow.ai",
    "REACT_APP_WEB_BASE_CUSTOM_URL": "",
    "REACT_APP_CUSTOM_SUBMISSION_URL": "http://192.168.0.101:{port}",
    "REACT_APP_CUSTOM_SUBMISSION_ENABLED": "false",
    "REACT_APP_ENABLE_APPLICATION_ACCESS_PERMISSION_CHECK": "false",
    "REACT_APP_MULTI_TENANCY_ENABLED": "false",
    "REACT_APP_DRAFT_ENABLED": "false",
    "REACT_APP_DRAFT_POLLING_RATE": "15000",
    "REACT_APP_EXPORT_PDF_ENABLED": "false",
    "REACT_APP_PUBLIC_WORKFLOW_ENABLED": "false",
    "REACT_APP_DOCUMENT_SERVICE_URL": "",
    "REACT_APP_CUSTOM_THEME_URL": "",
    "REACT_APP_MT_ADMIN_BASE_URL": "",
    "REACT_APP_KEYCLOAK_ENABLE_CLIENT_AUTH": "false",
    "REACT_APP_ENABLE_FORMS_MODULE": "true",
    "REACT_APP_ENABLE_TASKS_MODULE": "true",
    "REACT_APP_ENABLE_DASHBOARDS_MODULE": "true",
    "REACT_APP_ENABLE_PROCESSES_MODULE": "true",
    "REACT_APP_ENABLE_APPLICATIONS_MODULE": "true"
}
```

6. Create a .env file or replace sample.env with .env in the formsflow-web-root-config folder.
7. Set the URLs in the .env file based on your environment:
8. Alternatively, you can use the default CDN values.
```
MF_FORMSFLOW_WEB_URL=//localhost:3004/single-spa-build.js
MF_FORMSFLOW_NAV_URL=//{your-ip-address}:3005/forms-flow-nav.js
MF_FORMSFLOW_ADMIN_URL=//{your-ip-address}:3006/forms-flow-admin.js
MF_FORMSFLOW_SERVICE_URL=//{your-ip-address}:3007/forms-flow-service.js
MF_FORMSFLOW_THEME_URL=//{your-ip-address}:3008/forms-flow-theme.js
```


10.Run ``` npm start.```

  
You can copy and paste the above content into a Markdown file to document the steps required to set up the development environment for formsflow.ai.



