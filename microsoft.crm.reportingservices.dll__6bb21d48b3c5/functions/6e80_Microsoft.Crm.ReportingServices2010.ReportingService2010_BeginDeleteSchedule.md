# Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginDeleteSchedule

- ea: `0x6e80`
- end: `0x6e98`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginDeleteSchedule`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x6e81`: `DeleteSchedule`

## pseudocode

```c

```

## disassembly

```asm
0x6e80  ldarg.0
0x6e81  ldstr    aDeleteschedule// "DeleteSchedule"
0x6e86  ldc.i4.1
0x6e87  newarr   [mscorlib]System.Object
0x6e8c  dup
0x6e8d  ldc.i4.0
0x6e8e  ldarg.1
0x6e8f  stelem.ref
0x6e90  ldarg.2
0x6e91  ldarg.3
0x6e92  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x6e97  ret
```
