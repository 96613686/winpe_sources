# Microsoft.Crm.ReportingServices.ReportingService::CreateRole

- ea: `0x12d30`
- end: `0x12d4f`
- name: `Microsoft.Crm.ReportingServices.ReportingService::CreateRole`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x12d31`: `CreateRole`

## pseudocode

```c

```

## disassembly

```asm
0x12d30  ldarg.0
0x12d31  ldstr    aCreaterole// "CreateRole"
0x12d36  ldc.i4.3
0x12d37  newarr   [mscorlib]System.Object
0x12d3c  dup
0x12d3d  ldc.i4.0
0x12d3e  ldarg.1
0x12d3f  stelem.ref
0x12d40  dup
0x12d41  ldc.i4.1
0x12d42  ldarg.2
0x12d43  stelem.ref
0x12d44  dup
0x12d45  ldc.i4.2
0x12d46  ldarg.3
0x12d47  stelem.ref
0x12d48  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x12d4d  pop
0x12d4e  ret
```
