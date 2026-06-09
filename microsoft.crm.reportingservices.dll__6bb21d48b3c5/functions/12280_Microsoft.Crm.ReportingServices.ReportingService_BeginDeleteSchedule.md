# Microsoft.Crm.ReportingServices.ReportingService::BeginDeleteSchedule

- ea: `0x12280`
- end: `0x12298`
- name: `Microsoft.Crm.ReportingServices.ReportingService::BeginDeleteSchedule`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x12281`: `DeleteSchedule`

## pseudocode

```c

```

## disassembly

```asm
0x12280  ldarg.0
0x12281  ldstr    aDeleteschedule// "DeleteSchedule"
0x12286  ldc.i4.1
0x12287  newarr   [mscorlib]System.Object
0x1228c  dup
0x1228d  ldc.i4.0
0x1228e  ldarg.1
0x1228f  stelem.ref
0x12290  ldarg.2
0x12291  ldarg.3
0x12292  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x12297  ret
```
