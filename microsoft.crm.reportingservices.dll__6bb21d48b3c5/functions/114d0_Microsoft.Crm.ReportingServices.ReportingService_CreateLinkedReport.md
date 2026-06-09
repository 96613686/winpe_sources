# Microsoft.Crm.ReportingServices.ReportingService::CreateLinkedReport

- ea: `0x114d0`
- end: `0x114f4`
- name: `Microsoft.Crm.ReportingServices.ReportingService::CreateLinkedReport`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x114d1`: `CreateLinkedReport`

## pseudocode

```c

```

## disassembly

```asm
0x114d0  ldarg.0
0x114d1  ldstr    aCreatelinkedre// "CreateLinkedReport"
0x114d6  ldc.i4.4
0x114d7  newarr   [mscorlib]System.Object
0x114dc  dup
0x114dd  ldc.i4.0
0x114de  ldarg.1
0x114df  stelem.ref
0x114e0  dup
0x114e1  ldc.i4.1
0x114e2  ldarg.2
0x114e3  stelem.ref
0x114e4  dup
0x114e5  ldc.i4.2
0x114e6  ldarg.3
0x114e7  stelem.ref
0x114e8  dup
0x114e9  ldc.i4.3
0x114ea  ldarg.s  4
0x114ec  stelem.ref
0x114ed  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x114f2  pop
0x114f3  ret
```
