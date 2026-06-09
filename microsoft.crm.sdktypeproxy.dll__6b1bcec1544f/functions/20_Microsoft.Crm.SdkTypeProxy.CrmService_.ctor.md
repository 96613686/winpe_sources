# Microsoft.Crm.SdkTypeProxy.CrmService::.ctor

- ea: `0x20`
- end: `0x32`
- name: `Microsoft.Crm.SdkTypeProxy.CrmService::.ctor`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x27`: `http://localhost/MSCRMServices/2007/CrmService.asmx`

## pseudocode

```c

```

## disassembly

```asm
0x20  ldarg.0
0x21  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::.ctor()
0x26  ldarg.0
0x27  ldstr    aHttpLocalhostM// "http://localhost/MSCRMServices/2007/Crm"...
0x2c  call     instance void [System.Web.Services]System.Web.Services.Protocols.WebClientProtocol::set_Url(string)
0x31  ret
```
