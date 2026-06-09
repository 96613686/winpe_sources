# Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginSetItemLink

- ea: `0x7b90`
- end: `0x7bad`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginSetItemLink`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x7b91`: `SetItemLink`

## pseudocode

```c

```

## disassembly

```asm
0x7b90  ldarg.0
0x7b91  ldstr    aSetitemlink// "SetItemLink"
0x7b96  ldc.i4.2
0x7b97  newarr   [mscorlib]System.Object
0x7b9c  dup
0x7b9d  ldc.i4.0
0x7b9e  ldarg.1
0x7b9f  stelem.ref
0x7ba0  dup
0x7ba1  ldc.i4.1
0x7ba2  ldarg.2
0x7ba3  stelem.ref
0x7ba4  ldarg.3
0x7ba5  ldarg.s  4
0x7ba7  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x7bac  ret
```
