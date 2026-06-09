# Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::RetrieveEdmEntityCollection

- ea: `0x1d750`
- end: `0x1da33`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::RetrieveEdmEntityCollection`
- size: `739`
- prototype: ``
- caller_count: `2`
- callee_count: `21`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x11f10`
- `0x32370`

## callees

- `0xf880`
- `0xfab0`
- `0xfbf0`
- `0x13540`
- `0x147b0`
- `0x175f0`
- `0x1d750`
- `0x1da40`
- `0x1da80`
- `0x1db50`
- `0x1eb40`
- `0x1ed10`
- `0x20200`
- `0x20360`
- `0x21270`
- `0x247a0`
- `0x24cd0`
- `0x24e10`
- `0x24e50`
- `0x24ed0`
- `0x28fe0`

## string_xrefs

- `0x1d827`: `fetchXml`

## pseudocode

```c

```

## disassembly

```asm
0x1d750  ldarg.2
0x1d751  ldarg.3
0x1d752  call     void Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::AddRequestInfoToTelemetry(string entityCollectionName, string castedEntityName)
0x1d757  ldarg.1
0x1d758  callvirt instance class [System.Net.Http]System.Net.Http.HttpRequestMessage Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Request()
0x1d75d  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::QueryParameterDictionary(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x1d762  call     bool Microsoft.Crm.Extensibility.OData.EdmUtilities::ValidateAndReturnNoLock(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> queryParams)
0x1d767  stloc.0
0x1d768  ldarg.3
0x1d769  brtrue.s loc_1D76E
0x1d76b  ldarg.2
0x1d76c  br.s     loc_1D77A
0x1d76e  ldarg.3
0x1d76f  ldarg.0
0x1d770  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::edmModel
0x1d775  call     string Microsoft.Crm.Extensibility.OData.EdmUtilities::GetEdmEntityCollectionName(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x1d77a  starg.s  2
0x1d77c  ldarg.1
0x1d77d  callvirt instance class [System.Net.Http]System.Net.Http.HttpRequestMessage Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Request()
0x1d782  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Properties()
0x1d787  ldstr    aMsBatchrequest// "MS_BatchRequest"
0x1d78c  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::ContainsKey(var<u1>)
0x1d791  brfalse.s loc_1D7CA
0x1d793  ldarg.1
0x1d794  callvirt instance class [System.Net.Http]System.Net.Http.HttpRequestMessage Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Request()
0x1d799  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Properties()
0x1d79e  ldstr    aMsBatchrequest// "MS_BatchRequest"
0x1d7a3  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::get_Item(void)
0x1d7a8  unbox.any [mscorlib]System.Boolean
0x1d7ad  brfalse.s loc_1D7CA
0x1d7af  ldarg.1
0x1d7b0  callvirt instance class [System.Net.Http]System.Net.Http.HttpRequestMessage Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Request()
0x1d7b5  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Properties()
0x1d7ba  ldstr    aOdataShouldrec// "OData.ShouldRecalculateSelectExpandNode"
0x1d7bf  ldc.i4.1
0x1d7c0  box      [mscorlib]System.Boolean
0x1d7c5  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x1d7ca  ldarg.s  4
0x1d7cc  isinst   Microsoft.Crm.Extensibility.OData.CustomQueryOptions
0x1d7d1  brfalse  loc_1D889
0x1d7d6  ldarg.s  4
0x1d7d8  castclass Microsoft.Crm.Extensibility.OData.CustomQueryOptions
0x1d7dd  stloc.s  7
0x1d7df  ldloc.s  7
0x1d7e1  callvirt instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string> Microsoft.Crm.Extensibility.OData.CustomQueryOptions::get_CustomQueryParameter()
0x1d7e6  stloc.s  8
0x1d7e8  ldloca.s 8
0x1d7ea  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x1d7ef  ldstr    aSavedquery_0// "SavedQuery"
0x1d7f4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1d7f9  brtrue.s loc_1D833
0x1d7fb  ldloc.s  7
0x1d7fd  callvirt instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string> Microsoft.Crm.Extensibility.OData.CustomQueryOptions::get_CustomQueryParameter()
0x1d802  stloc.s  8
0x1d804  ldloca.s 8
0x1d806  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x1d80b  ldstr    aUserquery_0// "UserQuery"
0x1d810  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1d815  brtrue.s loc_1D833
0x1d817  ldloc.s  7
0x1d819  callvirt instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string> Microsoft.Crm.Extensibility.OData.CustomQueryOptions::get_CustomQueryParameter()
0x1d81e  stloc.s  8
0x1d820  ldloca.s 8
0x1d822  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x1d827  ldstr    aFetchxml// "fetchXml"
0x1d82c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1d831  brfalse.s loc_1D889
0x1d833  ldarg.0
0x1d834  ldarg.1
0x1d835  ldarg.2
0x1d836  ldloc.s  7
0x1d838  call     instance string Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::RetrieveFetchXmlForEntity(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, string entitySetName, class Microsoft.Crm.Extensibility.OData.CustomQueryOptions queryOptions)
0x1d83d  stloc.s  9
0x1d83f  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x1d844  brfalse.s loc_1D87C
0x1d846  ldarg.1
0x1d847  callvirt instance class [System.Net.Http]System.Net.Http.HttpRequestMessage Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Request()
0x1d84c  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Properties()
0x1d851  ldstr    aOdataShouldrec// "OData.ShouldRecalculateSelectExpandNode"
0x1d856  ldc.i4.1
0x1d857  box      [mscorlib]System.Boolean
0x1d85c  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x1d861  ldarg.1
0x1d862  callvirt instance class [System.Net.Http]System.Net.Http.HttpRequestMessage Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Request()
0x1d867  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Properties()
0x1d86c  ldstr    aOdataCustomque// "OData.CustomQueryOptionsArePresent"
0x1d871  ldc.i4.1
0x1d872  box      [mscorlib]System.Boolean
0x1d877  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x1d87c  ldarg.0
0x1d87d  ldarg.1
0x1d87e  ldarg.2
0x1d87f  ldloc.s  7
0x1d881  ldloc.s  9
0x1d883  call     instance class Microsoft.Crm.Extensibility.OData.CrmEdmEntityObjectCollection Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::ExecuteQueryForEntitySet(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, string entitySetName, class Microsoft.Crm.Extensibility.OData.CustomQueryOptions queryOptions, string fetchXml)
0x1d888  ret
0x1d889  ldarg.2
0x1d88a  ldarg.0
0x1d88b  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::edmModel
0x1d890  call     string Microsoft.Crm.Extensibility.OData.EdmUtilities::GetEdmEntityNameFromCollectionName(string entityCollectionName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x1d895  stloc.1
0x1d896  ldarg.0
0x1d897  ldarg.s  4
0x1d899  ldloc.1
0x1d89a  call     instance void Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::ThrowIfExpandWithRefForNonLookupNavProp(class [System.Web.OData]System.Web.OData.Query.ODataQueryOptions queryOptions, string edmEntityName)
0x1d89f  ldarg.1
0x1d8a0  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_CrmExecutionContext()
0x1d8a5  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Extensibility.OData.OrganizationServiceFactory::GetCurrentUserId()
0x1d8aa  ldc.i4.0
0x1d8ab  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnBeginRequest(valuetype [mscorlib]System.Guid, bool)
0x1d8b0  ldarg.0
0x1d8b1  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::edmModel
0x1d8b6  ldarg.1
0x1d8b7  newobj   instance void Microsoft.Crm.Extensibility.OData.DataQueryOptionsConverter::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel, class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context)
0x1d8bc  ldarg.s  4
0x1d8be  ldloc.1
0x1d8bf  ldarg.1
0x1d8c0  ldnull
0x1d8c1  call     instance var<u1> class Microsoft.Crm.Extensibility.OData.QueryOptionsConverterBase`4<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator>::GetQueryExpression(!!T0, class [System.Web.OData]System.Web.OData.Query.ODataQueryOptions, string, class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext)
0x1d8c6  stloc.2
0x1d8c7  ldarg.0
0x1d8c8  ldarg.2
0x1d8c9  ldarg.s  4
0x1d8cb  ldloc.2
0x1d8cc  call     instance class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::AddLinkExpressionToQuery(string entityCollectionName, class [System.Web.OData]System.Web.OData.Query.ODataQueryOptions queryOptions, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression qe)
0x1d8d1  stloc.3
0x1d8d2  ldarg.1
0x1d8d3  ldloc.2
0x1d8d4  callvirt instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::SerializeToFetchXml()
0x1d8d9  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FetchExpression::.ctor(string)
0x1d8de  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::RetrieveMultiple(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryBase query)
0x1d8e3  stloc.s  4
0x1d8e5  ldarg.s  4
0x1d8e7  callvirt instance class [System.Web.OData]System.Web.OData.Query.ApplyQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_Apply()
0x1d8ec  brfalse.s loc_1D924
0x1d8ee  ldarg.1
0x1d8ef  callvirt instance class [System.Net.Http]System.Net.Http.HttpRequestMessage Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Request()
0x1d8f4  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Properties()
0x1d8f9  ldstr    aOdataShouldrec// "OData.ShouldRecalculateSelectExpandNode"
0x1d8fe  ldc.i4.1
0x1d8ff  box      [mscorlib]System.Boolean
0x1d904  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x1d909  ldarg.1
0x1d90a  callvirt instance class [System.Net.Http]System.Net.Http.HttpRequestMessage Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Request()
0x1d90f  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Properties()
0x1d914  ldstr    aOdataCustomque// "OData.CustomQueryOptionsArePresent"
0x1d919  ldc.i4.1
0x1d91a  box      [mscorlib]System.Boolean
0x1d91f  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x1d924  ldarg.s  4
0x1d926  brfalse.s loc_1D952
0x1d928  ldarg.s  4
0x1d92a  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x1d92f  brfalse.s loc_1D952
0x1d931  ldarg.s  4
0x1d933  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x1d938  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption::get_SelectExpandClause()
0x1d93d  brfalse.s loc_1D952
0x1d93f  ldarg.s  4
0x1d941  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x1d946  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption::get_SelectExpandClause()
0x1d94b  callvirt instance bool [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause::get_AllSelected()
0x1d950  br.s     loc_1D953
0x1d952  ldc.i4.1
0x1d953  stloc.s  5
0x1d955  ldloc.s  4
0x1d957  ldloc.1
0x1d958  ldarg.0
0x1d959  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::edmModel
0x1d95e  ldc.i4.1
0x1d95f  ldloc.s  5
0x1d961  ldloc.0
0x1d962  ldloc.3
0x1d963  call     class [System.Web.OData]System.Web.OData.EdmEntityObjectCollection Microsoft.Crm.Extensibility.OData.EdmTypeConverter::ConvertToEdmEntityObjectCollection(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection xrmEntityCollection, string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel, [opt] bool fillDerivedEntityProperties, [opt] bool fillAllProperties, [opt] bool noLock, [opt] class [mscorlib]System.Collections.Generic.List`1<string> navigationPropertyNames)
0x1d968  ldloc.s  4
0x1d96a  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_TotalRecordCount()
0x1d96f  ldloc.s  4
0x1d971  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_TotalRecordCountLimitExceeded()
0x1d976  ldarg.1
0x1d977  call     int32 Microsoft.Crm.Extensibility.OData.CrmODataUtilities::GetPageNumber(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context)
0x1d97c  ldloc.s  4
0x1d97e  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_PagingCookie()
0x1d983  ldarg.1
0x1d984  call     bool Microsoft.Crm.Extensibility.OData.CrmODataUtilities::TryAddTrackingFieldToNextLink(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context)
0x1d989  call     string Microsoft.Crm.Extensibility.OData.CrmODataUtilities::SerializePagingCookie(int32 pageNumber, string crmPagingCookie, bool isTracking)
0x1d98e  ldloc.s  4
0x1d990  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_MoreRecords()
0x1d995  newobj   instance void Microsoft.Crm.Extensibility.OData.CrmEdmEntityObjectCollection::.ctor(class [System.Web.OData]System.Web.OData.EdmEntityObjectCollection edmEntityCollection, int32 totalRecordCount, bool totalRecordCountLimitExceeded, string pagingCookie, bool hasMoreRecords)
0x1d99a  stloc.s  6
0x1d99c  ldloc.s  6
0x1d99e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Web.OData]System.Web.OData.IEdmEntityObject>::GetEnumerator()
0x1d9a3  stloc.s  0xA
0x1d9a5  br.s     loc_1DA0E
0x1d9a7  ldloc.s  0xA
0x1d9a9  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Web.OData]System.Web.OData.IEdmEntityObject>::get_Current()
0x1d9ae  castclass [System.Web.OData]System.Web.OData.EdmEntityObject
0x1d9b3  stloc.s  0xB
0x1d9b5  ldnull
0x1d9b6  stloc.s  0xC
0x1d9b8  ldloc.3
0x1d9b9  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<string>::GetEnumerator()
0x1d9be  stloc.s  0xD
0x1d9c0  br.s     loc_1D9F5
0x1d9c2  ldloca.s 0xD
0x1d9c4  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::get_Current()
0x1d9c9  stloc.s  0xE
0x1d9cb  ldloc.s  0xB
0x1d9cd  ldloc.s  0xE
0x1d9cf  ldloca.s 0xC
0x1d9d1  callvirt instance bool [System.Web.OData]System.Web.OData.Delta::TryGetPropertyValue(string, object&)
0x1d9d6  brfalse.s loc_1D9F5
0x1d9d8  ldloc.s  0xC
0x1d9da  isinst   Microsoft.Crm.Extensibility.OData.CrmEdmEntityObject
0x1d9df  brtrue.s loc_1D9F5
0x1d9e1  ldloc.s  0xC
0x1d9e3  isinst   Microsoft.Crm.Extensibility.OData.CrmEdmEntityObjectCollection
0x1d9e8  brtrue.s loc_1D9F5
0x1d9ea  ldloc.s  0xB
0x1d9ec  ldloc.s  0xE
0x1d9ee  ldnull
0x1d9ef  callvirt instance bool [System.Web.OData]System.Web.OData.Delta::TrySetPropertyValue(string, object)
0x1d9f4  pop
0x1d9f5  ldloca.s 0xD
0x1d9f7  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::MoveNext()
0x1d9fc  brtrue.s loc_1D9C2
0x1d9fe  leave.s  loc_1DA0E
0x1da00  ldloca.s 0xD
0x1da02  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>
0x1da08  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1da0d  endfinally
0x1da0e  ldloc.s  0xA
0x1da10  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1da15  brtrue.s loc_1D9A7
0x1da17  leave.s  loc_1DA25
0x1da19  ldloc.s  0xA
0x1da1b  brfalse.s loc_1DA24
0x1da1d  ldloc.s  0xA
0x1da1f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1da24  endfinally
0x1da25  ldarg.1
0x1da26  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_CrmExecutionContext()
0x1da2b  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnEndRequest()
0x1da30  ldloc.s  6
0x1da32  ret
```
