# Microsoft.Crm.Asynchronous.StatisticsSqmCollectorBase::InternalCreateStatisticRow

- ea: `0xc470`
- end: `0xc555`
- name: `Microsoft.Crm.Asynchronous.StatisticsSqmCollectorBase::InternalCreateStatisticRow`
- size: `229`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xc3e0`
- `0xc440`
- `0xc460`

## callees

- `0xc470`
- `0xc690`

## string_xrefs

- `0xc544`: `InternalCreateStatisticRow`

## pseudocode

```c

```

## disassembly

```asm
0xc470  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationMetadataProvider::get_Instance()
0xc475  ldarg.0
0xc476  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.StatisticsSqmCollectorBase::get_OrganizationId()
0xc47b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider::GetOrganizationScaleGroupId(valuetype [mscorlib]System.Guid)
0xc480  stloc.0
0xc481  ldloc.0
0xc482  ldarg.0
0xc483  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.StatisticsSqmCollectorBase::get_OrganizationId()
0xc488  call     bool [Microsoft.Crm.Core]Microsoft.Crm.StatisticsDatabase.StatisticsAdministrator::DoesStatisticsExist(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xc48d  brtrue.s loc_C4C1
0xc48f  ldarg.0
0xc490  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.StatisticsSqmCollectorBase::get_OrganizationId()
0xc495  ldc.i4.s 0x15
0xc497  ldstr    aNoStatisticEnt// "No statistic entry found. Creating entr"...
0xc49c  ldc.i4.1
0xc49d  newarr   [mscorlib]System.Object
0xc4a2  dup
0xc4a3  ldc.i4.0
0xc4a4  ldarg.0
0xc4a5  ldfld    valuetype [Microsoft.Crm.Core]Microsoft.Crm.StatisticsDatabase.StatisticQueryType Microsoft.Crm.Asynchronous.StatisticsSqmCollectorBase::_queryType
0xc4aa  box      [Microsoft.Crm.Core]Microsoft.Crm.StatisticsDatabase.StatisticQueryType
0xc4af  stelem.ref
0xc4b0  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xc4b5  ldloc.0
0xc4b6  ldarg.0
0xc4b7  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.StatisticsSqmCollectorBase::get_OrganizationId()
0xc4bc  call     void [Microsoft.Crm.Core]Microsoft.Crm.StatisticsDatabase.StatisticsAdministrator::AddOrganizationToStatisticsDatabase(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xc4c1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0xc4c6  stloc.1
0xc4c7  ldloc.1
0xc4c8  ldstr    aStatisticsdata// "StatisticsDataId"
0xc4cd  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0xc4d2  box      [mscorlib]System.Guid
0xc4d7  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xc4dc  ldloc.1
0xc4dd  ldstr    aOrganizationid_1// "OrganizationId"
0xc4e2  ldarg.0
0xc4e3  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.StatisticsSqmCollectorBase::get_OrganizationId()
0xc4e8  box      [mscorlib]System.Guid
0xc4ed  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xc4f2  ldloc.1
0xc4f3  ldstr    aStatistictypei// "StatisticTypeId"
0xc4f8  ldarg.2
0xc4f9  box      [mscorlib]System.Int32
0xc4fe  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xc503  ldloc.1
0xc504  ldstr    aStarttime// "StartTime"
0xc509  ldarg.3
0xc50a  box      [mscorlib]System.DateTime
0xc50f  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xc514  ldloc.1
0xc515  ldstr    aEndtime// "EndTime"
0xc51a  ldarg.s  4
0xc51c  box      [mscorlib]System.DateTime
0xc521  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xc526  ldloc.1
0xc527  ldstr    aResult_0// "Result"
0xc52c  ldarg.s  5
0xc52e  box      [mscorlib]System.Int32
0xc533  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xc538  ldarg.1
0xc539  ldstr    aStatisticsdata_0// "StatisticsData"
0xc53e  ldloc.1
0xc53f  ldc.i4   0x8D
0xc544  ldstr    aInternalcreate// "InternalCreateStatisticRow"
0xc549  ldstr    aDDbsShDccm2110_16// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\5"...
0xc54e  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0xc553  pop
0xc554  ret
```
