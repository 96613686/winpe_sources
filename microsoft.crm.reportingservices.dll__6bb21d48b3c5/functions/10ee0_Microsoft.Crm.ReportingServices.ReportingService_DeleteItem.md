# Microsoft.Crm.ReportingServices.ReportingService::DeleteItem

- ea: `0x10ee0`
- end: `0x10ef7`
- name: `Microsoft.Crm.ReportingServices.ReportingService::DeleteItem`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x10ee1`: `DeleteItem`

## pseudocode

```c

```

## disassembly

```asm
0x10ee0  ldarg.0
0x10ee1  ldstr    aDeleteitem// "DeleteItem"
0x10ee6  ldc.i4.1
0x10ee7  newarr   [mscorlib]System.Object
0x10eec  dup
0x10eed  ldc.i4.0
0x10eee  ldarg.1
0x10eef  stelem.ref
0x10ef0  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x10ef5  pop
0x10ef6  ret
```
