# Microsoft.Crm.ReportingServices.ReportingService::.ctor

- ea: `0x10ce0`
- end: `0x10cf2`
- name: `Microsoft.Crm.ReportingServices.ReportingService::.ctor`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x10ce7`: `http://localhost/ReportServer/ReportService.asmx`

## pseudocode

```c

```

## disassembly

```asm
0x10ce0  ldarg.0
0x10ce1  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::.ctor()
0x10ce6  ldarg.0
0x10ce7  ldstr    aHttpLocalhostR// "http://localhost/ReportServer/ReportSer"...
0x10cec  call     instance void [System.Web.Services]System.Web.Services.Protocols.WebClientProtocol::set_Url(string)
0x10cf1  ret
```
