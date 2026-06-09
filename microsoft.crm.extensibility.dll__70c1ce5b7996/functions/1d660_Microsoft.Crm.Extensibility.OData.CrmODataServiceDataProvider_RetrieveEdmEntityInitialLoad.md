# Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::RetrieveEdmEntityInitialLoad

- ea: `0x1d660`
- end: `0x1d748`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::RetrieveEdmEntityInitialLoad`
- size: `232`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `service_task, broker_com_uri`

## callers

- `0x11f10`

## callees

- `0xfab0`
- `0xfbf0`
- `0x13540`
- `0x175f0`
- `0x17680`
- `0x18f50`
- `0x1d660`
- `0x1e330`
- `0x20200`
- `0x20360`
- `0x21070`
- `0x21200`
- `0x21270`
- `0x24c40`
- `0x24e10`
- `0x24e60`
- `0x28fe0`

## pseudocode

```c

```

## disassembly

```asm
0x1d660  ldarg.2
0x1d661  ldarg.0
0x1d662  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::edmModel
0x1d667  call     string Microsoft.Crm.Extensibility.OData.EdmUtilities::GetEdmEntityNameFromCollectionName(string entityCollectionName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x1d66c  stloc.0
0x1d66d  ldarg.1
0x1d66e  callvirt instance class [System.Net.Http]System.Net.Http.HttpRequestMessage Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Request()
0x1d673  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::QueryParameterDictionary(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x1d678  call     bool Microsoft.Crm.Extensibility.OData.EdmUtilities::ValidateAndReturnNoLock(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> queryParams)
0x1d67d  stloc.1
0x1d67e  ldarg.0
0x1d67f  ldarg.1
0x1d680  ldloc.0
0x1d681  ldarg.3
0x1d682  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveEntityChangesRequest Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::CreateEntityChangesRequest(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, string edmEntityName, class [System.Web.OData]System.Web.OData.Query.ODataQueryOptions queryOptions)
0x1d687  stloc.2
0x1d688  ldloc.2
0x1d689  ldarg.1
0x1d68a  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.PagingInfo Microsoft.Crm.Extensibility.OData.CrmODataUtilities::GetPagingInfoForChangeTracking(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context)
0x1d68f  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveEntityChangesRequest::set_PageInfo(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.PagingInfo)
0x1d694  ldarg.1
0x1d695  ldloc.2
0x1d696  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest request)
0x1d69b  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveEntityChangesResponse
0x1d6a0  stloc.3
0x1d6a1  ldarg.3
0x1d6a2  brfalse.s loc_1D6CB
0x1d6a4  ldarg.3
0x1d6a5  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x1d6aa  brfalse.s loc_1D6CB
0x1d6ac  ldarg.3
0x1d6ad  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x1d6b2  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption::get_SelectExpandClause()
0x1d6b7  brfalse.s loc_1D6CB
0x1d6b9  ldarg.3
0x1d6ba  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x1d6bf  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption::get_SelectExpandClause()
0x1d6c4  callvirt instance bool [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause::get_AllSelected()
0x1d6c9  br.s     loc_1D6CC
0x1d6cb  ldc.i4.1
0x1d6cc  stloc.s  4
0x1d6ce  ldloc.3
0x1d6cf  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BusinessEntityChanges [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveEntityChangesResponse::get_EntityChanges()
0x1d6d4  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection Microsoft.Crm.Extensibility.OData.CrmODataUtilities::CreateEntityCollectionForInitialLoad(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BusinessEntityChanges entityChanges)
0x1d6d9  ldloc.0
0x1d6da  ldarg.0
0x1d6db  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::edmModel
0x1d6e0  ldc.i4.1
0x1d6e1  ldloc.s  4
0x1d6e3  ldloc.1
0x1d6e4  ldnull
0x1d6e5  call     class [System.Web.OData]System.Web.OData.EdmEntityObjectCollection Microsoft.Crm.Extensibility.OData.EdmTypeConverter::ConvertToEdmEntityObjectCollection(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection xrmEntityCollection, string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel, [opt] bool fillDerivedEntityProperties, [opt] bool fillAllProperties, [opt] bool noLock, [opt] class [mscorlib]System.Collections.Generic.List`1<string> navigationPropertyNames)
0x1d6ea  ldc.i4.0
0x1d6eb  ldc.i4.0
0x1d6ec  ldarg.1
0x1d6ed  call     int32 Microsoft.Crm.Extensibility.OData.CrmODataUtilities::GetPageNumber(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context)
0x1d6f2  ldloc.3
0x1d6f3  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BusinessEntityChanges [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveEntityChangesResponse::get_EntityChanges()
0x1d6f8  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BusinessEntityChanges::get_PagingCookie()
0x1d6fd  ldarg.1
0x1d6fe  call     bool Microsoft.Crm.Extensibility.OData.CrmODataUtilities::TryAddTrackingFieldToNextLink(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context)
0x1d703  call     string Microsoft.Crm.Extensibility.OData.CrmODataUtilities::SerializePagingCookie(int32 pageNumber, string crmPagingCookie, bool isTracking)
0x1d708  ldloc.3
0x1d709  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BusinessEntityChanges [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveEntityChangesResponse::get_EntityChanges()
0x1d70e  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BusinessEntityChanges::get_MoreRecords()
0x1d713  newobj   instance void Microsoft.Crm.Extensibility.OData.CrmEdmEntityObjectCollection::.ctor(class [System.Web.OData]System.Web.OData.EdmEntityObjectCollection edmEntityCollection, int32 totalRecordCount, bool totalRecordCountLimitExceeded, string pagingCookie, bool hasMoreRecords)
0x1d718  dup
0x1d719  ldloc.3
0x1d71a  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BusinessEntityChanges [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveEntityChangesResponse::get_EntityChanges()
0x1d71f  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BusinessEntityChanges::get_DataToken()
0x1d724  callvirt instance void Microsoft.Crm.Extensibility.OData.CrmEdmEntityObjectCollection::set_DeltaToken(string value)
0x1d729  ldloc.2
0x1d72a  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.PagingInfo [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveEntityChangesRequest::get_PageInfo()
0x1d72f  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.PagingInfo::get_PageNumber()
0x1d734  ldc.i4.1
0x1d735  bne.un.s loc_1D747
0x1d737  ldarg.1
0x1d738  callvirt instance class Microsoft.Crm.Extensibility.OData.CrmODataHeaders Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Headers()
0x1d73d  ldstr    aOdataTrackChan// "odata.track-changes"
0x1d742  callvirt instance void Microsoft.Crm.Extensibility.OData.CrmODataHeaders::SetPreferenceAppliedResponse(string preferenceAppliedHeaderValue)
0x1d747  ret
```
