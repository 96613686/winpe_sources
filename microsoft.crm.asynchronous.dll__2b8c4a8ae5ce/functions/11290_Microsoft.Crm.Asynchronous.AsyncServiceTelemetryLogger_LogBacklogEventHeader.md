# Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogBacklogEventHeader

- ea: `0x11290`
- end: `0x1132b`
- name: `Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogBacklogEventHeader`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x111a0`

## callees

- `0x11740`

## pseudocode

```c

```

## disassembly

```asm
0x11290  call     class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat>> Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::GetPayLoadStructure()
0x11295  stloc.0
0x11296  ldloc.0
0x11297  ldstr    aAsyncorganizat_1// "AsyncOrganizationBacklog"
0x1129c  ldarga.s 1
0x1129e  constrained. [mscorlib]System.Guid
0x112a4  callvirt instance string [mscorlib]System.Object::ToString()
0x112a9  call     class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.StringJsonValueFormat [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryExtensions::ToJsonValueFormat(string)
0x112ae  call     T0x2B00002A
0x112b3  newobj   instance void [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryEventHeader::.ctor()
0x112b8  dup
0x112b9  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x112be  callvirt instance void [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryEventBase::set_StartTime(valuetype [mscorlib]System.DateTime)
0x112c3  dup
0x112c4  ldarg.1
0x112c5  callvirt instance void [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryEventHeader::set_OrganizationId(valuetype [mscorlib]System.Guid)
0x112ca  dup
0x112cb  ldloc.0
0x112cc  callvirt instance void [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryEventBase::set_EventPayload(class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat>>)
0x112d1  dup
0x112d2  ldc.i4.2
0x112d3  callvirt instance void [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryEventBase::set_PayloadType(valuetype [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.PayloadType)
0x112d8  dup
0x112d9  ldstr    aAsync// "Async"
0x112de  callvirt instance void [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryEventHeader::set_ClientType(string)
0x112e3  dup
0x112e4  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryContext::.ctor()
0x112e9  dup
0x112ea  ldarg.1
0x112eb  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryContext::set_OrganizationId(valuetype [mscorlib]System.Guid)
0x112f0  callvirt instance void [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryEventBase::set_Context(class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.ITelemetryContext)
0x112f5  stloc.1
0x112f6  call     class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryManager [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryManager::get_Instance()
0x112fb  newobj   instance void [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryActivity::.ctor()
0x11300  dup
0x11301  ldarg.2
0x11302  callvirt instance void [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryActivity::set_Id(valuetype [mscorlib]System.Guid)
0x11307  dup
0x11308  ldstr    aAsyncbacklog// "AsyncBacklog"
0x1130d  ldarga.s 3
0x1130f  constrained. Microsoft.Crm.Asynchronous.QueueType
0x11315  callvirt instance string [mscorlib]System.Object::ToString()
0x1131a  call     string [mscorlib]System.String::Concat(string, string)
0x1131f  callvirt instance void [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryActivity::set_Name(string)
0x11324  ldloc.1
0x11325  callvirt instance void [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryManager::StartActivity(class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.ITelemetryActivity, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryEventHeader)
0x1132a  ret
```
