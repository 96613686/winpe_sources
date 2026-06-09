# Microsoft.Crm.Asynchronous.QueueStatisticsHelper::WriteToTelemetry

- ea: `0x12780`
- end: `0x127be`
- name: `Microsoft.Crm.Asynchronous.QueueStatisticsHelper::WriteToTelemetry`
- size: `62`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x23f0`
- `0x57d0`
- `0x7bc0`

## callees

- `0xff10`
- `0x10900`
- `0x111a0`
- `0x12780`

## pseudocode

```c

```

## disassembly

```asm
0x12780  ldarg.1
0x12781  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid>::GetEnumerator()
0x12786  stloc.0
0x12787  br.s     loc_127A9
0x12789  ldloc.0
0x1278a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Guid>::get_Current()
0x1278f  stloc.1
0x12790  call     class Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::get_Instance()
0x12795  ldloc.1
0x12796  ldarg.2
0x12797  ldloc.1
0x12798  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.OrgStatistics>::get_Item(void)
0x1279d  ldarg.3
0x1279e  callvirt instance class Microsoft.Crm.Asynchronous.QueueStatistics[] Microsoft.Crm.Asynchronous.OrgStatistics::GetQueueSamples(valuetype Microsoft.Crm.Asynchronous.QueueType queueType)
0x127a3  ldarg.3
0x127a4  callvirt instance void Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogOrganizationBacklogData(valuetype [mscorlib]System.Guid organizationId, class Microsoft.Crm.Asynchronous.QueueStatistics[] statisticSamples, valuetype Microsoft.Crm.Asynchronous.QueueType queueType)
0x127a9  ldloc.0
0x127aa  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x127af  brtrue.s loc_12789
0x127b1  leave.s  loc_127BD
0x127b3  ldloc.0
0x127b4  brfalse.s loc_127BC
0x127b6  ldloc.0
0x127b7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x127bc  endfinally
0x127bd  ret
```
