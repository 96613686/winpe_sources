# Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::UpdateResourceNavigationPropertyReference

- ea: `0x1e600`
- end: `0x1e787`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::UpdateResourceNavigationPropertyReference`
- size: `391`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x12c70`

## callees

- `0xf740`
- `0xf7c0`
- `0x13460`
- `0x179f0`
- `0x17a00`
- `0x17a10`
- `0x1e5b0`
- `0x1e600`
- `0x1f840`
- `0x21370`
- `0x24b20`
- `0x24e20`
- `0x24e50`
- `0x291b0`

## pseudocode

```c

```

## disassembly

```asm
0x1e600  ldarg.s  5
0x1e602  callvirt instance string Microsoft.Crm.Extensibility.OData.CrmEdmEntityReference::get_EdmEntityCollectionName()
0x1e607  ldarg.s  5
0x1e609  callvirt instance string Microsoft.Crm.Extensibility.OData.CrmEdmEntityReference::get_EdmEntityKey()
0x1e60e  stloc.0
0x1e60f  ldarg.2
0x1e610  ldarg.3
0x1e611  ldarg.0
0x1e612  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::edmModel
0x1e617  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference Microsoft.Crm.Extensibility.OData.CrmODataUtilities::GetXrmEntityReferenceForKeys(string edmEntityName, string key, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x1e61c  stloc.1
0x1e61d  dup
0x1e61e  ldloc.0
0x1e61f  ldarg.0
0x1e620  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::edmModel
0x1e625  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference Microsoft.Crm.Extensibility.OData.CrmODataUtilities::GetXrmEntityReferenceForKeys(string edmEntityName, string key, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x1e62a  stloc.2
0x1e62b  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EdmEntityProvider::IsOwnerTypeEntity(string)
0x1e630  brfalse  loc_1E733
0x1e635  ldarg.2
0x1e636  ldarg.0
0x1e637  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::edmModel
0x1e63c  call     class Microsoft.Crm.Extensibility.OData.CrmEdmEntityObject Microsoft.Crm.Extensibility.OData.EdmUtilities::CreateNewEdmEntityObject(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x1e641  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmStructuredType [System.Web.OData]System.Web.OData.EdmStructuredObject::get_ActualEdmType()
0x1e646  ldarg.s  4
0x1e648  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmStructuredType::FindProperty(string)
0x1e64d  stloc.s  7
0x1e64f  ldloc.s  7
0x1e651  brfalse  loc_1E6FC
0x1e656  ldloc.s  7
0x1e658  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty::get_Type()
0x1e65d  call     bool [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmTypeSemantics::IsCollection(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference)
0x1e662  brfalse  loc_1E6FC
0x1e667  ldloc.2
0x1e668  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_LogicalName()
0x1e66d  ldloc.2
0x1e66e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x1e673  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string, valuetype [mscorlib]System.Guid)
0x1e678  stloc.s  8
0x1e67a  ldarg.1
0x1e67b  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_CrmExecutionContext()
0x1e680  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1e685  ldloc.s  8
0x1e687  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x1e68c  ldc.i4.1
0x1e68d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x1e692  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x1e697  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x1e69c  stloc.s  9
0x1e69e  ldloc.s  8
0x1e6a0  ldloc.s  9
0x1e6a2  ldloc.2
0x1e6a3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x1e6a8  box      [mscorlib]System.Guid
0x1e6ad  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x1e6b2  ldloc.s  8
0x1e6b4  ldloc.2
0x1e6b5  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_LogicalName()
0x1e6ba  ldarg.0
0x1e6bb  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::edmModel
0x1e6c0  ldc.i4.0
0x1e6c1  ldc.i4.0
0x1e6c2  ldc.i4.1
0x1e6c3  call     class [System.Web.OData]System.Web.OData.EdmEntityObject Microsoft.Crm.Extensibility.OData.EdmTypeConverter::ConvertToEdmEntityObject(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel, [opt] bool isDeltaEntity, [opt] bool fillAllProperties, [opt] bool noLock)
0x1e6c8  stloc.s  0xA
0x1e6ca  ldloc.2
0x1e6cb  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_LogicalName()
0x1e6d0  ldarg.0
0x1e6d1  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::edmModel
0x1e6d6  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CrmEdmEntityType Microsoft.Crm.Extensibility.OData.EdmUtilities::GetEdmEntityType(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x1e6db  ldc.i4.0
0x1e6dc  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::ToEdmTypeReference(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmType edmType, bool isNullable)
0x1e6e1  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmCollectionType::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference)
0x1e6e6  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmCollectionTypeReference::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmCollectionType)
0x1e6eb  newobj   instance void [System.Web.OData]System.Web.OData.EdmEntityObjectCollection::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmCollectionTypeReference)
0x1e6f0  dup
0x1e6f1  ldloc.s  0xA
0x1e6f3  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Web.OData]System.Web.OData.IEdmEntityObject>::Add(var<u1>)
0x1e6f8  stloc.s  6
0x1e6fa  br.s     loc_1E724
0x1e6fc  ldarg.1
0x1e6fd  callvirt instance class [System]System.Uri Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_ServiceRootUri()
0x1e702  callvirt instance string [mscorlib]System.Object::ToString()
0x1e707  ldstr    asc_422BE// "/"
0x1e70c  call     string [mscorlib]System.String::Concat(string, string)
0x1e711  newobj   instance void [System]System.Uri::.ctor(string)
0x1e716  ldarg.s  5
0x1e718  callvirt instance class [System]System.Uri Microsoft.Crm.Extensibility.OData.CrmEdmEntityReference::get_Link()
0x1e71d  call     instance class [System]System.Uri [System]System.Uri::MakeRelativeUri(class [System]System.Uri)
0x1e722  stloc.s  6
0x1e724  ldarg.0
0x1e725  ldarg.1
0x1e726  ldarg.2
0x1e727  ldarg.3
0x1e728  ldarg.s  4
0x1e72a  ldloc.s  6
0x1e72c  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::UpdateResourceProperty(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, string edmEntityName, string entityKeyValue, string propertyName, object edmPropertyValue)
0x1e731  pop
0x1e732  ret
0x1e733  ldloca.s 3
0x1e735  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityRole>
0x1e73b  ldarg.2
0x1e73c  ldarg.0
0x1e73d  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::edmModel
0x1e742  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CrmEdmEntityType Microsoft.Crm.Extensibility.OData.EdmUtilities::GetEdmEntityType(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x1e747  ldarg.s  4
0x1e749  ldloca.s 3
0x1e74b  call     class [mscorlib]System.Tuple`2<class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmNavigationProperty, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship> Microsoft.Crm.Extensibility.OData.CrmODataUtilities::GetRelationshipInformation(class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmEntityType edmEntityType, string propertyName, valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityRole>& role)
0x1e750  stloc.s  4
0x1e752  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference>::.ctor()
0x1e757  dup
0x1e758  ldloc.2
0x1e759  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference>::Add(var<u1>)
0x1e75e  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReferenceCollection::.ctor(class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference>)
0x1e763  stloc.s  5
0x1e765  ldarg.1
0x1e766  ldloc.1
0x1e767  ldloc.s  4
0x1e769  callvirt instance var<u1> class [mscorlib]System.Tuple`2<class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmNavigationProperty, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship>::get_Item2()
0x1e76e  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship::get_SchemaName()
0x1e773  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Relationship::.ctor(string)
0x1e778  dup
0x1e779  ldloc.3
0x1e77a  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Relationship::set_PrimaryEntityRole(valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityRole>)
0x1e77f  ldloc.s  5
0x1e781  callvirt instance void Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::Associate(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference entityReference, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Relationship relationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReferenceCollection relatedEntities)
0x1e786  ret
```
