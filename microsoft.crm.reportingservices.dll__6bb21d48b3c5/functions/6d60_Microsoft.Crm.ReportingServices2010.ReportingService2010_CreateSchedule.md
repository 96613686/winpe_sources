# Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateSchedule

- ea: `0x6d60`
- end: `0x6d85`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateSchedule`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x6d61`: `CreateSchedule`

## pseudocode

```c

```

## disassembly

```asm
0x6d60  ldarg.0
0x6d61  ldstr    aCreateschedule// "CreateSchedule"
0x6d66  ldc.i4.3
0x6d67  newarr   [mscorlib]System.Object
0x6d6c  dup
0x6d6d  ldc.i4.0
0x6d6e  ldarg.1
0x6d6f  stelem.ref
0x6d70  dup
0x6d71  ldc.i4.1
0x6d72  ldarg.2
0x6d73  stelem.ref
0x6d74  dup
0x6d75  ldc.i4.2
0x6d76  ldarg.3
0x6d77  stelem.ref
0x6d78  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x6d7d  ldc.i4.0
0x6d7e  ldelem.ref
0x6d7f  castclass [mscorlib]System.String
0x6d84  ret
```
