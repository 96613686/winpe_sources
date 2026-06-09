# Microsoft.Crm.ObjectModel.AppConfigService::CloneAppConfigInstancesAndNavigationSettings

- ea: `0x632e0`
- end: `0x63547`
- name: `Microsoft.Crm.ObjectModel.AppConfigService::CloneAppConfigInstancesAndNavigationSettings`
- size: `615`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x62be0`

## callees

- `0x632a0`
- `0x632c0`
- `0x632e0`
- `0x98c20`

## string_xrefs

- `0x6336b`: `componenttype`
- `0x632e0`: `AppConfig`
- `0x6330e`: `appconfigid`
- `0x6335b`: `appconfigid`
- `0x6338b`: `appconfigid`
- `0x632f2`: `appconfigidunique`
- `0x63414`: `appconfigidunique`
- `0x63445`: `appconfigidunique`
- `0x63489`: `appconfigidunique`
- `0x6337b`: `appconfigmasterid`
- `0x63326`: `componentstate`
- `0x63424`: `AppConfigInstance`

## pseudocode

```c

```

## disassembly

```asm
0x632e0  ldstr    aAppconfig// "AppConfig"
0x632e5  ldarg.3
0x632e6  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x632eb  stloc.0
0x632ec  ldloc.0
0x632ed  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x632f2  ldstr    aAppconfigiduni// "appconfigidunique"
0x632f7  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x632fc  ldloc.0
0x632fd  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x63302  ldc.i4.0
0x63303  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::set_FilterOperator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator)
0x63308  ldloc.0
0x63309  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x6330e  ldstr    aAppconfigid// "appconfigid"
0x63313  ldc.i4.0
0x63314  ldarg.1
0x63315  box      [mscorlib]System.Guid
0x6331a  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x6331f  pop
0x63320  ldloc.0
0x63321  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x63326  ldstr    aComponentstate_0// "componentstate"
0x6332b  ldc.i4.0
0x6332c  ldc.i4.1
0x6332d  box      [mscorlib]System.Int32
0x63332  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x63337  pop
0x63338  ldarg.0
0x63339  ldloc.0
0x6333a  ldarg.3
0x6333b  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveUnpublishedMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x63340  stloc.1
0x63341  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x63346  stloc.2
0x63347  ldloc.1
0x63348  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x6334d  ldc.i4.0
0x6334e  ble      loc_63545
0x63353  ldc.i4.5
0x63354  newarr   [mscorlib]System.String
0x63359  dup
0x6335a  ldc.i4.0
0x6335b  ldstr    aAppconfigid// "appconfigid"
0x63360  stelem.ref
0x63361  dup
0x63362  ldc.i4.1
0x63363  ldstr    aValue_1// "value"
0x63368  stelem.ref
0x63369  dup
0x6336a  ldc.i4.2
0x6336b  ldstr    aComponenttype// "componenttype"
0x63370  stelem.ref
0x63371  dup
0x63372  ldc.i4.3
0x63373  ldstr    aObjectid// "objectid"
0x63378  stelem.ref
0x63379  dup
0x6337a  ldc.i4.4
0x6337b  ldstr    aAppconfigmaste// "appconfigmasterid"
0x63380  stelem.ref
0x63381  stloc.3
0x63382  ldc.i4.s 0xE
0x63384  newarr   [mscorlib]System.String
0x63389  dup
0x6338a  ldc.i4.0
0x6338b  ldstr    aAppconfigid// "appconfigid"
0x63390  stelem.ref
0x63391  dup
0x63392  ldc.i4.1
0x63393  ldarg.0
0x63394  ldfld    string Microsoft.Crm.ObjectModel.AppConfigService::NavigationSettingNameAttrName
0x63399  stelem.ref
0x6339a  dup
0x6339b  ldc.i4.2
0x6339c  ldarg.0
0x6339d  ldfld    string Microsoft.Crm.ObjectModel.AppConfigService::NavigationSettingDescriptionAttrName
0x633a2  stelem.ref
0x633a3  dup
0x633a4  ldc.i4.3
0x633a5  ldarg.0
0x633a6  ldfld    string Microsoft.Crm.ObjectModel.AppConfigService::NavigationSettingGroupNameAttrName
0x633ab  stelem.ref
0x633ac  dup
0x633ad  ldc.i4.4
0x633ae  ldarg.0
0x633af  ldfld    string Microsoft.Crm.ObjectModel.AppConfigService::NavigationSettingSettingTypeAttrName
0x633b4  stelem.ref
0x633b5  dup
0x633b6  ldc.i4.5
0x633b7  ldarg.0
0x633b8  ldfld    string Microsoft.Crm.ObjectModel.AppConfigService::NavigationSettingObjectTypeCodeAttrName
0x633bd  stelem.ref
0x633be  dup
0x633bf  ldc.i4.6
0x633c0  ldarg.0
0x633c1  ldfld    string Microsoft.Crm.ObjectModel.AppConfigService::NavigationSettingPageUrlAttrName
0x633c6  stelem.ref
0x633c7  dup
0x633c8  ldc.i4.7
0x633c9  ldarg.0
0x633ca  ldfld    string Microsoft.Crm.ObjectModel.AppConfigService::NavigationSettingParentIdAttrName
0x633cf  stelem.ref
0x633d0  dup
0x633d1  ldc.i4.8
0x633d2  ldarg.0
0x633d3  ldfld    string Microsoft.Crm.ObjectModel.AppConfigService::NavigationSettingPrivilegesAttrName
0x633d8  stelem.ref
0x633d9  dup
0x633da  ldc.i4.s 9
0x633dc  ldarg.0
0x633dd  ldfld    string Microsoft.Crm.ObjectModel.AppConfigService::NavigationSettingProgressStateAttrName
0x633e2  stelem.ref
0x633e3  dup
0x633e4  ldc.i4.s 0xA
0x633e6  ldarg.0
0x633e7  ldfld    string Microsoft.Crm.ObjectModel.AppConfigService::NavigationSettingProgressStateAttrName
0x633ec  stelem.ref
0x633ed  dup
0x633ee  ldc.i4.s 0xB
0x633f0  ldarg.0
0x633f1  ldfld    string Microsoft.Crm.ObjectModel.AppConfigService::NavigationSettingResourceIdAttrName
0x633f6  stelem.ref
0x633f7  dup
0x633f8  ldc.i4.s 0xC
0x633fa  ldarg.0
0x633fb  ldfld    string Microsoft.Crm.ObjectModel.AppConfigService::NavigationSettingQuickSettingOrderAttrName
0x63400  stelem.ref
0x63401  dup
0x63402  ldc.i4.s 0xD
0x63404  ldarg.0
0x63405  ldfld    string Microsoft.Crm.ObjectModel.AppConfigService::NavigationSettingAdvancedSettingOrderAttrName
0x6340a  stelem.ref
0x6340b  stloc.s  4
0x6340d  ldloc.1
0x6340e  ldc.i4.0
0x6340f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x63414  ldstr    aAppconfigiduni// "appconfigidunique"
0x63419  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x6341e  unbox.any [mscorlib]System.Guid
0x63423  stloc.2
0x63424  ldstr    aAppconfiginsta_0// "AppConfigInstance"
0x63429  ldarg.3
0x6342a  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x6342f  stloc.s  5
0x63431  ldloc.s  5
0x63433  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x63438  ldloc.3
0x63439  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x6343e  ldloc.s  5
0x63440  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x63445  ldstr    aAppconfigiduni// "appconfigidunique"
0x6344a  ldc.i4.0
0x6344b  ldarg.2
0x6344c  box      [mscorlib]System.Guid
0x63451  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x63456  pop
0x63457  ldarg.0
0x63458  ldloc.s  5
0x6345a  ldarg.3
0x6345b  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x63460  stloc.s  6
0x63462  newobj   instance void Microsoft.Crm.ObjectModel.NavigationSettingService::.ctor()
0x63467  ldstr    aNavigationsett_0// "NavigationSetting"
0x6346c  ldarg.3
0x6346d  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x63472  stloc.s  7
0x63474  ldloc.s  7
0x63476  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x6347b  ldloc.s  4
0x6347d  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x63482  ldloc.s  7
0x63484  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x63489  ldstr    aAppconfigiduni// "appconfigidunique"
0x6348e  ldc.i4.0
0x6348f  ldarg.2
0x63490  box      [mscorlib]System.Guid
0x63495  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x6349a  pop
0x6349b  ldloc.s  7
0x6349d  ldarg.3
0x6349e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x634a3  stloc.s  8
0x634a5  ldloc.s  6
0x634a7  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x634ac  ldc.i4.0
0x634ad  ble.s    loc_634F4
0x634af  ldloc.s  6
0x634b1  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x634b6  stloc.s  9
0x634b8  br.s     loc_634D4
0x634ba  ldloc.s  9
0x634bc  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x634c1  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x634c6  stloc.s  0xA
0x634c8  ldarg.0
0x634c9  ldloc.s  0xA
0x634cb  ldloc.2
0x634cc  ldarg.3
0x634cd  ldarg.s  4
0x634cf  call     instance void Microsoft.Crm.ObjectModel.AppConfigService::CloneAppConfigInstance(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, valuetype [mscorlib]System.Guid IdUnique, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, bool isManaged)
0x634d4  ldloc.s  9
0x634d6  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x634db  brtrue.s loc_634BA
0x634dd  leave.s  loc_634F4
0x634df  ldloc.s  9
0x634e1  isinst   [mscorlib]System.IDisposable
0x634e6  stloc.s  0xB
0x634e8  ldloc.s  0xB
0x634ea  brfalse.s loc_634F3
0x634ec  ldloc.s  0xB
0x634ee  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x634f3  endfinally
0x634f4  ldloc.s  8
0x634f6  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x634fb  ldc.i4.0
0x634fc  ble.s    loc_63543
0x634fe  ldloc.s  8
0x63500  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x63505  stloc.s  9
0x63507  br.s     loc_63523
0x63509  ldloc.s  9
0x6350b  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x63510  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x63515  stloc.s  0xC
0x63517  ldarg.0
0x63518  ldloc.s  0xC
0x6351a  ldloc.2
0x6351b  ldarg.3
0x6351c  ldarg.s  4
0x6351e  call     instance void Microsoft.Crm.ObjectModel.AppConfigService::CloneNavigationSetting(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, valuetype [mscorlib]System.Guid IdUnique, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, bool isManaged)
0x63523  ldloc.s  9
0x63525  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x6352a  brtrue.s loc_63509
0x6352c  leave.s  loc_63543
0x6352e  ldloc.s  9
0x63530  isinst   [mscorlib]System.IDisposable
0x63535  stloc.s  0xB
0x63537  ldloc.s  0xB
0x63539  brfalse.s loc_63542
0x6353b  ldloc.s  0xB
0x6353d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x63542  endfinally
0x63543  ldc.i4.1
0x63544  ret
0x63545  ldc.i4.0
0x63546  ret
```
