# Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::RetrieveEdmEntityNavigation

- ea: `0x1e010`
- end: `0x1e29a`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::RetrieveEdmEntityNavigation`
- size: `650`
- prototype: ``
- caller_count: `3`
- callee_count: `22`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x11640`
- `0x11680`
- `0x12610`

## callees

- `0xf6f0`
- `0xf740`
- `0xf880`
- `0xfab0`
- `0xfff0`
- `0x13540`
- `0x147b0`
- `0x147e0`
- `0x14840`
- `0x175f0`
- `0x1e010`
- `0x1e2a0`
- `0x1ed10`
- `0x1f820`
- `0x20200`
- `0x20360`
- `0x21270`
- `0x21370`
- `0x247a0`
- `0x24e10`
- `0x28c90`
- `0x28fe0`

## string_xrefs

- `0x1e122`: `fetchXml`

## pseudocode

```c

```

## disassembly

```asm
0x1e010  ldarg.1
0x1e011  callvirt instance class [System.Net.Http]System.Net.Http.HttpRequestMessage Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Request()
0x1e016  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::QueryParameterDictionary(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x1e01b  call     bool Microsoft.Crm.Extensibility.OData.EdmUtilities::ValidateAndReturnNoLock(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> queryParams)
0x1e020  stloc.0
0x1e021  ldarg.2
0x1e022  ldarg.0
0x1e023  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::edmModel
0x1e028  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CrmEdmEntityType Microsoft.Crm.Extensibility.OData.EdmUtilities::GetEdmEntityType(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x1e02d  ldarg.s  4
0x1e02f  call     class [mscorlib]System.Tuple`2<class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmNavigationProperty, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship> Microsoft.Crm.Extensibility.OData.CrmODataUtilities::GetRelationshipInformation(class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmEntityType edmEntityType, string propertyName)
0x1e034  stloc.1
0x1e035  ldarg.2
0x1e036  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor(string)
0x1e03b  stloc.2
0x1e03c  ldloc.2
0x1e03d  ldloc.0
0x1e03e  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_NoLock(bool)
0x1e043  ldloc.2
0x1e044  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::.ctor()
0x1e049  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_Criteria(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression)
0x1e04e  ldarg.2
0x1e04f  ldarg.3
0x1e050  ldarg.0
0x1e051  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::edmModel
0x1e056  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference Microsoft.Crm.Extensibility.OData.CrmODataUtilities::GetXrmEntityReferenceForKeys(string edmEntityName, string key, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x1e05b  stloc.3
0x1e05c  ldloc.1
0x1e05d  callvirt instance var<u1> class [mscorlib]System.Tuple`2<class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmNavigationProperty, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship>::get_Item1()
0x1e062  call     string Microsoft.Crm.Extensibility.OData.EdmUtilities::GetEdmLinkedEntityName(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationProperty navigationProperty)
0x1e067  stloc.s  4
0x1e069  ldnull
0x1e06a  stloc.s  5
0x1e06c  ldarg.s  5
0x1e06e  isinst   Microsoft.Crm.Extensibility.OData.CustomQueryOptions
0x1e073  brfalse  loc_1E1A6
0x1e078  ldloc.1
0x1e079  callvirt instance var<u1> class [mscorlib]System.Tuple`2<class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmNavigationProperty, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship>::get_Item1()
0x1e07e  call     void Microsoft.Crm.Extensibility.OData.EdmUtilities::ThrowIfNavigationPropertyNotValidForCustomQuery(class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmNavigationProperty navigationProperty)
0x1e083  ldarg.1
0x1e084  callvirt instance class [System.Net.Http]System.Net.Http.HttpRequestMessage Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Request()
0x1e089  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Properties()
0x1e08e  ldstr    aMsBatchrequest// "MS_BatchRequest"
0x1e093  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::ContainsKey(var<u1>)
0x1e098  brfalse.s loc_1E0D1
0x1e09a  ldarg.1
0x1e09b  callvirt instance class [System.Net.Http]System.Net.Http.HttpRequestMessage Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Request()
0x1e0a0  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Properties()
0x1e0a5  ldstr    aMsBatchrequest// "MS_BatchRequest"
0x1e0aa  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::get_Item(void)
0x1e0af  unbox.any [mscorlib]System.Boolean
0x1e0b4  brfalse.s loc_1E0D1
0x1e0b6  ldarg.1
0x1e0b7  callvirt instance class [System.Net.Http]System.Net.Http.HttpRequestMessage Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Request()
0x1e0bc  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Properties()
0x1e0c1  ldstr    aOdataShouldrec// "OData.ShouldRecalculateSelectExpandNode"
0x1e0c6  ldc.i4.1
0x1e0c7  box      [mscorlib]System.Boolean
0x1e0cc  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x1e0d1  ldarg.s  5
0x1e0d3  castclass Microsoft.Crm.Extensibility.OData.CustomQueryOptions
0x1e0d8  stloc.s  9
0x1e0da  ldloc.s  9
0x1e0dc  callvirt instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string> Microsoft.Crm.Extensibility.OData.CustomQueryOptions::get_CustomQueryParameter()
0x1e0e1  stloc.s  0xA
0x1e0e3  ldloca.s 0xA
0x1e0e5  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x1e0ea  ldstr    aSavedquery_0// "SavedQuery"
0x1e0ef  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1e0f4  brtrue.s loc_1E131
0x1e0f6  ldloc.s  9
0x1e0f8  callvirt instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string> Microsoft.Crm.Extensibility.OData.CustomQueryOptions::get_CustomQueryParameter()
0x1e0fd  stloc.s  0xA
0x1e0ff  ldloca.s 0xA
0x1e101  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x1e106  ldstr    aUserquery_0// "UserQuery"
0x1e10b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1e110  brtrue.s loc_1E131
0x1e112  ldloc.s  9
0x1e114  callvirt instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string> Microsoft.Crm.Extensibility.OData.CustomQueryOptions::get_CustomQueryParameter()
0x1e119  stloc.s  0xA
0x1e11b  ldloca.s 0xA
0x1e11d  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x1e122  ldstr    aFetchxml// "fetchXml"
0x1e127  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1e12c  brfalse  loc_1E1C2
0x1e131  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x1e136  brfalse.s loc_1E16E
0x1e138  ldarg.1
0x1e139  callvirt instance class [System.Net.Http]System.Net.Http.HttpRequestMessage Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Request()
0x1e13e  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Properties()
0x1e143  ldstr    aOdataShouldrec// "OData.ShouldRecalculateSelectExpandNode"
0x1e148  ldc.i4.1
0x1e149  box      [mscorlib]System.Boolean
0x1e14e  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x1e153  ldarg.1
0x1e154  callvirt instance class [System.Net.Http]System.Net.Http.HttpRequestMessage Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Request()
0x1e159  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Properties()
0x1e15e  ldstr    aOdataCustomque// "OData.CustomQueryOptionsArePresent"
0x1e163  ldc.i4.1
0x1e164  box      [mscorlib]System.Boolean
0x1e169  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x1e16e  ldloc.s  4
0x1e170  ldarg.0
0x1e171  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::edmModel
0x1e176  call     string Microsoft.Crm.Extensibility.OData.EdmUtilities::GetEdmEntityCollectionName(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x1e17b  stloc.s  0xB
0x1e17d  ldarg.0
0x1e17e  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::edmModel
0x1e183  ldarg.1
0x1e184  newobj   instance void Microsoft.Crm.Extensibility.OData.DataQueryOptionsConverter::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel, class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context)
0x1e189  ldarg.0
0x1e18a  ldarg.1
0x1e18b  ldloc.s  0xB
0x1e18d  ldloc.s  9
0x1e18f  call     instance string Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::RetrieveFetchXmlForEntity(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, string entitySetName, class Microsoft.Crm.Extensibility.OData.CustomQueryOptions queryOptions)
0x1e194  ldarg.2
0x1e195  ldarg.s  4
0x1e197  ldarg.0
0x1e198  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::edmModel
0x1e19d  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RelationshipQueryCollection Microsoft.Crm.Extensibility.OData.DataQueryOptionsConverter::GetRelatedEntitiesCustomQuery(string fetchXml, string edmEntityName, string navigationProperty, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x1e1a2  stloc.s  5
0x1e1a4  br.s     loc_1E1C2
0x1e1a6  ldarg.0
0x1e1a7  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::edmModel
0x1e1ac  ldarg.1
0x1e1ad  newobj   instance void Microsoft.Crm.Extensibility.OData.DataQueryOptionsConverter::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel, class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context)
0x1e1b2  ldarg.s  5
0x1e1b4  ldarg.2
0x1e1b5  ldarg.s  4
0x1e1b7  ldloc.s  4
0x1e1b9  ldarg.s  6
0x1e1bb  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RelationshipQueryCollection Microsoft.Crm.Extensibility.OData.DataQueryOptionsConverter::GetRelatedEntityQuery(class [System.Web.OData]System.Web.OData.Query.ODataQueryOptions navigationEntityQueryOptions, string edmEntityName, string navigationProperty, string navigationEntityName, bool onlyRef)
0x1e1c0  stloc.s  5
0x1e1c2  ldarg.1
0x1e1c3  ldloc.3
0x1e1c4  ldloc.2
0x1e1c5  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_ColumnSet()
0x1e1ca  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<string> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::get_Columns()
0x1e1cf  callvirt instance var<u1>[] class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<string>::ToArray()
0x1e1d4  ldloc.s  5
0x1e1d6  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::RetrieveEntityWithRelatedRecords(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference primaryEntityReference, string[] columns, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RelationshipQueryCollection relatedEntitiesQuery)
0x1e1db  stloc.s  6
0x1e1dd  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::.ctor()
0x1e1e2  stloc.s  7
0x1e1e4  ldloc.s  6
0x1e1e6  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RelatedEntityCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_RelatedEntities()
0x1e1eb  callvirt instance int32 class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Relationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection>::get_Count()
0x1e1f0  ldc.i4.0
0x1e1f1  ble.s    loc_1E20A
0x1e1f3  ldloc.s  6
0x1e1f5  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RelatedEntityCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_RelatedEntities()
0x1e1fa  call     T0x2B0000BB
0x1e1ff  stloc.s  0xC
0x1e201  ldloca.s 0xC
0x1e203  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Relationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection>::get_Value()
0x1e208  stloc.s  7
0x1e20a  ldarg.s  5
0x1e20c  callvirt instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_Request()
0x1e211  ldarg.0
0x1e212  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::edmModel
0x1e217  call     bool Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::IsCustomQueryOptionPresent(class [System.Net.Http]System.Net.Http.HttpRequestMessage request, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x1e21c  brfalse.s loc_1E221
0x1e21e  ldc.i4.0
0x1e21f  br.s     loc_1E250
0x1e221  ldarg.s  5
0x1e223  brfalse.s loc_1E24F
0x1e225  ldarg.s  5
0x1e227  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x1e22c  brfalse.s loc_1E24F
0x1e22e  ldarg.s  5
0x1e230  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x1e235  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption::get_SelectExpandClause()
0x1e23a  brfalse.s loc_1E24F
0x1e23c  ldarg.s  5
0x1e23e  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x1e243  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption::get_SelectExpandClause()
0x1e248  callvirt instance bool [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause::get_AllSelected()
0x1e24d  br.s     loc_1E250
0x1e24f  ldc.i4.1
0x1e250  stloc.s  8
0x1e252  ldloc.s  7
0x1e254  ldloc.s  4
0x1e256  ldarg.0
0x1e257  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::edmModel
0x1e25c  ldloc.s  8
0x1e25e  ldloc.s  8
0x1e260  ldloc.0
0x1e261  ldnull
0x1e262  call     class [System.Web.OData]System.Web.OData.EdmEntityObjectCollection Microsoft.Crm.Extensibility.OData.EdmTypeConverter::ConvertToEdmEntityObjectCollection(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection xrmEntityCollection, string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel, [opt] bool fillDerivedEntityProperties, [opt] bool fillAllProperties, [opt] bool noLock, [opt] class [mscorlib]System.Collections.Generic.List`1<string> navigationPropertyNames)
0x1e267  ldloc.s  7
0x1e269  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_TotalRecordCount()
0x1e26e  ldloc.s  7
0x1e270  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_TotalRecordCountLimitExceeded()
0x1e275  ldarg.1
0x1e276  call     int32 Microsoft.Crm.Extensibility.OData.CrmODataUtilities::GetPageNumber(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context)
0x1e27b  ldloc.s  7
0x1e27d  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_PagingCookie()
0x1e282  ldarg.1
0x1e283  call     bool Microsoft.Crm.Extensibility.OData.CrmODataUtilities::TryAddTrackingFieldToNextLink(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context)
0x1e288  call     string Microsoft.Crm.Extensibility.OData.CrmODataUtilities::SerializePagingCookie(int32 pageNumber, string crmPagingCookie, bool isTracking)
0x1e28d  ldloc.s  7
0x1e28f  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_MoreRecords()
0x1e294  newobj   instance void Microsoft.Crm.Extensibility.OData.CrmEdmEntityObjectCollection::.ctor(class [System.Web.OData]System.Web.OData.EdmEntityObjectCollection edmEntityCollection, int32 totalRecordCount, bool totalRecordCountLimitExceeded, string pagingCookie, bool hasMoreRecords)
0x1e299  ret
```
