# Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateDataDrivenSubscription

- ea: `0x4750`
- end: `0x4789`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateDataDrivenSubscription`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x4751`: `CreateDataDrivenSubscription`

## pseudocode

```c

```

## disassembly

```asm
0x4750  ldarg.0
0x4751  ldstr    aCreatedatadriv// "CreateDataDrivenSubscription"
0x4756  ldc.i4.7
0x4757  newarr   [mscorlib]System.Object
0x475c  dup
0x475d  ldc.i4.0
0x475e  ldarg.1
0x475f  stelem.ref
0x4760  dup
0x4761  ldc.i4.1
0x4762  ldarg.2
0x4763  stelem.ref
0x4764  dup
0x4765  ldc.i4.2
0x4766  ldarg.3
0x4767  stelem.ref
0x4768  dup
0x4769  ldc.i4.3
0x476a  ldarg.s  4
0x476c  stelem.ref
0x476d  dup
0x476e  ldc.i4.4
0x476f  ldarg.s  5
0x4771  stelem.ref
0x4772  dup
0x4773  ldc.i4.5
0x4774  ldarg.s  6
0x4776  stelem.ref
0x4777  dup
0x4778  ldc.i4.6
0x4779  ldarg.s  7
0x477b  stelem.ref
0x477c  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x4781  ldc.i4.0
0x4782  ldelem.ref
0x4783  castclass [mscorlib]System.String
0x4788  ret
```
