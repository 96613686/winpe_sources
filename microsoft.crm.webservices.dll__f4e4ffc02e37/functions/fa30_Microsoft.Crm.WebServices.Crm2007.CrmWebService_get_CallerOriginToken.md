# Microsoft.Crm.WebServices.Crm2007.CrmWebService::get_CallerOriginToken

- ea: `0xfa30`
- end: `0xfa37`
- name: `Microsoft.Crm.WebServices.Crm2007.CrmWebService::get_CallerOriginToken`
- size: `7`
- prototype: ``
- caller_count: `7`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0xaa70`
- `0xaab0`
- `0xaaf0`
- `0xab30`
- `0xab80`
- `0xabd0`
- `0xac10`

## pseudocode

```c

```

## disassembly

```asm
0xfa30  ldarg.0
0xfa31  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken Microsoft.Crm.WebServices.Crm2007.CrmWebService::_callerOriginToken
0xfa36  ret
```
