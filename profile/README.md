# Schema
  ```mermaid
flowchart LR;
    nginx(("Nginx"))
    gateway(("GateWay"))
    websocket((WebSocket))
    
    auth((Auth))
    organizer((Organizer))
    engine((Engine))
    webhook((WebHook))
    leonardo((Leonardo))
    client((Client))

    client-.HTTPS.->nginx
    client-.WSS.->nginx
    leonardo-.HTTPS.->nginx
    
    nginx-.HTTP...->gateway
    nginx-.WS.->websocket
    nginx-.HTTP.-> webhook

    gateway-.TCP.->auth
    gateway-.TCP.->organizer
    gateway-.TCP.->engine
    webhook-.TCP.->websocket
```
