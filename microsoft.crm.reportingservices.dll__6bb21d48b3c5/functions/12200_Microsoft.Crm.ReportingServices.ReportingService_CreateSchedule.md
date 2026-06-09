# Microsoft.Crm.ReportingServices.ReportingService::CreateSchedule

- ea: `0x12200`
- end: `0x12221`
- name: `Microsoft.Crm.ReportingServices.ReportingService::CreateSchedule`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x12201`: `CreateSchedule`

## pseudocode

```c

```

## disassembly

```asm
0x12200  ldarg.0
0x12201  ldstr    aCreateschedule// "CreateSchedule"
0x12206  ldc.i4.2
0x12207  newarr   [mscorlib]System.Object
0x1220c  dup
0x1220d  ldc.i4.0
0x1220e  ldarg.1
0x1220f  stelem.ref
0x12210  dup
0x12211  ldc.i4.1
0x12212  ldarg.2
0x12213  stelem.ref
0x12214  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x12219  ldc.i4.0
0x1221a  ldelem.ref
0x1221b  castclass [mscorlib]System.String
0x12220  ret
```
