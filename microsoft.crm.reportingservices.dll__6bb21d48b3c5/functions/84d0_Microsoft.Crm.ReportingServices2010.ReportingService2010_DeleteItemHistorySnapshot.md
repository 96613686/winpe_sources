# Microsoft.Crm.ReportingServices2010.ReportingService2010::DeleteItemHistorySnapshot

- ea: `0x84d0`
- end: `0x84eb`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::DeleteItemHistorySnapshot`
- size: `27`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x84d1`: `DeleteItemHistorySnapshot`

## pseudocode

```c

```

## disassembly

```asm
0x84d0  ldarg.0
0x84d1  ldstr    aDeleteitemhist// "DeleteItemHistorySnapshot"
0x84d6  ldc.i4.2
0x84d7  newarr   [mscorlib]System.Object
0x84dc  dup
0x84dd  ldc.i4.0
0x84de  ldarg.1
0x84df  stelem.ref
0x84e0  dup
0x84e1  ldc.i4.1
0x84e2  ldarg.2
0x84e3  stelem.ref
0x84e4  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x84e9  pop
0x84ea  ret
```
