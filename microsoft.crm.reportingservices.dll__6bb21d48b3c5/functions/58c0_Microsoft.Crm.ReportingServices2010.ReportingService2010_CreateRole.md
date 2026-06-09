# Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateRole

- ea: `0x58c0`
- end: `0x58df`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateRole`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x58c1`: `CreateRole`

## pseudocode

```c

```

## disassembly

```asm
0x58c0  ldarg.0
0x58c1  ldstr    aCreaterole// "CreateRole"
0x58c6  ldc.i4.3
0x58c7  newarr   [mscorlib]System.Object
0x58cc  dup
0x58cd  ldc.i4.0
0x58ce  ldarg.1
0x58cf  stelem.ref
0x58d0  dup
0x58d1  ldc.i4.1
0x58d2  ldarg.2
0x58d3  stelem.ref
0x58d4  dup
0x58d5  ldc.i4.2
0x58d6  ldarg.3
0x58d7  stelem.ref
0x58d8  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x58dd  pop
0x58de  ret
```
