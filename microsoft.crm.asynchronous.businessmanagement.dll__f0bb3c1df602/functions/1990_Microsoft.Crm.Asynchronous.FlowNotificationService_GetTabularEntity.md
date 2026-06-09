# Microsoft.Crm.Asynchronous.FlowNotificationService::GetTabularEntity

- ea: `0x1990`
- end: `0x1b71`
- name: `Microsoft.Crm.Asynchronous.FlowNotificationService::GetTabularEntity`
- size: `481`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1630`

## callees

- `0x1990`
- `0x1b80`
- `0x1dd0`

## string_xrefs

- `0x1ad6`: `Create`
- `0x1aed`: `Update`

## pseudocode

```c

```

## disassembly

```asm
0x1990  ldc.i4.6
0x1991  newarr   [mscorlib]System.String
0x1996  dup
0x1997  ldc.i4.0
0x1998  ldstr    aLogicalname// "LogicalName"
0x199d  stelem.ref
0x199e  dup
0x199f  ldc.i4.1
0x19a0  ldstr    aDisplayname// "DisplayName"
0x19a5  stelem.ref
0x19a6  dup
0x19a7  ldc.i4.2
0x19a8  ldstr    aEntitysetname// "EntitySetName"
0x19ad  stelem.ref
0x19ae  dup
0x19af  ldc.i4.3
0x19b0  ldstr    aCollectionsche// "CollectionSchemaName"
0x19b5  stelem.ref
0x19b6  dup
0x19b7  ldc.i4.4
0x19b8  ldstr    aDisplaycollect// "DisplayCollectionName"
0x19bd  stelem.ref
0x19be  dup
0x19bf  ldc.i4.5
0x19c0  ldstr    aIsactivity// "IsActivity"
0x19c5  stelem.ref
0x19c6  stloc.0
0x19c7  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x19cc  dup
0x19cd  ldstr    aMetadataid// "MetadataId"
0x19d2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x19d7  dup
0x19d8  ldstr    aManytoonerelat// "ManyToOneRelationships"
0x19dd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x19e2  dup
0x19e3  ldstr    aAttributes// "Attributes"
0x19e8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x19ed  dup
0x19ee  ldstr    aIsintersect// "IsIntersect"
0x19f3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x19f8  dup
0x19f9  ldstr    aIsimportable// "IsImportable"
0x19fe  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1a03  dup
0x1a04  ldstr    aIsmanaged// "IsManaged"
0x1a09  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1a0e  dup
0x1a0f  ldstr    aIsprivate// "IsPrivate"
0x1a14  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1a19  dup
0x1a1a  ldstr    aPrimaryidattri// "PrimaryIdAttribute"
0x1a1f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1a24  dup
0x1a25  ldstr    aPrimarynameatt// "PrimaryNameAttribute"
0x1a2a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1a2f  stloc.1
0x1a30  ldloc.1
0x1a31  ldloc.0
0x1a32  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x1a37  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.EntityQueryExpression::.ctor()
0x1a3c  dup
0x1a3d  ldc.i4.0
0x1a3e  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataFilterExpression::.ctor(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator)
0x1a43  dup
0x1a44  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataFilterExpression::get_Conditions()
0x1a49  ldstr    aLogicalname// "LogicalName"
0x1a4e  ldc.i4.0
0x1a4f  ldarg.0
0x1a50  ldfld    class [Microsoft.Crm]Microsoft.Crm.FlowNotificationOperationData Microsoft.Crm.Asynchronous.FlowNotificationService::asyncOperationData
0x1a55  callvirt instance string [Microsoft.Crm]Microsoft.Crm.FlowNotificationOperationData::get_PrimaryEntityName()
0x1a5a  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataConditionOperator, object)
0x1a5f  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataConditionExpression>::Add(var<u1>)
0x1a64  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataQueryExpression::set_Criteria(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataFilterExpression)
0x1a69  dup
0x1a6a  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.AttributeQueryExpression::.ctor()
0x1a6f  dup
0x1a70  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataPropertiesExpression::.ctor()
0x1a75  dup
0x1a76  ldc.i4.1
0x1a77  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataPropertiesExpression::set_AllProperties(bool)
0x1a7c  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataQueryExpression::set_Properties(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataPropertiesExpression)
0x1a81  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.EntityQueryExpression::set_AttributeQuery(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.AttributeQueryExpression)
0x1a86  dup
0x1a87  ldloc.1
0x1a88  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<string>::ToArray()
0x1a8d  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataPropertiesExpression::.ctor(string[])
0x1a92  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataQueryExpression::set_Properties(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataPropertiesExpression)
0x1a97  stloc.2
0x1a98  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMetadataChangesRequest::.ctor()
0x1a9d  dup
0x1a9e  ldloc.2
0x1a9f  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMetadataChangesRequest::set_Query(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.EntityQueryExpression)
0x1aa4  stloc.3
0x1aa5  ldarg.0
0x1aa6  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.FlowNotificationService::orgService
0x1aab  ldloc.3
0x1aac  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x1ab1  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMetadataChangesResponse
0x1ab6  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadataCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMetadataChangesResponse::get_EntityMetadata()
0x1abb  ldc.i4.0
0x1abc  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata>::get_Item(!!T0)
0x1ac1  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata> Microsoft.Crm.Asynchronous.FlowNotificationService::GetEntityAttributesMetadata(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata entityMetadata)
0x1ac6  stloc.s  4
0x1ac8  ldnull
0x1ac9  stloc.s  5
0x1acb  ldarg.0
0x1acc  ldfld    class [Microsoft.Crm]Microsoft.Crm.FlowNotificationOperationData Microsoft.Crm.Asynchronous.FlowNotificationService::asyncOperationData
0x1ad1  callvirt instance string [Microsoft.Crm]Microsoft.Crm.FlowNotificationOperationData::get_MessageName()
0x1ad6  ldstr    aCreate// "Create"
0x1adb  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1ae0  brtrue.s loc_1AF9
0x1ae2  ldarg.0
0x1ae3  ldfld    class [Microsoft.Crm]Microsoft.Crm.FlowNotificationOperationData Microsoft.Crm.Asynchronous.FlowNotificationService::asyncOperationData
0x1ae8  callvirt instance string [Microsoft.Crm]Microsoft.Crm.FlowNotificationOperationData::get_MessageName()
0x1aed  ldstr    aUpdate// "Update"
0x1af2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1af7  brfalse.s loc_1B4B
0x1af9  ldarg.0
0x1afa  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.FlowNotificationService::orgService
0x1aff  ldarg.0
0x1b00  ldfld    class [Microsoft.Crm]Microsoft.Crm.FlowNotificationOperationData Microsoft.Crm.Asynchronous.FlowNotificationService::asyncOperationData
0x1b05  callvirt instance string [Microsoft.Crm]Microsoft.Crm.FlowNotificationOperationData::get_PrimaryEntityName()
0x1b0a  ldarg.0
0x1b0b  ldfld    class [Microsoft.Crm]Microsoft.Crm.FlowNotificationOperationData Microsoft.Crm.Asynchronous.FlowNotificationService::asyncOperationData
0x1b10  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm]Microsoft.Crm.FlowNotificationOperationData::get_PrimaryKeyOfRecord()
0x1b15  ldc.i4.1
0x1b16  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(bool)
0x1b1b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Retrieve(string, valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet)
0x1b20  ldloc.s  4
0x1b22  ldarg.0
0x1b23  ldfld    class [Microsoft.Crm]Microsoft.Crm.FlowNotificationOperationData Microsoft.Crm.Asynchronous.FlowNotificationService::asyncOperationData
0x1b28  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm]Microsoft.Crm.FlowNotificationOperationData::get_PrimaryKeyOfRecord()
0x1b2d  ldarg.0
0x1b2e  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.FlowNotificationService::asyncEvent
0x1b33  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x1b38  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x1b3d  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1b42  call     class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> Microsoft.Crm.Asynchronous.FlowNotificationService::GetTabularEntityFromCrmEntity(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata> attributesMetadata, valuetype [mscorlib]System.Guid primaryKey, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache metadataCache)
0x1b47  stloc.s  5
0x1b49  br.s     loc_1B52
0x1b4b  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x1b50  stloc.s  5
0x1b52  ldloc.s  5
0x1b54  ldstr    aIteminternalid// "ItemInternalId"
0x1b59  ldarg.0
0x1b5a  ldfld    class [Microsoft.Crm]Microsoft.Crm.FlowNotificationOperationData Microsoft.Crm.Asynchronous.FlowNotificationService::asyncOperationData
0x1b5f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm]Microsoft.Crm.FlowNotificationOperationData::get_PrimaryKeyOfRecord()
0x1b64  box      [mscorlib]System.Guid
0x1b69  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::Add(var<u1>, !!T0)
0x1b6e  ldloc.s  5
0x1b70  ret
```
