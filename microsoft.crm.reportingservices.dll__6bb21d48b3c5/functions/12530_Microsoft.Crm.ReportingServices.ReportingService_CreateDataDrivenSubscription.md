# Microsoft.Crm.ReportingServices.ReportingService::CreateDataDrivenSubscription

- ea: `0x12530`
- end: `0x12569`
- name: `Microsoft.Crm.ReportingServices.ReportingService::CreateDataDrivenSubscription`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x12531`: `CreateDataDrivenSubscription`

## pseudocode

```c

```

## disassembly

```asm
0x12530  ldarg.0
0x12531  ldstr    aCreatedatadriv// "CreateDataDrivenSubscription"
0x12536  ldc.i4.7
0x12537  newarr   [mscorlib]System.Object
0x1253c  dup
0x1253d  ldc.i4.0
0x1253e  ldarg.1
0x1253f  stelem.ref
0x12540  dup
0x12541  ldc.i4.1
0x12542  ldarg.2
0x12543  stelem.ref
0x12544  dup
0x12545  ldc.i4.2
0x12546  ldarg.3
0x12547  stelem.ref
0x12548  dup
0x12549  ldc.i4.3
0x1254a  ldarg.s  4
0x1254c  stelem.ref
0x1254d  dup
0x1254e  ldc.i4.4
0x1254f  ldarg.s  5
0x12551  stelem.ref
0x12552  dup
0x12553  ldc.i4.5
0x12554  ldarg.s  6
0x12556  stelem.ref
0x12557  dup
0x12558  ldc.i4.6
0x12559  ldarg.s  7
0x1255b  stelem.ref
0x1255c  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x12561  ldc.i4.0
0x12562  ldelem.ref
0x12563  castclass [mscorlib]System.String
0x12568  ret
```
