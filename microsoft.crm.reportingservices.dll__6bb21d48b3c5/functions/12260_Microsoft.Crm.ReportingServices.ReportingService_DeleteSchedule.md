# Microsoft.Crm.ReportingServices.ReportingService::DeleteSchedule

- ea: `0x12260`
- end: `0x12277`
- name: `Microsoft.Crm.ReportingServices.ReportingService::DeleteSchedule`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x12261`: `DeleteSchedule`

## pseudocode

```c

```

## disassembly

```asm
0x12260  ldarg.0
0x12261  ldstr    aDeleteschedule// "DeleteSchedule"
0x12266  ldc.i4.1
0x12267  newarr   [mscorlib]System.Object
0x1226c  dup
0x1226d  ldc.i4.0
0x1226e  ldarg.1
0x1226f  stelem.ref
0x12270  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x12275  pop
0x12276  ret
```
