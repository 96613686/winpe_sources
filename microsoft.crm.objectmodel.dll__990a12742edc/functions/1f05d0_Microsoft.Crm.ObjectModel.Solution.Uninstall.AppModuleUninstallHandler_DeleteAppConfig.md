# Microsoft.Crm.ObjectModel.Solution.Uninstall.AppModuleUninstallHandler::DeleteAppConfig

- ea: `0x1f05d0`
- end: `0x1f0756`
- name: `Microsoft.Crm.ObjectModel.Solution.Uninstall.AppModuleUninstallHandler::DeleteAppConfig`
- size: `390`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1f0420`

## callees

- `0x62830`
- `0x195e60`
- `0x197f10`
- `0x1c1fb0`
- `0x1c31c0`
- `0x1c3dc0`
- `0x1c4040`
- `0x1f05d0`
- `0x1f0760`
- `0x1f07f0`
- `0x1f0890`

## string_xrefs

- `0x1f05f1`: `AppConfig`
- `0x1f0610`: `appconfigid`
- `0x1f065a`: `appconfigid`
- `0x1f068a`: `appconfigid`
- `0x1f06ca`: `appconfigidunique`
- `0x1f06f4`: `appconfigidunique`
- `0x1f06d9`: `AppConfigInstance`

## pseudocode

```c

