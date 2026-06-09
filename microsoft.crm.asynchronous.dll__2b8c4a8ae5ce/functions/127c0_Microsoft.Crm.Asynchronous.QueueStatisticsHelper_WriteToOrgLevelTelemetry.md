# Microsoft.Crm.Asynchronous.QueueStatisticsHelper::WriteToOrgLevelTelemetry

- ea: `0x127c0`
- end: `0x1282a`
- name: `Microsoft.Crm.Asynchronous.QueueStatisticsHelper::WriteToOrgLevelTelemetry`
- size: `106`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x57d0`

## callees

- `0xfdf0`
- `0xff30`
- `0x10900`
- `0x11270`
- `0x127c0`
- `0x12830`

## pseudocode

```c

```

## disassembly

```asm
0x127c0  ldarg.1
0x127c1  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.OrgStatistics>::get_Keys()
0x127c6  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.OrgStatistics>::GetEnumerator()
0x127cb  stloc.0
0x127cc  br.s     loc_12810
0x127ce  ldloca.s 0
0x127d0  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.OrgStatistics>::get_Current()
0x127d5  stloc.1
0x127d6  ldc.i4.0
0x127d7  stloc.2
0x127d8  ldarg.1
0x127d9  ldloc.1
0x127da  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.OrgStatistics>::get_Item(void)
0x127df  ldc.i4.0
0x127e0  callvirt instance bool Microsoft.Crm.Asynchronous.OrgStatistics::IsQueueBackloggedForExtendedPeriod(valuetype Microsoft.Crm.Asynchronous.QueueType queueType)
0x127e5  brfalse.s loc_12803
0x127e7  ldarg.1
0x127e8  ldloc.1
0x127e9  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.OrgStatistics>::get_Item(void)
0x127ee  ldarg.2
0x127ef  callvirt instance class Microsoft.Crm.Asynchronous.QueueStatistics[] Microsoft.Crm.Asynchronous.OrgStatistics::GetQueueSamplesInReverse(valuetype Microsoft.Crm.Asynchronous.QueueType queueType)
0x127f4  stloc.3
0x127f5  ldarg.0
0x127f6  ldloc.3
0x127f7  ldstr    aBacklogvolume// "BacklogVolume"
0x127fc  ldarg.2
0x127fd  call     instance int32 Microsoft.Crm.Asynchronous.QueueStatisticsHelper::GetSampleValue(class Microsoft.Crm.Asynchronous.QueueStatistics[] backlogStats, string statName, int32 index)
0x12802  stloc.2
0x12803  call     class Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::get_Instance()
0x12808  ldloc.1
0x12809  ldloc.2
0x1280a  ldarg.2
0x1280b  callvirt instance void Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogOrganizationBacklogs(valuetype [mscorlib]System.Guid organizationId, int32 orgBacklogCount, valuetype Microsoft.Crm.Asynchronous.QueueType queueType)
0x12810  ldloca.s 0
0x12812  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.OrgStatistics>::MoveNext()
0x12817  brtrue.s loc_127CE
0x12819  leave.s  loc_12829
0x1281b  ldloca.s 0
0x1281d  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.OrgStatistics>
0x12823  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x12828  endfinally
0x12829  ret
```
