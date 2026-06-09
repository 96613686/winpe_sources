# Microsoft.Crm.ReportingServices.ReportingService::MoveItem

- ea: `0x10f30`
- end: `0x10f4b`
- name: `Microsoft.Crm.ReportingServices.ReportingService::MoveItem`
- size: `27`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x10f31`: `MoveItem`

## pseudocode

```c

```

## disassembly

```asm
0x10f30  ldarg.0
0x10f31  ldstr    aMoveitem// "MoveItem"
0x10f36  ldc.i4.2
0x10f37  newarr   [mscorlib]System.Object
0x10f3c  dup
0x10f3d  ldc.i4.0
0x10f3e  ldarg.1
0x10f3f  stelem.ref
0x10f40  dup
0x10f41  ldc.i4.1
0x10f42  ldarg.2
0x10f43  stelem.ref
0x10f44  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x10f49  pop
0x10f4a  ret
```
