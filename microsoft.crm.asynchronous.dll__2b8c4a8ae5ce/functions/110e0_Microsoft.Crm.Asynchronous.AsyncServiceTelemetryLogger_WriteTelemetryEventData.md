# Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::WriteTelemetryEventData

- ea: `0x110e0`
- end: `0x11150`
- name: `Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::WriteTelemetryEventData`
- size: `112`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x10ea0`
- `0x11080`

## callees

- `0x110e0`
- `0x118c0`
- `0x11900`
- `0x121e0`
- `0x12200`

## pseudocode

```c

```

## disassembly

```asm
0x110e0  ldarg.1
0x110e1  brtrue.s loc_110E4
0x110e3  ret
0x110e4  call     class Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLoggingEvaluator Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLoggingEvaluator::get_Instance()
0x110e9  ldarg.1
0x110ea  callvirt instance bool Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLoggingEvaluator::IsSystemJob(class Microsoft.Crm.Asynchronous.IAsyncEvent asyncEvent)
0x110ef  brfalse.s loc_110F9
0x110f1  ldarg.s  4
0x110f3  ldc.i4.s 0x32
0x110f5  conv.i8
0x110f6  bgt.s    loc_110F9
0x110f8  ret
0x110f9  newobj   instance void [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryEventData::.ctor()
0x110fe  dup
0x110ff  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x11104  callvirt instance void [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryEventBase::set_StartTime(valuetype [mscorlib]System.DateTime)
0x11109  dup
0x1110a  ldarg.2
0x1110b  callvirt instance void [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryEventData::set_EventName(string)
0x11110  dup
0x11111  ldarg.s  4
0x11113  callvirt instance void [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryEventData::set_ExecutionTimeMilliseconds(int64)
0x11118  dup
0x11119  ldarg.3
0x1111a  callvirt instance void [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryEventBase::set_EventPayload(class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat>>)
0x1111f  dup
0x11120  ldc.i4.2
0x11121  callvirt instance void [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryEventBase::set_PayloadType(valuetype [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.PayloadType)
0x11126  dup
0x11127  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryContext::.ctor()
0x1112c  dup
0x1112d  ldarg.1
0x1112e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.IAsyncEvent::get_OrganizationId()
0x11133  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryContext::set_OrganizationId(valuetype [mscorlib]System.Guid)
0x11138  callvirt instance void [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryEventBase::set_Context(class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.ITelemetryContext)
0x1113d  stloc.0
0x1113e  call     class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryManager [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryManager::get_Instance()
0x11143  ldarg.1
0x11144  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.IAsyncEvent::get_TelemetryActivityId()
0x11149  ldloc.0
0x1114a  callvirt instance void [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryManager::AddDataPointToActivity(valuetype [mscorlib]System.Guid, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryEventData)
0x1114f  ret
```
