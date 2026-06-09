# Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginCreateDataDrivenSubscription

- ea: `0x4790`
- end: `0x47c6`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginCreateDataDrivenSubscription`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x4791`: `CreateDataDrivenSubscription`

## pseudocode

```c

```

## disassembly

```asm
0x4790  ldarg.0
0x4791  ldstr    aCreatedatadriv// "CreateDataDrivenSubscription"
0x4796  ldc.i4.7
0x4797  newarr   [mscorlib]System.Object
0x479c  dup
0x479d  ldc.i4.0
0x479e  ldarg.1
0x479f  stelem.ref
0x47a0  dup
0x47a1  ldc.i4.1
0x47a2  ldarg.2
0x47a3  stelem.ref
0x47a4  dup
0x47a5  ldc.i4.2
0x47a6  ldarg.3
0x47a7  stelem.ref
0x47a8  dup
0x47a9  ldc.i4.3
0x47aa  ldarg.s  4
0x47ac  stelem.ref
0x47ad  dup
0x47ae  ldc.i4.4
0x47af  ldarg.s  5
0x47b1  stelem.ref
0x47b2  dup
0x47b3  ldc.i4.5
0x47b4  ldarg.s  6
0x47b6  stelem.ref
0x47b7  dup
0x47b8  ldc.i4.6
0x47b9  ldarg.s  7
0x47bb  stelem.ref
0x47bc  ldarg.s  8
0x47be  ldarg.s  9
0x47c0  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x47c5  ret
```
