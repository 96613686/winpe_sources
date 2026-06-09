# Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::RetrievePluginTypesFromFQN

- ea: `0x555c0`
- end: `0x556e8`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::RetrievePluginTypesFromFQN`
- size: `296`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x55530`

## string_xrefs

- `0x55672`: `publickeytoken`
- `0x55679`: `publickeytoken`
- `0x555d2`: `pluginassemblyid`
- `0x555d9`: `pluginassemblyid`
- `0x555c0`: `PluginType`
- `0x556ab`: `PluginType`

## pseudocode

```c

```

## disassembly

```asm
0x555c0  ldstr    aPlugintype// "PluginType"
0x555c5  ldarg.0
0x555c6  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::_context
0x555cb  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x555d0  stloc.0
0x555d1  ldloc.0
0x555d2  ldstr    aPluginassembly_1// "pluginassemblyid"
0x555d7  ldc.i4.0
0x555d8  ldarg.1
0x555d9  ldstr    aPluginassembly_1// "pluginassemblyid"
0x555de  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x555e3  unbox.any [mscorlib]System.Guid
0x555e8  box      [mscorlib]System.Guid
0x555ed  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x555f2  pop
0x555f3  ldloc.0
0x555f4  ldstr    aAssemblyname// "assemblyname"
0x555f9  ldc.i4.0
0x555fa  ldarg.1
0x555fb  ldstr    aAssemblyname// "assemblyname"
0x55600  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x55605  castclass [mscorlib]System.String
0x5560a  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x5560f  pop
0x55610  ldloc.0
0x55611  ldstr    aTypename// "typename"
0x55616  ldc.i4.0
0x55617  ldarg.1
0x55618  ldstr    aTypename// "typename"
0x5561d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x55622  castclass [mscorlib]System.String
0x55627  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x5562c  pop
0x5562d  ldloc.0
0x5562e  ldstr    aMajor// "major"
0x55633  ldc.i4.0
0x55634  ldarg.1
0x55635  ldstr    aMajor// "major"
0x5563a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5563f  unbox.any [mscorlib]System.Int32
0x55644  box      [mscorlib]System.Int32
0x55649  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x5564e  pop
0x5564f  ldloc.0
0x55650  ldstr    aMinor// "minor"
0x55655  ldc.i4.0
0x55656  ldarg.1
0x55657  ldstr    aMinor// "minor"
0x5565c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x55661  unbox.any [mscorlib]System.Int32
0x55666  box      [mscorlib]System.Int32
0x5566b  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x55670  pop
0x55671  ldloc.0
0x55672  ldstr    aPublickeytoken// "publickeytoken"
0x55677  ldc.i4.0
0x55678  ldarg.1
0x55679  ldstr    aPublickeytoken// "publickeytoken"
0x5567e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x55683  castclass [mscorlib]System.String
0x55688  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x5568d  pop
0x5568e  ldloc.0
0x5568f  ldstr    aCulture// "culture"
0x55694  ldc.i4.0
0x55695  ldarg.1
0x55696  ldstr    aCulture// "culture"
0x5569b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x556a0  castclass [mscorlib]System.String
0x556a5  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x556aa  pop
0x556ab  ldstr    aPlugintype// "PluginType"
0x556b0  ldarg.0
0x556b1  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::_context
0x556b6  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x556bb  pop
0x556bc  ldloc.0
0x556bd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::get_EntityMetadata()
0x556c2  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x556c7  ldarg.0
0x556c8  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::_context
0x556cd  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x556d2  stloc.1
0x556d3  ldloc.1
0x556d4  ldloc.0
0x556d5  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::set_Criteria(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression)
0x556da  ldarg.2
0x556db  ldloc.1
0x556dc  ldarg.0
0x556dd  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::_context
0x556e2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x556e7  ret
```
