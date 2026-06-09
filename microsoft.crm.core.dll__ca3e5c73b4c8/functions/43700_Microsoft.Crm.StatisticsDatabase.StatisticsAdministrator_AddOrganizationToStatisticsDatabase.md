# Microsoft.Crm.StatisticsDatabase.StatisticsAdministrator::AddOrganizationToStatisticsDatabase

- ea: `0x43700`
- end: `0x437d3`
- name: `Microsoft.Crm.StatisticsDatabase.StatisticsAdministrator::AddOrganizationToStatisticsDatabase`
- size: `211`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x4640`
- `0x4c00`
- `0x43700`
- `0x43850`
- `0x438f0`
- `0x44400`
- `0x444f0`
- `0x44510`
- `0x64b30`
- `0x64b60`

## string_xrefs

- `0x4371f`: `D:\a\1\s\src\Platform\Core\DataServices\StatsDB\ObjectModel\StatisticsAdministrator.cs`
- `0x4379a`: `D:\a\1\s\src\Platform\Core\DataServices\StatsDB\ObjectModel\StatisticsAdministrator.cs`
- `0x437bb`: `D:\a\1\s\src\Platform\Core\DataServices\StatsDB\ObjectModel\StatisticsAdministrator.cs`

## pseudocode

```c

```

## disassembly

```asm
0x43700  ldarg.0
0x43701  call     class Microsoft.Crm.SharedDatabase.IDatabaseService Microsoft.Crm.StatisticsDatabase.StatisticsDatabaseService::NewService(valuetype [mscorlib]System.Guid scaleGroup)
0x43706  stloc.0
0x43707  call     class Microsoft.Crm.LocatorService Microsoft.Crm.LocatorService::get_Instance()
0x4370c  ldstr    aOrganization// "Organization"
0x43711  ldarg.1
0x43712  box      [mscorlib]System.Guid
0x43717  ldnull
0x43718  ldc.i4.s 0x1B
0x4371a  ldstr    aAddorganizatio// "AddOrganizationToStatisticsDatabase"
0x4371f  ldstr    aDA1SSrcPlatfor_27// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x43724  callvirt instance class Microsoft.Crm.Data.PropertyBag Microsoft.Crm.LocatorService::RetrieveById(string tableName, object primaryKey, string[] columns, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x43729  stloc.1
0x4372a  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0x4372f  stloc.2
0x43730  ldloc.2
0x43731  ldstr    aOrganizationid_1// "OrganizationId"
0x43736  ldarg.1
0x43737  box      [mscorlib]System.Guid
0x4373c  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x43741  ldloc.2
0x43742  ldstr    aUniquename// "UniqueName"
0x43747  ldloc.1
0x43748  ldstr    aUniquename// "UniqueName"
0x4374d  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x43752  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x43757  ldloc.2
0x43758  ldstr    aMaxstoragesize// "MaxStorageSizeMb"
0x4375d  ldloc.1
0x4375e  ldstr    aMaxstoragesize// "MaxStorageSizeMb"
0x43763  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x43768  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x4376d  ldloc.2
0x4376e  ldstr    aCurrentstorage// "CurrentStorageSizeMb"
0x43773  ldloc.1
0x43774  ldstr    aCurrentstorage// "CurrentStorageSizeMb"
0x43779  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x4377e  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x43783  ldarg.0
0x43784  ldarg.1
0x43785  call     bool Microsoft.Crm.StatisticsDatabase.StatisticsAdministrator::DoesStatisticsExist(valuetype [mscorlib]System.Guid scaleGroupId, valuetype [mscorlib]System.Guid organizationId)
0x4378a  brtrue.s loc_437A7
0x4378c  ldloc.0
0x4378d  ldstr    aOrganization// "Organization"
0x43792  ldloc.2
0x43793  ldc.i4.s 0x28
0x43795  ldstr    aAddorganizatio// "AddOrganizationToStatisticsDatabase"
0x4379a  ldstr    aDA1SSrcPlatfor_27// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x4379f  callvirt instance object Microsoft.Crm.SharedDatabase.IDatabaseService::Create(string tableName, class Microsoft.Crm.Data.PropertyBag columnSet, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x437a4  pop
0x437a5  leave.s  loc_437D2
0x437a7  ldloc.0
0x437a8  ldstr    aOrganization// "Organization"
0x437ad  ldarg.1
0x437ae  box      [mscorlib]System.Guid
0x437b3  ldloc.2
0x437b4  ldc.i4.s 0x2C
0x437b6  ldstr    aAddorganizatio// "AddOrganizationToStatisticsDatabase"
0x437bb  ldstr    aDA1SSrcPlatfor_27// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x437c0  callvirt instance int32 Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string tableName, object id, class Microsoft.Crm.Data.PropertyBag columnSet, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x437c5  pop
0x437c6  leave.s  loc_437D2
0x437c8  ldloc.0
0x437c9  brfalse.s loc_437D1
0x437cb  ldloc.0
0x437cc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x437d1  endfinally
0x437d2  ret
```
