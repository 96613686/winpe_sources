# Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::RetrieveEdmEntity

- ea: `0x21d70`
- end: `0x21eb6`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::RetrieveEdmEntity`
- size: `326`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x10bc0`
- `0x11540`

## callees

- `0x15c70`
- `0x15e70`
- `0x15e90`
- `0x21d70`
- `0x22e60`
- `0x22fd0`
- `0x23060`
- `0x230b0`
- `0x23d50`
- `0x24570`
- `0x24640`

## pseudocode

```c

```

## disassembly

```asm
0x21d70  ldarg.2
0x21d71  ldarg.0
0x21d72  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::edmModel
0x21d77  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::GetCrmMetadataEntityMetadataFromEdmEntityName(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x21d7c  stloc.0
0x21d7d  ldloc.0
0x21d7e  callvirt instance class [mscorlib]System.Type [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata::get_ClrType()
0x21d83  stloc.1
0x21d84  ldnull
0x21d85  stloc.2
0x21d86  ldarg.s  4
0x21d88  callvirt instance class [System.Web.OData]System.Web.OData.Query.FilterQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_Filter()
0x21d8d  brfalse.s loc_21DA9
0x21d8f  ldc.i4   0x190
0x21d94  ldstr    aTheQueryParame_0// "The query parameter $filter is not supp"...
0x21d99  ldc.i4.1
0x21d9a  newarr   [mscorlib]System.Object
0x21d9f  dup
0x21da0  ldc.i4.0
0x21da1  ldarg.2
0x21da2  stelem.ref
0x21da3  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException::.ctor(valuetype [System]System.Net.HttpStatusCode, string, object[])
0x21da8  throw
0x21da9  ldloc.1
0x21daa  call     bool Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::IsManagedPropertyMetadata(class [mscorlib]System.Type xrmType)
0x21daf  brfalse.s loc_21DBB
0x21db1  ldarg.1
0x21db2  ldarg.3
0x21db3  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.ManagedPropertyMetadata Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::RetrieveManagedProeprtyMetadata(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, string entityIdValue)
0x21db8  stloc.2
0x21db9  br.s     loc_21E06
0x21dbb  ldloc.1
0x21dbc  call     bool Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::IsOptionSetMetadata(class [mscorlib]System.Type crmType)
0x21dc1  brfalse.s loc_21DCD
0x21dc3  ldarg.1
0x21dc4  ldarg.3
0x21dc5  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OptionSetMetadataBase Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::RetrieveOptionSetMetadata(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, string entityIdValue)
0x21dca  stloc.2
0x21dcb  br.s     loc_21E06
0x21dcd  ldarg.0
0x21dce  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::edmModel
0x21dd3  newobj   instance void Microsoft.Crm.Extensibility.OData.MetadataQueryOptionsConverter::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x21dd8  ldarg.s  4
0x21dda  ldarg.2
0x21ddb  ldarg.1
0x21ddc  ldarg.3
0x21ddd  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.EntityQueryExpression Microsoft.Crm.Extensibility.OData.MetadataQueryOptionsConverter::GetEntityQueryExpression(class [System.Web.OData]System.Web.OData.Query.ODataQueryOptions queryOptions, string edmEntityName, class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, [opt] string key)
0x21de2  stloc.s  4
0x21de4  ldarg.1
0x21de5  ldloc.1
0x21de6  ldloc.s  4
0x21de8  ldnull
0x21de9  ldnull
0x21dea  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase[] Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::RetrieveMetadataForEntityType(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, class [mscorlib]System.Type crmType, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.EntityQueryExpression entityQuery, [opt] string entityId, [opt] string crmPropertyName)
0x21def  stloc.s  5
0x21df1  ldloc.s  5
0x21df3  brfalse.s loc_21E06
0x21df5  ldloc.s  5
0x21df7  call     T0x2B0000C6
0x21dfc  brfalse.s loc_21E06
0x21dfe  ldloc.s  5
0x21e00  call     T0x2B0000C7
0x21e05  stloc.2
0x21e06  ldloc.2
0x21e07  brfalse  loc_21E96
0x21e0c  ldarg.s  4
0x21e0e  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x21e13  brfalse.s loc_21E59
0x21e15  ldarg.s  4
0x21e17  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x21e1c  callvirt instance string [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption::get_RawSelect()
0x21e21  brfalse.s loc_21E59
0x21e23  ldloc.0
0x21e24  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmEntitySet [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata::get_EdmEntitySet()
0x21e29  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmEntityType [Microsoft.OData.Edm]Microsoft.OData.Edm.ExtensionMethods::EntityType(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationSource)
0x21e2e  ldloc.2
0x21e2f  ldarg.0
0x21e30  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::edmModel
0x21e35  ldarg.s  4
0x21e37  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x21e3c  callvirt instance string [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption::get_RawSelect()
0x21e41  ldc.i4.1
0x21e42  newarr   [mscorlib]System.Char
0x21e47  dup
0x21e48  ldc.i4.0
0x21e49  ldc.i4.s 0x2C
0x21e4b  stelem.i2
0x21e4c  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x21e51  call     class [System.Web.OData]System.Web.OData.EdmEntityObject Microsoft.Crm.Extensibility.OData.EdmMetadataTypeConverter::ConvertToEdmMetadataValue(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmType edmType, object propertyValue, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel, [opt] class [mscorlib]System.Collections.Generic.IEnumerable`1<string> selectedProps)
0x21e56  stloc.3
0x21e57  br.s     loc_21E72
0x21e59  ldloc.0
0x21e5a  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmEntitySet [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata::get_EdmEntitySet()
0x21e5f  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmEntityType [Microsoft.OData.Edm]Microsoft.OData.Edm.ExtensionMethods::EntityType(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationSource)
0x21e64  ldloc.2
0x21e65  ldarg.0
0x21e66  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::edmModel
0x21e6b  ldnull
0x21e6c  call     class [System.Web.OData]System.Web.OData.EdmEntityObject Microsoft.Crm.Extensibility.OData.EdmMetadataTypeConverter::ConvertToEdmMetadataValue(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmType edmType, object propertyValue, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel, [opt] class [mscorlib]System.Collections.Generic.IEnumerable`1<string> selectedProps)
0x21e71  stloc.3
0x21e72  ldarg.s  4
0x21e74  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x21e79  brfalse.s loc_21EB4
0x21e7b  ldarg.s  4
0x21e7d  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x21e82  callvirt instance string [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption::get_RawExpand()
0x21e87  brfalse.s loc_21EB4
0x21e89  ldarg.0
0x21e8a  ldloc.3
0x21e8b  ldloc.0
0x21e8c  ldarg.s  4
0x21e8e  ldloc.2
0x21e8f  call     instance void Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::PopulateExpandedItemsInEntityObject(class [System.Web.OData]System.Web.OData.EdmEntityObject entityObject, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata metadataEntityMetadata, class [System.Web.OData]System.Web.OData.Query.ODataQueryOptions queryOptions, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase result)
0x21e94  br.s     loc_21EB4
0x21e96  ldc.i4   0x194
0x21e9b  ldstr    a0WithId1DoesNo// "{0} With Id = {1} does not exist."
0x21ea0  ldc.i4.2
0x21ea1  newarr   [mscorlib]System.Object
0x21ea6  dup
0x21ea7  ldc.i4.0
0x21ea8  ldarg.2
0x21ea9  stelem.ref
0x21eaa  dup
0x21eab  ldc.i4.1
0x21eac  ldarg.3
0x21ead  stelem.ref
0x21eae  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException::.ctor(valuetype [System]System.Net.HttpStatusCode, string, object[])
0x21eb3  throw
0x21eb4  ldloc.3
0x21eb5  ret
```
