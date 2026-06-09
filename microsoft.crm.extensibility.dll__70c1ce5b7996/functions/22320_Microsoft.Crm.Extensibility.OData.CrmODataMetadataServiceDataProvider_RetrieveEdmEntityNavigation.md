# Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::RetrieveEdmEntityNavigation

- ea: `0x22320`
- end: `0x22475`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::RetrieveEdmEntityNavigation`
- size: `341`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x11640`
- `0x11680`

## callees

- `0xf7d0`
- `0x15e10`
- `0x15e70`
- `0x16fd0`
- `0x175f0`
- `0x22320`
- `0x227e0`
- `0x228a0`
- `0x228d0`
- `0x22b80`
- `0x230b0`
- `0x23d50`
- `0x23f90`
- `0x24570`

## pseudocode

```c

```

## disassembly

```asm
0x22320  ldnull
0x22321  stloc.0
0x22322  ldarg.2
0x22323  ldarg.0
0x22324  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::edmModel
0x22329  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::GetCrmMetadataEntityMetadataFromEdmEntityName(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x2232e  stloc.1
0x2232f  ldloc.1
0x22330  callvirt instance class [mscorlib]System.Type [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata::get_ClrType()
0x22335  stloc.2
0x22336  ldarg.0
0x22337  ldarg.s  4
0x22339  ldarg.s  5
0x2233b  ldloc.1
0x2233c  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::GetXrmMetatadataEntityMetadataForNavigationProperty(string navigationPropertyName, string derivedAttributeName, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata xrmEntityMetadata)
0x22341  stloc.3
0x22342  ldloc.3
0x22343  callvirt instance class [mscorlib]System.Type [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata::get_ClrType()
0x22348  stloc.s  4
0x2234a  ldnull
0x2234b  stloc.s  5
0x2234d  ldloc.1
0x2234e  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmEntitySet [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata::get_EdmEntitySet()
0x22353  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmEntityType [Microsoft.OData.Edm]Microsoft.OData.Edm.ExtensionMethods::EntityType(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationSource)
0x22358  castclass [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmEntityType
0x2235d  stloc.s  6
0x2235f  ldarg.s  4
0x22361  ldloc.1
0x22362  ldloc.s  6
0x22364  call     string Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::GetCrmRelationshipNameFromEdmNavigationPropertyName(string edmNavigationPropertyName, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata xrmEntityMetadata, class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmEntityType entityType)
0x22369  stloc.s  7
0x2236b  ldloc.2
0x2236c  call     bool Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::IsOptionSetMetadata(class [mscorlib]System.Type crmType)
0x22371  brfalse.s loc_22383
0x22373  ldarg.1
0x22374  ldarg.3
0x22375  ldloc.2
0x22376  ldloc.s  5
0x22378  ldloc.s  7
0x2237a  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase[] Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::RetrieveOptionsForOptionSetMetadata(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, string key, class [mscorlib]System.Type entityCrmType, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase[] resultCollection, string crmRelationshipName)
0x2237f  stloc.s  5
0x22381  br.s     loc_223BD
0x22383  ldarg.s  7
0x22385  brfalse.s loc_2238F
0x22387  ldarg.s  6
0x22389  ldloc.3
0x2238a  call     void Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::SetQueryOptionSelectClause(class [System.Web.OData]System.Web.OData.Query.ODataQueryOptions queryOptions, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata navigationPropertyMetadata)
0x2238f  ldarg.0
0x22390  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::edmModel
0x22395  newobj   instance void Microsoft.Crm.Extensibility.OData.MetadataQueryOptionsConverter::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x2239a  ldloc.1
0x2239b  ldarg.3
0x2239c  ldarg.s  4
0x2239e  ldloc.3
0x2239f  callvirt instance class [mscorlib]System.Type [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata::get_ClrType()
0x223a4  ldarg.s  6
0x223a6  ldnull
0x223a7  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.EntityQueryExpression Microsoft.Crm.Extensibility.OData.MetadataQueryOptionsConverter::GetEntityQueryExpressionForEntityNavigationProperty(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata xrmEntityMetadata, string entityIdValue, string edmNavigationPropertyName, class [mscorlib]System.Type navigationPropertyCrmType, class [System.Web.OData]System.Web.OData.Query.ODataQueryOptions queryOptions, [opt] string navigationIdValue)
0x223ac  stloc.s  9
0x223ae  ldarg.1
0x223af  ldloc.s  4
0x223b1  ldloc.s  9
0x223b3  ldarg.3
0x223b4  ldloc.s  7
0x223b6  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase[] Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::RetrieveMetadataForEntityType(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, class [mscorlib]System.Type crmType, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.EntityQueryExpression entityQuery, [opt] string entityId, [opt] string crmPropertyName)
0x223bb  stloc.s  5
0x223bd  ldloc.3
0x223be  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmEntitySet [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata::get_EdmEntitySet()
0x223c3  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmEntityType [Microsoft.OData.Edm]Microsoft.OData.Edm.ExtensionMethods::EntityType(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationSource)
0x223c8  callvirt instance string [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNamedElement::get_Name()
0x223cd  stloc.s  8
0x223cf  ldloc.s  5
0x223d1  brfalse  loc_2245C
0x223d6  ldloc.s  5
0x223d8  call     T0x2B0000C6
0x223dd  brfalse.s loc_2245C
0x223df  ldarg.s  6
0x223e1  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x223e6  brfalse.s loc_22404
0x223e8  ldarg.s  6
0x223ea  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x223ef  callvirt instance string [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption::get_RawExpand()
0x223f4  brfalse.s loc_22404
0x223f6  ldarg.0
0x223f7  ldloc.s  5
0x223f9  ldloc.3
0x223fa  ldarg.s  6
0x223fc  call     instance class Microsoft.Crm.Extensibility.OData.CrmEdmEntityObjectCollection Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::PopulateEdmEntityObjectCollectionWithExpandedItems(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase[] resultCollection, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata metadataEntityMetadata, class [System.Web.OData]System.Web.OData.Query.ODataQueryOptions queryOptions)
0x22401  stloc.0
0x22402  br.s     loc_22473
0x22404  ldarg.s  6
0x22406  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x2240b  brfalse.s loc_22449
0x2240d  ldarg.s  6
0x2240f  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x22414  callvirt instance string [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption::get_RawSelect()
0x22419  brfalse.s loc_22449
0x2241b  ldloc.s  5
0x2241d  ldloc.s  8
0x2241f  ldarg.0
0x22420  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::edmModel
0x22425  ldarg.s  6
0x22427  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x2242c  callvirt instance string [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption::get_RawSelect()
0x22431  ldc.i4.1
0x22432  newarr   [mscorlib]System.Char
0x22437  dup
0x22438  ldc.i4.0
0x22439  ldc.i4.s 0x2C
0x2243b  stelem.i2
0x2243c  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x22441  call     class Microsoft.Crm.Extensibility.OData.CrmEdmEntityObjectCollection Microsoft.Crm.Extensibility.OData.EdmMetadataTypeConverter::ConvertToCrmEdmEntityObjectCollection(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase[] entitySetCollection, string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel, [opt] class [mscorlib]System.Collections.Generic.IEnumerable`1<string> selectedProps)
0x22446  stloc.0
0x22447  br.s     loc_22473
0x22449  ldloc.s  5
0x2244b  ldloc.s  8
0x2244d  ldarg.0
0x2244e  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::edmModel
0x22453  ldnull
0x22454  call     class Microsoft.Crm.Extensibility.OData.CrmEdmEntityObjectCollection Microsoft.Crm.Extensibility.OData.EdmMetadataTypeConverter::ConvertToCrmEdmEntityObjectCollection(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase[] entitySetCollection, string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel, [opt] class [mscorlib]System.Collections.Generic.IEnumerable`1<string> selectedProps)
0x22459  stloc.0
0x2245a  br.s     loc_22473
0x2245c  ldloc.s  8
0x2245e  ldarg.0
0x2245f  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::edmModel
0x22464  call     class [System.Web.OData]System.Web.OData.EdmEntityObjectCollection Microsoft.Crm.Extensibility.OData.EdmUtilities::CreateNewEdmEntityObjectCollection(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x22469  ldc.i4.0
0x2246a  ldc.i4.0
0x2246b  ldnull
0x2246c  ldc.i4.0
0x2246d  newobj   instance void Microsoft.Crm.Extensibility.OData.CrmEdmEntityObjectCollection::.ctor(class [System.Web.OData]System.Web.OData.EdmEntityObjectCollection edmEntityCollection, int32 totalRecordCount, bool totalRecordCountLimitExceeded, string pagingCookie, bool hasMoreRecords)
0x22472  stloc.0
0x22473  ldloc.0
0x22474  ret
```
