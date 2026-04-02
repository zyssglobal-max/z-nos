<div align="center">
  <img src="https://avatars.githubusercontent.com/u/269569607?v=4&size=64" alt="Z-NOS logo" width="100" height="100" /><br>
  
  <h1>Z-NOS / Nostr client</h1>
  <p><strong>Cliente Nostr de código abierto para el [protocolo Nostr](https://github.com/nostr-protocol/nostr). Z-NOS es un cliente web enfocado en la privacidad y la comunicación directa a través de mensajes privados cifrados.</strong></p>
  
  <p>
    Libre & de código abierto.<br/>
    Creado por <a href="https://github.com/zyssglobal-max/">ZYSS .CORP</a>, con un estilo moderno, diseño responsive con tema oscuro y animaciones.
  </p>
  
</div>

---

## ✨ Características

- **Mensajes Privados (NIP-04)** - Comunicación cifrada extremo a extremo
- **Gestión de Amigos** - Añade y organiza tus contactos Nostr
- **Múltiples Relays** - Conecta a varios relays simultáneamente
- **Búsqueda Global** - Busca mensajes y usuarios en toda la aplicación
- **Interfaz Moderna** - Diseño responsive con tema oscuro y animaciones
- **Persistencia Local** - Todos los datos se guardan localmente en tu sistema
- **Modo Pánico** - Borra todos tus datos locales con un solo clic

## 🧮 Vista previa

<img src="z-nos.png" alt="z-nos" width="100%"/>

## 📁 Estructura

```text
nos/
├── 🌐 feed      // feed social activo con (Perfil, Trending, likes)
├── 🌐 global    // canal global solo para tus amigos agregados
├── 🌐 help      // ayuda simple para los primeros pasos en z-nos
├── 🌐 index     // chat privado nuestra principal herramienta
├── 🌐 repo      // repositorios con las versiones z-nos desde github.com
└── 🌐 nos       // Red Nostr Promocional (repos) ...
```
├── `Nos promo`
<img src="promo.png" alt="z-nos" width="100%"/>

## 📦 Instalación

### Opción 1: Uso Directo (EXE)
1. Descarga los ficheros de la versión mas actual D' `Z-NOS`
2. Password del .rar 8905
2. Ábrelo en tu sistema windows (portable) ...
3. ¡Listo para usar!
4. [Probar Z-NOS](chat.html) V.HTML - (Proximamente)
5. [Nostr Track](nos.html) V.HTML
 . ├── script html demo pero funcional 100%
```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Z-NOS</title>
    <link rel="icon" href="https://avatars.githubusercontent.com/u/269569607?v=4&size=64" type="image/png">
    <style>
        html, body {
            background-color: #0e0e19ff;
            margin: 0;
            padding: 0;
            height: 100%;
            overflow: hidden;
            width: 100%;
            max-width: 100%;
            position: fixed;
        }
        :root {
            --primary: #ff2e62;
            --primary-dark: #d4003d;
            --primary-light: #ff6b9d;
            --dark: #0a0a15;
            --dark-secondary: #121220;
            --dark-tertiary: #1a1a2e;
            --light: #f8f9fa;
            --gray: #8a8aa3;
            --success: #00ff88;
            --warning: #ffcc00;
            --danger: #ff4444;
            --info: #00ccff;
            --premium: #ffd700;
            --vip: #9b51e0;
            --np: #8b5cf6;
        }
        * {
            margin: 0;
            padding: 10;
            box-sizing: border-box;
            max-width: 100%;
        }
        body {
            background: linear-gradient(135deg, var(--dark) 0%, var(--dark-secondary) 100%);
            color: var(--light);
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
            min-height: 100vh;
            width: 100%;
            overflow-x: hidden;
            position: relative;
        }
        .navbar-master {
            background: rgba(10, 10, 21, 0.95);
            backdrop-filter: blur(20px);
            border-bottom: 1px solid rgba(255, 46, 98, 0.2);
            height: 70px;
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            z-index: 1000;
            display: flex;
            align-items: center;
            padding: 0 20px;
            width: 100%;
            max-width: 100%;
            overflow-x: hidden;
        }
        .navbar-brand {
            font-weight: 800;
            font-size: 1.8rem;
            background: linear-gradient(45deg, var(--primary), var(--primary-light));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            text-decoration: none;
            display: flex;
            align-items: center;
            gap: 8px;
            white-space: nowrap;
        }
        .nav-search-container {
            position: relative;
            width: 400px;
            max-width: 100%;
            margin-left: auto;
            margin-right: 20px;
            min-width: 200px;
        }
        .nav-search {
            background: rgba(26, 26, 46, 0.8);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 25px;
            padding: 10px 20px;
            color: var(--light);
            width: 100%;
            transition: all 0.3s ease;
            padding-right: 50px;
        }
        .nav-search:focus {
            outline: none;
            border-color: var(--primary);
            box-shadow: 0 0 0 2px rgba(255, 46, 98, 0.2);
        }
        .nav-search-btn {
            position: absolute;
            right: 5px;
            top: 50%;
            transform: translateY(-50%);
            background: var(--primary);
            border: none;
            color: white;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            transition: all 0.3s ease;
            flex-shrink: 0;
        }
        .notification-badge {
            position: absolute;
            top: -5px;
            right: -5px;
            background: var(--primary);
            color: white;
            border-radius: 50%;
            width: 18px;
            height: 18px;
            font-size: 0.7rem;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        .main-container {
            display: grid;
            grid-template-columns: 280px minmax(0, 600px) 380px;
            gap: 0;
            height: calc(100vh - 70px);
            margin-top: 70px;
            justify-content: center;
            width: 100%;
            max-width: 100vw;
            overflow-x: hidden;
        }
        .sidebar-left {
            border-right: 1px solid rgba(255, 255, 255, 0.05);
            padding: 25px 15px;
            overflow-y: auto;
            overflow-x: hidden;
            width: 100%;
            max-width: 100%;
            scrollbar-width: none;
            -ms-overflow-style: none;
        }
        .sidebar-left::-webkit-scrollbar {
            display: none;
        }
        .user-card {
            text-align: center;
            padding: 25px 15px;
            background: linear-gradient(135deg, rgba(255, 46, 98, 0.1), rgba(26, 26, 46, 0.3));
            border-radius: 20px;
            margin-bottom: 25px;
            border: 1px solid rgba(255, 46, 98, 0.2);
            position: relative;
            overflow: hidden;
            width: 100%;
            max-width: 100%;
        }
        .user-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 3px;
            background: linear-gradient(90deg, var(--primary), var(--primary-light));
        }
        .user-avatar {
            width: 90px;
            height: 90px;
            border-radius: 50%;
            border: 3px solid var(--primary);
            margin: 0 auto 15px;
            display: flex;
            align-items: center;
            justify-content: center;
            background: var(--dark-secondary);
            transition: transform 0.3s ease;
            max-width: 100%;
        }
        .user-avatar:hover {
            transform: scale(1.05);
        }
        .user-avatar svg {
            width: 70px;
            height: 70px;
            stroke: var(--primary);
            max-width: 100%;
        }
        .badge-sec {
            background: rgba(16, 185, 129, 0.15);
            border: 1px solid rgba(16, 185, 129, 0.4);
            color: #10b981;
            padding: 7px 8px;
            border-radius: 20px;
            font-size: 0.8rem;
            display: inline-flex;
            align-items: center;
            gap: 5px;
            white-space: nowrap;
        }
        .nav-item {
            display: flex;
            align-items: center;
            margin: 5px 0;
            padding: 12px 15px;
            border-radius: 15px;
            color: var(--gray);
            text-decoration: none;
            transition: all 0.3s ease;
            width: 100%;
            max-width: 100%;
            overflow: hidden;
        }
        .nav-item:hover {
            background: rgba(255, 46, 98, 0.1);
            color: var(--light);
            transform: translateX(5px);
        }
        .nav-item.active {
            background: linear-gradient(90deg, rgba(255, 46, 98, 0.2), transparent);
            color: var(--primary);
            border-left: 3px solid var(--primary);
        }
        .nav-icon {
            width: 24px;
            text-align: center;
            margin-right: 15px;
            font-size: 1.2rem;
            flex-shrink: 0;
        }
        .feed-main {
            padding: 20px 15px;
            overflow-y: auto;
            overflow-x: hidden;
            width: 100%;
            max-width: 100%;
            scrollbar-width: none;
            -ms-overflow-style: none;
        }
        .feed-main::-webkit-scrollbar {
            display: none;
        }
        .hdr {
            padding: 0px;
            border-radius: 12px;
            margin-bottom: 20px;
            width: 100%;
            max-width: 100%;
            overflow: hidden;
        }
        .hdr h3 {
            color: var(--primary);
            margin: 0;
            display: flex;
            align-items: center;
            gap: 8px;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
        }
        #currentChatPubkey {
            font-size: 0.65rem; 
            color: var(--gray);
            max-width: 100%;
            overflow: hidden;
            white-space: nowrap;
            text-overflow: ellipsis;
            cursor: pointer;
            padding: 4px 8px;
            border-radius: 4px;
            transition: all 0.2s ease;
            display: inline-block;
            width: 100%;
            background: rgba(255, 46, 98, 0.05);
            border: 1px solid transparent;
        }
        #currentChatPubkey:hover {
            background: rgba(255, 46, 98, 0.15);
            border-color: var(--primary);
        }
        #currentChatPubkey:active {
            transform: scale(0.98);
        }
        .copy-tooltip {
            position: absolute;
            background: var(--primary);
            color: white;
            padding: 4px 8px;
            border-radius: 4px;
            font-size: 0.7rem;
            pointer-events: none;
            z-index: 10000;
            animation: fadeInOut 1s ease;
        }
        @keyframes fadeInOut {
            0% { opacity: 0; transform: translateY(10px); }
            20% { opacity: 1; transform: translateY(0); }
            80% { opacity: 1; transform: translateY(0); }
            100% { opacity: 0; transform: translateY(-10px); }
        }
        .messages-container {
            height: calc(100vh - 280px);
            overflow-y: auto;
            overflow-x: hidden;
            padding: 15px;
            border-radius: 12px;
            margin: 20px 0;
            width: 100%;
            max-width: 100%;
            scrollbar-width: none;
            -ms-overflow-style: none;
        }
        .messages-container::-webkit-scrollbar {
            display: none;
        }
        .message {
            display: flex;
            align-items: flex-start;
            gap: 10px;
            margin-bottom: 15px;
            max-width: 100%;
            width: 100%;
            position: relative;
        }
        .message.own {
            flex-direction: row-reverse;
        }
        .message-avatar {
            width: 35px;
            height: 35px;
            border-radius: 50%;
            background: var(--dark-tertiary);
            display: flex;
            align-items: center;
            justify-content: center;
            flex-shrink: 0;
        }
        .message-content {
            background: var(--dark-tertiary);
            padding: 10px 15px;
            border-radius: 18px;
            max-width: 70%;
            word-break: break-word;
            overflow-wrap: break-word;
            hyphens: auto;
            position: relative;
            padding-right: 35px;
        }
        .message.own .message-content {
            background: #ff2e621c;
        }
        .message-text {
            font-size: 0.9rem;
            line-height: 1.4;
            word-break: break-word;
            overflow-wrap: break-word;
        }
        .message-time {
            font-size: 0.65rem;
            color: var(--gray);
            margin-top: 4px;
            text-align: right;
        }
        .delete-message-btn {
            position: absolute;
            right: 5px;
            top: 5px;
            width: 24px;
            height: 24px;
            border-radius: 50%;
            background: rgba(255, 68, 68, 0.2);
            border: none;
            color: var(--danger);
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            opacity: 0;
            transition: all 0.3s ease;
            padding: 4px;
        }
        .message:hover .delete-message-btn {
            opacity: 1;
        }
        .delete-message-btn:hover {
            background: var(--danger);
            color: white;
            transform: scale(1.1);
        }
        .chat-input-wrapper {
            display: flex;
            gap: 10px;
            width: 100%;
            max-width: 100%;
        }
        .chat-input {
            flex: 1;
            background: var(--dark-tertiary);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 25px;
            padding: 12px 20px;
            color: var(--light);
            min-width: 0;
            width: 100%;
        }
        .chat-input:focus {
            outline: none;
            border-color: var(--primary);
        }
        .send-button {
            width: 45px;
            height: 45px;
            border-radius: 50%;
            background: var(--primary);
            border: none;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            transition: all 0.3s ease;
            flex-shrink: 0;
        }
        .send-button:hover {
            transform: scale(1.05);
            box-shadow: 0 5px 15px rgba(255, 46, 98, 0.3);
        }
        .sidebar-right {
            padding: 25px 20px;
            overflow-y: auto;
            overflow-x: hidden;
            border-left: 1px solid rgba(255, 255, 255, 0.05);
            width: 100%;
            max-width: 100%;
            scrollbar-width: none;
            -ms-overflow-style: none;
        }
        .sidebar-right::-webkit-scrollbar {
            display: none;
        }
        .section-title {
            font-size: 1rem;
            font-weight: 600;
            margin-bottom: 15px;
            color: var(--light);
            display: flex;
            align-items: center;
            justify-content: space-between;
            width: 100%;
            max-width: 100%;
        }
        .see-all {
            color: var(--primary);
            font-size: 0.85rem;
            text-decoration: none;
            transition: all 0.3s ease;
            white-space: nowrap;
        }
        .see-all:hover {
            color: var(--primary-light);
        }
        .input-group {
            margin-bottom: 15px;
            width: 100%;
            max-width: 100%;
        }
        .input-group label {
            display: block;
            margin-bottom: 5px;
            color: var(--gray);
            font-size: 0.8rem;
        }
        .input-field {
            width: 100%;
            background: var(--dark-tertiary);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 10px;
            padding: 10px 12px;
            color: var(--light);
            transition: all 0.3s ease;
        }
        .input-field:focus {
            outline: none;
            border-color: var(--primary);
            box-shadow: 0 0 0 2px rgba(255, 46, 98, 0.2);
        }
        .btn-premium {
            background: linear-gradient(45deg, #ff2e6200, #ff6b9d2b);
            color: white;
            border: none;
            padding: 12px;
            border-radius: 12px;
            font-weight: 600;
            cursor: pointer;
            width: 100%;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
            margin-bottom: 10px;
            transition: all 0.3s ease;
            white-space: nowrap;
        }
        .btn-premium:hover {
            transform: scale(1.02);
            box-shadow: 0 5px 15px rgba(255, 46, 98, 0.3);
        }
        .btn-outline {
            background: transparent;
            border: 1px solid #ff444438;
            color: var(--primary);
            padding: 5px 15px;
            border-radius: 10px;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 5px;
            width: 100%;
            transition: all 0.3s ease;
            white-space: nowrap;
        }
        .btn-outline:hover {
            background: rgba(255, 46, 98, 0.1);
            transform: scale(1.02);
        }
        .btn-danger {
            background: transparent;
            border: 1px solid #ff444438;
            color: #ff444478;
            padding: 5px 15px;
            border-radius: 10px;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 5px;
            width: 100%;
            transition: all 0.3s ease;
            white-space: nowrap;
            margin-top: 10px;
        }
        .btn-danger:hover {
            background: rgba(255, 68, 68, 0.1);
            transform: scale(1.02);
        }
        .relay-item {
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 12px;
            background: rgba(255, 255, 255, 0.03);
            border-radius: 12px;
            margin-bottom: 8px;
            font-size: 0.9rem;
            transition: all 0.3s ease;
            word-break: break-all;
            width: 100%;
            max-width: 100%;
            overflow: hidden;
            gap: 8px;
        }
        .relay-item:hover {
            background: rgba(255, 46, 98, 0.1);
            transform: translateX(5px);
        }
        .relay-item span:first-child {
            overflow: hidden;
            text-overflow: ellipsis;
            white-space: nowrap;
            flex: 1;
        }
        .relay-status {
            width: 10px;
            height: 10px;
            border-radius: 50%;
            background: var(--gray);
            flex-shrink: 0;
        }
        .relay-status.connected {
            background: var(--success);
            box-shadow: 0 0 10px var(--success);
        }
        .delete-relay-btn {
            background: transparent;
            border: none;
            color: var(--danger);
            cursor: pointer;
            padding: 4px;
            border-radius: 4px;
            display: flex;
            align-items: center;
            justify-content: center;
            opacity: 0.5;
            transition: all 0.3s ease;
            flex-shrink: 0;
        }
        .delete-relay-btn:hover {
            opacity: 1;
            background: rgba(255, 68, 68, 0.2);
            transform: scale(1.1);
        }
        .friend-item {
            display: flex;
            align-items: center;
            padding: 5px;
            background: rgba(255, 255, 255, 0.03);
            border-radius: 12px;
            margin-bottom: 8px;
            cursor: pointer;
            transition: all 0.3s ease;
            max-width: 100%;
            width: 100%;
            overflow: hidden;
        }
        .friend-item:hover {
            background: rgba(255, 46, 98, 0.1);
            transform: translateX(5px);
        }
        .friend-item.selected {
            background: rgba(255, 46, 98, 0.2);
            border-left: 3px solid var(--primary);
        }
        .friend-avatar {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background: var(--dark-tertiary);
            margin-right: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            flex-shrink: 0;
        }
        .friend-info {
            flex: 1;
            min-width: 0;
            overflow: hidden;
        }
        .friend-name {
            font-weight: 600;
            font-size: 0.95rem;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
        }
        .friend-pubkey {
            color: var(--gray);
            font-size: 0.8rem;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
        }
        .modal-custom {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.8);
            z-index: 9999;
            align-items: center;
            justify-content: center;
            padding: 20px;
            overflow-x: hidden;
        }
        .modal-content-custom {
            border-radius: 20px;
            padding: 30px;
            max-width: 450px;
            width: 90%;
            border: 1px solid var(--primary);
            animation: modalFadeIn 0.3s ease;
            max-height: 90vh;
            overflow-y: auto;
            overflow-x: hidden;
            scrollbar-width: none;
            -ms-overflow-style: none;
        }
        .modal-content-custom::-webkit-scrollbar {
            display: none;
        }
        @keyframes modalFadeIn {
            from {
                opacity: 0;
                transform: translateY(-30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        .modal-content-custom h3 {
            color: var(--primary);
            margin-bottom: 15px;
            font-size: 1.5rem;
        }
        .modal-icon {
            width: 60px;
            height: 60px;
            border-radius: 50%;
            background: rgba(255, 68, 68, 0.15);
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 20px;
        }
        .modal-icon svg {
            width: 30px;
            height: 30px;
            stroke: var(--danger);
        }
        .modal-message {
            color: var(--light);
            font-size: 1rem;
            margin-bottom: 10px;
            text-align: center;
        }
        .modal-details {
            padding: 10px;
            border-radius: 12px;
            margin: 15px 0;
            border-left: 4px solid var(--primary);
            font-size: 0.9rem;
            color: var(--primary-light);
            max-height: 100px;
        }
        .modal-warning {
            color: var(--warning);
            font-size: 0.85rem;
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            gap: 5px;
        }
        .modal-buttons {
            display: flex;
            gap: 10px;
            margin-top: 20px;
        }
        .modal-btn-cancel {
            flex: 1;
            background: transparent;
            border: 1px solid var(--gray);
            color: var(--gray);
            padding: 12px;
            border-radius: 12px;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        .modal-btn-cancel:hover {
            background: rgba(255, 255, 255, 0.05);
            border-color: var(--light);
            color: var(--light);
        }
        .modal-btn-confirm {
            flex: 1;
            background: var(--danger);
            border: none;
            color: white;
            padding: 12px;
            border-radius: 12px;
            cursor: pointer;
            transition: all 0.3s ease;
            font-weight: 600;
        }
        .modal-btn-confirm:hover {
            background: #ff6666;
            transform: scale(1.02);
            box-shadow: 0 5px 15px rgba(255, 68, 68, 0.4);
        }
        .badge-warn {
            background: rgba(245, 158, 11, 0.15);
            border: 1px solid rgba(245, 158, 11, 0.4);
            color: #f59e0b;
            padding: 4px 12px;
            border-radius: 20px;
            font-size: 0.8rem;
        }
        .key-box {
            background: rgba(0, 0, 0, 0.3);
            border: 1px solid rgba(255, 46, 98, 0.3);
            border-radius: 8px;
            padding: 10px 14px;
            font-family: monospace;
            font-size: 0.85rem;
            color: #ff2e62;
            word-break: break-all;
            margin-top: 5px;
        }
        .notification-success {
            position: fixed;
            top: 80px;
            right: 20px;
            background: linear-gradient(135deg, #00b09b, #96c93d);
            color: white;
            padding: 15px 20px;
            border-radius: 15px;
            z-index: 10000;
            display: flex;
            align-items: center;
            gap: 10px;
            animation: slideIn 0.3s ease;
            border-left: 5px solid rgba(255,255,255,0.5);
            backdrop-filter: blur(10px);
            min-width: 300px;
            max-width: 450px;
            box-shadow: 0 10px 40px rgba(0,0,0,0.3);
            word-break: break-word;
        }
        @keyframes slideIn {
            from { transform: translateX(100%); opacity: 0; }
            to { transform: translateX(0); opacity: 1; }
        }
        @media (max-width: 1400px) {
            .main-container {
                grid-template-columns: 250px minmax(0, 500px) 300px;
            }
        }
        @media (max-width: 1200px) {
            .main-container {
                grid-template-columns: 70px minmax(0, 500px) 250px;
            }
            .sidebar-left .friend-name,
            .sidebar-left .friend-pubkey {
                display: none;
            }
            .user-card h4,
            .user-pubkey,
            .user-card .btn-outline {
                display: none;
            }
            .user-avatar {
                width: 50px;
                height: 50px;
            }
            .user-avatar svg {
                width: 40px;
                height: 40px;
            }
        }
        @media (max-width: 992px) {
            .main-container {
                grid-template-columns: 1fr;
            }
            .sidebar-left,
            .sidebar-right {
                display: none;
            }
        }
        .svg-icon {
            width: 20px;
            height: 20px;
            stroke: currentColor;
            fill: none;
            max-width: 100%;
        }
        .text-muted {
            color: var(--gray) !important;
        }
        .mb-0 {
            margin-bottom: 0;
        }
        .mt-1 {
            margin-top: 4px;
        }
        .mt-2 {
            margin-top: 8px;
        }
        .mt-3 {
            margin-top: 12px;
        }
        .mb-2 {
            margin-bottom: 8px;
        }
        .mb-3 {
            margin-bottom: 12px;
        }
        .me-1 {
            margin-right: 4px;
        }
        .me-2 {
            margin-right: 8px;
        }
        .me-3 {
            margin-right: 12px;
        }
        .ms-auto {
            margin-left: auto;
        }
        .d-flex {
            display: flex;
        }
        .align-items-center {
            align-items: center;
        }
        .justify-content-between {
            justify-content: space-between;
        }
        .gap-2 {
            gap: 8px;
        }
        .gap-3 {
            gap: 12px;
        }
        .w-100 {
            width: 100%;
        }
        .position-relative {
            position: relative;
        }
        .search-result-item {
            padding: 10px;
            border-bottom: 1px solid rgba(255,255,255,0.1);
            cursor: pointer;
            transition: all 0.2s ease;
        }
        .search-result-item:hover {
            background: rgba(255,46,98,0.1);
        }
        .search-result-highlight {
            background-color: rgba(255,46,98,0.3);
            border-radius: 3px;
            padding: 2px;
        }
        .back-to-chat {
            display: inline-flex;
            align-items: center;
            gap: 5px;
            color: var(--primary);
            cursor: pointer;
            font-size: 0.8rem;
            margin-bottom: 10px;
        }
        .back-to-chat:hover {
            text-decoration: underline;
        }
        .z-logo-container {
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 40px 0;
            flex-direction: column;
            gap: 20px;
        }
        .animated-z {
            width: 120px;
            height: 120px;
            animation: zPulse 2s ease-in-out infinite;
        }
        .z-stroke-1, .z-stroke-2, .z-stroke-3 {
            stroke: var(--primary);
            stroke-width: 3;
            stroke-linecap: round;
            stroke-linejoin: round;
            fill: none;
            filter: drop-shadow(0 0 8px rgba(255, 46, 98, 0.5));
        }
        .z-stroke-1 {
            animation: drawZ1 3s ease-in-out infinite;
        }
        .z-stroke-2 {
            animation: drawZ2 3s ease-in-out infinite;
        }
        .z-stroke-3 {
            animation: drawZ3 3s ease-in-out infinite;
        }
        .z-glow {
            animation: glowPulse 2s ease-in-out infinite;
        }
        @keyframes drawZ1 {
            0%, 100% { stroke-dashoffset: 0; opacity: 1; }
            50% { stroke-dashoffset: 30; opacity: 0.7; }
        }
        @keyframes drawZ2 {
            0%, 100% { stroke-dashoffset: 0; opacity: 1; }
            50% { stroke-dashoffset: -30; opacity: 0.7; }
        }
        @keyframes drawZ3 {
            0%, 100% { stroke-dashoffset: 0; opacity: 1; }
            50% { stroke-dashoffset: 30; opacity: 0.7; }
        }
        @keyframes zPulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }
        @keyframes glowPulse {
            0%, 100% { filter: drop-shadow(0 0 8px rgba(255, 46, 98, 0.5)); }
            50% { filter: drop-shadow(0 0 20px rgba(255, 46, 98, 0.8)); }
        }
        .z-subtitle {
            color: var(--gray);
            font-size: 0.9rem;
            letter-spacing: 2px;
            animation: fadeInOut 3s ease-in-out infinite;
        }
        @keyframes fadeInOut {
            0%, 100% { opacity: 0.5; }
            50% { opacity: 1; }
        }
        @keyframes pulse {
            0%, 100% { opacity: 1; transform: scale(1); }
            50% { opacity: 0.7; transform: scale(1.1); }
        }
    </style>
    <script src="https://unpkg.com/nostr-tools@1.17.0/lib/nostr.bundle.js"></script>
</head>
<body>
    <nav class="navbar-master">
        <a class="navbar-brand" href="index.html">
            <svg width="32" height="32" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M6 6 L18 6 L6 18 L18 18" stroke="var(--primary)" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
                <circle cx="12" cy="12" r="8" stroke="var(--primary)" stroke-width="1" fill="none" stroke-dasharray="2 2"/>
            </svg>
            Z-NOS
        </a>
        <div class="nav-search-container">
            <input type="text" class="nav-search" placeholder="Buscar usuarios o mensajes..." id="globalSearch">
            <button class="nav-search-btn" onclick="performGlobalSearch()">
                <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor">
                    <circle cx="11" cy="11" r="8"/>
                    <line x1="21" y1="21" x2="16.65" y2="16.65"/>
                </svg>
            </button>
        </div>
        <div style="display: flex; gap: 20px; align-items: center;">
            <span class="badge-sec" id="connectionStatus">off</span>
            <div class="position-relative">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor">
                    <path d="M20 21v-2a4 4 0 0 0-4-4H8a4 4 0 0 0-4 4v2"/>
                    <circle cx="12" cy="7" r="4"/>
                </svg>
            </div>
        </div>
    </nav>
    <div class="main-container">
        <div class="sidebar-left">
            <div class="user-card">
                <div class="user-avatar">
                    <svg viewBox="0 0 24 24" fill="none" stroke="currentColor">
                        <path d="M20 21v-2a4 4 0 0 0-4-4H8a4 4 0 0 0-4 4v2"/>
                        <circle cx="12" cy="7" r="4"/>
                    </svg>
                </div>
                <h4 id="userNameDisplay">@Z-NOS</h4>
                <div class="user-pubkey" id="userPubkeyDisplay" style="font-size: 0.7rem; word-break: break-all; margin: 10px 0;">
                    No conectado
                </div>
                <button class="btn-outline" onclick="copyMyPubkey()">
                    <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor">
                        <rect x="9" y="9" width="13" height="13" rx="2" ry="2"/>
                        <path d="M5 15H4a2 2 0 0 1-2-2V4a2 2 0 0 1 2-2h9a2 2 0 0 1 2 2v1"/>
                    </svg>
                    Copiar mi npub
                </button>
            </div>
            <div class="section-title" style="margin-top: 20px;">
                <span>ᘏmigos</span>
                <button class="btn-outline" style="width: auto; padding: 5px 10px;" onclick="window.location.href='./help.html'">
                    <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" style="animation: pulse 1.5s ease-in-out infinite;">
                        <circle cx="12" cy="12" r="10"/>
                        <path d="M12 16v-4M12 8h.01"/>
                    </svg>
                </button>
                <button class="btn-outline" style="width: auto; padding: 5px 10px;" onclick="location.reload()">
                    <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor">
                        <path d="M23 4v6h-6M1 20v-6h6M3.51 9a9 9 0 0 1 14.85-3.36L23 10M1 14l4.64 4.36A9 9 0 0 0 20.49 15"/>
                    </svg>
                </button>
                <button class="btn-outline" style="width: auto; padding: 5px 10px;" onclick="showAddFriendModal()">
                    <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor">
                        <circle cx="12" cy="12" r="10"/>
                        <line x1="12" y1="8" x2="12" y2="16"/>
                        <line x1="8" y1="12" x2="16" y2="12"/>
                    </svg>
                </button>
                <button class="btn-outline" style="width: auto; padding: 5px 10px;" onclick="window.location.href='./global.html'">
                    <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor">
                        <circle cx="12" cy="12" r="10"></circle>
                        <line x1="2" y1="12" x2="22" y2="12"></line>
                        <path d="M12 2a15.3 15.3 0 0 1 4 10 15.3 15.3 0 0 1-4 10 15.3 15.3 0 0 1-4-10 15.3 15.3 0 0 1 4-10z"></path>
                    </svg>
                </button>
            </div>
            <div id="friendsList"></div>
        </div>
        <div class="feed-main">
            <div class="hdr">
                <div class="d-flex align-items-center justify-content-between">
                    <h3>
                        <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor">
                            <path d="M21 15a2 2 0 0 1-2 2H7l-4 4V5a2 2 0 0 1 2-2h14a2 2 0 0 1 2 2z"/>
                        </svg>
                        <span id="currentChatName">Selecciona un amigo</span>
                    </h3>
                    <span class="back-to-chat" id="backToChatBtn" style="display: none;" onclick="clearSearchResults()">← Volver al chat</span>
                </div>
                <p class="text-muted mb-0 mt-1" id="currentChatPubkey" onclick="copyCurrentChatPubkey()" title="Click para copiar la clave pública"></p>
            </div>
            <div class="messages-container" id="messagesContainer">
                <div class="z-logo-container">
                    <svg class="animated-z" viewBox="0 0 100 100">
                        <path class="z-stroke-1" d="M30 30 L70 30" stroke="var(--primary)" stroke-width="3"/>
                        <path class="z-stroke-2" d="M70 30 L30 70" stroke="var(--primary)" stroke-width="3"/>
                        <path class="z-stroke-3" d="M30 70 L70 70" stroke="var(--primary)" stroke-width="3"/>
                        <circle cx="50" cy="50" r="25" class="z-glow" stroke="var(--primary)" stroke-width="1" fill="none" stroke-dasharray="4 4"/>
                    </svg>
                    <div class="z-subtitle">✦ Z-NOS ✦</div>
                </div>
            </div>
            <div class="chat-input-wrapper">
                <input type="text" class="chat-input" id="messageInput" placeholder="Mensaje privado ..." disabled>
                <button class="send-button" id="sendButton" onclick="sendMessage()" disabled>
                    <svg viewBox="0 0 24 24" fill="none" stroke="white" width="20" height="20">
                        <line x1="22" y1="2" x2="11" y2="13"/>
                        <polygon points="22 2 15 22 11 13 2 9 22 2"/>
                    </svg>
                </button>
            </div>
        </div>
        <div class="sidebar-right">
            <div class="section-title">
                <span>Nostr .config ...</span>
                <a href="./feed.html" class="see-all">
                    <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor">
                        <circle cx="12" cy="12" r="3"/>
                        <path d="M19.4 15a1.65 1.65 0 0 0 .33-1.82 1.65 1.65 0 0 0-1.51-1H5.78a1.65 1.65 0 0 0-1.51 1 1.65 1.65 0 0 0 .33 1.82L12 22z"/>
                        <path d="M18 2A6 6 0 0 0 6 2c0 3.5 3 6 6 6s6-2.5 6-6z"/>
                    </svg>
                </a>
            </div>
            <div class="input-group">
                <label>Mi Clave Pública (npub)</label>
                <input type="text" class="input-field" id="myNpub" placeholder="npub1...">
            </div>
            <div class="input-group">
                <label>Mi Clave Privada (nsec)</label>
                <input type="password" class="input-field" id="myNsec" placeholder="nsec1...">
            </div>
            <button class="btn-premium" onclick="connectNostr()">
                <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor">
                    <circle cx="12" cy="12" r="10"/>
                    <line x1="12" y1="8" x2="12" y2="16"/>
                    <line x1="8" y1="12" x2="16" y2="12"/>
                </svg>
                Conectar a Nostr
            </button>
            <button class="btn-outline" style="margin-top: 10px;" onclick="generateKeys()">
                <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor">
                    <path d="M23 4v6h-6M1 20v-6h6M3.51 9a9 9 0 0 1 14.85-3.36L23 10M1 14l4.64 4.36A9 9 0 0 0 20.49 15"/>
                </svg>
                Generar Nuevas Claves
            </button>
            <div class="section-title" style="margin-top: 20px;">
                <span>₹elays</span>
                <button class="btn-outline" style="width: auto; padding: 5px 10px;" onclick="showRelayModal()">
                    <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor">
                        <circle cx="12" cy="12" r="10"/>
                        <line x1="12" y1="8" x2="12" y2="16"/>
                        <line x1="8" y1="12" x2="16" y2="12"/>
                    </svg>
                </button>
            </div>
            <div id="relaysList"></div>
            <button class="btn-danger" onclick="showDeleteAllMessagesModal()">
                <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor">
                    <polyline points="3 6 5 6 21 6"></polyline>
                    <path d="M19 6v14a2 2 0 0 1-2 2H7a2 2 0 0 1-2-2V6m3 0V4a2 2 0 0 1 2-2h4a2 2 0 0 1 2 2v2"/>
                    <line x1="10" y1="11" x2="10" y2="17"/>
                    <line x1="14" y1="11" x2="14" y2="17"/>
                </svg>
                Borrar todos los mensajes
            </button>
            <button class="btn-outline" style="margin-top: 10px; border-color: #ff444438; color: #ff444478;" onclick="panicButton()">
                <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor">
                    <circle cx="12" cy="12" r="10"/>
                    <line x1="12" y1="8" x2="12" y2="12"/>
                    <line x1="12" y1="16" x2="12.01" y2="16"/>
                </svg>
                🧨 Pánico - borrar todo !!!
            </button>
            <br>
            <div class="input-group">
                <label>✦ Z-NOS ✦ CHAT (zySs.corp) by Nostr ✦ ...</label>
                <label>✦ eMAIL. ✦ zyss.global@gmail.com</label>
                <label>✦ vREV0. ✦ 1.8.0.0</label>
            </div>
        </div>
    </div>
    <div class="modal-custom" id="addFriendModal">
        <div class="modal-content-custom">
            <h3><svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor">
                        <circle cx="12" cy="12" r="10"></circle>
                        <line x1="12" y1="8" x2="12" y2="16"></line>
                        <line x1="8" y1="12" x2="16" y2="12"></line>
                </svg> agregar amigo</h3>
            <div class="input-group">
                <label>Nombre</label>
                <input type="text" class="input-field" id="friendName" placeholder="Ej: Alice">
            </div>
            <div class="input-group">
                <label>Clave Pública (npub)</label>
                <input type="text" class="input-field" id="friendPubkey" placeholder="npub1..." required>
            </div>
            <div style="display: flex; gap: 10px;">
                <button class="btn-premium" style="flex: 1;" onclick="addFriend()">Agregar</button>
            </div>
        </div>
    </div>
    <div class="modal-custom" id="deleteFriendModal">
        <div class="modal-content-custom">
            <h3 style="color: var(--danger);">Eliminar Amigo</h3>
            <p>¿Estás seguro de eliminar a <span id="deleteFriendName"></span>?</p>
            <p style="font-size: 0.8rem; color: var(--gray);" id="deleteFriendPubkey"></p><br>
            <div style="display: flex; gap: 10px;">
                <button class="btn-outline" style="flex: 1;" onclick="closeDeleteFriendModal()">Cancelar</button>
                <button class="btn-premium" style="flex: 1; background: var(--danger);" onclick="confirmDeleteFriend()">Eliminar</button>
            </div>
        </div>
    </div>
    <div class="modal-custom" id="relayModal">
        <div class="modal-content-custom">
            <h3><svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                <circle cx="12" cy="12" r="10"></circle>
                <path d="M7 12L10 12"></path>
                <path d="M14 12L17 12"></path>
                <circle cx="12" cy="12" r="2" fill="currentColor"></circle>
            </svg> nuevo relay</h3>
            <input type="text" class="input-field" id="newRelay" placeholder="wss://relay.ejemplo.com" style="margin-bottom: 20px;">
            <div style="display: flex; gap: 10px;">
                <button class="btn-premium" style="flex: 1;" onclick="addRelay()">Añadir</button>
            </div>
        </div>
    </div>
    <div class="modal-custom" id="deleteRelayModal">
        <div class="modal-content-custom">
            <div class="modal-icon">
                <svg viewBox="0 0 24 24" fill="none" stroke="currentColor">
                    <circle cx="12" cy="12" r="10"/>
                    <line x1="12" y1="8" x2="12" y2="12"/>
                    <line x1="12" y1="16" x2="12.01" y2="16"/>
                </svg>
            </div>
            <h3 style="color: var(--danger); text-align: center;">Eliminar Relay</h3>
            <p class="modal-message">¿Estás seguro de eliminar este relay?</p>
            <div class="modal-details" id="deleteRelayUrl"></div>
            <div class="modal-warning">
                <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor">
                    <circle cx="12" cy="12" r="10"/>
                    <line x1="12" y1="8" x2="12" y2="12"/>
                    <line x1="12" y1="16" x2="12.01" y2="16"/>
                </svg>
                Esta acción no se puede deshacer
            </div>
            <div class="modal-buttons">
                <button class="modal-btn-cancel" onclick="closeDeleteRelayModal()">Cancelar</button>
                <button class="modal-btn-confirm" onclick="confirmDeleteRelay()">Eliminar</button>
            </div>
        </div>
    </div>
    <div class="modal-custom" id="deleteMessageModal">
        <div class="modal-content-custom">
            <div class="modal-icon">
                <svg viewBox="0 0 24 24" fill="none" stroke="currentColor">
                    <polyline points="3 6 5 6 21 6"></polyline>
                    <path d="M19 6v14a2 2 0 0 1-2 2H7a2 2 0 0 1-2-2V6m3 0V4a2 2 0 0 1 2-2h4a2 2 0 0 1 2 2v2"/>
                </svg>
            </div>
            <h3 style="color: var(--danger); text-align: center;">Eliminar Mensaje</h3>
            <p class="modal-message">¿Estás seguro de eliminar este mensaje?</p>
            <div class="modal-details" id="deleteMessageContent"></div>
            <div class="modal-warning">
                <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor">
                    <circle cx="12" cy="12" r="10"/>
                    <line x1="12" y1="8" x2="12" y2="12"/>
                    <line x1="12" y1="16" x2="12.01" y2="16"/>
                </svg>
                Esta acción no se puede deshacer
            </div>
            <div class="modal-buttons">
                <button class="modal-btn-cancel" onclick="closeDeleteMessageModal()">Cancelar</button>
                <button class="modal-btn-confirm" onclick="confirmDeleteMessage()">Eliminar</button>
            </div>
        </div>
    </div>
    <div class="modal-custom" id="deleteAllMessagesModal">
        <div class="modal-content-custom">
            <div class="modal-icon">
                <svg viewBox="0 0 24 24" fill="none" stroke="currentColor">
                    <polyline points="3 6 5 6 21 6"></polyline>
                    <path d="M19 6v14a2 2 0 0 1-2 2H7a2 2 0 0 1-2-2V6m3 0V4a2 2 0 0 1 2-2h4a2 2 0 0 1 2 2v2"/>
                    <line x1="10" y1="11" x2="10" y2="17"/>
                    <line x1="14" y1="11" x2="14" y2="17"/>
                </svg>
            </div>
            <h3 style="color: var(--danger); text-align: center;">Borrar todos los mensajes</h3>
            <p class="modal-message">¿Estás seguro?</p>
            <div class="modal-details">
                Se eliminarán permanentemente todos los mensajes de todos los chats
            </div>
            <div class="modal-warning">
                <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor">
                    <circle cx="12" cy="12" r="10"/>
                    <line x1="12" y1="8" x2="12" y2="12"/>
                    <line x1="12" y1="16" x2="12.01" y2="16"/>
                </svg>
                Esta acción no se puede deshacer ! ...
            </div>
            <div class="modal-buttons">
                <button class="modal-btn-cancel" onclick="closeDeleteAllMessagesModal()">Cancelar</button>
                <button class="modal-btn-confirm" onclick="confirmDeleteAllMessages()">Borrar Todo</button>
            </div>
        </div>
    </div>
    <div class="modal-custom" id="searchResultsModal">
        <div class="modal-content-custom" style="max-width: 500px;">
            <h3>Resultados de Búsqueda</h3>
            <div id="searchResultsList" style="max-height: 400px; overflow-y: auto;"></div>
            <button class="btn-outline" style="margin-top: 15px;" onclick="closeSearchModal()">Cerrar</button>
        </div>
    </div>
    <div class="modal-custom" id="panicModal">
        <div class="modal-content-custom">
            <div class="modal-icon">
                <svg viewBox="0 0 24 24" fill="none" stroke="currentColor">
                    <circle cx="12" cy="12" r="10"/>
                    <line x1="12" y1="8" x2="12" y2="12"/>
                    <line x1="12" y1="16" x2="12.01" y2="16"/>
                </svg>
            </div>
            <h3 style="color: var(--danger); text-align: center;">⚠️ ¡PELIGRO! ⚠️</h3>
            <p class="modal-message">Esto ELIMINARÁ TODOS tus datos:</p>
            <div class="modal-details">
                <ul style="color: var(--gray); margin-bottom: 20px; text-align: left;">
                    <li>Amigos guardados</li>
                    <li>Mensajes almacenados</li>
                    <li>Claves guardadas</li>
                    <li>Relays personalizados</li>
                </ul>
            </div>
            <div class="modal-warning">
                <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor">
                    <circle cx="12" cy="12" r="10"/>
                    <line x1="12" y1="8" x2="12" y2="12"/>
                    <line x1="12" y1="16" x2="12.01" y2="16"/>
                </svg>
                Esta acción no se puede deshacer
            </div>
            <div class="modal-buttons">
                <button class="modal-btn-cancel" onclick="closePanicModal()">Cancelar</button>
                <button class="modal-btn-confirm" onclick="confirmPanic()">SÍ, BORRAR TODO</button>
            </div>
        </div>
    </div>
    <div id="notification" style="display: none;"></div>
    <script>
        let appState = {
            myNpub: localStorage.getItem('myNpub') || '',
            myNsec: localStorage.getItem('myNsec') || '',
            myPubkeyHex: localStorage.getItem('myPubkeyHex') || '',
            myPrivkeyHex: localStorage.getItem('myPrivkeyHex') || '',
            friends: JSON.parse(localStorage.getItem('friends') || '[]'),
            relays: JSON.parse(localStorage.getItem('relays') || '["wss://relay.damus.io","wss://nos.lol","wss://relay.nostr.band"]'),
            messages: JSON.parse(localStorage.getItem('messages') || '{}'),
            selectedFriend: null,
            connected: false,
            relayConnections: [],
            processedEventIds: new Set(),
            searchResults: [], 
            searchActive: false, 
            friendToDelete: null,
            messageToDelete: null,
            relayToDelete: null
        };
        const savedIds = localStorage.getItem('processedEventIds');
        if (savedIds) {
            try {
                appState.processedEventIds = new Set(JSON.parse(savedIds));
            } catch (e) {
                appState.processedEventIds = new Set();
            }
        }
        function performGlobalSearch() {
            const searchInput = document.querySelector('.nav-search');
            const query = searchInput.value.trim();
            if (!query) {
                showNotification('Buscador', 'Ingresa un término para buscar');
                return;
            }
            if (query.startsWith('npub1')) {
                searchUserByPubkey(query);
            } else {
                searchInMessages(query);
            }
        }
        function searchUserByPubkey(npub) {
            const existingFriend = appState.friends.find(f => f.pubkey === npub);
            if (existingFriend) {
                appState.searchResults = [{
                    type: 'friend',
                    name: existingFriend.name,
                    pubkey: existingFriend.pubkey,
                    message: 'Amigo existente'
                }];
            } else {
                try {
                    const hex = bech32ToHex(npub);
                    if (hex) {
                        appState.searchResults = [{
                            type: 'potential',
                            name: 'Usuario Nostr',
                            pubkey: npub,
                            message: 'Usuario encontrado - Haz clic para agregar'
                        }];
                    }
                } catch (e) {
                    appState.searchResults = [];
                }
            }
            showSearchResults();
        }
        function searchInMessages(query) {
            const results = [];
            const searchTerm = query.toLowerCase();
            Object.entries(appState.messages).forEach(([chatId, messages]) => {
                const participants = chatId.split('_');
                const otherParticipant = participants.find(p => p !== appState.myPubkeyHex);
                let friendName = 'Desconocido';
                let friendPubkey = '';
                for (const friend of appState.friends) {
                    const friendHex = bech32ToHex(friend.pubkey);
                    if (friendHex === otherParticipant) {
                        friendName = friend.name;
                        friendPubkey = friend.pubkey;
                        break;
                    }
                }
                messages.forEach(msg => {
                    if (msg.content.toLowerCase().includes(searchTerm)) {
                        results.push({
                            type: 'message',
                            chatId: chatId,
                            friendName: friendName,
                            friendPubkey: friendPubkey,
                            content: msg.content,
                            time: msg.time,
                            sender: msg.sender === appState.myPubkeyHex ? 'Yo' : friendName
                        });
                    }
                });
            });
            appState.searchResults = results;
            showSearchResults();
        }
        function showSearchResults() {
            const modal = document.getElementById('searchResultsModal');
            const resultsList = document.getElementById('searchResultsList');
            if (appState.searchResults.length === 0) {
                resultsList.innerHTML = '<div style="text-align: center; color: var(--gray); padding: 20px;">No se encontraron resultados</div>';
            } else {
                resultsList.innerHTML = appState.searchResults.map(result => {
                    if (result.type === 'friend' || result.type === 'potential') {
                        return `
                            <div class="search-result-item" onclick="selectUserFromSearch('${result.pubkey}', '${result.name}')">
                                <div style="font-weight: 600;">${result.name}</div>
                                <div style="font-size: 0.8rem; color: var(--gray);">${result.pubkey.substring(0, 30)}...</div>
                                <div style="font-size: 0.75rem; color: var(--primary);">${result.message}</div>
                            </div>
                        `;
                    } else if (result.type === 'message') {
                        return `
                            <div class="search-result-item" onclick="selectMessageFromSearch('${result.friendPubkey}', '${result.content.replace(/'/g, "\\'")}')">
                                <div style="font-weight: 600;">${result.friendName}</div>
                                <div style="font-size: 0.85rem; margin: 5px 0;">
                                    <span class="search-result-highlight">${result.content}</span>
                                </div>
                                <div style="display: flex; justify-content: space-between; font-size: 0.7rem; color: var(--gray);">
                                    <span>${result.sender}</span>
                                    <span>${result.time}</span>
                                </div>
                            </div>
                        `;
                    }
                }).join('');
            }
            modal.style.display = 'flex';
        }
        function selectUserFromSearch(pubkey, name) {
            closeSearchModal();
            const existingFriend = appState.friends.find(f => f.pubkey === pubkey);
            if (existingFriend) {
                selectFriend(pubkey);
            } else {
                if (confirm(`¿Quieres agregar a ${name} como amigo?`)) {
                    document.getElementById('friendPubkey').value = pubkey;
                    document.getElementById('friendName').value = name;
                    showAddFriendModal();
                }
            }
        }
        function selectMessageFromSearch(friendPubkey, content) {
            closeSearchModal();
            selectFriend(friendPubkey);
            setTimeout(() => {
                const messages = document.querySelectorAll('.message-text');
                messages.forEach(msg => {
                    if (msg.textContent.includes(content)) {
                        msg.style.backgroundColor = 'rgba(255,46,98,0.3)';
                        msg.style.padding = '2px';
                        msg.style.borderRadius = '3px';
                        msg.scrollIntoView({ behavior: 'smooth', block: 'center' });
                        setTimeout(() => {
                            msg.style.backgroundColor = '';
                            msg.style.padding = '';
                            msg.style.borderRadius = '';
                        }, 3000);
                    }
                });
            }, 500);
        }
        function closeSearchModal() {
            document.getElementById('searchResultsModal').style.display = 'none';
        }
        function clearSearchResults() {
            appState.searchActive = false;
            document.getElementById('backToChatBtn').style.display = 'none';
            if (appState.selectedFriend) {
                renderMessages();
            } else {
                document.getElementById('messagesContainer').innerHTML = `<div class="z-logo-container">
                    <svg class="animated-z" viewBox="0 0 100 100">
                        <path class="z-stroke-1" d="M30 30 L70 30" stroke="var(--primary)" stroke-width="3"/>
                        <path class="z-stroke-2" d="M70 30 L30 70" stroke="var(--primary)" stroke-width="3"/>
                        <path class="z-stroke-3" d="M30 70 L70 70" stroke="var(--primary)" stroke-width="3"/>
                        <circle cx="50" cy="50" r="25" class="z-glow" stroke="var(--primary)" stroke-width="1" fill="none" stroke-dasharray="4 4"/>
                    </svg>
                    <div class="z-subtitle">✦ Z-CHAT ✦</div>
                </div>`;
            }
        }
        function bech32ToHex(bech32) {
            try {
                if (!window.NostrTools) return null;
                const decoded = window.NostrTools.nip19.decode(bech32);
                return decoded.data;
            } catch (e) {
                console.error('Error decodificando bech32:', e);
                return null;
            }
        }
        function connectToRelays() {
            appState.relayConnections.forEach(ws => {
                if (ws.readyState === WebSocket.OPEN) ws.close();
            });
            appState.relayConnections = [];
            appState.relays.forEach(relayUrl => {
                try {
                    const ws = new WebSocket(relayUrl);
                    ws.onopen = () => {
                        console.log(`✅ Conectado a ${relayUrl}`);
                        updateRelayStatus(relayUrl, true);
                        if (appState.connected && appState.myPubkeyHex) {
                            const subscriptionId = 'sub_' + Math.random().toString(36).substring(7);
                            const filter = {
                                kinds: [4],
                                '#p': [appState.myPubkeyHex],
                                limit: 100
                            };
                            ws.send(JSON.stringify(["REQ", subscriptionId, filter]));
                        }
                    };
                    ws.onmessage = (event) => {
                        try {
                            const data = JSON.parse(event.data);
                            handleRelayMessage(data);
                        } catch (e) {
                            console.error('Error parsing message:', e);
                        }
                    };
                    ws.onerror = () => updateRelayStatus(relayUrl, false);
                    ws.onclose = () => updateRelayStatus(relayUrl, false);
                    appState.relayConnections.push(ws);
                } catch (e) {
                    console.error(`No se pudo conectar a ${relayUrl}:`, e);
                }
            });
        }
        function updateRelayStatus(relayUrl, connected) {
            const relaysList = document.getElementById('relaysList');
            const items = relaysList.getElementsByClassName('relay-item');
            for (let item of items) {
                if (item.querySelector('span').textContent === relayUrl) {
                    const status = item.querySelector('.relay-status');
                    if (connected) {
                        status.classList.add('connected');
                    } else {
                        status.classList.remove('connected');
                    }
                    break;
                }
            }
        }
        function handleRelayMessage(data) {
            const [type, ...rest] = data;
            if (type === 'EVENT' && rest[1] && rest[1].kind === 4) {
                const event = rest[1];
                const eventId = event.id;
                if (appState.processedEventIds.has(eventId)) {
                    console.log('Evento duplicado ignorado:', eventId);
                    return;
                }
                const isForMe = event.tags.some(tag => tag[0] === 'p' && tag[1] === appState.myPubkeyHex);
                if (isForMe) {
                    const senderPubkey = event.pubkey;
                    const friend = appState.friends.find(f => {
                        const friendHex = bech32ToHex(f.pubkey);
                        return friendHex === senderPubkey;
                    });
                    if (friend) {
                        const chatId = [appState.myPubkeyHex, senderPubkey].sort().join('_');
                        if (!appState.messages[chatId]) {
                            appState.messages[chatId] = [];
                        }
                        const time = new Date().toLocaleTimeString();
                        appState.messages[chatId].push({
                            sender: senderPubkey,
                            content: event.content,
                            time: time,
                            timestamp: Date.now(),
                            eventId: eventId
                        });
                        appState.processedEventIds.add(eventId);
                        localStorage.setItem('processedEventIds', JSON.stringify([...appState.processedEventIds]));
                        localStorage.setItem('messages', JSON.stringify(appState.messages));
                        if (appState.selectedFriend && bech32ToHex(appState.selectedFriend.pubkey) === senderPubkey) {
                            renderMessages();
                        }
                        showNotification('📨 Nuevo mensaje', `De: ${friend.name || 'Amigo'}`);
                    }
                }
            }
        }
        function broadcastEvent(event) {
            appState.relayConnections.forEach(ws => {
                if (ws.readyState === WebSocket.OPEN) {
                    ws.send(JSON.stringify(["EVENT", event]));
                }
            });
        }
        function renderFriends() {
            const list = document.getElementById('friendsList');
            if (appState.friends.length === 0) {
                list.innerHTML = '<div style="color: var(--gray); text-align: center; padding: 20px;">No hay amigos</div>';
                return;
            }
            list.innerHTML = appState.friends.map(friend => `
                <div class="friend-item ${appState.selectedFriend?.pubkey === friend.pubkey ? 'selected' : ''}" 
                     onclick="selectFriend('${friend.pubkey}')">
                    <div class="friend-avatar">
                        <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="var(--primary)">
                            <path d="M20 21v-2a4 4 0 0 0-4-4H8a4 4 0 0 0-4 4v2"/>
                            <circle cx="12" cy="7" r="4"/>
                        </svg>
                    </div>
                    <div class="friend-info">
                        <div class="friend-name">${friend.name || 'Amigo'}</div>
                        <div class="friend-pubkey">${friend.pubkey.substring(0, 20)}...</div>
                    </div>
                    <button class="btn-outline" style="width: auto; padding: 4px 8px; margin-left: 5px;" onclick="event.stopPropagation(); showDeleteFriendModal('${friend.pubkey}', '${friend.name}')">
                        <svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor">
                            <polyline points="3 6 5 6 21 6"></polyline>
                            <path d="M19 6v14a2 2 0 0 1-2 2H7a2 2 0 0 1-2-2V6m3 0V4a2 2 0 0 1 2-2h4a2 2 0 0 1 2 2v2"/>
                        </svg>
                    </button>
                </div>
            `).join('');
        }
        function selectFriend(pubkey) {
            appState.selectedFriend = appState.friends.find(f => f.pubkey === pubkey);
            document.getElementById('currentChatName').textContent = appState.selectedFriend?.name || 'Chat';
            document.getElementById('currentChatPubkey').textContent = pubkey;
            if (appState.connected) {
                document.getElementById('messageInput').disabled = false;
                document.getElementById('sendButton').disabled = false;
            }
            appState.searchActive = false;
            document.getElementById('backToChatBtn').style.display = 'none';
            renderMessages();
            renderFriends();
        }
        function renderMessages() {
            const container = document.getElementById('messagesContainer');
            if (!appState.selectedFriend) {
                container.innerHTML = `<div class="z-logo-container">
                    <svg class="animated-z" viewBox="0 0 100 100">
                        <path class="z-stroke-1" d="M30 30 L70 30" stroke="var(--primary)" stroke-width="3"/>
                        <path class="z-stroke-2" d="M70 30 L30 70" stroke="var(--primary)" stroke-width="3"/>
                        <path class="z-stroke-3" d="M30 70 L70 70" stroke="var(--primary)" stroke-width="3"/>
                        <circle cx="50" cy="50" r="25" class="z-glow" stroke="var(--primary)" stroke-width="1" fill="none" stroke-dasharray="4 4"/>
                    </svg>
                    <div class="z-subtitle">✦ Z-CHAT ✦</div>
                </div>`;
                return;
            }
            const friendHex = bech32ToHex(appState.selectedFriend.pubkey);
            const chatId = [appState.myPubkeyHex, friendHex].sort().join('_');
            const messages = appState.messages[chatId] || [];
            if (messages.length === 0) {
                container.innerHTML = '<div style="text-align: center; color: var(--gray); padding: 50px;">✦ No tienes mensajes con este amigo ! ...</div>';
                return;
            }
            container.innerHTML = messages.map((msg, index) => `
                <div class="message ${msg.sender === appState.myPubkeyHex ? 'own' : ''}">
                    <div class="message-avatar">
                        <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="var(--primary)">
                            <path d="M20 21v-2a4 4 0 0 0-4-4H8a4 4 0 0 0-4 4v2"/>
                            <circle cx="12" cy="7" r="4"/>
                        </svg>
                    </div>
                    <div class="message-content">
                        <div class="message-text">${msg.content}</div>
                        <div class="message-time">${msg.time}</div>
                        <button class="delete-message-btn" onclick="event.stopPropagation(); showDeleteMessageModal('${chatId}', ${index})" title="Eliminar mensaje">
                            <svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor">
                                <polyline points="3 6 5 6 21 6"></polyline>
                                <path d="M19 6v14a2 2 0 0 1-2 2H7a2 2 0 0 1-2-2V6m3 0V4a2 2 0 0 1 2-2h4a2 2 0 0 1 2 2v2"/>
                            </svg>
                        </button>
                    </div>
                </div>
            `).join('');
            container.scrollTop = container.scrollHeight;
        }
        function addFriend() {
            const name = document.getElementById('friendName').value;
            const pubkey = document.getElementById('friendPubkey').value.trim();
            if (!pubkey.startsWith('npub1')) {
                alert('La clave debe comenzar con npub1');
                return;
            }
            appState.friends.push({ name, pubkey });
            localStorage.setItem('friends', JSON.stringify(appState.friends));
            renderFriends();
            closeAddFriendModal();
            document.getElementById('friendName').value = '';
            document.getElementById('friendPubkey').value = '';
        }
        function showDeleteFriendModal(pubkey, name) {
            appState.friendToDelete = pubkey;
            document.getElementById('deleteFriendName').textContent = name;
            document.getElementById('deleteFriendPubkey').textContent = pubkey;
            document.getElementById('deleteFriendModal').style.display = 'flex';
        }
        function closeDeleteFriendModal() {
            document.getElementById('deleteFriendModal').style.display = 'none';
            appState.friendToDelete = null;
        }
        function confirmDeleteFriend() {
            if (!appState.friendToDelete) return;
            appState.friends = appState.friends.filter(f => f.pubkey !== appState.friendToDelete);
            if (appState.selectedFriend && appState.selectedFriend.pubkey === appState.friendToDelete) {
                appState.selectedFriend = null;
                document.getElementById('currentChatName').textContent = 'Selecciona un amigo';
                document.getElementById('currentChatPubkey').textContent = '';
                document.getElementById('messageInput').disabled = true;
                document.getElementById('sendButton').disabled = true;
                document.getElementById('messagesContainer').innerHTML = `<div class="z-logo-container">
                    <svg class="animated-z" viewBox="0 0 100 100">
                        <path class="z-stroke-1" d="M30 30 L70 30" stroke="var(--primary)" stroke-width="3"/>
                        <path class="z-stroke-2" d="M70 30 L30 70" stroke="var(--primary)" stroke-width="3"/>
                        <path class="z-stroke-3" d="M30 70 L70 70" stroke="var(--primary)" stroke-width="3"/>
                        <circle cx="50" cy="50" r="25" class="z-glow" stroke="var(--primary)" stroke-width="1" fill="none" stroke-dasharray="4 4"/>
                    </svg>
                    <div class="z-subtitle">✦ Z-CHAT ✦</div>
                </div>`;
            }
            const friendHex = bech32ToHex(appState.friendToDelete);
            if (friendHex && appState.myPubkeyHex) {
                const chatId = [appState.myPubkeyHex, friendHex].sort().join('_');
                delete appState.messages[chatId];
            }
            localStorage.setItem('friends', JSON.stringify(appState.friends));
            localStorage.setItem('messages', JSON.stringify(appState.messages));
            renderFriends();
            closeDeleteFriendModal();
            showNotification('Amigo eliminado', 'El amigo y sus mensajes han sido eliminados');
        }
        function panicButton() {
            document.getElementById('panicModal').style.display = 'flex';
        }
        function closePanicModal() {
            document.getElementById('panicModal').style.display = 'none';
        }
        function confirmPanic() {
            localStorage.clear();
            appState = {
                myNpub: '',
                myNsec: '',
                myPubkeyHex: '',
                myPrivkeyHex: '',
                friends: [],
                relays: ['wss://relay.damus.io', 'wss://nos.lol', 'wss://relay.nostr.band'],
                messages: {},
                selectedFriend: null,
                connected: false,
                relayConnections: [],
                processedEventIds: new Set(),
                searchResults: [],
                searchActive: false,
                friendToDelete: null,
                messageToDelete: null,
                relayToDelete: null
            };
            appState.relayConnections.forEach(ws => {
                if (ws.readyState === WebSocket.OPEN) ws.close();
            });
            document.getElementById('myNpub').value = '';
            document.getElementById('myNsec').value = '';
            document.getElementById('userPubkeyDisplay').textContent = 'No conectado';
            document.getElementById('connectionStatus').innerHTML = 'off';
            document.getElementById('connectionStatus').classList.remove('badge-sec');
            document.getElementById('currentChatName').textContent = 'Selecciona un amigo';
            document.getElementById('currentChatPubkey').textContent = '';
            document.getElementById('messageInput').disabled = true;
            document.getElementById('sendButton').disabled = true;
            document.getElementById('messagesContainer').innerHTML = `<div class="z-logo-container">
                <svg class="animated-z" viewBox="0 0 100 100">
                    <path class="z-stroke-1" d="M30 30 L70 30" stroke="var(--primary)" stroke-width="3"/>
                    <path class="z-stroke-2" d="M70 30 L30 70" stroke="var(--primary)" stroke-width="3"/>
                    <path class="z-stroke-3" d="M30 70 L70 70" stroke="var(--primary)" stroke-width="3"/>
                    <circle cx="50" cy="50" r="25" class="z-glow" stroke="var(--primary)" stroke-width="1" fill="none" stroke-dasharray="4 4"/>
                </svg>
                <div class="z-subtitle">✦ Z-CHAT ✦</div>
            </div>`;
            renderFriends();
            renderRelays();
            closePanicModal();
            showNotification('🧨 Datos borrados', 'La aplicación ha sido reiniciada');
        }
        function generateKeys() {
            if (!window.NostrTools) {
                alert('Error: NostrTools no cargado');
                return;
            }
            const privateKey = window.NostrTools.generatePrivateKey();
            const publicKey = window.NostrTools.getPublicKey(privateKey);
            const npub = window.NostrTools.nip19.npubEncode(publicKey);
            const nsec = window.NostrTools.nip19.nsecEncode(privateKey);
            document.getElementById('myNpub').value = npub;
            document.getElementById('myNsec').value = nsec;
            showNotification('Claves generadas', 'Guarda tu nsec seguro');
        }
        function connectNostr() {
            const npub = document.getElementById('myNpub').value.trim();
            const nsec = document.getElementById('myNsec').value.trim();
            if (!npub || !nsec) {
                alert('Completa ambos campos');
                return;
            }
            try {
                const pubkeyHex = bech32ToHex(npub);
                const privkeyHex = bech32ToHex(nsec);
                if (!pubkeyHex || !privkeyHex) {
                    throw new Error('No se pudieron decodificar las claves');
                }
                appState.myNpub = npub;
                appState.myNsec = nsec;
                appState.myPubkeyHex = pubkeyHex;
                appState.myPrivkeyHex = privkeyHex;
                appState.connected = true;
                localStorage.setItem('myNpub', npub);
                localStorage.setItem('myNsec', nsec);
                localStorage.setItem('myPubkeyHex', pubkeyHex);
                localStorage.setItem('myPrivkeyHex', privkeyHex);
                document.getElementById('userPubkeyDisplay').textContent = npub.substring(0, 30) + '...';
                document.getElementById('connectionStatus').innerHTML = 'on';
                document.getElementById('connectionStatus').classList.add('badge-sec');
                connectToRelays();
                showNotification('Conectado', 'Listo para chatear');
                if (appState.selectedFriend) {
                    document.getElementById('messageInput').disabled = false;
                    document.getElementById('sendButton').disabled = false;
                }
            } catch (e) {
                alert('Error decodificando claves: ' + e.message);
            }
        }
        function copyMyPubkey() {
            if (appState.myNpub) {
                navigator.clipboard.writeText(appState.myNpub);
                showNotification('Copiado', 'npub copiado');
            }
        }
        function copyCurrentChatPubkey() {
            const pubkeyElement = document.getElementById('currentChatPubkey');
            const pubkey = pubkeyElement.textContent;
            if (pubkey && pubkey !== 'Selecciona un amigo') {
                navigator.clipboard.writeText(pubkey).then(() => {
                    const tooltip = document.createElement('div');
                    tooltip.className = 'copy-tooltip';
                    tooltip.textContent = '¡Copiado! ✓';
                    tooltip.style.left = (pubkeyElement.getBoundingClientRect().left + window.scrollX) + 'px';
                    tooltip.style.top = (pubkeyElement.getBoundingClientRect().top + window.scrollY - 30) + 'px';
                    document.body.appendChild(tooltip);
                    setTimeout(() => {
                        tooltip.remove();
                    }, 1000);
                }).catch(err => {
                    console.error('Error al copiar:', err);
                    showNotification('Error', 'No se pudo copiar');
                });
            }
        }
        function sendMessage() {
            const input = document.getElementById('messageInput');
            const content = input.value.trim();
            if (!content || !appState.connected || !appState.selectedFriend) return;
            try {
                const friendHex = bech32ToHex(appState.selectedFriend.pubkey);
                const event = {
                    kind: 4,
                    created_at: Math.floor(Date.now() / 1000),
                    tags: [['p', friendHex]],
                    content: content,
                    pubkey: appState.myPubkeyHex
                };
                const eventId = window.NostrTools.getEventHash(event);
                const signature = window.NostrTools.getSignature(event, appState.myPrivkeyHex);
                const signedEvent = {
                    ...event,
                    id: eventId,
                    sig: signature
                };
                appState.processedEventIds.add(eventId);
                localStorage.setItem('processedEventIds', JSON.stringify([...appState.processedEventIds]));
                broadcastEvent(signedEvent);
                const chatId = [appState.myPubkeyHex, friendHex].sort().join('_');
                const time = new Date().toLocaleTimeString();
                if (!appState.messages[chatId]) {
                    appState.messages[chatId] = [];
                }
                appState.messages[chatId].push({
                    sender: appState.myPubkeyHex,
                    content: content,
                    time: time,
                    timestamp: Date.now(),
                    eventId: eventId
                });
                localStorage.setItem('messages', JSON.stringify(appState.messages));
                renderMessages();
                input.value = '';
                showNotification('Enviado', 'Mensaje publicado en Nostr');
            } catch (e) {
                console.error('Error enviando mensaje:', e);
                alert('Error: ' + e.message);
            }
        }
        function renderRelays() {
            const list = document.getElementById('relaysList');
            list.innerHTML = appState.relays.map(relay => `
                <div class="relay-item">
                    <span>${relay}</span>
                    <span class="relay-status"></span>
                    <button class="delete-relay-btn" onclick="event.stopPropagation(); showDeleteRelayModal('${relay}')" title="Eliminar relay">
                        <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor">
                            <polyline points="3 6 5 6 21 6"></polyline>
                            <path d="M19 6v14a2 2 0 0 1-2 2H7a2 2 0 0 1-2-2V6m3 0V4a2 2 0 0 1 2-2h4a2 2 0 0 1 2 2v2"/>
                        </svg>
                    </button>
                </div>
            `).join('');
        }
        function showDeleteRelayModal(relayUrl) {
            appState.relayToDelete = relayUrl;
            document.getElementById('deleteRelayUrl').textContent = relayUrl;
            document.getElementById('deleteRelayModal').style.display = 'flex';
        }
        function closeDeleteRelayModal() {
            document.getElementById('deleteRelayModal').style.display = 'none';
            appState.relayToDelete = null;
        }
        function confirmDeleteRelay() {
            if (!appState.relayToDelete) return;
            appState.relays = appState.relays.filter(r => r !== appState.relayToDelete);
            localStorage.setItem('relays', JSON.stringify(appState.relays));
            renderRelays();
            if (appState.connected) {
                connectToRelays();
            }
            closeDeleteRelayModal();
            showNotification('Relay eliminado', 'El relay ha sido eliminado');
        }
        function showRelayModal() {
            document.getElementById('relayModal').style.display = 'flex';
        }
        function closeRelayModal() {
            document.getElementById('relayModal').style.display = 'none';
        }
        function addRelay() {
            const relay = document.getElementById('newRelay').value.trim();
            if (relay && relay.startsWith('wss://')) {
                if (!appState.relays.includes(relay)) {
                    appState.relays.push(relay);
                    localStorage.setItem('relays', JSON.stringify(appState.relays));
                    renderRelays();
                    if (appState.connected) {
                        connectToRelays();
                    }
                    showNotification('Relay añadido', 'El relay ha sido agregado');
                } else {
                    alert('Este relay ya existe');
                }
                closeRelayModal();
                document.getElementById('newRelay').value = '';
            } else {
                alert('El relay debe comenzar con wss://');
            }
        }
        function showAddFriendModal() {
            document.getElementById('addFriendModal').style.display = 'flex';
        }
        function closeAddFriendModal() {
            document.getElementById('addFriendModal').style.display = 'none';
        }
        function showDeleteMessageModal(chatId, messageIndex) {
            appState.messageToDelete = { chatId, messageIndex };
            const messages = appState.messages[chatId] || [];
            if (messages[messageIndex]) {
                document.getElementById('deleteMessageContent').textContent = messages[messageIndex].content;
                document.getElementById('deleteMessageModal').style.display = 'flex';
            }
        }
        function closeDeleteMessageModal() {
            document.getElementById('deleteMessageModal').style.display = 'none';
            appState.messageToDelete = null;
        }
        function confirmDeleteMessage() {
            if (!appState.messageToDelete) return;
            const { chatId, messageIndex } = appState.messageToDelete;
            if (appState.messages[chatId] && appState.messages[chatId][messageIndex]) {
                appState.messages[chatId].splice(messageIndex, 1);
                if (appState.messages[chatId].length === 0) {
                    delete appState.messages[chatId];
                }
                localStorage.setItem('messages', JSON.stringify(appState.messages));
                renderMessages();
                showNotification('Mensaje eliminado', 'El mensaje ha sido eliminado');
            }
            closeDeleteMessageModal();
        }
        function showDeleteAllMessagesModal() {
            document.getElementById('deleteAllMessagesModal').style.display = 'flex';
        }
        function closeDeleteAllMessagesModal() {
            document.getElementById('deleteAllMessagesModal').style.display = 'none';
        }
        function confirmDeleteAllMessages() {
            appState.messages = {};
            localStorage.setItem('messages', JSON.stringify(appState.messages));
            renderMessages();
            closeDeleteAllMessagesModal();
            showNotification('Mensajes eliminados', 'Todos los mensajes han sido borrados');
        }
        function showNotification(title, message) {
            const notif = document.getElementById('notification');
            notif.style.display = 'block';
            notif.innerHTML = `
                <div class="notification-success">
                    <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="white">
                        <circle cx="12" cy="12" r="10"/>
                        <path d="M22 11.08V12a10 10 0 1 1-5.93-9.14"/>
                        <polyline points="22 4 12 14.01 9 11.01"/>
                    </svg>
                    <div>
                        <strong>${title}</strong><br>
                        <small>${message}</small>
                    </div>
                </div>
            `;
            setTimeout(() => { notif.style.display = 'none'; }, 3000);
        }
        function init() {
            document.getElementById('myNpub').value = appState.myNpub;
            document.getElementById('myNsec').value = appState.myNsec;
            renderFriends();
            renderRelays();
            if (appState.myNpub && appState.myPubkeyHex) {
                appState.connected = true;
                document.getElementById('userPubkeyDisplay').textContent = appState.myNpub.substring(0, 30) + '...';
                document.getElementById('connectionStatus').innerHTML = 'on';
                document.getElementById('connectionStatus').classList.add('badge-sec');
                connectToRelays();
            }
            document.getElementById('messageInput').addEventListener('keypress', (e) => {
                if (e.key === 'Enter') sendMessage();
            });
            document.querySelector('.nav-search').addEventListener('keypress', (e) => {
                if (e.key === 'Enter') {
                    performGlobalSearch();
                }
            });
            window.onclick = (event) => {
                if (event.target.classList.contains('modal-custom')) {
                    event.target.style.display = 'none';
                }
            };
        }
        if (document.readyState === 'loading') {
            document.addEventListener('DOMContentLoaded', init);
        } else {
            init();
        }
    </script>
</body>
</html>
```
