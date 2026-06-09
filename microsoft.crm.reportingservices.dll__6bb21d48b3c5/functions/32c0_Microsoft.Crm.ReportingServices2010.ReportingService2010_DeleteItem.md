# Microsoft.Crm.ReportingServices2010.ReportingService2010::DeleteItem

- ea: `0x32c0`
- end: `0x32d7`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::DeleteItem`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x32c1`: `DeleteItem`

## pseudocode

```c

```

## disassembly

```asm
0x32c0  ldarg.0
0x32c1  ldstr    aDeleteitem// "DeleteItem"
0x32c6  ldc.i4.1
0x32c7  newarr   [mscorlib]System.Object
0x32cc  dup
0x32cd  ldc.i4.0
0x32ce  ldarg.1
0x32cf  stelem.ref
0x32d0  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x32d5  pop
0x32d6  ret
```
