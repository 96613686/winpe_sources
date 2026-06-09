# Microsoft.Crm.ReportingServices.ReportingService::CreateDataSource

- ea: `0x11b70`
- end: `0x11b9e`
- name: `Microsoft.Crm.ReportingServices.ReportingService::CreateDataSource`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x11b71`: `CreateDataSource`

## pseudocode

```c

```

## disassembly

```asm
0x11b70  ldarg.0
0x11b71  ldstr    aCreatedatasour// "CreateDataSource"
0x11b76  ldc.i4.5
0x11b77  newarr   [mscorlib]System.Object
0x11b7c  dup
0x11b7d  ldc.i4.0
0x11b7e  ldarg.1
0x11b7f  stelem.ref
0x11b80  dup
0x11b81  ldc.i4.1
0x11b82  ldarg.2
0x11b83  stelem.ref
0x11b84  dup
0x11b85  ldc.i4.2
0x11b86  ldarg.3
0x11b87  box      [mscorlib]System.Boolean
0x11b8c  stelem.ref
0x11b8d  dup
0x11b8e  ldc.i4.3
0x11b8f  ldarg.s  4
0x11b91  stelem.ref
0x11b92  dup
0x11b93  ldc.i4.4
0x11b94  ldarg.s  5
0x11b96  stelem.ref
0x11b97  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x11b9c  pop
0x11b9d  ret
```
