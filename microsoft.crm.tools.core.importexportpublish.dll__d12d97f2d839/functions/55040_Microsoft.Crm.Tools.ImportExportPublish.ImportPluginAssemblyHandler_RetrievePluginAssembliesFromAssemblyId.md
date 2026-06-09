# Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::RetrievePluginAssembliesFromAssemblyId

- ea: `0x55040`
- end: `0x550d1`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::RetrievePluginAssembliesFromAssemblyId`
- size: `145`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x550e0`
- `0x553e0`

## callees

- `0x55040`

## string_xrefs

- `0x5504f`: `PluginAssembly`
- `0x55082`: `PluginAssembly`
- `0x55041`: `pluginassemblyid`
- `0x55061`: `pluginassemblyid`
- `0x55068`: `pluginassemblyid`
- `0x550b2`: `pluginassemblyid`

## pseudocode

```c

```

## disassembly

```asm
0x55040  ldarg.1
0x55041  ldstr    aPluginassembly_1// "pluginassemblyid"
0x55046  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x5504b  brfalse.s loc_5504F
0x5504d  ldnull
0x5504e  ret
0x5504f  ldstr    aPluginassembly_0// "PluginAssembly"
0x55054  ldarg.0
0x55055  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::_context
0x5505a  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5505f  stloc.0
0x55060  ldloc.0
0x55061  ldstr    aPluginassembly_1// "pluginassemblyid"
0x55066  ldc.i4.0
0x55067  ldarg.1
0x55068  ldstr    aPluginassembly_1// "pluginassemblyid"
0x5506d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x55072  unbox.any [mscorlib]System.Guid
0x55077  box      [mscorlib]System.Guid
0x5507c  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x55081  pop
0x55082  ldstr    aPluginassembly_0// "PluginAssembly"
0x55087  ldarg.0
0x55088  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::_context
0x5508d  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x55092  stloc.1
0x55093  ldloc.0
0x55094  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::get_EntityMetadata()
0x55099  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x5509e  ldarg.0
0x5509f  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::_context
0x550a4  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x550a9  stloc.2
0x550aa  ldloc.2
0x550ab  ldloc.0
0x550ac  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::set_Criteria(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression)
0x550b1  ldloc.1
0x550b2  ldstr    aPluginassembly_1// "pluginassemblyid"
0x550b7  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x550bc  ldloc.2
0x550bd  ldloc.1
0x550be  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::set_ColumnSet(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression)
0x550c3  ldarg.2
0x550c4  ldloc.2
0x550c5  ldarg.0
0x550c6  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::_context
0x550cb  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x550d0  ret
```
