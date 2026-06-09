# Microsoft.Crm.ObjectModel.MetricService::Create

- ea: `0x173740`
- end: `0x173831`
- name: `Microsoft.Crm.ObjectModel.MetricService::Create`
- size: `241`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x6cfa0`
- `0x6cfb0`
- `0x6d0c0`
- `0x173670`
- `0x173740`

## string_xrefs

- `0x1737f5`: `CREATE`
- `0x173759`: `isamount`
- `0x173766`: `isamount`
- `0x173771`: `isamount`
- `0x1737bb`: `isamount`
- `0x173783`: `amountdatatype`
- `0x17379b`: `amountdatatype`
- `0x17378f`: `For metric of type amount, amountdatatype is mandatory.`
- `0x1737a7`: `For metric of type count, amountdatatype should not be specified.`
- `0x1737d3`: `Amount`

## pseudocode

```c

```

## disassembly

```asm
0x173740  ldarg.1
0x173741  ldstr    aIsstretchtrack// "isstretchtracked"
0x173746  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x17374b  brfalse.s loc_173758
0x17374d  ldnull
0x17374e  ldstr    aIsstretchtrack// "isstretchtracked"
0x173753  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x173758  ldarg.1
0x173759  ldstr    aIsamount// "isamount"
0x17375e  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x173763  brfalse.s loc_173770
0x173765  ldnull
0x173766  ldstr    aIsamount// "isamount"
0x17376b  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x173770  ldarg.1
0x173771  ldstr    aIsamount// "isamount"
0x173776  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x17377b  unbox.any [mscorlib]System.Boolean
0x173780  brfalse.s loc_17379A
0x173782  ldarg.1
0x173783  ldstr    aAmountdatatype// "amountdatatype"
0x173788  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x17378d  brfalse.s loc_1737B2
0x17378f  ldstr    aForMetricOfTyp// "For metric of type amount, amountdataty"...
0x173794  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x173799  throw
0x17379a  ldarg.1
0x17379b  ldstr    aAmountdatatype// "amountdatatype"
0x1737a0  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x1737a5  brtrue.s loc_1737B2
0x1737a7  ldstr    aForMetricOfTyp_0// "For metric of type count, amountdatatyp"...
0x1737ac  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x1737b1  throw
0x1737b2  ldarg.0
0x1737b3  ldarg.1
0x1737b4  ldarg.2
0x1737b5  call     instance void Microsoft.Crm.ObjectModel.MetricService::ValidateDuplicateName(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity metric, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1737ba  ldarg.1
0x1737bb  ldstr    aIsamount// "isamount"
0x1737c0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1737c5  unbox.any [mscorlib]System.Boolean
0x1737ca  brtrue.s loc_1737D3
0x1737cc  ldstr    aCount_0// "Count"
0x1737d1  br.s     loc_1737D8
0x1737d3  ldstr    aAmount// "Amount"
0x1737d8  stloc.0
0x1737d9  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x1737de  stloc.1
0x1737df  call     class Microsoft.Crm.ObjectModel.GoalEntityEventSource Microsoft.Crm.ObjectModel.GoalEntityEventSource::get_Instance()
0x1737e4  ldloc.1
0x1737e5  ldarg.2
0x1737e6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_OrganizationSettings()
0x1737eb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_OrganizationId()
0x1737f0  ldc.i4   0x2583
0x1737f5  ldstr    aCreate_0// "CREATE"
0x1737fa  callvirt instance void Microsoft.Crm.ObjectModel.GoalEntityEventSource::WriteCrudTelemetryEvent(valuetype [mscorlib]System.DateTime Timestamp, valuetype [mscorlib]System.Guid organizationId, int32 EntityTypeCode, string OperationType)
0x1737ff  call     class Microsoft.Crm.ObjectModel.GoalEntityEventSource Microsoft.Crm.ObjectModel.GoalEntityEventSource::get_Instance()
0x173804  ldloc.1
0x173805  ldarg.2
0x173806  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_OrganizationSettings()
0x17380b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_OrganizationId()
0x173810  ldarg.1
0x173811  ldstr    aMetricid// "metricid"
0x173816  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x17381b  unbox.any [mscorlib]System.Guid
0x173820  ldloc.0
0x173821  ldc.i4.0
0x173822  conv.i8
0x173823  callvirt instance void Microsoft.Crm.ObjectModel.GoalEntityEventSource::WriteGoalMetricEntityTelemetryEvent(valuetype [mscorlib]System.DateTime Timestamp, valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid MetricId, string GoalMetricType, int64 NumberOfRollupFields)
0x173828  ldarg.0
0x173829  ldarg.1
0x17382a  ldarg.2
0x17382b  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x173830  ret
```
