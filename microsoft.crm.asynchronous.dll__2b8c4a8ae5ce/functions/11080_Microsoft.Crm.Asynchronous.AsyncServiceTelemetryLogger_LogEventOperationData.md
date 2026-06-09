# Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogEventOperationData

- ea: `0x11080`
- end: `0x110c0`
- name: `Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogEventOperationData`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x11080`
- `0x110e0`
- `0x11740`

## string_xrefs

- `0x1109b`: `PluginTypeName`

## pseudocode

```c

```

## disassembly

```asm
0x11080  ldarg.1
0x11081  brfalse.s loc_11086
0x11083  ldarg.2
0x11084  brtrue.s loc_11087
0x11086  ret
0x11087  call     class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat>> Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::GetPayLoadStructure()
0x1108c  stloc.0
0x1108d  ldarg.2
0x1108e  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeData::get_PluginTypeName()
0x11093  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x11098  brtrue.s loc_110B0
0x1109a  ldloc.0
0x1109b  ldstr    aPlugintypename// "PluginTypeName"
0x110a0  ldarg.2
0x110a1  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeData::get_PluginTypeName()
0x110a6  call     class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.StringJsonValueFormat [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryExtensions::ToJsonValueFormat(string)
0x110ab  call     T0x2B00002A
0x110b0  ldarg.0
0x110b1  ldarg.1
0x110b2  ldstr    aAsynceventoper// "AsyncEventOperation"
0x110b7  ldloc.0
0x110b8  ldc.i4.0
0x110b9  conv.i8
0x110ba  call     instance void Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::WriteTelemetryEventData(class Microsoft.Crm.Asynchronous.IAsyncEvent asyncEvent, string eventName, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat>> payload, [opt] int64 executionTimeMs)
0x110bf  ret
```
