# Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::GetInnerNavigationForEntityNavigation

- ea: `0x23610`
- end: `0x236b2`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::GetInnerNavigationForEntityNavigation`
- size: `162`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x22bb0`
- `0x22d40`

## callees

- `0x15e70`
- `0x16ec0`
- `0x16fd0`
- `0x22b80`
- `0x230b0`
- `0x23610`
- `0x23d50`
- `0x23ec0`

## pseudocode

```c

```

## disassembly

```asm
0x23610  ldnull
0x23611  stloc.0
0x23612  ldarg.2
0x23613  ldarg.0
0x23614  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::edmModel
0x23619  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::GetCrmMetadataEntityMetadataFromEdmEntityName(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x2361e  stloc.1
0x2361f  ldarg.0
0x23620  ldarg.s  4
0x23622  ldarg.s  6
0x23624  ldloc.1
0x23625  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::GetXrmMetatadataEntityMetadataForNavigationProperty(string navigationPropertyName, string derivedAttributeName, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata xrmEntityMetadata)
0x2362a  stloc.2
0x2362b  ldloc.2
0x2362c  callvirt instance class [mscorlib]System.Type [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata::get_ClrType()
0x23631  stloc.3
0x23632  ldarg.0
0x23633  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::edmModel
0x23638  newobj   instance void Microsoft.Crm.Extensibility.OData.MetadataQueryOptionsConverter::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x2363d  ldloc.1
0x2363e  ldarg.3
0x2363f  ldarg.s  4
0x23641  ldloc.2
0x23642  callvirt instance class [mscorlib]System.Type [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata::get_ClrType()
0x23647  ldnull
0x23648  ldarg.s  5
0x2364a  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.EntityQueryExpression Microsoft.Crm.Extensibility.OData.MetadataQueryOptionsConverter::GetEntityQueryExpressionForEntityNavigationProperty(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata xrmEntityMetadata, string entityIdValue, string edmNavigationPropertyName, class [mscorlib]System.Type navigationPropertyCrmType, class [System.Web.OData]System.Web.OData.Query.ODataQueryOptions queryOptions, [opt] string navigationIdValue)
0x2364f  stloc.s  4
0x23651  ldloc.2
0x23652  ldarg.s  7
0x23654  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::GetXrmEntityMetadataOfNavigationPropertyName(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata xrmEntityMetadata, string edmNavigationPropertyName)
0x23659  stloc.s  5
0x2365b  ldarg.s  8
0x2365d  ldloc.s  5
0x2365f  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmEntitySet [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata::get_EdmEntitySet()
0x23664  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmEntityType [Microsoft.OData.Edm]Microsoft.OData.Edm.ExtensionMethods::EntityType(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationSource)
0x23669  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CrmEdmEntityType
0x2366e  stind.ref
0x2366f  ldarg.s  7
0x23671  ldloc.2
0x23672  ldloc.s  4
0x23674  call     string Microsoft.Crm.Extensibility.OData.MetadataQueryOptionsConverter::PopulateEntityQueryExpressionForInnerNavigation(string innerNavigation, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata navigationPropertyMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.EntityQueryExpression queryExpression)
0x23679  stloc.s  6
0x2367b  ldarg.1
0x2367c  ldloc.3
0x2367d  ldloc.s  4
0x2367f  ldarg.3
0x23680  ldnull
0x23681  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase[] Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::RetrieveMetadataForEntityType(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, class [mscorlib]System.Type crmType, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.EntityQueryExpression entityQuery, [opt] string entityId, [opt] string crmPropertyName)
0x23686  stloc.s  7
0x23688  ldloc.s  7
0x2368a  brfalse.s loc_236B0
0x2368c  ldloc.s  7
0x2368e  call     T0x2B0000C6
0x23693  brfalse.s loc_236B0
0x23695  ldloc.3
0x23696  ldloc.s  6
0x23698  callvirt instance class [mscorlib]System.Reflection.PropertyInfo [mscorlib]System.Type::GetProperty(string)
0x2369d  ldloc.s  7
0x2369f  call     T0x2B0000C7
0x236a4  ldnull
0x236a5  callvirt instance object [mscorlib]System.Reflection.PropertyInfo::GetValue(object, object[])
0x236aa  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase
0x236af  stloc.0
0x236b0  ldloc.0
0x236b1  ret
```
