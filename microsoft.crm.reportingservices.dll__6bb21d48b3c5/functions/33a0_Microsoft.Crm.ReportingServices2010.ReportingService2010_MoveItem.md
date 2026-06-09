# Microsoft.Crm.ReportingServices2010.ReportingService2010::MoveItem

- ea: `0x33a0`
- end: `0x33bb`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::MoveItem`
- size: `27`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x33a1`: `MoveItem`

## pseudocode

```c

```

## disassembly

```asm
0x33a0  ldarg.0
0x33a1  ldstr    aMoveitem// "MoveItem"
0x33a6  ldc.i4.2
0x33a7  newarr   [mscorlib]System.Object
0x33ac  dup
0x33ad  ldc.i4.0
0x33ae  ldarg.1
0x33af  stelem.ref
0x33b0  dup
0x33b1  ldc.i4.1
0x33b2  ldarg.2
0x33b3  stelem.ref
0x33b4  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x33b9  pop
0x33ba  ret
```
