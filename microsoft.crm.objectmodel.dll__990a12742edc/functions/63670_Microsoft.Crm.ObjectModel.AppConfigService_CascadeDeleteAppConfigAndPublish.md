# Microsoft.Crm.ObjectModel.AppConfigService::CascadeDeleteAppConfigAndPublish

- ea: `0x63670`
- end: `0x6392d`
- name: `Microsoft.Crm.ObjectModel.AppConfigService::CascadeDeleteAppConfigAndPublish`
- size: `701`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x63550`

## callees

- `0x63670`
- `0x63cf0`
- `0x98c20`

## string_xrefs

- `0x636a4`: `appconfigid`
- `0x63705`: `appconfigid`
- `0x63688`: `appconfiginstanceid`
- `0x63752`: `appconfiginstanceid`
- `0x6386c`: `appconfiginstanceid`
- `0x63676`: `AppConfigInstance`
- `0x63761`: `AppConfigInstance`
- `0x6385d`: `AppConfigInstance`

## pseudocode

```c

```

## disassembly

```asm
0x63670  newobj   instance void Microsoft.Crm.ObjectModel.AppConfigInstanceService::.ctor()
0x63675  stloc.0
0x63676  ldstr    aAppconfiginsta_0// "AppConfigInstance"
0x6367b  ldarg.2
0x6367c  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x63681  stloc.1
0x63682  ldloc.1
0x63683  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x63688  ldstr    aAppconfiginsta// "appconfiginstanceid"
0x6368d  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x63692  ldloc.1
0x63693  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x63698  ldc.i4.0
0x63699  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::set_FilterOperator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator)
0x6369e  ldloc.1
0x6369f  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x636a4  ldstr    aAppconfigid// "appconfigid"
0x636a9  ldc.i4.0
0x636aa  ldarg.1
0x636ab  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x636b0  box      [mscorlib]System.Guid
0x636b5  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x636ba  pop
0x636bb  ldloc.0
0x636bc  ldloc.1
0x636bd  ldarg.2
0x636be  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveUnpublishedMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x636c3  dup
0x636c4  ldloc.0
0x636c5  ldloc.1
0x636c6  ldarg.2
0x636c7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x636cc  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::AddRange(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection)
0x636d1  newobj   instance void Microsoft.Crm.ObjectModel.NavigationSettingService::.ctor()
0x636d6  stloc.2
0x636d7  ldstr    aNavigationsett_0// "NavigationSetting"
0x636dc  ldarg.2
0x636dd  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x636e2  stloc.3
0x636e3  ldloc.3
0x636e4  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x636e9  ldstr    aNavigationsett// "navigationsettingid"
0x636ee  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x636f3  ldloc.3
0x636f4  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x636f9  ldc.i4.0
0x636fa  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::set_FilterOperator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator)
0x636ff  ldloc.3
0x63700  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x63705  ldstr    aAppconfigid// "appconfigid"
0x6370a  ldc.i4.0
0x6370b  ldarg.1
0x6370c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x63711  box      [mscorlib]System.Guid
0x63716  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x6371b  pop
0x6371c  ldloc.2
0x6371d  ldloc.3
0x6371e  ldarg.2
0x6371f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveUnpublishedMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x63724  stloc.s  4
0x63726  ldloc.s  4
0x63728  ldloc.2
0x63729  ldloc.3
0x6372a  ldarg.2
0x6372b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x63730  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::AddRange(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection)
0x63735  ldarg.0
0x63736  ldarg.1
0x63737  ldarg.2
0x63738  call     instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Delete(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x6373d  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x63742  stloc.s  5
0x63744  br.s     loc_63777
0x63746  ldloc.s  5
0x63748  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x6374d  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x63752  ldstr    aAppconfiginsta// "appconfiginstanceid"
0x63757  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x6375c  unbox.any [mscorlib]System.Guid
0x63761  ldstr    aAppconfiginsta_0// "AppConfigInstance"
0x63766  ldarg.2
0x63767  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6376c  stloc.s  6
0x6376e  ldarg.0
0x6376f  ldloc.s  6
0x63771  ldarg.2
0x63772  call     instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::PublishDeleteShared(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x63777  ldloc.s  5
0x63779  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x6377e  brtrue.s loc_63746
0x63780  leave.s  loc_63797
0x63782  ldloc.s  5
0x63784  isinst   [mscorlib]System.IDisposable
0x63789  stloc.s  7
0x6378b  ldloc.s  7
0x6378d  brfalse.s loc_63796
0x6378f  ldloc.s  7
0x63791  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x63796  endfinally
0x63797  ldloc.s  4
0x63799  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x6379e  stloc.s  5
0x637a0  br.s     loc_637D3
0x637a2  ldloc.s  5
0x637a4  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x637a9  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x637ae  ldstr    aNavigationsett// "navigationsettingid"
0x637b3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x637b8  unbox.any [mscorlib]System.Guid
0x637bd  ldstr    aNavigationsett_0// "NavigationSetting"
0x637c2  ldarg.2
0x637c3  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x637c8  stloc.s  8
0x637ca  ldarg.0
0x637cb  ldloc.s  8
0x637cd  ldarg.2
0x637ce  call     instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::PublishDeleteShared(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x637d3  ldloc.s  5
0x637d5  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x637da  brtrue.s loc_637A2
0x637dc  leave.s  loc_637F3
0x637de  ldloc.s  5
0x637e0  isinst   [mscorlib]System.IDisposable
0x637e5  stloc.s  7
0x637e7  ldloc.s  7
0x637e9  brfalse.s loc_637F2
0x637eb  ldloc.s  7
0x637ed  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x637f2  endfinally
0x637f3  ldarg.2
0x637f4  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x637f9  brfalse  loc_63924
0x637fe  ldarg.2
0x637ff  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x63804  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SolutionOperationContext [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionOperationContext()
0x63809  ldc.i4.2
0x6380a  bne.un   loc_63924
0x6380f  ldarg.2
0x63810  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x63815  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionId()
0x6381a  stloc.s  0xB
0x6381c  ldloc.1
0x6381d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Entity()
0x63822  ldloc.1
0x63823  ldarg.2
0x63824  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity[] [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::ReadRawEntityRows(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x63829  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, valuetype [mscorlib]System.Guid> <>c::<>9__34_0
0x6382e  dup
0x6382f  brtrue.s loc_63848
0x63831  pop
0x63832  ldsfld   class <>c <>c::<>9
0x63837  ldftn    instance valuetype [mscorlib]System.Guid <>c::<CascadeDeleteAppConfigAndPublish>b__34_0(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity x)
0x6383d  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, valuetype [mscorlib]System.Guid>::.ctor(object, native int)
0x63842  dup
0x63843  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, valuetype [mscorlib]System.Guid> <>c::<>9__34_0
0x63848  call     T0x2B0000E3
0x6384d  call     T0x2B00005B
0x63852  stloc.s  9
0x63854  ldloc.s  9
0x63856  call     T0x2B000060
0x6385b  brfalse.s loc_638A0
0x6385d  ldstr    aAppconfiginsta_0// "AppConfigInstance"
0x63862  ldarg.2
0x63863  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x63868  stloc.s  0xC
0x6386a  ldloc.s  0xC
0x6386c  ldstr    aAppconfiginsta// "appconfiginstanceid"
0x63871  ldc.i4.8
0x63872  ldloc.s  9
0x63874  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, class [mscorlib]System.Array)
0x63879  pop
0x6387a  ldloc.s  0xC
0x6387c  ldstr    aSolutionid// "solutionid"
0x63881  ldc.i4.0
0x63882  ldloc.s  0xB
0x63884  box      [mscorlib]System.Guid
0x63889  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x6388e  pop
0x6388f  ldloc.s  0xC
0x63891  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::get_EntityMetadata()
0x63896  ldloc.s  0xC
0x63898  ldc.i4.0
0x63899  ldarg.2
0x6389a  call     int32 [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::DeleteUsingDeletePlan(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression, bool, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x6389f  pop
0x638a0  ldloc.3
0x638a1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Entity()
0x638a6  ldloc.3
0x638a7  ldarg.2
0x638a8  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity[] [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::ReadRawEntityRows(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x638ad  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, valuetype [mscorlib]System.Guid> <>c::<>9__34_1
0x638b2  dup
0x638b3  brtrue.s loc_638CC
0x638b5  pop
0x638b6  ldsfld   class <>c <>c::<>9
0x638bb  ldftn    instance valuetype [mscorlib]System.Guid <>c::<CascadeDeleteAppConfigAndPublish>b__34_1(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity x)
0x638c1  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, valuetype [mscorlib]System.Guid>::.ctor(object, native int)
0x638c6  dup
0x638c7  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, valuetype [mscorlib]System.Guid> <>c::<>9__34_1
0x638cc  call     T0x2B0000E3
0x638d1  call     T0x2B00005B
0x638d6  stloc.s  0xA
0x638d8  ldloc.s  0xA
0x638da  call     T0x2B000060
0x638df  brfalse.s loc_63924
0x638e1  ldstr    aNavigationsett_0// "NavigationSetting"
0x638e6  ldarg.2
0x638e7  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x638ec  stloc.s  0xC
0x638ee  ldloc.s  0xC
0x638f0  ldstr    aNavigationsett// "navigationsettingid"
0x638f5  ldc.i4.8
0x638f6  ldloc.s  0xA
0x638f8  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, class [mscorlib]System.Array)
0x638fd  pop
0x638fe  ldloc.s  0xC
0x63900  ldstr    aSolutionid// "solutionid"
0x63905  ldc.i4.0
0x63906  ldloc.s  0xB
0x63908  box      [mscorlib]System.Guid
0x6390d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x63912  pop
0x63913  ldloc.s  0xC
0x63915  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::get_EntityMetadata()
0x6391a  ldloc.s  0xC
0x6391c  ldc.i4.0
0x6391d  ldarg.2
0x6391e  call     int32 [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::DeleteUsingDeletePlan(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression, bool, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x63923  pop
0x63924  ldarg.0
0x63925  ldarg.1
0x63926  ldarg.2
0x63927  call     instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::PublishDeleteShared(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x6392c  ret
```
