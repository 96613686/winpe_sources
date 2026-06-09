# Microsoft.Crm.StatisticsDatabase.StatisticsAdministrator::DeleteOrganizationFromStatisticsDatabase

- ea: `0x437e0`
- end: `0x4384a`
- name: `Microsoft.Crm.StatisticsDatabase.StatisticsAdministrator::DeleteOrganizationFromStatisticsDatabase`
- size: `106`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x437e0`
- `0x438f0`
- `0x44400`
- `0x44510`
- `0x64b90`
- `0x64ba0`

## string_xrefs

- `0x43815`: `D:\a\1\s\src\Platform\Core\DataServices\StatsDB\ObjectModel\StatisticsAdministrator.cs`
- `0x43833`: `D:\a\1\s\src\Platform\Core\DataServices\StatsDB\ObjectModel\StatisticsAdministrator.cs`
- `0x43810`: `DeleteOrganizationFromStatisticsDatabase`
- `0x4382e`: `DeleteOrganizationFromStatisticsDatabase`

## pseudocode

```c

```

## disassembly

```asm
0x437e0  ldarg.0
0x437e1  call     class Microsoft.Crm.SharedDatabase.IDatabaseService Microsoft.Crm.StatisticsDatabase.StatisticsDatabaseService::NewService(valuetype [mscorlib]System.Guid scaleGroup)
0x437e6  stloc.0
0x437e7  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0x437ec  stloc.1
0x437ed  ldloc.1
0x437ee  ldstr    aOrganizationid_1// "OrganizationId"
0x437f3  ldarg.1
0x437f4  box      [mscorlib]System.Guid
0x437f9  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x437fe  ldloc.0
0x437ff  ldstr    aStatisticsdata// "StatisticsData"
0x43804  ldc.i4.1
0x43805  newarr   Microsoft.Crm.Data.PropertyBag
0x4380a  dup
0x4380b  ldc.i4.0
0x4380c  ldloc.1
0x4380d  stelem.ref
0x4380e  ldc.i4.s 0x39
0x43810  ldstr    aDeleteorganiza// "DeleteOrganizationFromStatisticsDatabas"...
0x43815  ldstr    aDA1SSrcPlatfor_27// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x4381a  callvirt instance int32 Microsoft.Crm.SharedDatabase.IDatabaseService::Delete(string tableName, class Microsoft.Crm.Data.PropertyBag[] conditions, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x4381f  pop
0x43820  ldloc.0
0x43821  ldstr    aOrganization// "Organization"
0x43826  ldarg.1
0x43827  box      [mscorlib]System.Guid
0x4382c  ldc.i4.s 0x3C
0x4382e  ldstr    aDeleteorganiza// "DeleteOrganizationFromStatisticsDatabas"...
0x43833  ldstr    aDA1SSrcPlatfor_27// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x43838  callvirt instance void Microsoft.Crm.SharedDatabase.IDatabaseService::Delete(string tableName, object id, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x4383d  leave.s  loc_43849
0x4383f  ldloc.0
0x43840  brfalse.s loc_43848
0x43842  ldloc.0
0x43843  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x43848  endfinally
0x43849  ret
```
