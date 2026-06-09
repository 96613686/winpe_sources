# Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::RetrievePluginAssembliesFromFQN

- ea: `0x54f10`
- end: `0x5503e`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::RetrievePluginAssembliesFromFQN`
- size: `302`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x550e0`
- `0x553e0`

## callees

- `0x54ee0`
- `0x54f10`

## string_xrefs

- `0x54f26`: `PluginAssembly`
- `0x54fd1`: `PluginAssembly`
- `0x54f85`: `publickeytoken`
- `0x54f8c`: `publickeytoken`
- `0x5501f`: `pluginassemblyid`

## pseudocode

```c

```

## disassembly

```asm
0x54f10  ldarg.1
0x54f11  ldstr    aVersion// "version"
0x54f16  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x54f1b  castclass [mscorlib]System.String
0x54f20  newobj   instance void [mscorlib]System.Version::.ctor(string)
0x54f25  stloc.0
0x54f26  ldstr    aPluginassembly_0// "PluginAssembly"
0x54f2b  ldarg.0
0x54f2c  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::_context
0x54f31  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x54f36  stloc.1
0x54f37  ldloc.1
0x54f38  ldstr    aName// "name"
0x54f3d  ldc.i4.0
0x54f3e  ldarg.1
0x54f3f  ldstr    aName// "name"
0x54f44  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x54f49  castclass [mscorlib]System.String
0x54f4e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x54f53  pop
0x54f54  ldloc.1
0x54f55  ldstr    aMajor// "major"
0x54f5a  ldc.i4.0
0x54f5b  ldloc.0
0x54f5c  callvirt instance int32 [mscorlib]System.Version::get_Major()
0x54f61  box      [mscorlib]System.Int32
0x54f66  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x54f6b  pop
0x54f6c  ldloc.1
0x54f6d  ldstr    aMinor// "minor"
0x54f72  ldc.i4.0
0x54f73  ldloc.0
0x54f74  callvirt instance int32 [mscorlib]System.Version::get_Minor()
0x54f79  box      [mscorlib]System.Int32
0x54f7e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x54f83  pop
0x54f84  ldloc.1
0x54f85  ldstr    aPublickeytoken// "publickeytoken"
0x54f8a  ldc.i4.0
0x54f8b  ldarg.1
0x54f8c  ldstr    aPublickeytoken// "publickeytoken"
0x54f91  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x54f96  castclass [mscorlib]System.String
0x54f9b  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x54fa0  pop
0x54fa1  ldloc.1
0x54fa2  ldstr    aCulture// "culture"
0x54fa7  ldc.i4.0
0x54fa8  ldarg.1
0x54fa9  ldstr    aCulture// "culture"
0x54fae  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x54fb3  castclass [mscorlib]System.String
0x54fb8  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x54fbd  pop
0x54fbe  ldloc.1
0x54fbf  ldstr    aSourcetype// "sourcetype"
0x54fc4  ldc.i4.1
0x54fc5  ldc.i4.3
0x54fc6  box      [mscorlib]System.Int32
0x54fcb  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x54fd0  pop
0x54fd1  ldstr    aPluginassembly_0// "PluginAssembly"
0x54fd6  ldarg.0
0x54fd7  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::_context
0x54fdc  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x54fe1  stloc.2
0x54fe2  ldloc.2
0x54fe3  ldstr    aSolutionid// "solutionid"
0x54fe8  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x54fed  ldarg.0
0x54fee  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::get_CustomizableAttributeExists()
0x54ff3  brfalse.s loc_55000
0x54ff5  ldloc.2
0x54ff6  ldstr    aIscustomizable// "iscustomizable"
0x54ffb  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x55000  ldloc.1
0x55001  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::get_EntityMetadata()
0x55006  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x5500b  ldarg.0
0x5500c  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::_context
0x55011  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x55016  stloc.3
0x55017  ldloc.3
0x55018  ldloc.1
0x55019  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::set_Criteria(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression)
0x5501e  ldloc.2
0x5501f  ldstr    aPluginassembly_1// "pluginassemblyid"
0x55024  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x55029  ldloc.3
0x5502a  ldloc.2
0x5502b  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::set_ColumnSet(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression)
0x55030  ldarg.2
0x55031  ldloc.3
0x55032  ldarg.0
0x55033  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::_context
0x55038  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5503d  ret
```
