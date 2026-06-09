# Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginCreateReportEditSession

- ea: `0x7980`
- end: `0x79a2`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginCreateReportEditSession`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x7981`: `CreateReportEditSession`

## pseudocode

```c

```

## disassembly

```asm
0x7980  ldarg.0
0x7981  ldstr    aCreatereported// "CreateReportEditSession"
0x7986  ldc.i4.3
0x7987  newarr   [mscorlib]System.Object
0x798c  dup
0x798d  ldc.i4.0
0x798e  ldarg.1
0x798f  stelem.ref
0x7990  dup
0x7991  ldc.i4.1
0x7992  ldarg.2
0x7993  stelem.ref
0x7994  dup
0x7995  ldc.i4.2
0x7996  ldarg.3
0x7997  stelem.ref
0x7998  ldarg.s  4
0x799a  ldarg.s  5
0x799c  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x79a1  ret
```
