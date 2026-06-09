# Microsoft.Crm.ReportingServices.ReportingService::BeginGetExtensionSettings

- ea: `0x129b0`
- end: `0x129c8`
- name: `Microsoft.Crm.ReportingServices.ReportingService::BeginGetExtensionSettings`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## string_xrefs

- `0x129b1`: `GetExtensionSettings`

## pseudocode

```c

```

## disassembly

```asm
0x129b0  ldarg.0
0x129b1  ldstr    aGetextensionse// "GetExtensionSettings"
0x129b6  ldc.i4.1
0x129b7  newarr   [mscorlib]System.Object
0x129bc  dup
0x129bd  ldc.i4.0
0x129be  ldarg.1
0x129bf  stelem.ref
0x129c0  ldarg.2
0x129c1  ldarg.3
0x129c2  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x129c7  ret
```
