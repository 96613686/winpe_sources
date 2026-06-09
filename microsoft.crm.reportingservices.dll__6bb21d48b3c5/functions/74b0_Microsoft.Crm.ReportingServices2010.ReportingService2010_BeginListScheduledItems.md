# Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginListScheduledItems

- ea: `0x74b0`
- end: `0x74c8`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginListScheduledItems`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x74b1`: `ListScheduledItems`

## pseudocode

```c

```

## disassembly

```asm
0x74b0  ldarg.0
0x74b1  ldstr    aListscheduledi// "ListScheduledItems"
0x74b6  ldc.i4.1
0x74b7  newarr   [mscorlib]System.Object
0x74bc  dup
0x74bd  ldc.i4.0
0x74be  ldarg.1
0x74bf  stelem.ref
0x74c0  ldarg.2
0x74c1  ldarg.3
0x74c2  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x74c7  ret
```
