# Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::UpdateNavigationPropertyCollection

- ea: `0x1e790`
- end: `0x1e803`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::UpdateNavigationPropertyCollection`
- size: `115`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x128a0`

## callees

- `0xf6f0`
- `0xf740`
- `0xf7c0`
- `0xfe00`
- `0xffb0`
- `0x133e0`
- `0x13510`
- `0x1f820`
- `0x20090`
- `0x21370`
- `0x24c10`

## pseudocode

```c

```

## disassembly

```asm
0x1e790  ldarg.2
0x1e791  ldarg.0
0x1e792  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::edmModel
0x1e797  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CrmEdmEntityType Microsoft.Crm.Extensibility.OData.EdmUtilities::GetEdmEntityType(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x1e79c  ldarg.s  4
0x1e79e  call     class [mscorlib]System.Tuple`2<class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmNavigationProperty, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship> Microsoft.Crm.Extensibility.OData.CrmODataUtilities::GetRelationshipInformation(class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmEntityType edmEntityType, string propertyName)
0x1e7a3  callvirt instance var<u1> class [mscorlib]System.Tuple`2<class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmNavigationProperty, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship>::get_Item1()
0x1e7a8  call     string Microsoft.Crm.Extensibility.OData.EdmUtilities::GetEdmLinkedEntityName(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationProperty navigationProperty)
0x1e7ad  stloc.0
0x1e7ae  ldloc.0
0x1e7af  call     void Microsoft.Crm.Extensibility.OData.EdmUtilities::ThrowIfNavigationPropertyCollectionNotValidForUpdate(string navigationEntityName)
0x1e7b4  ldarg.2
0x1e7b5  ldarg.3
0x1e7b6  ldarg.0
0x1e7b7  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::edmModel
0x1e7bc  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference Microsoft.Crm.Extensibility.OData.CrmODataUtilities::GetXrmEntityReferenceForKeys(string edmEntityName, string key, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x1e7c1  stloc.1
0x1e7c2  ldarg.2
0x1e7c3  ldarg.0
0x1e7c4  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::edmModel
0x1e7c9  call     class Microsoft.Crm.Extensibility.OData.CrmEdmEntityObject Microsoft.Crm.Extensibility.OData.EdmUtilities::CreateNewEdmEntityObject(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x1e7ce  ldloc.1
0x1e7cf  ldarg.0
0x1e7d0  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::edmModel
0x1e7d5  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Extensibility.OData.EdmTypeConverter::ConvertToCrmEntity(class [System.Web.OData]System.Web.OData.EdmEntityObject edmEntity, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference entityReference, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x1e7da  stloc.2
0x1e7db  ldloc.2
0x1e7dc  ldarg.2
0x1e7dd  ldarg.0
0x1e7de  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::edmModel
0x1e7e3  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Extensibility.OData.EdmUtilities::GetXrmEntityMetadataFromEdmEntityName(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x1e7e8  ldarg.s  5
0x1e7ea  ldloc.0
0x1e7eb  ldarg.0
0x1e7ec  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::edmModel
0x1e7f1  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection Microsoft.Crm.Extensibility.OData.EdmTypeConverter::ConvertToCrmEntityCollection(class [System.Web.OData]System.Web.OData.EdmEntityObjectCollection edmEntityCollection, string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x1e7f6  call     void Microsoft.Crm.Extensibility.OData.CrmODataUtilities::SetNavigationPropertyCollectonForUpdate(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity crmEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entityMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection entityCollection)
0x1e7fb  ldarg.1
0x1e7fc  ldloc.2
0x1e7fd  callvirt instance void Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::Update(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity)
0x1e802  ret
```
