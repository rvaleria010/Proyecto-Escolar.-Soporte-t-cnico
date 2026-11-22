# Proyecto-Escolar.-Soporte-técnico

## Especificaciones de lo que se desea desarrollar:

Sistema web para registrar, clasificar, priorizar y dar seguimiento a incidencias de soporte técnico del DTIC para la facultad de ingeniería. Proyecto escolar.

•	Autenticación y roles: Login local para correos con terminación uaemex.mx. Roles con permisos (administrador, jefe de servicio, técnico, clasificador, auditor, solicitante). 

•	Alta de solicitudes: Formulario del solicitante y registro asistido del técnico por teléfono o presencial (portal).

•	Prioridad: Se calcula con la matriz urgencia x impacto (de la prioridad 1 a la 4).

•	Clasificación automática: Propone categoría, urgencia e impacto por palabras clave y Naive Bayes en Python puro. Con confianza menos a 0.75 la solicitud va a la cola de revisión humana y cada corrección se guarda como ejemplo.

•	Seguimiento: Bitácora, diagnóstico, iniciar, resolver y confirmar.

•	Avisos: Notificaciones dentro de la app. 

•	Administración y auditoria: Gestión de usuarios y bitácora de auditoría inmutable (triggers que bloquean cambios). 


## Como correrlo 
1.  Descargue sigpi-main1211.zip
2.  Descomprima el zip
3.	Ubíquese en la raíz del proyecto
4.	Corra en una máquina Linux 
  
        docker compose up --build -d
        
        docker compose exec backend alembic upgrade head
        
        docker compose exec backend python -m app.seeds all

5.	Ingrese, por ejemplo, con el usuario

        Administrador: "email": "amartinez@uaemex.mx", "password": "Prueba1234"
        
        Técnico: "email": "lhernandez@uaemex.mx", "password": " ClaveSegura#2026"
        
        Usuario normal: "email": "egarcia@uaemex.mx", "password": "ClaveSegura#2026"
