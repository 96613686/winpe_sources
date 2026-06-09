# Microsoft.Crm.Tools.ImportExportPublish.PluginAssemblyImportExportDependencyHelper::DoesComponentExistInternal

- ea: `0x15c10`
- end: `0x15d83`
- name: `Microsoft.Crm.Tools.ImportExportPublish.PluginAssemblyImportExportDependencyHelper::DoesComponentExistInternal`
- size: `371`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x15a30`
- `0x15ba0`

## callees

- `0x12d60`
- `0x15c10`

## string_xrefs

- `0x15c16`: `PluginAssembly`
- `0x15c32`: `PluginAssembly`
- `0x15c70`: `PluginAssembly`
- `0x15cf5`: `publickeytoken`
- `0x15c45`: `pluginassemblyid`
- `0x15d58`: `pluginassemblyid`

## pseudocode

```c

```

## disassembly

```asm
0x15c10  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x15c15  stloc.0
0x15c16  ldstr    aPluginassembly_0// "PluginAssembly"
0x15c1b  ldarg.s  4
0x15c1d  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ServiceClassFactory::CreateInstance(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x15c22  stloc.1
0x15c23  ldnull
0x15c24  stloc.2
0x15c25  ldarg.3
0x15c26  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x15c2b  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x15c30  brfalse.s loc_15C61
0x15c32  ldstr    aPluginassembly_0// "PluginAssembly"
0x15c37  ldarg.s  4
0x15c39  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x15c3e  stloc.3
0x15c3f  ldloc.3
0x15c40  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x15c45  ldstr    aPluginassembly_1// "pluginassemblyid"
0x15c4a  ldc.i4.0
0x15c4b  ldarg.3
0x15c4c  box      [mscorlib]System.Guid
0x15c51  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x15c56  pop
0x15c57  ldloc.1
0x15c58  ldloc.3
0x15c59  ldarg.s  4
0x15c5b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x15c60  stloc.2
0x15c61  ldloc.2
0x15c62  brfalse.s loc_15C70
0x15c64  ldloc.2
0x15c65  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x15c6a  ldc.i4.1
0x15c6b  bge      loc_15D48
0x15c70  ldstr    aPluginassembly_0// "PluginAssembly"
0x15c75  ldarg.s  4
0x15c77  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x15c7c  stloc.s  4
0x15c7e  ldarg.2
0x15c7f  call     class [Microsoft.Crm]Microsoft.Crm.CrmPluginAssemblyMetadata [Microsoft.Crm]Microsoft.Crm.CrmPluginAssemblyMetadata::GenerateFromFullAssemblyName(string)
0x15c84  stloc.s  5
0x15c86  ldloc.s  4
0x15c88  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x15c8d  ldstr    aName// "name"
0x15c92  ldc.i4.0
0x15c93  ldloc.s  5
0x15c95  callvirt instance string [Microsoft.Crm]Microsoft.Crm.CrmPluginAssemblyMetadata::get_ShortName()
0x15c9a  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x15c9f  pop
0x15ca0  ldloc.s  4
0x15ca2  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x15ca7  ldstr    aMajor// "major"
0x15cac  ldc.i4.0
0x15cad  ldloc.s  5
0x15caf  callvirt instance string [Microsoft.Crm]Microsoft.Crm.CrmPluginAssemblyMetadata::get_VersionMajor()
0x15cb4  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x15cb9  pop
0x15cba  ldloc.s  4
0x15cbc  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x15cc1  ldstr    aMinor// "minor"
0x15cc6  ldc.i4.0
0x15cc7  ldloc.s  5
0x15cc9  callvirt instance string [Microsoft.Crm]Microsoft.Crm.CrmPluginAssemblyMetadata::get_VersionMinor()
0x15cce  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x15cd3  pop
0x15cd4  ldloc.s  4
0x15cd6  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x15cdb  ldstr    aCulture// "culture"
0x15ce0  ldc.i4.0
0x15ce1  ldloc.s  5
0x15ce3  callvirt instance string [Microsoft.Crm]Microsoft.Crm.CrmPluginAssemblyMetadata::get_Culture()
0x15ce8  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x15ced  pop
0x15cee  ldloc.s  4
0x15cf0  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x15cf5  ldstr    aPublickeytoken// "publickeytoken"
0x15cfa  ldc.i4.0
0x15cfb  ldloc.s  5
0x15cfd  callvirt instance string [Microsoft.Crm]Microsoft.Crm.CrmPluginAssemblyMetadata::get_PublicKeyToken()
0x15d02  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x15d07  pop
0x15d08  ldloc.s  4
0x15d0a  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x15d0f  ldstr    aSourcetype// "sourcetype"
0x15d14  ldc.i4.1
0x15d15  ldc.i4.3
0x15d16  box      [mscorlib]System.Int32
0x15d1b  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x15d20  pop
0x15d21  ldarg.1
0x15d22  brfalse.s loc_15D3D
0x15d24  ldloc.s  4
0x15d26  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x15d2b  ldstr    aIsmanaged// "ismanaged"
0x15d30  ldc.i4.0
0x15d31  ldc.i4.1
0x15d32  box      [mscorlib]System.Boolean
0x15d37  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x15d3c  pop
0x15d3d  ldloc.1
0x15d3e  ldloc.s  4
0x15d40  ldarg.s  4
0x15d42  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x15d47  stloc.2
0x15d48  ldloc.2
0x15d49  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x15d4e  ldc.i4.0
0x15d4f  ble.s    loc_15D81
0x15d51  ldloc.2
0x15d52  ldc.i4.0
0x15d53  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x15d58  ldstr    aPluginassembly_1// "pluginassemblyid"
0x15d5d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x15d62  unbox.any [mscorlib]System.Guid
0x15d67  stloc.0
0x15d68  ldarg.1
0x15d69  brfalse.s loc_15D81
0x15d6b  ldarg.s  6
0x15d6d  ldc.i4.s 0x5B
0x15d6f  ldloc.0
0x15d70  ldarg.s  5
0x15d72  ldarg.s  4
0x15d74  call     bool Microsoft.Crm.Tools.ImportExportPublish.Helper::HasTheSamePublisher(class [System.Xml]System.Xml.XmlNode requiredNode, int32 componentType, valuetype [mscorlib]System.Guid objectId, valuetype [mscorlib]System.Guid publisherId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x15d79  brtrue.s loc_15D81
0x15d7b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x15d80  stloc.0
0x15d81  ldloc.0
0x15d82  ret
```
