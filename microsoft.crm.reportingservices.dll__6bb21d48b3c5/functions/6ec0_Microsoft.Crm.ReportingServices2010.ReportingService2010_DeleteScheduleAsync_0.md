# Microsoft.Crm.ReportingServices2010.ReportingService2010::DeleteScheduleAsync_0

- ea: `0x6ec0`
- end: `0x6ef7`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::DeleteScheduleAsync_0`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x6eb0`

## callees

- `0x6ec0`

## string_xrefs

- `0x6edb`: `DeleteSchedule`

## pseudocode

```c

```

## disassembly

```asm
0x6ec0  ldarg.0
0x6ec1  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::DeleteScheduleOperationCompleted
0x6ec6  brtrue.s loc_6EDA
0x6ec8  ldarg.0
0x6ec9  ldarg.0
0x6eca  ldftn    instance void Microsoft.Crm.ReportingServices2010.ReportingService2010::OnDeleteScheduleOperationCompleted(object arg)
0x6ed0  newobj   instance void [mscorlib]System.Threading.SendOrPostCallback::.ctor(object, native int)
0x6ed5  stfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::DeleteScheduleOperationCompleted
0x6eda  ldarg.0
0x6edb  ldstr    aDeleteschedule// "DeleteSchedule"
0x6ee0  ldc.i4.1
0x6ee1  newarr   [mscorlib]System.Object
0x6ee6  dup
0x6ee7  ldc.i4.0
0x6ee8  ldarg.1
0x6ee9  stelem.ref
0x6eea  ldarg.0
0x6eeb  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::DeleteScheduleOperationCompleted
0x6ef0  ldarg.2
0x6ef1  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::InvokeAsync(string, object[], class [mscorlib]System.Threading.SendOrPostCallback, object)
0x6ef6  ret
```
