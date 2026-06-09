# Microsoft.Crm.ObjectModel.AppConfigUtility::GetAppConfigDefinition

- ea: `0x1c4060`
- end: `0x1c4153`
- name: `Microsoft.Crm.ObjectModel.AppConfigUtility::GetAppConfigDefinition`
- size: `243`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1c31c0`
- `0x1c3320`
- `0x1c3dc0`
- `0x1c3e50`
- `0x1c4b40`

## callees

- `0x18cf0`
- `0x1c4060`
- `0x1c4160`

## string_xrefs

- `0x1c407c`: `appconfigidunique`
- `0x1c4083`: `appconfigidunique`
- `0x1c40eb`: `appconfigidunique`
- `0x1c40f2`: `appconfigidunique`
- `0x1c40af`: `componentstate`
- `0x1c411e`: `componentstate`
- `0x1c4065`: `AppConfigInstance`

## pseudocode

```c

```

## disassembly

```asm
0x1c4060  ldarg.1
0x1c4061  brtrue.s loc_1C4065
0x1c4063  ldnull
0x1c4064  ret
0x1c4065  ldstr    aAppconfiginsta_0// "AppConfigInstance"
0x1c406a  ldarg.0
0x1c406b  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.AppConfigUtility::_context
0x1c4070  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x1c4075  stloc.0
0x1c4076  ldloc.0
0x1c4077  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x1c407c  ldstr    aAppconfigiduni// "appconfigidunique"
0x1c4081  ldc.i4.0
0x1c4082  ldarg.1
0x1c4083  ldstr    aAppconfigiduni// "appconfigidunique"
0x1c4088  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1c408d  unbox.any [mscorlib]System.Guid
0x1c4092  box      [mscorlib]System.Guid
0x1c4097  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x1c409c  pop
0x1c409d  ldloc.0
0x1c409e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x1c40a3  ldc.i4.0
0x1c40a4  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::set_FilterOperator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator)
0x1c40a9  ldloc.0
0x1c40aa  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x1c40af  ldstr    aComponentstate_0// "componentstate"
0x1c40b4  ldc.i4.1
0x1c40b5  ldc.i4.2
0x1c40b6  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState
0x1c40bb  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x1c40c0  pop
0x1c40c1  ldloc.0
0x1c40c2  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x1c40c7  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddAllColumns()
0x1c40cc  ldarg.0
0x1c40cd  ldloc.0
0x1c40ce  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.ObjectModel.AppConfigUtility::RetrieveRawEntityRows(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression expression)
0x1c40d3  stloc.1
0x1c40d4  ldstr    aNavigationsett_0// "NavigationSetting"
0x1c40d9  ldarg.0
0x1c40da  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.AppConfigUtility::_context
0x1c40df  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x1c40e4  stloc.0
0x1c40e5  ldloc.0
0x1c40e6  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x1c40eb  ldstr    aAppconfigiduni// "appconfigidunique"
0x1c40f0  ldc.i4.0
0x1c40f1  ldarg.1
0x1c40f2  ldstr    aAppconfigiduni// "appconfigidunique"
0x1c40f7  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1c40fc  unbox.any [mscorlib]System.Guid
0x1c4101  box      [mscorlib]System.Guid
0x1c4106  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x1c410b  pop
0x1c410c  ldloc.0
0x1c410d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x1c4112  ldc.i4.0
0x1c4113  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::set_FilterOperator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator)
0x1c4118  ldloc.0
0x1c4119  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x1c411e  ldstr    aComponentstate_0// "componentstate"
0x1c4123  ldc.i4.1
0x1c4124  ldc.i4.2
0x1c4125  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState
0x1c412a  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x1c412f  pop
0x1c4130  ldloc.0
0x1c4131  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x1c4136  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddAllColumns()
0x1c413b  ldarg.0
0x1c413c  ldloc.0
0x1c413d  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.ObjectModel.AppConfigUtility::RetrieveRawEntityRows(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression expression)
0x1c4142  stloc.2
0x1c4143  ldarg.1
0x1c4144  ldloc.1
0x1c4145  ldloc.2
0x1c4146  ldarg.0
0x1c4147  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.ObjectModel.AppConfigUtility::_cache
0x1c414c  ldarg.2
0x1c414d  newobj   instance void Microsoft.Crm.AppConfig.AppConfigDefinition::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity appConfig, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection appConfigInstances, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection navigationSettings, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache cache, string appModuleUniqueName)
0x1c4152  ret
```
