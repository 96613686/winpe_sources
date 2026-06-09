# Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::RetrieveEdmEntityCollection

- ea: `0x218d0`
- end: `0x21a30`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::RetrieveEdmEntityCollection`
- size: `352`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callers

- `0x32310`

## callees

- `0xf7d0`
- `0xfb50`
- `0x15e10`
- `0x15e70`
- `0x15e90`
- `0x175f0`
- `0x218d0`
- `0x21a30`
- `0x227e0`
- `0x22b80`
- `0x22ef0`
- `0x22f60`
- `0x230b0`
- `0x23d50`
- `0x24570`
- `0x24640`

## pseudocode

```c

```

## disassembly

```asm
0x218d0  ldarg.2
0x218d1  ldarg.3
0x218d2  call     void Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::AddRequestInfoToTelemetry(string entitySetName, string castedEntityName)
0x218d7  ldarg.2
0x218d8  ldarg.0
0x218d9  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::edmModel
0x218de  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmEntitySet Microsoft.Crm.Extensibility.OData.EdmUtilities::TryGetEdmEntitySet(string edmEntitySetName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x218e3  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmEntityType [Microsoft.OData.Edm]Microsoft.OData.Edm.ExtensionMethods::EntityType(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationSource)
0x218e8  callvirt instance string [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNamedElement::get_Name()
0x218ed  stloc.1
0x218ee  ldloc.1
0x218ef  ldarg.0
0x218f0  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::edmModel
0x218f5  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::GetCrmMetadataEntityMetadataFromEdmEntityName(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x218fa  stloc.2
0x218fb  ldarg.0
0x218fc  ldarg.2
0x218fd  ldarg.3
0x218fe  ldloc.2
0x218ff  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::GetXrmMetatadataEntityMetadataForNavigationProperty(string navigationPropertyName, string derivedAttributeName, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata xrmEntityMetadata)
0x21904  callvirt instance class [mscorlib]System.Type [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata::get_ClrType()
0x21909  stloc.3
0x2190a  ldarg.s  4
0x2190c  callvirt instance class [System.Web.OData]System.Web.OData.Query.FilterQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_Filter()
0x21911  brfalse.s loc_2193D
0x21913  ldloc.3
0x21914  call     bool Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::IsManagedPropertyMetadata(class [mscorlib]System.Type xrmType)
0x21919  brtrue.s loc_21923
0x2191b  ldloc.3
0x2191c  call     bool Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::IsOptionSetMetadata(class [mscorlib]System.Type crmType)
0x21921  brfalse.s loc_2193D
0x21923  ldc.i4   0x195
0x21928  ldstr    aTheQueryParame_0// "The query parameter $filter is not supp"...
0x2192d  ldc.i4.1
0x2192e  newarr   [mscorlib]System.Object
0x21933  dup
0x21934  ldc.i4.0
0x21935  ldarg.2
0x21936  stelem.ref
0x21937  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException::.ctor(valuetype [System]System.Net.HttpStatusCode, string, object[])
0x2193c  throw
0x2193d  ldnull
0x2193e  stloc.s  4
0x21940  ldloc.3
0x21941  call     bool Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::IsManagedPropertyMetadata(class [mscorlib]System.Type xrmType)
0x21946  brfalse.s loc_21954
0x21948  ldarg.1
0x21949  ldloc.s  4
0x2194b  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase[] Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::RetrieveAllManagedProperties(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase[] resultCollection)
0x21950  stloc.s  4
0x21952  br.s     loc_2198D
0x21954  ldloc.3
0x21955  call     bool Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::IsOptionSetMetadata(class [mscorlib]System.Type crmType)
0x2195a  brfalse.s loc_21969
0x2195c  ldarg.1
0x2195d  ldloc.s  4
0x2195f  ldloc.3
0x21960  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase[] Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::RetrieveAllOptionSets(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase[] resultCollection, class [mscorlib]System.Type crmType)
0x21965  stloc.s  4
0x21967  br.s     loc_2198D
0x21969  ldarg.0
0x2196a  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::edmModel
0x2196f  newobj   instance void Microsoft.Crm.Extensibility.OData.MetadataQueryOptionsConverter::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x21974  ldarg.s  4
0x21976  ldarg.3
0x21977  ldarg.1
0x21978  ldnull
0x21979  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.EntityQueryExpression Microsoft.Crm.Extensibility.OData.MetadataQueryOptionsConverter::GetEntityQueryExpression(class [System.Web.OData]System.Web.OData.Query.ODataQueryOptions queryOptions, string edmEntityName, class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, [opt] string key)
0x2197e  stloc.s  5
0x21980  ldarg.1
0x21981  ldloc.3
0x21982  ldloc.s  5
0x21984  ldnull
0x21985  ldnull
0x21986  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase[] Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::RetrieveMetadataForEntityType(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, class [mscorlib]System.Type crmType, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.EntityQueryExpression entityQuery, [opt] string entityId, [opt] string crmPropertyName)
0x2198b  stloc.s  4
0x2198d  ldloc.s  4
0x2198f  brfalse  loc_21A18
0x21994  ldloc.s  4
0x21996  call     T0x2B0000C6
0x2199b  brfalse.s loc_21A18
0x2199d  ldarg.s  4
0x2199f  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x219a4  brfalse.s loc_219C2
0x219a6  ldarg.s  4
0x219a8  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x219ad  callvirt instance string [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption::get_RawExpand()
0x219b2  brfalse.s loc_219C2
0x219b4  ldarg.0
0x219b5  ldloc.s  4
0x219b7  ldloc.2
0x219b8  ldarg.s  4
0x219ba  call     instance class Microsoft.Crm.Extensibility.OData.CrmEdmEntityObjectCollection Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::PopulateEdmEntityObjectCollectionWithExpandedItems(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase[] resultCollection, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata metadataEntityMetadata, class [System.Web.OData]System.Web.OData.Query.ODataQueryOptions queryOptions)
0x219bf  stloc.0
0x219c0  br.s     loc_21A2E
0x219c2  ldarg.s  4
0x219c4  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x219c9  brfalse.s loc_21A06
0x219cb  ldarg.s  4
0x219cd  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x219d2  callvirt instance string [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption::get_RawSelect()
0x219d7  brfalse.s loc_21A06
0x219d9  ldloc.s  4
0x219db  ldloc.1
0x219dc  ldarg.0
0x219dd  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::edmModel
0x219e2  ldarg.s  4
0x219e4  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x219e9  callvirt instance string [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption::get_RawSelect()
0x219ee  ldc.i4.1
0x219ef  newarr   [mscorlib]System.Char
0x219f4  dup
0x219f5  ldc.i4.0
0x219f6  ldc.i4.s 0x2C
0x219f8  stelem.i2
0x219f9  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x219fe  call     class Microsoft.Crm.Extensibility.OData.CrmEdmEntityObjectCollection Microsoft.Crm.Extensibility.OData.EdmMetadataTypeConverter::ConvertToCrmEdmEntityObjectCollection(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase[] entitySetCollection, string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel, [opt] class [mscorlib]System.Collections.Generic.IEnumerable`1<string> selectedProps)
0x21a03  stloc.0
0x21a04  br.s     loc_21A2E
0x21a06  ldloc.s  4
0x21a08  ldloc.1
0x21a09  ldarg.0
0x21a0a  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::edmModel
0x21a0f  ldnull
0x21a10  call     class Microsoft.Crm.Extensibility.OData.CrmEdmEntityObjectCollection Microsoft.Crm.Extensibility.OData.EdmMetadataTypeConverter::ConvertToCrmEdmEntityObjectCollection(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase[] entitySetCollection, string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel, [opt] class [mscorlib]System.Collections.Generic.IEnumerable`1<string> selectedProps)
0x21a15  stloc.0
0x21a16  br.s     loc_21A2E
0x21a18  ldloc.1
0x21a19  ldarg.0
0x21a1a  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::edmModel
0x21a1f  call     class [System.Web.OData]System.Web.OData.EdmEntityObjectCollection Microsoft.Crm.Extensibility.OData.EdmUtilities::CreateNewEdmEntityObjectCollection(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x21a24  ldc.i4.0
0x21a25  ldc.i4.0
0x21a26  ldnull
0x21a27  ldc.i4.0
0x21a28  newobj   instance void Microsoft.Crm.Extensibility.OData.CrmEdmEntityObjectCollection::.ctor(class [System.Web.OData]System.Web.OData.EdmEntityObjectCollection edmEntityCollection, int32 totalRecordCount, bool totalRecordCountLimitExceeded, string pagingCookie, bool hasMoreRecords)
0x21a2d  stloc.0
0x21a2e  ldloc.0
0x21a2f  ret
```
