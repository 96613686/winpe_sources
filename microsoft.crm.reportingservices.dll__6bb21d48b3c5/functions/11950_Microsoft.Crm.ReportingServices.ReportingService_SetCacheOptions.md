# Microsoft.Crm.ReportingServices.ReportingService::SetCacheOptions

- ea: `0x11950`
- end: `0x11974`
- name: `Microsoft.Crm.ReportingServices.ReportingService::SetCacheOptions`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x11951`: `SetCacheOptions`

## pseudocode

```c

```

## disassembly

```asm
0x11950  ldarg.0
0x11951  ldstr    aSetcacheoption// "SetCacheOptions"
0x11956  ldc.i4.3
0x11957  newarr   [mscorlib]System.Object
0x1195c  dup
0x1195d  ldc.i4.0
0x1195e  ldarg.1
0x1195f  stelem.ref
0x11960  dup
0x11961  ldc.i4.1
0x11962  ldarg.2
0x11963  box      [mscorlib]System.Boolean
0x11968  stelem.ref
0x11969  dup
0x1196a  ldc.i4.2
0x1196b  ldarg.3
0x1196c  stelem.ref
0x1196d  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x11972  pop
0x11973  ret
```
