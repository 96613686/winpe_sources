# Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateCatalogItem

- ea: `0x2e90`
- end: `0x2ed6`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateCatalogItem`
- size: `70`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x2e91`: `CreateCatalogItem`

## pseudocode

```c

```

## disassembly

```asm
0x2e90  ldarg.0
0x2e91  ldstr    aCreatecatalogi// "CreateCatalogItem"
0x2e96  ldc.i4.6
0x2e97  newarr   [mscorlib]System.Object
0x2e9c  dup
0x2e9d  ldc.i4.0
0x2e9e  ldarg.1
0x2e9f  stelem.ref
0x2ea0  dup
0x2ea1  ldc.i4.1
0x2ea2  ldarg.2
0x2ea3  stelem.ref
0x2ea4  dup
0x2ea5  ldc.i4.2
0x2ea6  ldarg.3
0x2ea7  stelem.ref
0x2ea8  dup
0x2ea9  ldc.i4.3
0x2eaa  ldarg.s  4
0x2eac  box      [mscorlib]System.Boolean
0x2eb1  stelem.ref
0x2eb2  dup
0x2eb3  ldc.i4.4
0x2eb4  ldarg.s  5
0x2eb6  stelem.ref
0x2eb7  dup
0x2eb8  ldc.i4.5
0x2eb9  ldarg.s  6
0x2ebb  stelem.ref
0x2ebc  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x2ec1  stloc.0
0x2ec2  ldarg.s  7
0x2ec4  ldloc.0
0x2ec5  ldc.i4.1
0x2ec6  ldelem.ref
0x2ec7  castclass class Microsoft.Crm.ReportingServices2010.Warning[]
0x2ecc  stind.ref
0x2ecd  ldloc.0
0x2ece  ldc.i4.0
0x2ecf  ldelem.ref
0x2ed0  castclass Microsoft.Crm.ReportingServices2010.CatalogItem
0x2ed5  ret
```
