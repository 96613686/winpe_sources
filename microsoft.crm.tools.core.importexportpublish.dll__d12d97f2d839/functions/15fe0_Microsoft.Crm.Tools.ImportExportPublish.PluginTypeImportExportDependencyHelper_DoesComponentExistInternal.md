# Microsoft.Crm.Tools.ImportExportPublish.PluginTypeImportExportDependencyHelper::DoesComponentExistInternal

- ea: `0x15fe0`
- end: `0x161c1`
- name: `Microsoft.Crm.Tools.ImportExportPublish.PluginTypeImportExportDependencyHelper::DoesComponentExistInternal`
- size: `481`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x15db0`
- `0x15f80`

## callees

- `0x12d60`
- `0x15fe0`

## string_xrefs

- `0x1610d`: `PluginAssembly`
- `0x160f8`: `publickeytoken`
- `0x16112`: `pluginassemblyid`
- `0x16117`: `pluginassemblyid`
- `0x15fe6`: `PluginType`
- `0x16002`: `PluginType`
- `0x16066`: `PluginType`
- `0x16015`: `plugintypeid`
- `0x16196`: `plugintypeid`

## pseudocode

```c

```

## disassembly

```asm
0x15fe0  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x15fe5  stloc.0
0x15fe6  ldstr    aPlugintype// "PluginType"
0x15feb  ldarg.s  4
0x15fed  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ServiceClassFactory::CreateInstance(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x15ff2  stloc.1
0x15ff3  ldnull
0x15ff4  stloc.2
0x15ff5  ldarg.3
0x15ff6  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x15ffb  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x16000  brfalse.s loc_16031
0x16002  ldstr    aPlugintype// "PluginType"
0x16007  ldarg.s  4
0x16009  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x1600e  stloc.3
0x1600f  ldloc.3
0x16010  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x16015  ldstr    aPlugintypeid_0// "plugintypeid"
0x1601a  ldc.i4.0
0x1601b  ldarg.3
0x1601c  box      [mscorlib]System.Guid
0x16021  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x16026  pop
0x16027  ldloc.1
0x16028  ldloc.3
0x16029  ldarg.s  4
0x1602b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x16030  stloc.2
0x16031  ldloc.2
0x16032  brfalse.s loc_16040
0x16034  ldloc.2
0x16035  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x1603a  ldc.i4.1
0x1603b  bge      loc_16186
0x16040  ldarg.2
0x16041  ldc.i4.s 0x2C
0x16043  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x16048  stloc.s  4
0x1604a  ldarg.2
0x1604b  ldc.i4.0
0x1604c  ldloc.s  4
0x1604e  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x16053  stloc.s  5
0x16055  ldarg.2
0x16056  ldloc.s  4
0x16058  ldc.i4.2
0x16059  add
0x1605a  callvirt instance string [mscorlib]System.String::Substring(int32)
0x1605f  call     class [Microsoft.Crm]Microsoft.Crm.CrmPluginAssemblyMetadata [Microsoft.Crm]Microsoft.Crm.CrmPluginAssemblyMetadata::GenerateFromFullAssemblyName(string)
0x16064  stloc.s  6
0x16066  ldstr    aPlugintype// "PluginType"
0x1606b  ldarg.s  4
0x1606d  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x16072  stloc.s  7
0x16074  ldloc.s  7
0x16076  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x1607b  ldstr    aTypename// "typename"
0x16080  ldc.i4.0
0x16081  ldloc.s  5
0x16083  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x16088  pop
0x16089  ldloc.s  7
0x1608b  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x16090  ldstr    aAssemblyname// "assemblyname"
0x16095  ldc.i4.0
0x16096  ldloc.s  6
0x16098  callvirt instance string [Microsoft.Crm]Microsoft.Crm.CrmPluginAssemblyMetadata::get_ShortName()
0x1609d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x160a2  pop
0x160a3  ldloc.s  7
0x160a5  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x160aa  ldstr    aMajor// "major"
0x160af  ldc.i4.0
0x160b0  ldloc.s  6
0x160b2  callvirt instance string [Microsoft.Crm]Microsoft.Crm.CrmPluginAssemblyMetadata::get_VersionMajor()
0x160b7  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x160bc  pop
0x160bd  ldloc.s  7
0x160bf  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x160c4  ldstr    aMinor// "minor"
0x160c9  ldc.i4.0
0x160ca  ldloc.s  6
0x160cc  callvirt instance string [Microsoft.Crm]Microsoft.Crm.CrmPluginAssemblyMetadata::get_VersionMinor()
0x160d1  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x160d6  pop
0x160d7  ldloc.s  7
0x160d9  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x160de  ldstr    aCulture// "culture"
0x160e3  ldc.i4.0
0x160e4  ldloc.s  6
0x160e6  callvirt instance string [Microsoft.Crm]Microsoft.Crm.CrmPluginAssemblyMetadata::get_Culture()
0x160eb  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x160f0  pop
0x160f1  ldloc.s  7
0x160f3  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x160f8  ldstr    aPublickeytoken// "publickeytoken"
0x160fd  ldc.i4.0
0x160fe  ldloc.s  6
0x16100  callvirt instance string [Microsoft.Crm]Microsoft.Crm.CrmPluginAssemblyMetadata::get_PublicKeyToken()
0x16105  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x1610a  pop
0x1610b  ldloc.s  7
0x1610d  ldstr    aPluginassembly_0// "PluginAssembly"
0x16112  ldstr    aPluginassembly_1// "pluginassemblyid"
0x16117  ldstr    aPluginassembly_1// "pluginassemblyid"
0x1611c  ldc.i4.0
0x1611d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::AddLinkEntity(string, string, string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0x16122  pop
0x16123  ldloc.s  7
0x16125  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpressionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_LinkedEntities()
0x1612a  ldc.i4.0
0x1612b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression>::get_Item(!!T0)
0x16130  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_LinkCriteria()
0x16135  ldstr    aSourcetype// "sourcetype"
0x1613a  ldc.i4.1
0x1613b  ldc.i4.3
0x1613c  box      [mscorlib]System.Int32
0x16141  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x16146  pop
0x16147  ldloc.s  7
0x16149  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpressionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_LinkedEntities()
0x1614e  ldc.i4.0
0x1614f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression>::get_Item(!!T0)
0x16154  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_LinkCriteria()
0x16159  ldc.i4.0
0x1615a  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::set_FilterOperator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator)
0x1615f  ldarg.1
0x16160  brfalse.s loc_1617B
0x16162  ldloc.s  7
0x16164  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x16169  ldstr    aIsmanaged// "ismanaged"
0x1616e  ldc.i4.0
0x1616f  ldc.i4.1
0x16170  box      [mscorlib]System.Boolean
0x16175  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x1617a  pop
0x1617b  ldloc.1
0x1617c  ldloc.s  7
0x1617e  ldarg.s  4
0x16180  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x16185  stloc.2
0x16186  ldloc.2
0x16187  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x1618c  ldc.i4.0
0x1618d  ble.s    loc_161BF
0x1618f  ldloc.2
0x16190  ldc.i4.0
0x16191  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x16196  ldstr    aPlugintypeid_0// "plugintypeid"
0x1619b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x161a0  unbox.any [mscorlib]System.Guid
0x161a5  stloc.0
0x161a6  ldarg.1
0x161a7  brfalse.s loc_161BF
0x161a9  ldarg.s  6
0x161ab  ldc.i4.s 0x5A
0x161ad  ldloc.0
0x161ae  ldarg.s  5
0x161b0  ldarg.s  4
0x161b2  call     bool Microsoft.Crm.Tools.ImportExportPublish.Helper::HasTheSamePublisher(class [System.Xml]System.Xml.XmlNode requiredNode, int32 componentType, valuetype [mscorlib]System.Guid objectId, valuetype [mscorlib]System.Guid publisherId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x161b7  brtrue.s loc_161BF
0x161b9  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x161be  stloc.0
0x161bf  ldloc.0
0x161c0  ret
```
