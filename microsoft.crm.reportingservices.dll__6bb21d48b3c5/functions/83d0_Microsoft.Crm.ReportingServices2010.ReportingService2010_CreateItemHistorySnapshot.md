# Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateItemHistorySnapshot

- ea: `0x83d0`
- end: `0x83f9`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateItemHistorySnapshot`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x83d1`: `CreateItemHistorySnapshot`

## pseudocode

```c

```

## disassembly

```asm
0x83d0  ldarg.0
0x83d1  ldstr    aCreateitemhist// "CreateItemHistorySnapshot"
0x83d6  ldc.i4.1
0x83d7  newarr   [mscorlib]System.Object
0x83dc  dup
0x83dd  ldc.i4.0
0x83de  ldarg.1
0x83df  stelem.ref
0x83e0  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x83e5  stloc.0
0x83e6  ldarg.2
0x83e7  ldloc.0
0x83e8  ldc.i4.1
0x83e9  ldelem.ref
0x83ea  castclass class Microsoft.Crm.ReportingServices2010.Warning[]
0x83ef  stind.ref
0x83f0  ldloc.0
0x83f1  ldc.i4.0
0x83f2  ldelem.ref
0x83f3  castclass [mscorlib]System.String
0x83f8  ret
```
