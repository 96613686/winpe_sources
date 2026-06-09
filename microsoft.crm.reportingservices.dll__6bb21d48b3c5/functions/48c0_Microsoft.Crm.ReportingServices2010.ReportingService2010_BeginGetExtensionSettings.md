# Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginGetExtensionSettings

- ea: `0x48c0`
- end: `0x48d8`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginGetExtensionSettings`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## string_xrefs

- `0x48c1`: `GetExtensionSettings`

## pseudocode

```c

```

## disassembly

```asm
0x48c0  ldarg.0
0x48c1  ldstr    aGetextensionse// "GetExtensionSettings"
0x48c6  ldc.i4.1
0x48c7  newarr   [mscorlib]System.Object
0x48cc  dup
0x48cd  ldc.i4.0
0x48ce  ldarg.1
0x48cf  stelem.ref
0x48d0  ldarg.2
0x48d1  ldarg.3
0x48d2  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x48d7  ret
```
