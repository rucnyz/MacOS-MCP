# MacOS-MCP

FastAPI backend for macOS desktop automation. Provides VNC-based GUI control (screenshot, click, type, key) and SSH-based shell command execution.

Runs inside the Docker container alongside the QEMU macOS VM. Used by [DecodingTrust-Agent](https://github.com/rucnyz/DecodingTrust-Agent) evaluation framework.

## Endpoints

| Endpoint | Method | Description |
|----------|--------|-------------|
| `/health` | GET | Health check |
| `/shell` | POST | Execute shell command via SSH |
| `/remote_macos_get_screen` | POST | Capture screenshot via VNC |
| `/remote_macos_mouse_click` | POST | Mouse click |
| `/remote_macos_mouse_double_click` | POST | Mouse double-click |
| `/remote_macos_send_keys` | POST | Keyboard input |
| `/remote_macos_mouse_move` | POST | Move mouse cursor |
| `/remote_macos_mouse_scroll` | POST | Mouse scroll |
| `/remote_macos_open_application` | POST | Launch application |
| `/remote_macos_mouse_drag_n_drop` | POST | Drag and drop |

## Environment Variables

| Variable | Description |
|----------|-------------|
| `MACOS_HOST` | VNC host (VM's Screen Sharing IP) |
| `MACOS_PORT` | VNC port (default: 5900) |
| `MACOS_PASSWORD` | VNC/login password |
| `MACOS_USERNAME` | VNC/login username |
| `MACOS_SSH_HOST` | SSH host (same as VNC host) |
| `MACOS_SSH_PORT` | SSH port (default: 22) |
| `MACOS_SSH_USER` | SSH username |
| `MACOS_SSH_PASSWORD` | SSH password |
