# Microsoft.Crm.Tools.ImportExportPublish.SdkMessageProcessingStepConvertor::FindPluginTypeId

- ea: `0x90060`
- end: `0x9018e`
- name: `Microsoft.Crm.Tools.ImportExportPublish.SdkMessageProcessingStepConvertor::FindPluginTypeId`
- size: `302`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x8fac0`

## callees

- `0x90060`

## string_xrefs

- `0x9012d`: `PluginAssembly`
- `0x9011a`: `publickeytoken`
- `0x90132`: `pluginassemblyid`
- `0x90137`: `pluginassemblyid`
- `0x9008a`: `PluginType`
- `0x90095`: `PluginType`

## pseudocode

```c

```

## disassembly

```asm
0x90060  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x90065  stloc.0
0x90066  ldarg.2
0x90067  ldc.i4.0
0x90068  ldarg.2
0x90069  ldc.i4.s 0x2C
0x9006b  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x90070  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x90075  stloc.1
0x90076  ldarg.2
0x90077  ldloc.1
0x90078  callvirt instance int32 [mscorlib]System.String::get_Length()
0x9007d  ldc.i4.2
0x9007e  add
0x9007f  callvirt instance string [mscorlib]System.String::Substring(int32)
0x90084  call     class [Microsoft.Crm]Microsoft.Crm.CrmPluginAssemblyMetadata [Microsoft.Crm]Microsoft.Crm.CrmPluginAssemblyMetadata::GenerateFromFullAssemblyName(string)
0x90089  stloc.2
0x9008a  ldstr    aPlugintype// "PluginType"
0x9008f  ldarg.1
0x90090  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ServiceClassFactory::CreateInstance(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x90095  ldstr    aPlugintype// "PluginType"
0x9009a  ldarg.1
0x9009b  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x900a0  stloc.3
0x900a1  ldloc.3
0x900a2  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x900a7  ldstr    aTypename// "typename"
0x900ac  ldc.i4.0
0x900ad  ldloc.1
0x900ae  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x900b3  pop
0x900b4  ldloc.3
0x900b5  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x900ba  ldstr    aAssemblyname// "assemblyname"
0x900bf  ldc.i4.0
0x900c0  ldloc.2
0x900c1  callvirt instance string [Microsoft.Crm]Microsoft.Crm.CrmPluginAssemblyMetadata::get_ShortName()
0x900c6  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x900cb  pop
0x900cc  ldloc.3
0x900cd  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x900d2  ldstr    aMajor// "major"
0x900d7  ldc.i4.0
0x900d8  ldloc.2
0x900d9  callvirt instance string [Microsoft.Crm]Microsoft.Crm.CrmPluginAssemblyMetadata::get_VersionMajor()
0x900de  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x900e3  pop
0x900e4  ldloc.3
0x900e5  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x900ea  ldstr    aMinor// "minor"
0x900ef  ldc.i4.0
0x900f0  ldloc.2
0x900f1  callvirt instance string [Microsoft.Crm]Microsoft.Crm.CrmPluginAssemblyMetadata::get_VersionMinor()
0x900f6  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x900fb  pop
0x900fc  ldloc.3
0x900fd  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x90102  ldstr    aCulture// "culture"
0x90107  ldc.i4.0
0x90108  ldloc.2
0x90109  callvirt instance string [Microsoft.Crm]Microsoft.Crm.CrmPluginAssemblyMetadata::get_Culture()
0x9010e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x90113  pop
0x90114  ldloc.3
0x90115  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x9011a  ldstr    aPublickeytoken// "publickeytoken"
0x9011f  ldc.i4.0
0x90120  ldloc.2
0x90121  callvirt instance string [Microsoft.Crm]Microsoft.Crm.CrmPluginAssemblyMetadata::get_PublicKeyToken()
0x90126  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x9012b  pop
0x9012c  ldloc.3
0x9012d  ldstr    aPluginassembly_0// "PluginAssembly"
0x90132  ldstr    aPluginassembly_1// "pluginassemblyid"
0x90137  ldstr    aPluginassembly_1// "pluginassemblyid"
0x9013c  ldc.i4.0
0x9013d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::AddLinkEntity(string, string, string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0x90142  pop
0x90143  ldloc.3
0x90144  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpressionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_LinkedEntities()
0x90149  ldc.i4.0
0x9014a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression>::get_Item(!!T0)
0x9014f  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_LinkCriteria()
0x90154  ldstr    aSourcetype// "sourcetype"
0x90159  ldc.i4.1
0x9015a  ldc.i4.3
0x9015b  box      [mscorlib]System.Int32
0x90160  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x90165  pop
0x90166  ldloc.3
0x90167  ldarg.1
0x90168  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x9016d  stloc.s  4
0x9016f  ldloc.s  4
0x90171  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x90176  ldc.i4.0
0x90177  ble.s    loc_9018C
0x90179  ldloc.s  4
0x9017b  ldc.i4.0
0x9017c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x90181  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PrimaryKey()
0x90186  unbox.any [mscorlib]System.Guid
0x9018b  stloc.0
0x9018c  ldloc.0
0x9018d  ret
```
