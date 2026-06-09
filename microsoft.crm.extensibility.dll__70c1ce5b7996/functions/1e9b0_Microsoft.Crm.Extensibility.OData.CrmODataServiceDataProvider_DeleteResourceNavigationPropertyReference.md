# Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::DeleteResourceNavigationPropertyReference

- ea: `0x1e9b0`
- end: `0x1ea1f`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::DeleteResourceNavigationPropertyReference`
- size: `111`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x12d50`

## callees

- `0xf740`
- `0x10050`
- `0x1e5b0`
- `0x1f820`

## string_xrefs

- `0x1e9d1`: `Delete References directly is only valid for OneToManyEntityRelationship`

## pseudocode

```c

```

## disassembly

```asm
0x1e9b0  ldarg.2
0x1e9b1  ldarg.0
0x1e9b2  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::edmModel
0x1e9b7  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CrmEdmEntityType Microsoft.Crm.Extensibility.OData.EdmUtilities::GetEdmEntityType(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x1e9bc  ldarg.s  4
0x1e9be  call     class [mscorlib]System.Tuple`2<class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmNavigationProperty, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship> Microsoft.Crm.Extensibility.OData.CrmODataUtilities::GetRelationshipInformation(class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmEntityType edmEntityType, string propertyName)
0x1e9c3  dup
0x1e9c4  callvirt instance var<u1> class [mscorlib]System.Tuple`2<class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmNavigationProperty, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship>::get_Item2()
0x1e9c9  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OneToManyEntityRelationship
0x1e9ce  ldnull
0x1e9cf  cgt.un
0x1e9d1  ldstr    aDeleteReferenc// "Delete References directly is only vali"...
0x1e9d6  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x1e9db  callvirt instance var<u1> class [mscorlib]System.Tuple`2<class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmNavigationProperty, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship>::get_Item2()
0x1e9e0  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OneToManyEntityRelationship
0x1e9e5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OneToManyEntityRelationship::get_Relationship()
0x1e9ea  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencingAttribute()
0x1e9ef  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Name()
0x1e9f4  stloc.0
0x1e9f5  ldarg.2
0x1e9f6  ldarg.0
0x1e9f7  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::edmModel
0x1e9fc  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CrmEdmEntityType Microsoft.Crm.Extensibility.OData.EdmUtilities::GetEdmEntityType(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x1ea01  ldloc.0
0x1ea02  call     valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ModelVersion Microsoft.Crm.Extensibility.OData.ModelUtilities::GetModelVersion()
0x1ea07  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CrmEdmEntityType::GetEdmProperty(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ModelVersion)
0x1ea0c  callvirt instance string [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNamedElement::get_Name()
0x1ea11  stloc.1
0x1ea12  ldarg.0
0x1ea13  ldarg.1
0x1ea14  ldarg.2
0x1ea15  ldarg.3
0x1ea16  ldloc.1
0x1ea17  ldnull
0x1ea18  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::UpdateResourceProperty(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, string edmEntityName, string entityKeyValue, string propertyName, object edmPropertyValue)
0x1ea1d  pop
0x1ea1e  ret
```
