# Microsoft.Crm.Asynchronous.Rollups.AsyncJobPostponeAgent::Execute

- ea: `0xced0`
- end: `0xcf4d`
- name: `Microsoft.Crm.Asynchronous.Rollups.AsyncJobPostponeAgent::Execute`
- size: `125`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0xc2b0`
- `0xc310`

## callees

- `0xced0`
- `0xcf50`
- `0xcfe0`

## pseudocode

```c

```

## disassembly

```asm
0xced0  ldarg.0
0xced1  ldfld    valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerEarlyExitRequest Microsoft.Crm.Asynchronous.Rollups.AsyncJobPostponeAgent::_earlyExitRequest
0xced6  brfalse.s loc_CF2B
0xced8  ldarg.0
0xced9  ldfld    valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerEarlyExitRequest Microsoft.Crm.Asynchronous.Rollups.AsyncJobPostponeAgent::_earlyExitRequest
0xcede  stloc.1
0xcedf  ldloc.1
0xcee0  ldc.i4.1
0xcee1  beq.s    loc_CEE9
0xcee3  ldloc.1
0xcee4  ldc.i4.2
0xcee5  beq.s    loc_CF0A
0xcee7  br.s     loc_CF2B
0xcee9  ldstr    aRequestedjobst// "RequestedJobState"
0xceee  ldarg.0
0xceef  ldflda   valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerEarlyExitRequest Microsoft.Crm.Asynchronous.Rollups.AsyncJobPostponeAgent::_earlyExitRequest
0xcef4  constrained. [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerEarlyExitRequest
0xcefa  callvirt instance string [mscorlib]System.Object::ToString()
0xceff  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0xcf04  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncPausedResult::.ctor()
0xcf09  ret
0xcf0a  ldstr    aRequestedjobst// "RequestedJobState"
0xcf0f  ldarg.0
0xcf10  ldflda   valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerEarlyExitRequest Microsoft.Crm.Asynchronous.Rollups.AsyncJobPostponeAgent::_earlyExitRequest
0xcf15  constrained. [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerEarlyExitRequest
0xcf1b  callvirt instance string [mscorlib]System.Object::ToString()
0xcf20  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0xcf25  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncCanceledResult::.ctor()
0xcf2a  ret
0xcf2b  ldarg.0
0xcf2c  call     instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.Rollups.AsyncJobPostponeAgent::GetNearestPostponeTime()
0xcf31  stloc.0
0xcf32  ldloc.0
0xcf33  ldarg.0
0xcf34  call     instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.Rollups.AsyncJobPostponeAgent::get_DateTimeEpoch()
0xcf39  call     bool [mscorlib]System.DateTime::op_Inequality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0xcf3e  brfalse.s loc_CF47
0xcf40  ldloc.0
0xcf41  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncPausedResult::.ctor(valuetype [mscorlib]System.DateTime)
0xcf46  ret
0xcf47  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSucceededResult::.ctor()
0xcf4c  ret
```
