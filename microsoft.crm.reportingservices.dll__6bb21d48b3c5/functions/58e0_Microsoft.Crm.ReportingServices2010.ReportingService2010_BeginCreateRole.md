# Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginCreateRole

- ea: `0x58e0`
- end: `0x5902`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginCreateRole`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x58e1`: `CreateRole`

## pseudocode

```c

```

## disassembly

```asm
0x58e0  ldarg.0
0x58e1  ldstr    aCreaterole// "CreateRole"
0x58e6  ldc.i4.3
0x58e7  newarr   [mscorlib]System.Object
0x58ec  dup
0x58ed  ldc.i4.0
0x58ee  ldarg.1
0x58ef  stelem.ref
0x58f0  dup
0x58f1  ldc.i4.1
0x58f2  ldarg.2
0x58f3  stelem.ref
0x58f4  dup
0x58f5  ldc.i4.2
0x58f6  ldarg.3
0x58f7  stelem.ref
0x58f8  ldarg.s  4
0x58fa  ldarg.s  5
0x58fc  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x5901  ret
```
