# Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginCreateDataSource

- ea: `0x4e40`
- end: `0x4e71`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginCreateDataSource`
- size: `49`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x4e41`: `CreateDataSource`

## pseudocode

```c

```

## disassembly

```asm
0x4e40  ldarg.0
0x4e41  ldstr    aCreatedatasour// "CreateDataSource"
0x4e46  ldc.i4.5
0x4e47  newarr   [mscorlib]System.Object
0x4e4c  dup
0x4e4d  ldc.i4.0
0x4e4e  ldarg.1
0x4e4f  stelem.ref
0x4e50  dup
0x4e51  ldc.i4.1
0x4e52  ldarg.2
0x4e53  stelem.ref
0x4e54  dup
0x4e55  ldc.i4.2
0x4e56  ldarg.3
0x4e57  box      [mscorlib]System.Boolean
0x4e5c  stelem.ref
0x4e5d  dup
0x4e5e  ldc.i4.3
0x4e5f  ldarg.s  4
0x4e61  stelem.ref
0x4e62  dup
0x4e63  ldc.i4.4
0x4e64  ldarg.s  5
0x4e66  stelem.ref
0x4e67  ldarg.s  6
0x4e69  ldarg.s  7
0x4e6b  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x4e70  ret
```
