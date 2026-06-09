# Microsoft.Crm.ReportingServices.ReportingService::GetSystemProperties

- ea: `0x10e40`
- end: `0x10e5d`
- name: `Microsoft.Crm.ReportingServices.ReportingService::GetSystemProperties`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x10e41`: `GetSystemProperties`

## pseudocode

```c

```

## disassembly

```asm
0x10e40  ldarg.0
0x10e41  ldstr    aGetsystemprope// "GetSystemProperties"
0x10e46  ldc.i4.1
0x10e47  newarr   [mscorlib]System.Object
0x10e4c  dup
0x10e4d  ldc.i4.0
0x10e4e  ldarg.1
0x10e4f  stelem.ref
0x10e50  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x10e55  ldc.i4.0
0x10e56  ldelem.ref
0x10e57  castclass class Microsoft.Crm.ReportingServices.Property[]
0x10e5c  ret
```
