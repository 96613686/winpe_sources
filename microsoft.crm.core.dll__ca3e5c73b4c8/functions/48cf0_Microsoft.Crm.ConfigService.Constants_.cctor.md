# Microsoft.Crm.ConfigService.Constants::.cctor

- ea: `0x48cf0`
- end: `0x48d05`
- name: `Microsoft.Crm.ConfigService.Constants::.cctor`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## string_xrefs

- `0x48cf0`: `ServerLocatorService`
- `0x48cfa`: `ConfigService`

## pseudocode

```c

```

## disassembly

```asm
0x48cf0  ldstr    aServerlocators// "ServerLocatorService"
0x48cf5  stsfld   string Microsoft.Crm.ConfigService.Constants::ServerLocatorService
0x48cfa  ldstr    aConfigservice// "ConfigService"
0x48cff  stsfld   string Microsoft.Crm.ConfigService.Constants::ConfigService
0x48d04  ret
```
