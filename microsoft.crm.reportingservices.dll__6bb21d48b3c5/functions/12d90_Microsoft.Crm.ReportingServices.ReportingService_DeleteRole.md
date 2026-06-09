# Microsoft.Crm.ReportingServices.ReportingService::DeleteRole

- ea: `0x12d90`
- end: `0x12da7`
- name: `Microsoft.Crm.ReportingServices.ReportingService::DeleteRole`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x12d91`: `DeleteRole`

## pseudocode

```c

```

## disassembly

```asm
0x12d90  ldarg.0
0x12d91  ldstr    aDeleterole// "DeleteRole"
0x12d96  ldc.i4.1
0x12d97  newarr   [mscorlib]System.Object
0x12d9c  dup
0x12d9d  ldc.i4.0
0x12d9e  ldarg.1
0x12d9f  stelem.ref
0x12da0  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x12da5  pop
0x12da6  ret
```
