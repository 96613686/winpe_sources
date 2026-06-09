# Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginSetItemParameters

- ea: `0x7590`
- end: `0x75ad`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginSetItemParameters`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x7591`: `SetItemParameters`

## pseudocode

```c

```

## disassembly

```asm
0x7590  ldarg.0
0x7591  ldstr    aSetitemparamet// "SetItemParameters"
0x7596  ldc.i4.2
0x7597  newarr   [mscorlib]System.Object
0x759c  dup
0x759d  ldc.i4.0
0x759e  ldarg.1
0x759f  stelem.ref
0x75a0  dup
0x75a1  ldc.i4.1
0x75a2  ldarg.2
0x75a3  stelem.ref
0x75a4  ldarg.3
0x75a5  ldarg.s  4
0x75a7  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x75ac  ret
```
