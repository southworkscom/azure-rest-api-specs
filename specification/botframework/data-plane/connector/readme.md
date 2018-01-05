# BotFramework Connector

> see https://aka.ms/autorest

Configuration for generating BotFramework Connector SDK.

``` yaml
add-credentials: true
openapi-type: data-plane
```
The current release for the BotFramework Connector is v3.0.

# Releases

## Connector API 3.0

``` yaml
input-file: v3.0/ConnectorAPI.json
```

### Connector API 3.0 - CSharp Settings
These settings apply only when `--csharp` is specified on the command line.
``` yaml $(csharp)
csharp:
  override-client-name: BotConnector
  sync-methods: None
  license-header: MICROSOFT_MIT_NO_VERSION
  azure-arm: false
  namespace: Microsoft.Azure.BotFramework.Connector
  output-folder: $(csharp-sdks-folder)/BotFramework/dataPlane/Connector/BotFramework.Connector/Generated
  clear-output-folder: true
```

### Connector API 3.0 - Python Settings

These settings apply only when `--python` is specified on the command line.
Please also specify `--python-sdks-folder=<path to the root directory of your azure-sdk-for-python clone>`.
Use `--python-mode=update` if you already have a setup.py and just want to update the code itself.

``` yaml $(python)
python-mode: create
python:
  license-header: MICROSOFT_MIT_NO_VERSION
  add-credentials: true
  payload-flattening-threshold: 2
  namespace: azure.botframework.connector
  package-name: azure-botframework-connector
  override-client-name: BotConnector
  clear-output-folder: true
```
``` yaml $(python) && $(python-mode) == 'update'
python:
  no-namespace-folders: true
  output-folder: $(python-sdks-folder)/azure-botframework-connector/azure/botframework/connector
```
``` yaml $(python) && $(python-mode) == 'create'
python:
  basic-setup-py: true
  output-folder: $(python-sdks-folder)/azure-botframework-connector
```

## Connector API 3.0 - Java Settings

These settings apply only when `--java` is specified on the command line.

``` yaml $(java)
java:
  # override the default output folder
  override-client-name: BotConnector
  license-header: MICROSOFT_MIT_NO_VERSION
  add-credentials: true
  namespace: com.microsoft.azure.botframework.connector
```
