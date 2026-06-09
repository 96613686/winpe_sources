# Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::RetrievePluginTypesFromPluginId

- ea: `0x556f0`
- end: `0x55791`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::RetrievePluginTypesFromPluginId`
- size: `161`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x55530`

## callees

- `0x556f0`

## string_xrefs

- `0x55733`: `pluginassemblyid`
- `0x5573a`: `pluginassemblyid`
- `0x556ff`: `PluginType`
- `0x55754`: `PluginType`
- `0x556f1`: `plugintypeid`
- `0x55711`: `plugintypeid`
- `0x55718`: `plugintypeid`

## pseudocode

```c

```

## disassembly

```asm
0x556f0  ldarg.1
0x556f1  ldstr    aPlugintypeid_0// "plugintypeid"
0x556f6  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x556fb  brfalse.s loc_556FF
0x556fd  ldnull
0x556fe  ret
0x556ff  ldstr    aPlugintype// "PluginType"
0x55704  ldarg.0
0x55705  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::_context
0x5570a  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5570f  stloc.0
0x55710  ldloc.0
0x55711  ldstr    aPlugintypeid_0// "plugintypeid"
0x55716  ldc.i4.0
0x55717  ldarg.1
0x55718  ldstr    aPlugintypeid_0// "plugintypeid"
0x5571d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x55722  unbox.any [mscorlib]System.Guid
0x55727  box      [mscorlib]System.Guid
0x5572c  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x55731  pop
0x55732  ldloc.0
0x55733  ldstr    aPluginassembly_1// "pluginassemblyid"
0x55738  ldc.i4.0
0x55739  ldarg.1
0x5573a  ldstr    aPluginassembly_1// "pluginassemblyid"
0x5573f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x55744  unbox.any [mscorlib]System.Guid
0x55749  box      [mscorlib]System.Guid
0x5574e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x55753  pop
0x55754  ldstr    aPlugintype// "PluginType"
0x55759  ldarg.0
0x5575a  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::_context
0x5575f  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x55764  pop
0x55765  ldloc.0
0x55766  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::get_EntityMetadata()
0x5576b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x55770  ldarg.0
0x55771  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::_context
0x55776  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x5577b  stloc.1
0x5577c  ldloc.1
0x5577d  ldloc.0
0x5577e  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::set_Criteria(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression)
0x55783  ldarg.2
0x55784  ldloc.1
0x55785  ldarg.0
0x55786  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::_context
0x5578b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x55790  ret
```
