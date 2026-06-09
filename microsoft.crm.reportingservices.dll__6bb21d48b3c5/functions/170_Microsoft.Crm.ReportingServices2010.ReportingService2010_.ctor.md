# Microsoft.Crm.ReportingServices2010.ReportingService2010::.ctor

- ea: `0x170`
- end: `0x182`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::.ctor`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x177`: `http://localhost:80/ReportServer/ReportService2010.asmx`

## pseudocode

```c

```

## disassembly

```asm
0x170  ldarg.0
0x171  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::.ctor()
0x176  ldarg.0
0x177  ldstr    aHttpLocalhost8// "http://localhost:80/ReportServer/Report"...
0x17c  call     instance void [System.Web.Services]System.Web.Services.Protocols.WebClientProtocol::set_Url(string)
0x181  ret
```
