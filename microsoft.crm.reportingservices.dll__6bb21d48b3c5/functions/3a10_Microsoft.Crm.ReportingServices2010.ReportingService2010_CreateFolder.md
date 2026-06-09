# Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateFolder

- ea: `0x3a10`
- end: `0x3a35`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateFolder`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x3a11`: `CreateFolder`

## pseudocode

```c

```

## disassembly

```asm
0x3a10  ldarg.0
0x3a11  ldstr    aCreatefolder// "CreateFolder"
0x3a16  ldc.i4.3
0x3a17  newarr   [mscorlib]System.Object
0x3a1c  dup
0x3a1d  ldc.i4.0
0x3a1e  ldarg.1
0x3a1f  stelem.ref
0x3a20  dup
0x3a21  ldc.i4.1
0x3a22  ldarg.2
0x3a23  stelem.ref
0x3a24  dup
0x3a25  ldc.i4.2
0x3a26  ldarg.3
0x3a27  stelem.ref
0x3a28  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x3a2d  ldc.i4.0
0x3a2e  ldelem.ref
0x3a2f  castclass Microsoft.Crm.ReportingServices2010.CatalogItem
0x3a34  ret
```
