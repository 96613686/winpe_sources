# Microsoft.Crm.ReportingServices.ReportingService::GetSystemPermissions

- ea: `0x13060`
- end: `0x13079`
- name: `Microsoft.Crm.ReportingServices.ReportingService::GetSystemPermissions`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x13061`: `GetSystemPermissions`

## pseudocode

```c

```

## disassembly

```asm
0x13060  ldarg.0
0x13061  ldstr    aGetsystempermi// "GetSystemPermissions"
0x13066  ldc.i4.0
0x13067  newarr   [mscorlib]System.Object
0x1306c  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x13071  ldc.i4.0
0x13072  ldelem.ref
0x13073  castclass string[]
0x13078  ret
```
