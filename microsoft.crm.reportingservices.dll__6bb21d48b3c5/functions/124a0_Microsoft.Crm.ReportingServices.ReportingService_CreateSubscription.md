# Microsoft.Crm.ReportingServices.ReportingService::CreateSubscription

- ea: `0x124a0`
- end: `0x124d4`
- name: `Microsoft.Crm.ReportingServices.ReportingService::CreateSubscription`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x124a1`: `CreateSubscription`

## pseudocode

```c

```

## disassembly

```asm
0x124a0  ldarg.0
0x124a1  ldstr    aCreatesubscrip// "CreateSubscription"
0x124a6  ldc.i4.6
0x124a7  newarr   [mscorlib]System.Object
0x124ac  dup
0x124ad  ldc.i4.0
0x124ae  ldarg.1
0x124af  stelem.ref
0x124b0  dup
0x124b1  ldc.i4.1
0x124b2  ldarg.2
0x124b3  stelem.ref
0x124b4  dup
0x124b5  ldc.i4.2
0x124b6  ldarg.3
0x124b7  stelem.ref
0x124b8  dup
0x124b9  ldc.i4.3
0x124ba  ldarg.s  4
0x124bc  stelem.ref
0x124bd  dup
0x124be  ldc.i4.4
0x124bf  ldarg.s  5
0x124c1  stelem.ref
0x124c2  dup
0x124c3  ldc.i4.5
0x124c4  ldarg.s  6
0x124c6  stelem.ref
0x124c7  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x124cc  ldc.i4.0
0x124cd  ldelem.ref
0x124ce  castclass [mscorlib]System.String
0x124d3  ret
```
