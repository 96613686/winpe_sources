# Microsoft.Crm.SdkTypeProxy.Metadata.MetadataService::.ctor

- ea: `0x36120`
- end: `0x36132`
- name: `Microsoft.Crm.SdkTypeProxy.Metadata.MetadataService::.ctor`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x36127`: `http://localhost/MSCRMServices/MetadataService.asmx`

## pseudocode

```c

```

## disassembly

```asm
0x36120  ldarg.0
0x36121  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::.ctor()
0x36126  ldarg.0
0x36127  ldstr    aHttpLocalhostM_0// "http://localhost/MSCRMServices/Metadata"...
0x3612c  call     instance void [System.Web.Services]System.Web.Services.Protocols.WebClientProtocol::set_Url(string)
0x36131  ret
```
