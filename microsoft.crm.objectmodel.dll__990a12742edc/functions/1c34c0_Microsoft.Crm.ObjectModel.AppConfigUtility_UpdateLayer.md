# Microsoft.Crm.ObjectModel.AppConfigUtility::UpdateLayer

- ea: `0x1c34c0`
- end: `0x1c3b91`
- name: `Microsoft.Crm.ObjectModel.AppConfigUtility::UpdateLayer`
- size: `1745`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1c4b40`

## callees

- `0x18bd0`
- `0x18c70`
- `0x18fe0`
- `0x19000`
- `0x19060`
- `0x19080`
- `0x190a0`
- `0x19250`
- `0x192c0`
- `0x192e0`
- `0x193f0`
- `0x1c2950`
- `0x1c29a0`
- `0x1c2fc0`
- `0x1c34c0`
- `0x1c3ba0`
- `0x1c4160`
- `0x1c4380`
- `0x1c4430`
- `0x1c4760`
- `0x1c47b0`
- `0x1c4800`
- `0x1c4850`

## string_xrefs

- `0x1c3618`: `appconfigid`
- `0x1c3808`: `appconfigid`
- `0x1c3a44`: `appconfigid`
- `0x1c3697`: `appconfigidunique`
- `0x1c37d1`: `appconfigidunique`
- `0x1c37f1`: `appconfigidunique`
- `0x1c3a2d`: `appconfigidunique`
- `0x1c35ef`: `appconfigmasterid`
- `0x1c3686`: `appconfiginstanceid`
- `0x1c36d1`: `appconfiginstanceid`
- `0x1c36e4`: `appconfiginstanceid`
- `0x1c36f9`: `appconfiginstanceid`
- `0x1c3713`: `appconfiginstanceid`
- `0x1c36a8`: `overwritetime`
- `0x1c3745`: `overwritetime`
- `0x1c37b1`: `overwritetime`
- `0x1c366d`: `componentstate`
- `0x1c3558`: `AppConfigInstance`
- `0x1c35c9`: `AppConfigInstance`
- `0x1c379d`: `AppConfigInstance`
- `0x1c352e`: `Removed`
- `0x1c39a5`: `Removed`

## pseudocode

```c

