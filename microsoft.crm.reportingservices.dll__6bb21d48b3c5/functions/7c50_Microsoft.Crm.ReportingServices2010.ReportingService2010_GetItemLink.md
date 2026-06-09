# Microsoft.Crm.ReportingServices2010.ReportingService2010::GetItemLink

- ea: `0x7c50`
- end: `0x7c6d`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::GetItemLink`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x7c51`: `GetItemLink`

## pseudocode

```c

```

## disassembly

```asm
0x7c50  ldarg.0
0x7c51  ldstr    aGetitemlink// "GetItemLink"
0x7c56  ldc.i4.1
0x7c57  newarr   [mscorlib]System.Object
0x7c5c  dup
0x7c5d  ldc.i4.0
0x7c5e  ldarg.1
0x7c5f  stelem.ref
0x7c60  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x7c65  ldc.i4.0
0x7c66  ldelem.ref
0x7c67  castclass [mscorlib]System.String
0x7c6c  ret
```
