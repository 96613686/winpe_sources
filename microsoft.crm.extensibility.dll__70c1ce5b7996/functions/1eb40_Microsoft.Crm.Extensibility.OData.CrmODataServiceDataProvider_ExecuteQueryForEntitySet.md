# Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::ExecuteQueryForEntitySet

- ea: `0x1eb40`
- end: `0x1ed0f`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::ExecuteQueryForEntitySet`
- size: `463`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `service_task, broker_com_uri`

## callers

- `0x1d750`

## callees

- `0xf740`
- `0xfab0`
- `0xfbf0`
- `0xfe20`
- `0x13540`
- `0x175f0`
- `0x1eb40`
- `0x20200`
- `0x202c0`
- `0x20360`
- `0x20bf0`
- `0x20c30`
- `0x21270`
- `0x24790`
- `0x24cd0`
- `0x24e10`
- `0x28fe0`

## string_xrefs

- `0x1eb72`: `$skiptoken`
- `0x1eb80`: `$skiptoken`

## pseudocode

```c

```

## disassembly

```asm
0x1eb40  ldarg.1
0x1eb41  callvirt instance class [System.Net.Http]System.Net.Http.HttpRequestMessage Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Request()
0x1eb46  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::QueryParameterDictionary(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x1eb4b  call     bool Microsoft.Crm.Extensibility.OData.EdmUtilities::ValidateAndReturnNoLock(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> queryParams)
0x1eb50  stloc.0
0x1eb51  ldarg.s  4
0x1eb53  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FetchExpression::.ctor(string)
0x1eb58  stloc.1
0x1eb59  ldnull
0x1eb5a  stloc.2
0x1eb5b  ldarg.3
0x1eb5c  call     bool Microsoft.Crm.Extensibility.OData.CrmODataUtilities::IsSavedOrUserQueryOption(class Microsoft.Crm.Extensibility.OData.CustomQueryOptions queryOptions)
0x1eb61  brfalse.s loc_1EBA4
0x1eb63  ldarg.1
0x1eb64  callvirt instance class [System.Net.Http]System.Net.Http.HttpRequestMessage Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Request()
0x1eb69  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::QueryParameterDictionary(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x1eb6e  stloc.s  5
0x1eb70  ldloc.s  5
0x1eb72  ldstr    aSkiptoken// "$skiptoken"
0x1eb77  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x1eb7c  brfalse.s loc_1EBA4
0x1eb7e  ldloc.s  5
0x1eb80  ldstr    aSkiptoken// "$skiptoken"
0x1eb85  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x1eb8a  call     class Microsoft.Crm.Extensibility.OData.CrmODataPagingCookie Microsoft.Crm.Extensibility.OData.CrmODataUtilities::DeserializePagingCookie(string batchCookie)
0x1eb8f  stloc.s  6
0x1eb91  ldloc.1
0x1eb92  ldloc.1
0x1eb93  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FetchExpression::get_Query()
0x1eb98  ldloc.s  6
0x1eb9a  call     string Microsoft.Crm.Extensibility.OData.CrmODataUtilities::InjectFetchExpressionWithPagingInformation(string query, class Microsoft.Crm.Extensibility.OData.CrmODataPagingCookie crmODataPagingCookie)
0x1eb9f  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FetchExpression::set_Query(string)
0x1eba4  ldarg.1
0x1eba5  ldloc.1
0x1eba6  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::RetrieveMultiple(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryBase query)
0x1ebab  stloc.2
0x1ebac  ldarg.2
0x1ebad  ldarg.0
0x1ebae  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::edmModel
0x1ebb3  call     string Microsoft.Crm.Extensibility.OData.EdmUtilities::GetEdmEntityNameFromCollectionName(string entityCollectionName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x1ebb8  stloc.3
0x1ebb9  ldloc.2
0x1ebba  ldloc.3
0x1ebbb  ldarg.0
0x1ebbc  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::edmModel
0x1ebc1  ldc.i4.0
0x1ebc2  ldc.i4.0
0x1ebc3  ldloc.0
0x1ebc4  ldnull
0x1ebc5  call     class [System.Web.OData]System.Web.OData.EdmEntityObjectCollection Microsoft.Crm.Extensibility.OData.EdmTypeConverter::ConvertToEdmEntityObjectCollection(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection xrmEntityCollection, string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel, [opt] bool fillDerivedEntityProperties, [opt] bool fillAllProperties, [opt] bool noLock, [opt] class [mscorlib]System.Collections.Generic.List`1<string> navigationPropertyNames)
0x1ebca  ldloc.2
0x1ebcb  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_TotalRecordCount()
0x1ebd0  ldloc.2
0x1ebd1  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_TotalRecordCountLimitExceeded()
0x1ebd6  ldarg.1
0x1ebd7  call     int32 Microsoft.Crm.Extensibility.OData.CrmODataUtilities::GetPageNumber(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context)
0x1ebdc  ldloc.2
0x1ebdd  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_PagingCookie()
0x1ebe2  ldarg.1
0x1ebe3  call     bool Microsoft.Crm.Extensibility.OData.CrmODataUtilities::TryAddTrackingFieldToNextLink(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context)
0x1ebe8  call     string Microsoft.Crm.Extensibility.OData.CrmODataUtilities::SerializePagingCookie(int32 pageNumber, string crmPagingCookie, bool isTracking)
0x1ebed  ldloc.2
0x1ebee  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_MoreRecords()
0x1ebf3  newobj   instance void Microsoft.Crm.Extensibility.OData.CrmEdmEntityObjectCollection::.ctor(class [System.Web.OData]System.Web.OData.EdmEntityObjectCollection edmEntityCollection, int32 totalRecordCount, bool totalRecordCountLimitExceeded, string pagingCookie, bool hasMoreRecords)
0x1ebf8  stloc.s  4
0x1ebfa  ldloc.s  4
0x1ebfc  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Web.OData]System.Web.OData.IEdmEntityObject>::get_Count()
0x1ec01  ldc.i4.0
0x1ec02  ble      loc_1ED0C
0x1ec07  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x1ec0c  stloc.s  7
0x1ec0e  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x1ec13  stloc.s  8
0x1ec15  ldloc.s  4
0x1ec17  ldc.i4.0
0x1ec18  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Web.OData]System.Web.OData.IEdmEntityObject>::get_Item(!!T0)
0x1ec1d  castclass Microsoft.Crm.Extensibility.OData.CrmEdmEntityObject
0x1ec22  dup
0x1ec23  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> [System.Web.OData]System.Web.OData.Delta::GetChangedPropertyNames()
0x1ec28  stloc.s  9
0x1ec2a  dup
0x1ec2b  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmStructuredType [System.Web.OData]System.Web.OData.EdmStructuredObject::get_ActualEdmType()
0x1ec30  castclass [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmEntityType
0x1ec35  stloc.s  0xA
0x1ec37  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Extensibility.OData.CrmEdmEntityObject::_extraSetContainer
0x1ec3c  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Count()
0x1ec41  ldc.i4.0
0x1ec42  cgt
0x1ec44  stloc.s  0xB
0x1ec46  ldloc.s  9
0x1ec48  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x1ec4d  stloc.s  0xC
0x1ec4f  br.s     loc_1ECB3
0x1ec51  ldloc.s  0xC
0x1ec53  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x1ec58  stloc.s  0xD
0x1ec5a  ldloc.s  0xA
0x1ec5c  ldloc.s  0xD
0x1ec5e  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmStructuredType::FindProperty(string)
0x1ec63  stloc.s  0xE
0x1ec65  ldloc.s  0xE
0x1ec67  callvirt instance valuetype [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmPropertyKind [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty::get_PropertyKind()
0x1ec6c  ldc.i4.2
0x1ec6d  bne.un.s loc_1EC93
0x1ec6f  ldloc.s  0xA
0x1ec71  ldloc.3
0x1ec72  ldarg.0
0x1ec73  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::edmModel
0x1ec78  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CrmEdmEntityType Microsoft.Crm.Extensibility.OData.EdmUtilities::GetEdmEntityType(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x1ec7d  bne.un.s loc_1ECB3
0x1ec7f  ldloc.s  7
0x1ec81  ldloc.s  0xD
0x1ec83  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1ec88  ldloc.s  8
0x1ec8a  ldloc.s  0xD
0x1ec8c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1ec91  br.s     loc_1ECB3
0x1ec93  ldloc.s  0xE
0x1ec95  callvirt instance valuetype [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmPropertyKind [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty::get_PropertyKind()
0x1ec9a  ldc.i4.1
0x1ec9b  bne.un.s loc_1ECA8
0x1ec9d  ldloc.s  8
0x1ec9f  ldloc.s  0xD
0x1eca1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1eca6  br.s     loc_1ECB3
0x1eca8  ldstr    aInvalidPropert// "Invalid PropertyKind"
0x1ecad  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x1ecb2  throw
0x1ecb3  ldloc.s  0xC
0x1ecb5  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1ecba  brtrue.s loc_1EC51
0x1ecbc  leave.s  loc_1ECCA
0x1ecbe  ldloc.s  0xC
0x1ecc0  brfalse.s loc_1ECC9
0x1ecc2  ldloc.s  0xC
0x1ecc4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1ecc9  endfinally
0x1ecca  ldloc.s  7
0x1eccc  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x1ecd1  ldc.i4.0
0x1ecd2  bgt.s    loc_1ECE2
0x1ecd4  ldloc.s  8
0x1ecd6  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x1ecdb  ldc.i4.0
0x1ecdc  bgt.s    loc_1ECE2
0x1ecde  ldloc.s  0xB
0x1ece0  brtrue.s loc_1ED02
0x1ece2  ldstr    asc_366F0// ","
0x1ece7  ldloc.s  8
0x1ece9  call     string [mscorlib]System.String::Join(string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x1ecee  ldarg.3
0x1ecef  ldstr    asc_366F0// ","
0x1ecf4  ldloc.s  7
0x1ecf6  call     string [mscorlib]System.String::Join(string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x1ecfb  call     void Microsoft.Crm.Extensibility.OData.EdmUtilities::PopulateSelectExpandClauseForQueryOptions(string selectClause, class Microsoft.Crm.Extensibility.OData.CustomQueryOptions queryOptions, [opt] string expandClause)
0x1ed00  br.s     loc_1ED0C
0x1ed02  ldarg.3
0x1ed03  brfalse.s loc_1ED0C
0x1ed05  ldarg.3
0x1ed06  ldnull
0x1ed07  callvirt instance void Microsoft.Crm.Extensibility.OData.CustomQueryOptions::set_SelectExpandQueryOption(class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption value)
0x1ed0c  ldloc.s  4
0x1ed0e  ret
```
