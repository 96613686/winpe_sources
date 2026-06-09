# Microsoft.Crm.Asynchronous.StatisticsSqmCollectorBase::UpdateStatisticRow

- ea: `0xc560`
- end: `0xc5cf`
- name: `Microsoft.Crm.Asynchronous.StatisticsSqmCollectorBase::UpdateStatisticRow`
- size: `111`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0xb750`

## string_xrefs

- `0xc5be`: `UpdateStatisticRow`

## pseudocode

```c

```

## disassembly

```asm
0xc560  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0xc565  stloc.0
0xc566  ldloc.0
0xc567  ldstr    aStatisticsdata// "StatisticsDataId"
0xc56c  ldarg.2
0xc56d  box      [mscorlib]System.Guid
0xc572  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xc577  ldloc.0
0xc578  ldstr    aStarttime// "StartTime"
0xc57d  ldarg.3
0xc57e  box      [mscorlib]System.DateTime
0xc583  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xc588  ldloc.0
0xc589  ldstr    aEndtime// "EndTime"
0xc58e  ldarg.s  4
0xc590  box      [mscorlib]System.DateTime
0xc595  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xc59a  ldloc.0
0xc59b  ldstr    aResult_0// "Result"
0xc5a0  ldarg.s  5
0xc5a2  box      [mscorlib]System.Int32
0xc5a7  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xc5ac  ldarg.1
0xc5ad  ldstr    aStatisticsdata_0// "StatisticsData"
0xc5b2  ldarg.2
0xc5b3  box      [mscorlib]System.Guid
0xc5b8  ldloc.0
0xc5b9  ldc.i4   0x98
0xc5be  ldstr    aUpdatestatisti// "UpdateStatisticRow"
0xc5c3  ldstr    aDDbsShDccm2110_16// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\5"...
0xc5c8  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::Update(string, object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0xc5cd  pop
0xc5ce  ret
```