```

## disassembly

```asm
0x1f05d0  ldarg.0
0x1f05d1  ldarg.2
0x1f05d2  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.SolutionUninstallContext::get_ExecutionContext()
0x1f05d7  newobj   instance void Microsoft.Crm.ObjectModel.AppConfigUtility::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1f05dc  stfld    class Microsoft.Crm.ObjectModel.AppConfigUtility Microsoft.Crm.ObjectModel.Solution.Uninstall.AppModuleUninstallHandler::_appConfigUtility
0x1f05e1  call     class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Solution.ComponentTypeMapData> [Microsoft.Crm.Platform.Server]Microsoft.Crm.Solution.SolutionComponentTypeMap::get_SolutionComponentTypeDictionary()
0x1f05e6  ldc.i4   0xBF
0x1f05eb  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Solution.ComponentTypeMapData>::get_Item(void)
0x1f05f0  stloc.0
0x1f05f1  ldstr    aAppconfig// "AppConfig"
0x1f05f6  ldarg.2
0x1f05f7  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.SolutionUninstallContext::get_ExecutionContext()
0x1f05fc  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x1f0601  stloc.1
0x1f0602  ldloc.1
0x1f0603  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x1f0608  ldc.i4.1
0x1f0609  newarr   [mscorlib]System.String
0x1f060e  dup
0x1f060f  ldc.i4.0
0x1f0610  ldstr    aAppconfigid// "appconfigid"
0x1f0615  stelem.ref
0x1f0616  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x1f061b  ldloc.1
0x1f061c  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x1f0621  ldstr    aAppmoduleid// "appmoduleid"
0x1f0626  ldc.i4.0
0x1f0627  ldarg.1
0x1f0628  box      [mscorlib]System.Guid
0x1f062d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x1f0632  pop
0x1f0633  newobj   instance void Microsoft.Crm.ObjectModel.AppConfigService::.ctor()
0x1f0638  ldloc.1
0x1f0639  ldarg.2
0x1f063a  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.SolutionUninstallContext::get_ExecutionContext()
0x1f063f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1f0644  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x1f0649  stloc.3
0x1f064a  br       loc_1F0734
0x1f064f  ldloc.3
0x1f0650  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1f0655  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x1f065a  ldstr    aAppconfigid// "appconfigid"
0x1f065f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1f0664  unbox.any [mscorlib]System.Guid
0x1f0669  stloc.2
0x1f066a  ldarg.0
0x1f066b  ldfld    class Microsoft.Crm.ObjectModel.AppConfigUtility Microsoft.Crm.ObjectModel.Solution.Uninstall.AppModuleUninstallHandler::_appConfigUtility
0x1f0670  ldloc.2
0x1f0671  ldc.i4   0xBF
0x1f0676  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState Microsoft.Crm.ObjectModel.AppConfigUtility::RetrieveEntityStates(valuetype [mscorlib]System.Guid Id, int32 componentType)
0x1f067b  stloc.s  4
0x1f067d  ldarg.0
0x1f067e  ldfld    class Microsoft.Crm.ObjectModel.AppConfigUtility Microsoft.Crm.ObjectModel.Solution.Uninstall.AppModuleUninstallHandler::_appConfigUtility
0x1f0683  ldloc.s  4
0x1f0685  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_BasePublishedInstance()
0x1f068a  ldstr    aAppconfigid// "appconfigid"
0x1f068f  callvirt instance object [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_Item(string)
0x1f0694  unbox.any [mscorlib]System.Guid
0x1f0699  ldarg.3
0x1f069a  callvirt instance class Microsoft.Crm.AppConfig.AppConfigDefinition Microsoft.Crm.ObjectModel.AppConfigUtility::CalculateCustomizationDiff(valuetype [mscorlib]System.Guid appConfigId, string appModuleUniqueName)
0x1f069f  stloc.s  5
0x1f06a1  ldarg.0
0x1f06a2  ldloc.2
0x1f06a3  ldarg.2
0x1f06a4  ldc.i4   0xBF
0x1f06a9  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.ObjectModel.Solution.Uninstall.AppModuleUninstallHandler::getEntityUninstallComponent(valuetype [mscorlib]System.Guid componentObjectId, class Microsoft.Crm.ObjectModel.SolutionUninstallContext solutionUninstallContext, int32 solutionComponentType)
0x1f06ae  stloc.s  6
0x1f06b0  ldnull
0x1f06b1  stloc.s  7
0x1f06b3  ldloc.s  6
0x1f06b5  brfalse.s loc_1F0734
0x1f06b7  ldloc.s  6
0x1f06b9  castclass [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentInstance
0x1f06be  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentInstance::get_Entity()
0x1f06c3  stloc.s  7
0x1f06c5  ldarg.0
0x1f06c6  ldarg.0
0x1f06c7  ldloc.2
0x1f06c8  ldloc.s  7
0x1f06ca  ldstr    aAppconfigiduni// "appconfigidunique"
0x1f06cf  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1f06d4  unbox.any [mscorlib]System.Guid
0x1f06d9  ldstr    aAppconfiginsta_0// "AppConfigInstance"
0x1f06de  ldarg.2
0x1f06df  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.ObjectModel.Solution.Uninstall.AppModuleUninstallHandler::GetAppConfigChildRecords(valuetype [mscorlib]System.Guid appConfigId, valuetype [mscorlib]System.Guid appConfigIdUnique, string childEntityName, class Microsoft.Crm.ObjectModel.SolutionUninstallContext solutionUninstallContext)
0x1f06e4  ldc.i4   0xC0
0x1f06e9  ldarg.2
0x1f06ea  call     instance void Microsoft.Crm.ObjectModel.Solution.Uninstall.AppModuleUninstallHandler::DeleteChildEntities(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection childEntities, int32 childComponentType, class Microsoft.Crm.ObjectModel.SolutionUninstallContext solutionUninstallContext)
0x1f06ef  ldarg.0
0x1f06f0  ldarg.0
0x1f06f1  ldloc.2
0x1f06f2  ldloc.s  7
0x1f06f4  ldstr    aAppconfigiduni// "appconfigidunique"
0x1f06f9  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1f06fe  unbox.any [mscorlib]System.Guid
0x1f0703  ldstr    aNavigationsett_0// "NavigationSetting"
0x1f0708  ldarg.2
0x1f0709  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.ObjectModel.Solution.Uninstall.AppModuleUninstallHandler::GetAppConfigChildRecords(valuetype [mscorlib]System.Guid appConfigId, valuetype [mscorlib]System.Guid appConfigIdUnique, string childEntityName, class Microsoft.Crm.ObjectModel.SolutionUninstallContext solutionUninstallContext)
0x1f070e  ldc.i4   0xFA
0x1f0713  ldarg.2
0x1f0714  call     instance void Microsoft.Crm.ObjectModel.Solution.Uninstall.AppModuleUninstallHandler::DeleteChildEntities(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection childEntities, int32 childComponentType, class Microsoft.Crm.ObjectModel.SolutionUninstallContext solutionUninstallContext)
0x1f0719  ldarg.0
0x1f071a  ldfld    class Microsoft.Crm.ObjectModel.AppConfigUtility Microsoft.Crm.ObjectModel.Solution.Uninstall.AppModuleUninstallHandler::_appConfigUtility
0x1f071f  ldloc.s  4
0x1f0721  ldarg.3
0x1f0722  ldloc.s  5
0x1f0724  callvirt instance void Microsoft.Crm.ObjectModel.AppConfigUtility::HandleSolutionDelete(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState appConfigStates, string appModuleUniqueName, class Microsoft.Crm.AppConfig.AppConfigDefinition customizationDiff)
0x1f0729  ldarg.0
0x1f072a  ldloc.0
0x1f072b  ldloc.2
0x1f072c  ldloc.s  6
0x1f072e  ldarg.2
0x1f072f  call     instance void Microsoft.Crm.ObjectModel.NonMetadataUninstallHandler::UpdateComponent(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Solution.ComponentTypeMapData componentTypeData, valuetype [mscorlib]System.Guid componentObjectId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance componentInstance, class Microsoft.Crm.ObjectModel.SolutionUninstallContext solutionUninstallContext)
0x1f0734  ldloc.3
0x1f0735  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1f073a  brtrue   loc_1F064F
0x1f073f  leave.s  loc_1F0755
0x1f0741  ldloc.3
0x1f0742  isinst   [mscorlib]System.IDisposable
0x1f0747  stloc.s  8
0x1f0749  ldloc.s  8
0x1f074b  brfalse.s loc_1F0754
0x1f074d  ldloc.s  8
0x1f074f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f0754  endfinally
0x1f0755  ret
```
