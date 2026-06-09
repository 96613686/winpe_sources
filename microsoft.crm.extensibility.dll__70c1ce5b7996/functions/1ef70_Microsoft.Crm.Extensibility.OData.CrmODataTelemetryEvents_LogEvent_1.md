# Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents::LogEvent_1

- ea: `0x1ef70`
- end: `0x1f01b`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents::LogEvent_1`
- size: `171`
- prototype: ``
- caller_count: `25`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x11bf0`
- `0x11c90`
- `0x11e10`
- `0x11eb0`
- `0x11f10`
- `0x12150`
- `0x12280`
- `0x123d0`
- `0x12490`
- `0x12570`
- `0x12610`
- `0x127d0`
- `0x128a0`
- `0x12940`
- `0x12a60`
- `0x12bb0`
- `0x12c10`
- `0x12d50`
- `0x12df0`
- `0x12e90`
- `0x12f30`
- `0x12fe0`
- `0x130f0`
- `0x131b0`
- `0x132a0`

## callees

- `0x1ef70`
- `0x1f020`

## string_xrefs

- `0x1efa6`: `CrmODataGetEntitySetCompleted`
- `0x1efb3`: `CrmODataPostEntitySetCompleted`

## pseudocode

```c

```

## disassembly

```asm
0x1ef70  ldarg.1
0x1ef71  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1ef76  brtrue.s loc_1EF88
0x1ef78  ldarg.2
0x1ef79  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1ef7e  brtrue.s loc_1EF88
0x1ef80  ldarg.3
0x1ef81  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1ef86  brfalse.s loc_1EF89
0x1ef88  ret
0x1ef89  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat>>::.ctor()
0x1ef8e  stloc.0
0x1ef8f  ldloc.0
0x1ef90  ldstr    aHttpverb// "httpVerb"
0x1ef95  ldarg.3
0x1ef96  call     class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.StringJsonValueFormat [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryExtensions::ToJsonValueFormat(string)
0x1ef9b  newobj   instance void valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat>::.ctor(var<u1>, !!T0)
0x1efa0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat>>::Add(var<u1>)
0x1efa5  ldarg.1
0x1efa6  ldstr    aCrmodatagetent_0// "CrmODataGetEntitySetCompleted"
0x1efab  callvirt instance bool [mscorlib]System.String::Equals(string)
0x1efb0  brtrue.s loc_1EFBF
0x1efb2  ldarg.1
0x1efb3  ldstr    aCrmodataposten// "CrmODataPostEntitySetCompleted"
0x1efb8  callvirt instance bool [mscorlib]System.String::Equals(string)
0x1efbd  brfalse.s loc_1EFD7
0x1efbf  ldloc.0
0x1efc0  ldstr    aEntitysetname// "entitySetName"
0x1efc5  ldarg.2
0x1efc6  call     class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.StringJsonValueFormat [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryExtensions::ToJsonValueFormat(string)
0x1efcb  newobj   instance void valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat>::.ctor(var<u1>, !!T0)
0x1efd0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat>>::Add(var<u1>)
0x1efd5  br.s     loc_1EFED
0x1efd7  ldloc.0
0x1efd8  ldstr    aEntityname_0// "entityName"
0x1efdd  ldarg.2
0x1efde  call     class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.StringJsonValueFormat [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryExtensions::ToJsonValueFormat(string)
0x1efe3  newobj   instance void valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat>::.ctor(var<u1>, !!T0)
0x1efe8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat>>::Add(var<u1>)
0x1efed  ldarg.s  4
0x1efef  brfalse.s loc_1F00F
0x1eff1  ldloc.0
0x1eff2  ldarg.s  4
0x1eff4  callvirt instance var<u1> class [mscorlib]System.Tuple`2<string, string>::get_Item1()
0x1eff9  ldarg.s  4
0x1effb  callvirt instance var<u1> class [mscorlib]System.Tuple`2<string, string>::get_Item2()
0x1f000  call     class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.StringJsonValueFormat [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryExtensions::ToJsonValueFormat(string)
0x1f005  newobj   instance void valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat>::.ctor(var<u1>, !!T0)
0x1f00a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat>>::Add(var<u1>)
0x1f00f  ldarg.0
0x1f010  ldarg.1
0x1f011  ldloc.0
0x1f012  ldarg.s  5
0x1f014  ldnull
0x1f015  call     instance void Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents::LogTelemetryEvent(string eventName, class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat>> infoPayload, class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken executionToken, class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat>> extraInfoPayload)
0x1f01a  ret
```
