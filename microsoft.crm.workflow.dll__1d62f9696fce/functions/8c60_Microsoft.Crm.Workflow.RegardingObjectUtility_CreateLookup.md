# Microsoft.Crm.Workflow.RegardingObjectUtility::CreateLookup

- ea: `0x8c60`
- end: `0x8e0c`
- name: `Microsoft.Crm.Workflow.RegardingObjectUtility::CreateLookup`
- size: `428`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x7970`
- `0x12c20`
- `0x17550`

## callees

- `0x8c60`

## pseudocode

```c

```

## disassembly

```asm
0x8c60  ldarg.1
0x8c61  ldstr    aEntityname// "entityName"
0x8c66  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x8c6b  ldarg.2
0x8c6c  ldstr    aEntityid// "entityId"
0x8c71  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x8c76  ldarg.0
0x8c77  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.RegardingObjectUtility::OrganizationId
0x8c7c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x8c81  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8c86  ldarg.1
0x8c87  ldc.i4.1
0x8c88  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x8c8d  stloc.0
0x8c8e  ldnull
0x8c8f  stloc.1
0x8c90  ldnull
0x8c91  stloc.2
0x8c92  ldloc.0
0x8c93  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryField()
0x8c98  brfalse  loc_8DF3
0x8c9d  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor()
0x8ca2  stloc.3
0x8ca3  ldloc.3
0x8ca4  ldc.i4.1
0x8ca5  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_NoLock(bool)
0x8caa  ldloc.3
0x8cab  ldarg.1
0x8cac  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_EntityName(string)
0x8cb1  ldloc.3
0x8cb2  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_ColumnSet()
0x8cb7  ldloc.0
0x8cb8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x8cbd  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x8cc2  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumn(string)
0x8cc7  ldloc.3
0x8cc8  ldc.i4.1
0x8cc9  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x8cce  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_TopCount(valuetype [mscorlib]System.Nullable`1<int32>)
0x8cd3  ldloc.0
0x8cd4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryField()
0x8cd9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_AttributeOf()
0x8cde  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x8ce3  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x8ce8  brfalse.s loc_8D17
0x8cea  ldloc.3
0x8ceb  ldc.i4.1
0x8cec  newarr   [mscorlib]System.String
0x8cf1  dup
0x8cf2  ldc.i4.0
0x8cf3  ldloc.0
0x8cf4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryField()
0x8cf9  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x8cfe  stelem.ref
0x8cff  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(string[])
0x8d04  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_ColumnSet(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet)
0x8d09  ldloc.0
0x8d0a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryField()
0x8d0f  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x8d14  stloc.2
0x8d15  br.s     loc_8D58
0x8d17  ldloc.3
0x8d18  ldc.i4.1
0x8d19  newarr   [mscorlib]System.String
0x8d1e  dup
0x8d1f  ldc.i4.0
0x8d20  ldloc.0
0x8d21  ldloc.0
0x8d22  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryField()
0x8d27  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_AttributeOf()
0x8d2c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(valuetype [mscorlib]System.Guid)
0x8d31  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x8d36  stelem.ref
0x8d37  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(string[])
0x8d3c  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_ColumnSet(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet)
0x8d41  ldloc.0
0x8d42  ldloc.0
0x8d43  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryField()
0x8d48  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_AttributeOf()
0x8d4d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(valuetype [mscorlib]System.Guid)
0x8d52  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x8d57  stloc.2
0x8d58  ldloc.3
0x8d59  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x8d5e  ldloc.0
0x8d5f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x8d64  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x8d69  ldc.i4.0
0x8d6a  ldarg.2
0x8d6b  box      [mscorlib]System.Guid
0x8d70  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x8d75  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression)
0x8d7a  ldarg.0
0x8d7b  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Workflow.RegardingObjectUtility::_sdkService
0x8d80  ldloc.3
0x8d81  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::RetrieveMultiple(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryBase)
0x8d86  stloc.s  4
0x8d88  ldloc.s  4
0x8d8a  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x8d8f  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Count()
0x8d94  ldc.i4.0
0x8d95  ble.s    loc_8DF3
0x8d97  ldloc.s  4
0x8d99  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x8d9e  ldc.i4.0
0x8d9f  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Item(!!T0)
0x8da4  stloc.s  5
0x8da6  ldloc.s  5
0x8da8  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x8dad  ldloc.2
0x8dae  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x8db3  brfalse.s loc_8DF3
0x8db5  ldloc.2
0x8db6  ldloc.0
0x8db7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryField()
0x8dbc  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x8dc1  callvirt instance bool [mscorlib]System.String::Equals(string)
0x8dc6  brfalse.s loc_8DD8
0x8dc8  ldloc.s  5
0x8dca  ldloc.2
0x8dcb  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x8dd0  isinst   [mscorlib]System.String
0x8dd5  stloc.1
0x8dd6  br.s     loc_8DF3
0x8dd8  ldloc.s  5
0x8dda  ldloc.2
0x8ddb  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x8de0  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x8de5  stloc.s  6
0x8de7  ldloc.s  6
0x8de9  brfalse.s loc_8DF3
0x8deb  ldloc.s  6
0x8ded  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Name()
0x8df2  stloc.1
0x8df3  ldarg.1
0x8df4  ldarg.2
0x8df5  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x8dfa  dup
0x8dfb  ldloc.1
0x8dfc  dup
0x8dfd  brtrue.s loc_8E06
0x8dff  pop
0x8e00  ldloc.0
0x8e01  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_OriginalLocalizedName()
0x8e06  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::set_Name(string)
0x8e0b  ret
```
