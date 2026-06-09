# Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginSetCacheOptions

- ea: `0x8110`
- end: `0x8137`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginSetCacheOptions`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x8111`: `SetCacheOptions`

## pseudocode

```c

```

## disassembly

```asm
0x8110  ldarg.0
0x8111  ldstr    aSetcacheoption// "SetCacheOptions"
0x8116  ldc.i4.3
0x8117  newarr   [mscorlib]System.Object
0x811c  dup
0x811d  ldc.i4.0
0x811e  ldarg.1
0x811f  stelem.ref
0x8120  dup
0x8121  ldc.i4.1
0x8122  ldarg.2
0x8123  box      [mscorlib]System.Boolean
0x8128  stelem.ref
0x8129  dup
0x812a  ldc.i4.2
0x812b  ldarg.3
0x812c  stelem.ref
0x812d  ldarg.s  4
0x812f  ldarg.s  5
0x8131  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x8136  ret
```
