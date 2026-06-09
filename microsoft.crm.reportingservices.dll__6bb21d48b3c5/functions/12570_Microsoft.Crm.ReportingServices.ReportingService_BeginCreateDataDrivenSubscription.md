# Microsoft.Crm.ReportingServices.ReportingService::BeginCreateDataDrivenSubscription

- ea: `0x12570`
- end: `0x125a6`
- name: `Microsoft.Crm.ReportingServices.ReportingService::BeginCreateDataDrivenSubscription`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x12571`: `CreateDataDrivenSubscription`

## pseudocode

```c

```

## disassembly

```asm
0x12570  ldarg.0
0x12571  ldstr    aCreatedatadriv// "CreateDataDrivenSubscription"
0x12576  ldc.i4.7
0x12577  newarr   [mscorlib]System.Object
0x1257c  dup
0x1257d  ldc.i4.0
0x1257e  ldarg.1
0x1257f  stelem.ref
0x12580  dup
0x12581  ldc.i4.1
0x12582  ldarg.2
0x12583  stelem.ref
0x12584  dup
0x12585  ldc.i4.2
0x12586  ldarg.3
0x12587  stelem.ref
0x12588  dup
0x12589  ldc.i4.3
0x1258a  ldarg.s  4
0x1258c  stelem.ref
0x1258d  dup
0x1258e  ldc.i4.4
0x1258f  ldarg.s  5
0x12591  stelem.ref
0x12592  dup
0x12593  ldc.i4.5
0x12594  ldarg.s  6
0x12596  stelem.ref
0x12597  dup
0x12598  ldc.i4.6
0x12599  ldarg.s  7
0x1259b  stelem.ref
0x1259c  ldarg.s  8
0x1259e  ldarg.s  9
0x125a0  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x125a5  ret
```
