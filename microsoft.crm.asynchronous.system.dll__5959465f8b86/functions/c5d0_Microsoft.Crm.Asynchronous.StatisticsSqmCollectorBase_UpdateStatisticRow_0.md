# Microsoft.Crm.Asynchronous.StatisticsSqmCollectorBase::UpdateStatisticRow_0

- ea: `0xc5d0`
- end: `0xc61b`
- name: `Microsoft.Crm.Asynchronous.StatisticsSqmCollectorBase::UpdateStatisticRow_0`
- size: `75`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0xb370`

## string_xrefs

- `0xc60a`: `UpdateStatisticRow`

## pseudocode

```c

```

## disassembly

```asm
0xc5d0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0xc5d5  stloc.0
0xc5d6  ldloc.0
0xc5d7  ldstr    aStatisticsdata// "StatisticsDataId"
0xc5dc  ldarg.2
0xc5dd  box      [mscorlib]System.Guid
0xc5e2  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xc5e7  ldloc.0
0xc5e8  ldstr    aResult_0// "Result"
0xc5ed  ldarg.3
0xc5ee  box      [mscorlib]System.Int32
0xc5f3  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xc5f8  ldarg.1
0xc5f9  ldstr    aStatisticsdata_0// "StatisticsData"
0xc5fe  ldarg.2
0xc5ff  box      [mscorlib]System.Guid
0xc604  ldloc.0
0xc605  ldc.i4   0xA1
0xc60a  ldstr    aUpdatestatisti// "UpdateStatisticRow"
0xc60f  ldstr    aDDbsShDccm2110_16// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\5"...
0xc614  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::Update(string, object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0xc619  pop
0xc61a  ret
```
