# Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginFlushCache

- ea: `0x8310`
- end: `0x8328`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginFlushCache`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x8311`: `FlushCache`

## pseudocode

```c

```

## disassembly

```asm
0x8310  ldarg.0
0x8311  ldstr    aFlushcache// "FlushCache"
0x8316  ldc.i4.1
0x8317  newarr   [mscorlib]System.Object
0x831c  dup
0x831d  ldc.i4.0
0x831e  ldarg.1
0x831f  stelem.ref
0x8320  ldarg.2
0x8321  ldarg.3
0x8322  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x8327  ret
```
