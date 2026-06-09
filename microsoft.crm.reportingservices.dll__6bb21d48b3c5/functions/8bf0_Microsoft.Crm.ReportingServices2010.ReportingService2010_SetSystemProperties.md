# Microsoft.Crm.ReportingServices2010.ReportingService2010::SetSystemProperties

- ea: `0x8bf0`
- end: `0x8c07`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::SetSystemProperties`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x8bf1`: `SetSystemProperties`

## pseudocode

```c

```

## disassembly

```asm
0x8bf0  ldarg.0
0x8bf1  ldstr    aSetsystemprope// "SetSystemProperties"
0x8bf6  ldc.i4.1
0x8bf7  newarr   [mscorlib]System.Object
0x8bfc  dup
0x8bfd  ldc.i4.0
0x8bfe  ldarg.1
0x8bff  stelem.ref
0x8c00  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x8c05  pop
0x8c06  ret
```
