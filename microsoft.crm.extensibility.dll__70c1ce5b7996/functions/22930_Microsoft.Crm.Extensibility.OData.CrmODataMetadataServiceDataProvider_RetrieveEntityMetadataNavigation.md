# Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::RetrieveEntityMetadataNavigation

- ea: `0x22930`
- end: `0x22a4f`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::RetrieveEntityMetadataNavigation`
- size: `287`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x12940`
- `0x12f30`

## callees

- `0x15c70`
- `0x15e70`
- `0x16fd0`
- `0x22930`
- `0x22b80`
- `0x22e60`
- `0x230b0`
- `0x23d50`

## pseudocode

```c

```

## disassembly

```asm
0x22930  ldarg.2
0x22931  ldarg.0
0x22932  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::edmModel
0x22937  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::GetCrmMetadataEntityMetadataFromEdmEntityName(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x2293c  stloc.0
0x2293d  ldarg.0
0x2293e  ldarg.s  4
0x22940  ldarg.s  6
0x22942  ldloc.0
0x22943  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::GetXrmMetatadataEntityMetadataForNavigationProperty(string navigationPropertyName, string derivedAttributeName, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata xrmEntityMetadata)
0x22948  stloc.1
0x22949  ldloc.1
0x2294a  callvirt instance class [mscorlib]System.Type [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata::get_ClrType()
0x2294f  stloc.2
0x22950  ldarg.0
0x22951  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::edmModel
0x22956  newobj   instance void Microsoft.Crm.Extensibility.OData.MetadataQueryOptionsConverter::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x2295b  ldloc.0
0x2295c  ldarg.3
0x2295d  ldarg.s  4
0x2295f  ldloc.1
0x22960  callvirt instance class [mscorlib]System.Type [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata::get_ClrType()
0x22965  ldarg.s  7
0x22967  ldarg.s  5
0x22969  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.EntityQueryExpression Microsoft.Crm.Extensibility.OData.MetadataQueryOptionsConverter::GetEntityQueryExpressionForEntityNavigationProperty(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata xrmEntityMetadata, string entityIdValue, string edmNavigationPropertyName, class [mscorlib]System.Type navigationPropertyCrmType, class [System.Web.OData]System.Web.OData.Query.ODataQueryOptions queryOptions, [opt] string navigationIdValue)
0x2296e  stloc.3
0x2296f  ldarg.1
0x22970  ldloc.2
0x22971  ldloc.3
0x22972  ldarg.3
0x22973  ldnull
0x22974  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase[] Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::RetrieveMetadataForEntityType(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, class [mscorlib]System.Type crmType, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.EntityQueryExpression entityQuery, [opt] string entityId, [opt] string crmPropertyName)
0x22979  stloc.s  4
0x2297b  ldloc.s  4
0x2297d  brfalse  loc_22A2B
0x22982  ldloc.s  4
0x22984  call     T0x2B0000C6
0x22989  brfalse  loc_22A2B
0x2298e  ldloc.s  4
0x22990  call     T0x2B0000C7
0x22995  stloc.s  5
0x22997  ldnull
0x22998  stloc.s  6
0x2299a  ldarg.s  7
0x2299c  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x229a1  brfalse.s loc_229E9
0x229a3  ldarg.s  7
0x229a5  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x229aa  callvirt instance string [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption::get_RawSelect()
0x229af  brfalse.s loc_229E9
0x229b1  ldloc.1
0x229b2  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmEntitySet [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata::get_EdmEntitySet()
0x229b7  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmEntityType [Microsoft.OData.Edm]Microsoft.OData.Edm.ExtensionMethods::EntityType(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationSource)
0x229bc  ldloc.s  5
0x229be  ldarg.0
0x229bf  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::edmModel
0x229c4  ldarg.s  7
0x229c6  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x229cb  callvirt instance string [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption::get_RawSelect()
0x229d0  ldc.i4.1
0x229d1  newarr   [mscorlib]System.Char
0x229d6  dup
0x229d7  ldc.i4.0
0x229d8  ldc.i4.s 0x2C
0x229da  stelem.i2
0x229db  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x229e0  call     class [System.Web.OData]System.Web.OData.EdmEntityObject Microsoft.Crm.Extensibility.OData.EdmMetadataTypeConverter::ConvertToEdmMetadataValue(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmType edmType, object propertyValue, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel, [opt] class [mscorlib]System.Collections.Generic.IEnumerable`1<string> selectedProps)
0x229e5  stloc.s  6
0x229e7  br.s     loc_22A04
0x229e9  ldloc.1
0x229ea  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmEntitySet [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata::get_EdmEntitySet()
0x229ef  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmEntityType [Microsoft.OData.Edm]Microsoft.OData.Edm.ExtensionMethods::EntityType(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationSource)
0x229f4  ldloc.s  5
0x229f6  ldarg.0
0x229f7  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::edmModel
0x229fc  ldnull
0x229fd  call     class [System.Web.OData]System.Web.OData.EdmEntityObject Microsoft.Crm.Extensibility.OData.EdmMetadataTypeConverter::ConvertToEdmMetadataValue(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmType edmType, object propertyValue, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel, [opt] class [mscorlib]System.Collections.Generic.IEnumerable`1<string> selectedProps)
0x22a02  stloc.s  6
0x22a04  ldarg.s  7
0x22a06  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x22a0b  brfalse.s loc_22A28
0x22a0d  ldarg.s  7
0x22a0f  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x22a14  callvirt instance string [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption::get_RawExpand()
0x22a19  brfalse.s loc_22A28
0x22a1b  ldarg.0
0x22a1c  ldloc.s  6
0x22a1e  ldloc.1
0x22a1f  ldarg.s  7
0x22a21  ldloc.s  5
0x22a23  call     instance void Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::PopulateExpandedItemsInEntityObject(class [System.Web.OData]System.Web.OData.EdmEntityObject entityObject, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata metadataEntityMetadata, class [System.Web.OData]System.Web.OData.Query.ODataQueryOptions queryOptions, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase result)
0x22a28  ldloc.s  6
0x22a2a  ret
0x22a2b  ldc.i4   0x194
0x22a30  ldstr    aNavigationProp_0// "Navigation property {0} With Id = {1} d"...
0x22a35  ldc.i4.3
0x22a36  newarr   [mscorlib]System.Object
0x22a3b  dup
0x22a3c  ldc.i4.0
0x22a3d  ldarg.s  4
0x22a3f  stelem.ref
0x22a40  dup
0x22a41  ldc.i4.1
0x22a42  ldarg.s  5
0x22a44  stelem.ref
0x22a45  dup
0x22a46  ldc.i4.2
0x22a47  ldarg.3
0x22a48  stelem.ref
0x22a49  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException::.ctor(valuetype [System]System.Net.HttpStatusCode, string, object[])
0x22a4e  throw
```
