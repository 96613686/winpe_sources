# Microsoft.Crm.ReportingServices2010.ReportingService2010::DeleteSchedule

- ea: `0x6e60`
- end: `0x6e77`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::DeleteSchedule`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x6e61`: `DeleteSchedule`

## pseudocode

```c

```

## disassembly

```asm
0x6e60  ldarg.0
0x6e61  ldstr    aDeleteschedule// "DeleteSchedule"
0x6e66  ldc.i4.1
0x6e67  newarr   [mscorlib]System.Object
0x6e6c  dup
0x6e6d  ldc.i4.0
0x6e6e  ldarg.1
0x6e6f  stelem.ref
0x6e70  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x6e75  pop
0x6e76  ret
```
