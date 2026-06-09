# Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateSubscription

- ea: `0x4610`
- end: `0x4644`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateSubscription`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x4611`: `CreateSubscription`

## pseudocode

```c

```

## disassembly

```asm
0x4610  ldarg.0
0x4611  ldstr    aCreatesubscrip// "CreateSubscription"
0x4616  ldc.i4.6
0x4617  newarr   [mscorlib]System.Object
0x461c  dup
0x461d  ldc.i4.0
0x461e  ldarg.1
0x461f  stelem.ref
0x4620  dup
0x4621  ldc.i4.1
0x4622  ldarg.2
0x4623  stelem.ref
0x4624  dup
0x4625  ldc.i4.2
0x4626  ldarg.3
0x4627  stelem.ref
0x4628  dup
0x4629  ldc.i4.3
0x462a  ldarg.s  4
0x462c  stelem.ref
0x462d  dup
0x462e  ldc.i4.4
0x462f  ldarg.s  5
0x4631  stelem.ref
0x4632  dup
0x4633  ldc.i4.5
0x4634  ldarg.s  6
0x4636  stelem.ref
0x4637  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x463c  ldc.i4.0
0x463d  ldelem.ref
0x463e  castclass [mscorlib]System.String
0x4643  ret
```