```

## disassembly

```asm
0x1c34c0  ldarg.0
0x1c34c1  ldarg.2
0x1c34c2  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.AppConfig.AppConfigInstanceDefinition> Microsoft.Crm.ObjectModel.AppConfigUtility::GenerateComponentDict(class Microsoft.Crm.AppConfig.AppConfigDefinition appConfig)
0x1c34c7  stloc.0
0x1c34c8  ldarg.0
0x1c34c9  ldarg.1
0x1c34ca  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.AppConfig.AppConfigInstanceDefinition> Microsoft.Crm.ObjectModel.AppConfigUtility::GenerateComponentDict(class Microsoft.Crm.AppConfig.AppConfigDefinition appConfig)
0x1c34cf  stloc.1
0x1c34d0  ldarg.0
0x1c34d1  ldarg.2
0x1c34d2  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.AppConfig.NavigationSettingDefinition> Microsoft.Crm.ObjectModel.AppConfigUtility::GenerateNavSettingDict(class Microsoft.Crm.AppConfig.AppConfigDefinition appConfig)
0x1c34d7  stloc.2
0x1c34d8  ldarg.0
0x1c34d9  ldarg.1
0x1c34da  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.AppConfig.NavigationSettingDefinition> Microsoft.Crm.ObjectModel.AppConfigUtility::GenerateNavSettingDict(class Microsoft.Crm.AppConfig.AppConfigDefinition appConfig)
0x1c34df  stloc.3
0x1c34e0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x1c34e5  stloc.s  4
0x1c34e7  ldloc.0
0x1c34e8  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.AppConfig.AppConfigInstanceDefinition>::GetEnumerator()
0x1c34ed  stloc.s  6
0x1c34ef  br       loc_1C387A
0x1c34f4  ldloca.s 6
0x1c34f6  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class Microsoft.Crm.AppConfig.AppConfigInstanceDefinition>::get_Current()
0x1c34fb  stloc.s  7
0x1c34fd  ldloc.1
0x1c34fe  ldloca.s 7
0x1c3500  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class Microsoft.Crm.AppConfig.AppConfigInstanceDefinition>::get_Key()
0x1c3505  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.AppConfig.AppConfigInstanceDefinition>::ContainsKey(var<u1>)
0x1c350a  brfalse  loc_1C35A2
0x1c350f  ldnull
0x1c3510  stloc.s  8
0x1c3512  ldloc.1
0x1c3513  ldloca.s 7
0x1c3515  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class Microsoft.Crm.AppConfig.AppConfigInstanceDefinition>::get_Key()
0x1c351a  ldloca.s 8
0x1c351c  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.AppConfig.AppConfigInstanceDefinition>::TryGetValue(var<u1>, !!T0)
0x1c3521  pop
0x1c3522  ldloca.s 7
0x1c3524  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class Microsoft.Crm.AppConfig.AppConfigInstanceDefinition>::get_Value()
0x1c3529  callvirt instance string Microsoft.Crm.AppConfig.AppConfigInstanceDefinition::get_SolutionAction()
0x1c352e  ldstr    aRemoved// "Removed"
0x1c3533  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1c3538  brfalse.s loc_1C3558
0x1c353a  ldarg.0
0x1c353b  ldarg.1
0x1c353c  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.AppConfig.AppConfigDefinition::get_AppConfigIdUnique()
0x1c3541  ldloc.s  8
0x1c3543  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.AppConfig.AppConfigInstanceDefinition::get_AppConfigInstanceId()
0x1c3548  ldarg.0
0x1c3549  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.AppConfigUtility::_context
0x1c354e  call     instance void Microsoft.Crm.ObjectModel.AppConfigUtility::DeleteInstanceByDeletePlan(valuetype [mscorlib]System.Guid appConfigIdunique, valuetype [mscorlib]System.Guid appConfigInstanceId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1c3553  br       loc_1C387A
0x1c3558  ldstr    aAppconfiginsta_0// "AppConfigInstance"
0x1c355d  ldarg.0
0x1c355e  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.AppConfigUtility::_context
0x1c3563  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1c3568  stloc.s  9
0x1c356a  ldloc.s  9
0x1c356c  ldstr    aValue_1// "value"
0x1c3571  ldloca.s 7
0x1c3573  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class Microsoft.Crm.AppConfig.AppConfigInstanceDefinition>::get_Value()
0x1c3578  callvirt instance string Microsoft.Crm.AppConfig.AppConfigInstanceDefinition::get_Value()
0x1c357d  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string, object)
0x1c3582  ldarg.0
0x1c3583  ldarg.1
0x1c3584  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.AppConfig.AppConfigDefinition::get_AppConfigIdUnique()
0x1c3589  ldloc.s  8
0x1c358b  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.AppConfig.AppConfigInstanceDefinition::get_AppConfigInstanceId()
0x1c3590  ldloc.s  9
0x1c3592  ldarg.0
0x1c3593  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.AppConfigUtility::_context
0x1c3598  call     instance void Microsoft.Crm.ObjectModel.AppConfigUtility::UpdateInstaceByUpdatePlan(valuetype [mscorlib]System.Guid appConfigIdunique, valuetype [mscorlib]System.Guid appConfigInstanceId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression columns, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1c359d  br       loc_1C387A
0x1c35a2  ldarg.0
0x1c35a3  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.AppConfigUtility::_context
0x1c35a8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1c35ad  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppConfigInstance::.ctor(valuetype [mscorlib]System.Guid)
0x1c35b2  stloc.s  0xA
0x1c35b4  ldarg.0
0x1c35b5  ldloc.s  0xA
0x1c35b7  ldloca.s 7
0x1c35b9  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class Microsoft.Crm.AppConfig.AppConfigInstanceDefinition>::get_Value()
0x1c35be  ldarg.2
0x1c35bf  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.AppConfig.AppConfigDefinition::get_AppConfigId()
0x1c35c4  call     instance void Microsoft.Crm.ObjectModel.AppConfigUtility::PopulateAppConfigInstanceEntity(class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppConfigInstance appConfigInstanceEntity, class Microsoft.Crm.AppConfig.AppConfigInstanceDefinition appConfigInstanceDefinition, valuetype [mscorlib]System.Guid appConfigId)
0x1c35c9  ldstr    aAppconfiginsta_0// "AppConfigInstance"
0x1c35ce  ldarg.0
0x1c35cf  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.AppConfigUtility::_context
0x1c35d4  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x1c35d9  stloc.s  0xB
0x1c35db  ldloc.s  0xB
0x1c35dd  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x1c35e2  ldc.i4.0
0x1c35e3  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::set_FilterOperator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator)
0x1c35e8  ldloc.s  0xB
0x1c35ea  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x1c35ef  ldstr    aAppconfigmaste// "appconfigmasterid"
0x1c35f4  ldc.i4.0
0x1c35f5  ldloca.s 7
0x1c35f7  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class Microsoft.Crm.AppConfig.AppConfigInstanceDefinition>::get_Value()
0x1c35fc  callvirt instance string Microsoft.Crm.AppConfig.AppConfigInstanceDefinition::get_AppConfigMasterId()
0x1c3601  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Parse(string)
0x1c3606  box      [mscorlib]System.Guid
0x1c360b  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x1c3610  pop
0x1c3611  ldloc.s  0xB
0x1c3613  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x1c3618  ldstr    aAppconfigid// "appconfigid"
0x1c361d  ldc.i4.0
0x1c361e  ldarg.1
0x1c361f  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.AppConfig.AppConfigDefinition::get_AppConfigId()
0x1c3624  box      [mscorlib]System.Guid
0x1c3629  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x1c362e  pop
0x1c362f  ldloca.s 7
0x1c3631  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class Microsoft.Crm.AppConfig.AppConfigInstanceDefinition>::get_Value()
0x1c3636  callvirt instance string Microsoft.Crm.AppConfig.AppConfigInstanceDefinition::get_ObjectId()
0x1c363b  brfalse.s loc_1C3666
0x1c363d  ldloc.s  0xB
0x1c363f  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x1c3644  ldstr    aObjectid// "objectid"
0x1c3649  ldc.i4.0
0x1c364a  ldloca.s 7
0x1c364c  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class Microsoft.Crm.AppConfig.AppConfigInstanceDefinition>::get_Value()
0x1c3651  callvirt instance string Microsoft.Crm.AppConfig.AppConfigInstanceDefinition::get_ObjectId()
0x1c3656  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Parse(string)
0x1c365b  box      [mscorlib]System.Guid
0x1c3660  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x1c3665  pop
0x1c3666  ldloc.s  0xB
0x1c3668  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x1c366d  ldstr    aComponentstate_0// "componentstate"
0x1c3672  ldc.i4.0
0x1c3673  ldc.i4.0
0x1c3674  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState
0x1c3679  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x1c367e  pop
0x1c367f  ldloc.s  0xB
0x1c3681  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x1c3686  ldstr    aAppconfiginsta// "appconfiginstanceid"
0x1c368b  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x1c3690  ldloc.s  0xB
0x1c3692  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x1c3697  ldstr    aAppconfigiduni// "appconfigidunique"
0x1c369c  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x1c36a1  ldloc.s  0xB
0x1c36a3  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x1c36a8  ldstr    aOverwritetime// "overwritetime"
0x1c36ad  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x1c36b2  ldarg.0
0x1c36b3  ldloc.s  0xB
0x1c36b5  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.ObjectModel.AppConfigUtility::RetrieveRawEntityRows(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression expression)
0x1c36ba  stloc.s  0xC
0x1c36bc  ldloc.s  0xC
0x1c36be  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x1c36c3  ldc.i4.0
0x1c36c4  ble      loc_1C37EF
0x1c36c9  ldloc.s  0xC
0x1c36cb  ldc.i4.0
0x1c36cc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x1c36d1  ldstr    aAppconfiginsta// "appconfiginstanceid"
0x1c36d6  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1c36db  unbox.any [mscorlib]System.Guid
0x1c36e0  stloc.s  0xE
0x1c36e2  ldloc.s  0xA
0x1c36e4  ldstr    aAppconfiginsta// "appconfiginstanceid"
0x1c36e9  ldloc.s  0xE
0x1c36eb  box      [mscorlib]System.Guid
0x1c36f0  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1c36f5  ldloc.s  4
0x1c36f7  ldloc.s  0xA
0x1c36f9  ldstr    aAppconfiginsta// "appconfiginstanceid"
0x1c36fe  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1c3703  unbox.any [mscorlib]System.Guid
0x1c3708  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Contains(var<u1>)
0x1c370d  brtrue.s loc_1C3727
0x1c370f  ldloc.s  4
0x1c3711  ldloc.s  0xA
0x1c3713  ldstr    aAppconfiginsta// "appconfiginstanceid"
0x1c3718  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1c371d  unbox.any [mscorlib]System.Guid
0x1c3722  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x1c3727  ldnull
0x1c3728  stloc.s  0xF
0x1c372a  ldloc.s  0xC
0x1c372c  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x1c3731  stloc.s  0x10
0x1c3733  br.s     loc_1C3779
0x1c3735  ldloc.s  0x10
0x1c3737  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1c373c  castclass [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppConfigInstance
0x1c3741  stloc.s  0x11
0x1c3743  ldloc.s  0x11
0x1c3745  ldstr    aOverwritetime// "overwritetime"
0x1c374a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1c374f  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime
0x1c3754  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::get_UniversalTime()
0x1c3759  stloc.s  0x12
0x1c375b  ldloca.s 0x12
0x1c375d  ldstr    aYyyyMmDdHhMmSs// "yyyy-MM-dd HH:mm:ss.fff"
0x1c3762  call     instance string [mscorlib]System.DateTime::ToString(string)
0x1c3767  ldstr    a19000101000000// "1900-01-01 00:00:00.000"
0x1c376c  callvirt instance bool [mscorlib]System.String::Equals(string)
0x1c3771  brfalse.s loc_1C3779
0x1c3773  ldloc.s  0x11
0x1c3775  stloc.s  0xF
0x1c3777  leave.s  loc_1C3799
0x1c3779  ldloc.s  0x10
0x1c377b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1c3780  brtrue.s loc_1C3735
0x1c3782  leave.s  loc_1C3799
0x1c3784  ldloc.s  0x10
0x1c3786  isinst   [mscorlib]System.IDisposable
0x1c378b  stloc.s  0x13
0x1c378d  ldloc.s  0x13
0x1c378f  brfalse.s loc_1C3798
0x1c3791  ldloc.s  0x13
0x1c3793  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1c3798  endfinally
0x1c3799  ldloc.s  0xF
0x1c379b  brfalse.s loc_1C37EF
0x1c379d  ldstr    aAppconfiginsta_0// "AppConfigInstance"
0x1c37a2  ldarg.0
0x1c37a3  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.AppConfigUtility::_context
0x1c37a8  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1c37ad  stloc.s  0x14
0x1c37af  ldloc.s  0x14
0x1c37b1  ldstr    aOverwritetime// "overwritetime"
0x1c37b6  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x1c37bb  stloc.s  0x12
0x1c37bd  ldloca.s 0x12
0x1c37bf  ldstr    aYyyyMmDdHhMmSs// "yyyy-MM-dd HH:mm:ss.fff"
0x1c37c4  call     instance string [mscorlib]System.DateTime::ToString(string)
0x1c37c9  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string, object)
0x1c37ce  ldarg.0
0x1c37cf  ldloc.s  0xF
0x1c37d1  ldstr    aAppconfigiduni// "appconfigidunique"
0x1c37d6  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1c37db  unbox.any [mscorlib]System.Guid
0x1c37e0  ldloc.s  0xE
0x1c37e2  ldloc.s  0x14
0x1c37e4  ldarg.0
0x1c37e5  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.AppConfigUtility::_context
0x1c37ea  call     instance void Microsoft.Crm.ObjectModel.AppConfigUtility::UpdateInstaceByUpdatePlan(valuetype [mscorlib]System.Guid appConfigIdunique, valuetype [mscorlib]System.Guid appConfigInstanceId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression columns, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1c37ef  ldloc.s  0xA
0x1c37f1  ldstr    aAppconfigiduni// "appconfigidunique"
0x1c37f6  ldarg.1
0x1c37f7  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.AppConfig.AppConfigDefinition::get_AppConfigIdUnique()
0x1c37fc  box      [mscorlib]System.Guid
0x1c3801  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1c3806  ldloc.s  0xA
0x1c3808  ldstr    aAppconfigid// "appconfigid"
0x1c380d  ldarg.1
0x1c380e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.AppConfig.AppConfigDefinition::get_AppConfigId()
0x1c3813  box      [mscorlib]System.Guid
0x1c3818  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1c381d  ldloc.s  0xA
0x1c381f  ldstr    aSolutionid// "solutionid"
0x1c3824  ldarg.s  4
0x1c3826  box      [mscorlib]System.Guid
0x1c382b  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1c3830  ldarg.0
0x1c3831  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.AppConfigUtility::_context
0x1c3836  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x1c383b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionId()
0x1c3840  stloc.s  0xD
0x1c3842  ldarg.0
0x1c3843  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.AppConfigUtility::_context
0x1c3848  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x1c384d  ldarg.s  4
0x1c384f  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::set_SolutionId(valuetype [mscorlib]System.Guid)
0x1c3854  ldarg.0
0x1c3855  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject Microsoft.Crm.ObjectModel.AppConfigUtility::_businessProcessObject
0x1c385a  ldloc.s  0xA
0x1c385c  ldarg.0
0x1c385d  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.AppConfigUtility::_context
0x1c3862  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1c3867  pop
0x1c3868  ldarg.0
0x1c3869  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.AppConfigUtility::_context
0x1c386e  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x1c3873  ldloc.s  0xD
0x1c3875  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::set_SolutionId(valuetype [mscorlib]System.Guid)
0x1c387a  ldloca.s 6
0x1c387c  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class Microsoft.Crm.AppConfig.AppConfigInstanceDefinition>::MoveNext()
0x1c3881  brtrue   loc_1C34F4
0x1c3886  leave.s  loc_1C3896
0x1c3888  ldloca.s 6
0x1c388a  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class Microsoft.Crm.AppConfig.AppConfigInstanceDefinition>
0x1c3890  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1c3895  endfinally
0x1c3896  ldloc.1
0x1c3897  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.AppConfig.AppConfigInstanceDefinition>::GetEnumerator()
0x1c389c  stloc.s  6
0x1c389e  br.s     loc_1C38D6
0x1c38a0  ldloca.s 6
0x1c38a2  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class Microsoft.Crm.AppConfig.AppConfigInstanceDefinition>::get_Current()
0x1c38a7  stloc.s  0x15
0x1c38a9  ldloc.0
  ... truncated ...
```
