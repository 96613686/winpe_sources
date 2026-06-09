# Microsoft.Crm.ReportingServices.ReportingService::SetSystemProperties

- ea: `0x10e90`
- end: `0x10ea7`
- name: `Microsoft.Crm.ReportingServices.ReportingService::SetSystemProperties`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x10e91`: `SetSystemProperties`

## pseudocode

```c

```

## disassembly

```asm
0x10e90  ldarg.0
0x10e91  ldstr    aSetsystemprope// "SetSystemProperties"
0x10e96  ldc.i4.1
0x10e97  newarr   [mscorlib]System.Object
0x10e9c  dup
0x10e9d  ldc.i4.0
0x10e9e  ldarg.1
0x10e9f  stelem.ref
0x10ea0  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x10ea5  pop
0x10ea6  ret
```
