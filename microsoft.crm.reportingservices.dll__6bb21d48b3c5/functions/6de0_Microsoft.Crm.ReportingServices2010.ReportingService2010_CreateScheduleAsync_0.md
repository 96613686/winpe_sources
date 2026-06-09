# Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateScheduleAsync_0

- ea: `0x6de0`
- end: `0x6e20`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateScheduleAsync_0`
- size: `64`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x6dd0`

## callees

- `0x6de0`

## string_xrefs

- `0x6dfb`: `CreateSchedule`

## pseudocode

```c

```

## disassembly

```asm
0x6de0  ldarg.0
0x6de1  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateScheduleOperationCompleted
0x6de6  brtrue.s loc_6DFA
0x6de8  ldarg.0
0x6de9  ldarg.0
0x6dea  ldftn    instance void Microsoft.Crm.ReportingServices2010.ReportingService2010::OnCreateScheduleOperationCompleted(object arg)
0x6df0  newobj   instance void [mscorlib]System.Threading.SendOrPostCallback::.ctor(object, native int)
0x6df5  stfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateScheduleOperationCompleted
0x6dfa  ldarg.0
0x6dfb  ldstr    aCreateschedule// "CreateSchedule"
0x6e00  ldc.i4.3
0x6e01  newarr   [mscorlib]System.Object
0x6e06  dup
0x6e07  ldc.i4.0
0x6e08  ldarg.1
0x6e09  stelem.ref
0x6e0a  dup
0x6e0b  ldc.i4.1
0x6e0c  ldarg.2
0x6e0d  stelem.ref
0x6e0e  dup
0x6e0f  ldc.i4.2
0x6e10  ldarg.3
0x6e11  stelem.ref
0x6e12  ldarg.0
0x6e13  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateScheduleOperationCompleted
0x6e18  ldarg.s  4
0x6e1a  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::InvokeAsync(string, object[], class [mscorlib]System.Threading.SendOrPostCallback, object)
0x6e1f  ret
```
