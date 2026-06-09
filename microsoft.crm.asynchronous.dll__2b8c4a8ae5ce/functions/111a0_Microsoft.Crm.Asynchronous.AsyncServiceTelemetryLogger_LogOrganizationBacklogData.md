# Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogOrganizationBacklogData

- ea: `0x111a0`
- end: `0x1126c`
- name: `Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogOrganizationBacklogData`
- size: `204`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x12780`

## callees

- `0x10090`
- `0x11150`
- `0x111a0`
- `0x11290`
- `0x11740`

## pseudocode

```c

```

## disassembly

```asm
0x111a0  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x111a5  stloc.0
0x111a6  ldarg.0
0x111a7  ldarg.1
0x111a8  ldloc.0
0x111a9  ldarg.3
0x111aa  call     instance void Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogBacklogEventHeader(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid telemetryActivityId, valuetype Microsoft.Crm.Asynchronous.QueueType queueType)
0x111af  ldc.i4.0
0x111b0  stloc.1
0x111b1  ldarg.2
0x111b2  stloc.2
0x111b3  ldc.i4.0
0x111b4  stloc.3
0x111b5  br       loc_11247
0x111ba  ldloc.2
0x111bb  ldloc.3
0x111bc  ldelem.ref
0x111bd  call     class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat>> Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::GetPayLoadStructure()
0x111c2  stloc.s  4
0x111c4  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Asynchronous.QueueStatistics::get_GetStatisticsDictionary()
0x111c9  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::GetEnumerator()
0x111ce  stloc.s  6
0x111d0  br.s     loc_111F5
0x111d2  ldloca.s 6
0x111d4  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, int32>::get_Current()
0x111d9  stloc.s  7
0x111db  ldloc.s  4
0x111dd  ldloca.s 7
0x111df  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, int32>::get_Key()
0x111e4  ldloca.s 7
0x111e6  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, int32>::get_Value()
0x111eb  call     class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IntJsonValueFormat [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryExtensions::ToJsonValueFormat(int32)
0x111f0  call     T0x2B00002C
0x111f5  ldloca.s 6
0x111f7  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, int32>::MoveNext()
0x111fc  brtrue.s loc_111D2
0x111fe  leave.s  loc_1120E
0x11200  ldloca.s 6
0x11202  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, int32>
0x11208  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1120d  endfinally
0x1120e  ldarga.s 3
0x11210  constrained. Microsoft.Crm.Asynchronous.QueueType
0x11216  callvirt instance string [mscorlib]System.Object::ToString()
0x1121b  ldstr    aQueuesample// "QueueSample"
0x11220  ldloca.s 1
0x11222  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x11227  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1122c  call     string [mscorlib]System.String::Concat(string, string, string)
0x11231  stloc.s  5
0x11233  ldarg.0
0x11234  ldloc.s  5
0x11236  ldarg.1
0x11237  ldloc.s  4
0x11239  ldloc.0
0x1123a  call     instance void Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::WriteTelemetryEventData(string eventName, valuetype [mscorlib]System.Guid organizationId, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat>> payload, valuetype [mscorlib]System.Guid telemetryActivityId)
0x1123f  ldloc.1
0x11240  ldc.i4.1
0x11241  add
0x11242  stloc.1
0x11243  ldloc.3
0x11244  ldc.i4.1
0x11245  add
0x11246  stloc.3
0x11247  ldloc.3
0x11248  ldloc.2
0x11249  ldlen
0x1124a  conv.i4
0x1124b  blt      loc_111BA
0x11250  call     class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryManager [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryManager::get_Instance()
0x11255  ldloc.0
0x11256  newobj   instance void [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryEventData::.ctor()
0x1125b  dup
0x1125c  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x11261  callvirt instance void [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryEventBase::set_StartTime(valuetype [mscorlib]System.DateTime)
0x11266  callvirt instance void [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryManager::FinishActivity(valuetype [mscorlib]System.Guid, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryEventData)
0x1126b  ret
```
