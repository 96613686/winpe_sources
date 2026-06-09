# Microsoft.Crm.Extensibility.OData.EntityController::GetNavigationImplementation

- ea: `0x12610`
- end: `0x127c7`
- name: `Microsoft.Crm.Extensibility.OData.EntityController::GetNavigationImplementation`
- size: `439`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x31d50`

## callees

- `0xfe80`
- `0x11500`
- `0x11640`
- `0x12610`
- `0x17630`
- `0x18fd0`
- `0x1e010`
- `0x1eea0`
- `0x1ef70`
- `0x20d50`
- `0x23e80`
- `0x24780`
- `0x24e60`
- `0x28b60`
- `0x28bb0`
- `0x28c90`
- `0x28e40`
- `0x28f60`
- `0x28fa0`

## string_xrefs

- `0x12745`: `CrmODataGetNavigationCompleted`

## pseudocode

```c

```

## disassembly

```asm
0x12610  ldarg.0
0x12611  call     instance class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary [System.Web.Http]System.Web.Http.ApiController::get_ModelState()
0x12616  call     void Microsoft.Crm.Extensibility.OData.CrmODataUtilities::ValidateInputParameters(class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary controllerModelState)
0x1261b  ldarg.1
0x1261c  ldind.ref
0x1261d  ldarg.0
0x1261e  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.EntityController::_edmModel
0x12623  call     bool Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::IsMetadataEntity(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x12628  stloc.0
0x12629  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0x1262e  stloc.1
0x1262f  ldarg.0
0x12630  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x12635  call     class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetCrmODataExecutionContext(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x1263a  stloc.2
0x1263b  ldarg.0
0x1263c  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x12641  ldarg.0
0x12642  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.EntityController::_edmModel
0x12647  call     class [System.Web.OData]System.Web.OData.Query.ODataQueryOptions Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetQueryOptions(class [System.Net.Http]System.Net.Http.HttpRequestMessage request, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x1264c  stloc.3
0x1264d  ldarg.1
0x1264e  ldarg.0
0x1264f  ldarg.1
0x12650  ldind.ref
0x12651  call     instance string Microsoft.Crm.Extensibility.OData.EntityController::GetCastedEntityNameIfAvailable(string entityName)
0x12656  stind.ref
0x12657  ldarg.0
0x12658  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x1265d  call     string Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetCastNavigationEntityName(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x12662  stloc.s  4
0x12664  ldarg.0
0x12665  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x1266a  call     bool Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetCountSegment(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x1266f  stloc.s  5
0x12671  ldnull
0x12672  stloc.s  6
0x12674  ldnull
0x12675  stloc.s  7
0x12677  ldarg.0
0x12678  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x1267d  ldarg.0
0x1267e  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.EntityController::_edmModel
0x12683  call     bool Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::IsCustomQueryOptionPresent(class [System.Net.Http]System.Net.Http.HttpRequestMessage request, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x12688  brfalse.s loc_126BD
0x1268a  ldarg.0
0x1268b  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x12690  ldarg.0
0x12691  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.EntityController::_edmModel
0x12696  call     class Microsoft.Crm.Extensibility.OData.CustomQueryOptions Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetCustomQueryOptionForQueryView(class [System.Net.Http]System.Net.Http.HttpRequestMessage request, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x1269b  stloc.s  8
0x1269d  ldarg.0
0x1269e  ldfld    class Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider Microsoft.Crm.Extensibility.OData.EntityController::crmODataServiceDataProvider
0x126a3  ldloc.2
0x126a4  ldarg.1
0x126a5  ldind.ref
0x126a6  ldarg.2
0x126a7  ldarg.3
0x126a8  ldloc.s  8
0x126aa  ldc.i4.0
0x126ab  callvirt instance class Microsoft.Crm.Extensibility.OData.CrmEdmEntityObjectCollection Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::RetrieveEdmEntityNavigation(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, string edmEntityName, string entityKeyValue, string navigationPropertyName, class [System.Web.OData]System.Web.OData.Query.ODataQueryOptions queryOptions, [opt] bool onlyRef)
0x126b0  stloc.s  7
0x126b2  ldloc.s  8
0x126b4  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption Microsoft.Crm.Extensibility.OData.CustomQueryOptions::get_SelectExpandQueryOption()
0x126b9  stloc.s  6
0x126bb  br.s     loc_1271C
0x126bd  ldarg.0
0x126be  ldarg.1
0x126bf  ldind.ref
0x126c0  ldarg.2
0x126c1  ldarg.3
0x126c2  ldloc.s  4
0x126c4  ldloc.0
0x126c5  ldloc.2
0x126c6  ldloc.3
0x126c7  ldloc.s  7
0x126c9  call     instance class Microsoft.Crm.Extensibility.OData.CrmEdmEntityObjectCollection Microsoft.Crm.Extensibility.OData.EntityController::GetNavigationInternal(string entityName, string key, string navigation, string derivedNavigation, bool isMetadataEntity, class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, class [System.Web.OData]System.Web.OData.Query.ODataQueryOptions queryOptions, class Microsoft.Crm.Extensibility.OData.CrmEdmEntityObjectCollection crmEdmEntityObject)
0x126ce  stloc.s  7
0x126d0  ldloc.3
0x126d1  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x126d6  stloc.s  6
0x126d8  ldloc.3
0x126d9  callvirt instance class [System.Web.OData]System.Web.OData.Query.CountQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_Count()
0x126de  brfalse.s loc_1270A
0x126e0  ldloc.3
0x126e1  callvirt instance class [System.Web.OData]System.Web.OData.Query.CountQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_Count()
0x126e6  callvirt instance bool [System.Web.OData]System.Web.OData.Query.CountQueryOption::get_Value()
0x126eb  brfalse.s loc_1270A
0x126ed  ldarg.0
0x126ee  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x126f3  call     class [System.Web.OData]System.Web.OData.Extensions.HttpRequestMessageProperties [System.Web.OData]System.Web.OData.Extensions.HttpRequestMessageExtensions::ODataProperties(class [System.Net.Http]System.Net.Http.HttpRequestMessage)
0x126f8  ldloc.s  7
0x126fa  callvirt instance int32 Microsoft.Crm.Extensibility.OData.CrmEdmEntityObjectCollection::get_TotalRecordCount()
0x126ff  conv.i8
0x12700  newobj   instance void valuetype [mscorlib]System.Nullable`1<int64>::.ctor(var<u1>)
0x12705  callvirt instance void [System.Web.OData]System.Web.OData.Extensions.HttpRequestMessageProperties::set_TotalCount(valuetype [mscorlib]System.Nullable`1<int64>)
0x1270a  ldloc.s  5
0x1270c  brfalse.s loc_1271C
0x1270e  ldarg.0
0x1270f  ldloc.s  7
0x12711  callvirt instance int32 Microsoft.Crm.Extensibility.OData.CrmEdmEntityObjectCollection::get_TotalRecordCount()
0x12716  callvirt T0x2B000074
0x1271b  ret
0x1271c  ldloc.s  6
0x1271e  brfalse.s loc_12740
0x12720  ldloc.s  6
0x12722  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption::get_SelectExpandClause()
0x12727  brfalse.s loc_12740
0x12729  ldarg.0
0x1272a  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x1272f  call     class [System.Web.OData]System.Web.OData.Extensions.HttpRequestMessageProperties [System.Web.OData]System.Web.OData.Extensions.HttpRequestMessageExtensions::ODataProperties(class [System.Net.Http]System.Net.Http.HttpRequestMessage)
0x12734  ldloc.s  6
0x12736  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption::get_SelectExpandClause()
0x1273b  callvirt instance void [System.Web.OData]System.Web.OData.Extensions.HttpRequestMessageProperties::set_SelectExpandClause(class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause)
0x12740  call     class Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents::get_Instance()
0x12745  ldstr    aCrmodatagetnav// "CrmODataGetNavigationCompleted"
0x1274a  ldarg.1
0x1274b  ldind.ref
0x1274c  ldstr    aGet// "get"
0x12751  ldstr    aNavigationname// "navigationName"
0x12756  ldarg.3
0x12757  newobj   instance void class [mscorlib]System.Tuple`2<string, string>::.ctor(var<u1>, !!T0)
0x1275c  ldloc.1
0x1275d  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::Stop()
0x12762  callvirt instance void Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents::LogEvent(string eventName, string entityOrEntitySetName, string verb, class [mscorlib]System.Tuple`2<string, string> extraParam, class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken executionToken)
0x12767  ldloc.s  7
0x12769  brfalse.s loc_12774
0x1276b  ldloc.s  7
0x1276d  call     T0x2B000079
0x12772  brtrue.s loc_1279F
0x12774  ldarg.1
0x12775  ldind.ref
0x12776  ldarg.3
0x12777  ldarg.0
0x12778  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.EntityController::_edmModel
0x1277d  ldloc.0
0x1277e  call     bool Microsoft.Crm.Extensibility.OData.EdmUtilities::IsManyToOneRelationship(string edmEntityName, string navigationPropertyName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel, [opt] bool isMetadataEntity)
0x12783  brtrue.s loc_12789
0x12785  ldloc.s  7
0x12787  brtrue.s loc_12796
0x12789  ldloc.2
0x1278a  callvirt instance class Microsoft.Crm.Extensibility.OData.CrmODataHeaders Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Headers()
0x1278f  ldc.i4.0
0x12790  callvirt instance class [System.Web.Http]System.Web.Http.IHttpActionResult Microsoft.Crm.Extensibility.OData.CrmODataHeaders::GetEmptyODataResponse([opt] bool isResponseFromAction)
0x12795  ret
0x12796  ldarg.0
0x12797  ldloc.s  7
0x12799  callvirt T0x2B000076
0x1279e  ret
0x1279f  ldarg.1
0x127a0  ldind.ref
0x127a1  ldarg.3
0x127a2  ldarg.0
0x127a3  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.EntityController::_edmModel
0x127a8  ldloc.0
0x127a9  call     bool Microsoft.Crm.Extensibility.OData.EdmUtilities::IsManyToOneRelationship(string edmEntityName, string navigationPropertyName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel, [opt] bool isMetadataEntity)
0x127ae  brfalse.s loc_127BE
0x127b0  ldarg.0
0x127b1  ldloc.s  7
0x127b3  call     T0x2B00007A
0x127b8  callvirt T0x2B00007B
0x127bd  ret
0x127be  ldarg.0
0x127bf  ldloc.s  7
0x127c1  callvirt T0x2B000076
0x127c6  ret
```
