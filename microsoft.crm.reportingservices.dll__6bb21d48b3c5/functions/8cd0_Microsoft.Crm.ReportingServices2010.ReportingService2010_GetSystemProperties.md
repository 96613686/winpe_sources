# Microsoft.Crm.ReportingServices2010.ReportingService2010::GetSystemProperties

- ea: `0x8cd0`
- end: `0x8ced`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::GetSystemProperties`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x8cd1`: `GetSystemProperties`

## pseudocode

```c

```

## disassembly

```asm
0x8cd0  ldarg.0
0x8cd1  ldstr    aGetsystemprope// "GetSystemProperties"
0x8cd6  ldc.i4.1
0x8cd7  newarr   [mscorlib]System.Object
0x8cdc  dup
0x8cdd  ldc.i4.0
0x8cde  ldarg.1
0x8cdf  stelem.ref
0x8ce0  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x8ce5  ldc.i4.0
0x8ce6  ldelem.ref
0x8ce7  castclass class Microsoft.Crm.ReportingServices2010.Property[]
0x8cec  ret
```
