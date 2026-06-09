# Microsoft.Crm.ReportingServices.ReportingService::BeginFlushCache

- ea: `0x11aa0`
- end: `0x11ab8`
- name: `Microsoft.Crm.ReportingServices.ReportingService::BeginFlushCache`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x11aa1`: `FlushCache`

## pseudocode

```c

```

## disassembly

```asm
0x11aa0  ldarg.0
0x11aa1  ldstr    aFlushcache// "FlushCache"
0x11aa6  ldc.i4.1
0x11aa7  newarr   [mscorlib]System.Object
0x11aac  dup
0x11aad  ldc.i4.0
0x11aae  ldarg.1
0x11aaf  stelem.ref
0x11ab0  ldarg.2
0x11ab1  ldarg.3
0x11ab2  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x11ab7  ret
```
