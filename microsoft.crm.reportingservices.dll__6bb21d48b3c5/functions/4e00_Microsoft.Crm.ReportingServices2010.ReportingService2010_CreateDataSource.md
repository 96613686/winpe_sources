# Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateDataSource

- ea: `0x4e00`
- end: `0x4e34`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateDataSource`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x4e01`: `CreateDataSource`

## pseudocode

```c

```

## disassembly

```asm
0x4e00  ldarg.0
0x4e01  ldstr    aCreatedatasour// "CreateDataSource"
0x4e06  ldc.i4.5
0x4e07  newarr   [mscorlib]System.Object
0x4e0c  dup
0x4e0d  ldc.i4.0
0x4e0e  ldarg.1
0x4e0f  stelem.ref
0x4e10  dup
0x4e11  ldc.i4.1
0x4e12  ldarg.2
0x4e13  stelem.ref
0x4e14  dup
0x4e15  ldc.i4.2
0x4e16  ldarg.3
0x4e17  box      [mscorlib]System.Boolean
0x4e1c  stelem.ref
0x4e1d  dup
0x4e1e  ldc.i4.3
0x4e1f  ldarg.s  4
0x4e21  stelem.ref
0x4e22  dup
0x4e23  ldc.i4.4
0x4e24  ldarg.s  5
0x4e26  stelem.ref
0x4e27  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x4e2c  ldc.i4.0
0x4e2d  ldelem.ref
0x4e2e  castclass Microsoft.Crm.ReportingServices2010.CatalogItem
0x4e33  ret
```
