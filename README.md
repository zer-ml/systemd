# Configuration

Begin by selecting an authentication method and updating the file accordingly. Example unit files are provided for each method. These examples assume `zerNet` runs as the `root` user and is installed at `/opt/zerNet/zerNet`.

Before proceeding, make sure the `zerNet` client has been registered as described in the top-level README.md.

## Dotfiles

If using `~/.otoy/zerNet` for authentication, no changes are needed as long as the service runs as `root` and the dotfile is located at `/root/.otoy/zerNet`. If using a different user, update the `User` parameter and the `HOME` environment variable under `Environment` in the unit file.

## Environment Variables

For authentication via environment variables, update the public key and secret values in the `Environment` section of the unit file.

## CLI Arguments

If using CLI flags for authentication, update the arguments in the `ExecStart` line of `zerNet.service-cliflags`.

# Installation

Copy the unit file to the systemd `system` directory, reload units so systemd picks up the change, then enable and start the service:

```bash
sudo cp zerNet.service-dotfiles /usr/lib/systemd/system/zerNet.service
sudo systemctl daemon-reload
sudo systemctl enable zerNet.service
sudo systemctl start zerNet.service
```
