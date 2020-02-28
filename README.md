# Sensu Go Bird Checks

This plugin will check the state of bird using the `birdc` command and alert if bird isn't exporting any routes, or reporting an error. Also supports birdc6.

## Configuration

Example Sensu Go definition:

```yaml
api_version: core/v2
type: CheckConfig
metadata:
  namespace: default
  name: bird_state
spec:
  runtime_assets:
  - sensu-bird-checks
  command: sudo check-bird-state
  subscriptions:
  - bird
  publish: true
  interval: 30
  handlers:
  - slack
  - pagerduty
  - email
```

## Usage Examples

Help:

```
The Sensu Go Bird State plugin

Usage:
  bird-state [6]

  Use the `6` argument to check `bird6`
