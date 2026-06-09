# Microsoft.Crm.Extensibility.OData.CrmODataConfigurator::Register

- ea: `0x18060`
- end: `0x182b8`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataConfigurator::Register`
- size: `600`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x103f0`
- `0x17b70`
- `0x18060`
- `0x182c0`
- `0x18c40`
- `0x18d00`
- `0x20fc0`
- `0x24a40`
- `0x282c0`
- `0x28880`
- `0x289f0`
- `0x2aca0`
- `0x2b9c0`
- `0x2c200`
- `0x2e550`
- `0x32d80`
- `0x32e60`

## string_xrefs

- `0x18080`: `ODataServiceDocWithoutVersion`
- `0x1808a`: `ODataServiceDocWithoutVersion`
- `0x180b6`: `ODataServiceDocWithoutVersion`
- `0x180d3`: `ODataServiceDocWithoutVersion`
- `0x180dd`: `ODataServiceDocWithoutVersion`
- `0x180ac`: `ODataServiceDocWithoutVersionIFD`

## pseudocode

```c

```

## disassembly

```asm
0x18060  newobj   instance void <>c__DisplayClass1_0::.ctor()
0x18065  stloc.0
0x18066  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x1806b  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::GetSku()
0x18070  ldc.i4.1
0x18071  bne.un.s loc_180CD
0x18073  ldsfld   bool Microsoft.Crm.Extensibility.OData.CrmODataConfigurator::_isOutlookOfflineEnabled
0x18078  brtrue.s loc_180CD
0x1807a  ldarg.0
0x1807b  callvirt instance class [System.Web.Http]System.Web.Http.HttpRouteCollection [System.Web.Http]System.Web.Http.HttpConfiguration::get_Routes()
0x18080  ldstr    aOdataservicedo// "ODataServiceDocWithoutVersion"
0x18085  ldstr    aOrganizationAp// "{organization}/api/data/"
0x1808a  ldstr    aOdataservicedo// "ODataServiceDocWithoutVersion"
0x1808f  ldstr    aGet_1// "Get"
0x18094  newobj   instance void class <>f__AnonymousType2`2<string, string>::.ctor(var<u1>, !!T0)
0x18099  call     class [System.Web.Http]System.Web.Http.Routing.IHttpRoute [System.Web.Http]System.Web.Http.HttpRouteCollectionExtensions::MapHttpRoute(class [System.Web.Http]System.Web.Http.HttpRouteCollection, string, string, object)
0x1809e  pop
0x1809f  call     bool Microsoft.Crm.Extensibility.OData.CrmODataUtilities::IsIfdEnabled()
0x180a4  brfalse.s loc_180F2
0x180a6  ldarg.0
0x180a7  callvirt instance class [System.Web.Http]System.Web.Http.HttpRouteCollection [System.Web.Http]System.Web.Http.HttpConfiguration::get_Routes()
0x180ac  ldstr    aOdataservicedo_0// "ODataServiceDocWithoutVersionIFD"
0x180b1  ldstr    aApiData// "api/data/"
0x180b6  ldstr    aOdataservicedo// "ODataServiceDocWithoutVersion"
0x180bb  ldstr    aGet_1// "Get"
0x180c0  newobj   instance void class <>f__AnonymousType2`2<string, string>::.ctor(var<u1>, !!T0)
0x180c5  call     class [System.Web.Http]System.Web.Http.Routing.IHttpRoute [System.Web.Http]System.Web.Http.HttpRouteCollectionExtensions::MapHttpRoute(class [System.Web.Http]System.Web.Http.HttpRouteCollection, string, string, object)
0x180ca  pop
0x180cb  br.s     loc_180F2
0x180cd  ldarg.0
0x180ce  callvirt instance class [System.Web.Http]System.Web.Http.HttpRouteCollection [System.Web.Http]System.Web.Http.HttpConfiguration::get_Routes()
0x180d3  ldstr    aOdataservicedo// "ODataServiceDocWithoutVersion"
0x180d8  ldstr    aApiData// "api/data/"
0x180dd  ldstr    aOdataservicedo// "ODataServiceDocWithoutVersion"
0x180e2  ldstr    aGet_1// "Get"
0x180e7  newobj   instance void class <>f__AnonymousType2`2<string, string>::.ctor(var<u1>, !!T0)
0x180ec  call     class [System.Web.Http]System.Web.Http.Routing.IHttpRoute [System.Web.Http]System.Web.Http.HttpRouteCollectionExtensions::MapHttpRoute(class [System.Web.Http]System.Web.Http.HttpRouteCollection, string, string, object)
0x180f1  pop
0x180f2  ldloc.0
0x180f3  ldsfld   class [mscorlib]System.Func`2<class [mscorlib]System.IServiceProvider, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel> <>c::<>9__1_0
0x180f8  dup
0x180f9  brtrue.s loc_18112
0x180fb  pop
0x180fc  ldsfld   class <>c <>c::<>9
0x18101  ldftn    instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel <>c::<Register>b__1_0(class [mscorlib]System.IServiceProvider sp)
0x18107  newobj   instance void class [mscorlib]System.Func`2<class [mscorlib]System.IServiceProvider, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel>::.ctor(object, native int)
0x1810c  dup
0x1810d  stsfld   class [mscorlib]System.Func`2<class [mscorlib]System.IServiceProvider, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel> <>c::<>9__1_0
0x18112  stfld    class [mscorlib]System.Func`2<class [mscorlib]System.IServiceProvider, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel> <>c__DisplayClass1_0::modelService
0x18117  ldloc.0
0x18118  ldsfld   class [mscorlib]System.Func`2<class [mscorlib]System.IServiceProvider, class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataUriResolver> <>c::<>9__1_1
0x1811d  dup
0x1811e  brtrue.s loc_18137
0x18120  pop
0x18121  ldsfld   class <>c <>c::<>9
0x18126  ldftn    instance class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataUriResolver <>c::<Register>b__1_1(class [mscorlib]System.IServiceProvider sp)
0x1812c  newobj   instance void class [mscorlib]System.Func`2<class [mscorlib]System.IServiceProvider, class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataUriResolver>::.ctor(object, native int)
0x18131  dup
0x18132  stsfld   class [mscorlib]System.Func`2<class [mscorlib]System.IServiceProvider, class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataUriResolver> <>c::<>9__1_1
0x18137  stfld    class [mscorlib]System.Func`2<class [mscorlib]System.IServiceProvider, class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataUriResolver> <>c__DisplayClass1_0::uriResolverService
0x1813c  ldloc.0
0x1813d  call     class [System.Web.Http]System.Web.Http.HttpServer [System.Web.Http.WebHost]System.Web.Http.GlobalConfiguration::get_DefaultServer()
0x18142  newobj   instance void Microsoft.Crm.Extensibility.OData.CrmODataBatchHandler::.ctor(class [System.Web.Http]System.Web.Http.HttpServer server)
0x18147  stfld    class Microsoft.Crm.Extensibility.OData.CrmODataBatchHandler <>c__DisplayClass1_0::batchHandler
0x1814c  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x18151  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::GetSku()
0x18156  ldc.i4.1
0x18157  bne.un.s loc_18160
0x18159  ldsfld   bool Microsoft.Crm.Extensibility.OData.CrmODataConfigurator::_isOutlookOfflineEnabled
0x1815e  brfalse.s loc_18167
0x18160  ldstr    aApiDataApivers// "api/data/{apiversion}/"
0x18165  br.s     loc_1816C
0x18167  ldstr    aOrganizationAp_0// "{organization}/api/data/{apiversion}/"
0x1816c  stloc.1
0x1816d  ldloc.0
0x1816e  call     class [mscorlib]System.Collections.Generic.IList`1<class [System.Web.OData]System.Web.OData.Routing.Conventions.IODataRoutingConvention> [System.Web.OData]System.Web.OData.Routing.Conventions.ODataRoutingConventions::CreateDefault()
0x18173  stfld    class [mscorlib]System.Collections.Generic.IList`1<class [System.Web.OData]System.Web.OData.Routing.Conventions.IODataRoutingConvention> <>c__DisplayClass1_0::conventions
0x18178  ldloc.0
0x18179  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class [System.Web.OData]System.Web.OData.Routing.Conventions.IODataRoutingConvention> <>c__DisplayClass1_0::conventions
0x1817e  ldc.i4.0
0x1817f  newobj   instance void Microsoft.Crm.Extensibility.ODataV4.Routing.CrmODataRoutingConvention::.ctor()
0x18184  callvirt instance void class [mscorlib]System.Collections.Generic.IList`1<class [System.Web.OData]System.Web.OData.Routing.Conventions.IODataRoutingConvention>::Insert(int32, var<u1>)
0x18189  ldarg.0
0x1818a  ldstr    aCrmodataroute// "CrmODataRoute"
0x1818f  ldloc.1
0x18190  ldloc.0
0x18191  ldftn    instance void <>c__DisplayClass1_0::<Register>b__2(class [Microsoft.OData.Core]Microsoft.OData.IContainerBuilder builder)
0x18197  newobj   instance void class [mscorlib]System.Action`1<class [Microsoft.OData.Core]Microsoft.OData.IContainerBuilder>::.ctor(object, native int)
0x1819c  call     class [System.Web.OData]System.Web.OData.Routing.ODataRoute [System.Web.OData]System.Web.OData.Extensions.HttpConfigurationExtensions::MapODataServiceRoute(class [System.Web.Http]System.Web.Http.HttpConfiguration, string, string, class [mscorlib]System.Action`1<class [Microsoft.OData.Core]Microsoft.OData.IContainerBuilder>)
0x181a1  pop
0x181a2  call     bool Microsoft.Crm.Extensibility.OData.CrmODataUtilities::IsIfdEnabled()
0x181a7  brfalse.s loc_181F3
0x181a9  newobj   instance void <>c__DisplayClass1_1::.ctor()
0x181ae  stloc.3
0x181af  ldloc.3
0x181b0  ldloc.0
0x181b1  stfld    class <>c__DisplayClass1_0 <>c__DisplayClass1_1::CS$<>8__locals1
0x181b6  ldstr    aApiDataApivers// "api/data/{apiversion}/"
0x181bb  stloc.s  4
0x181bd  ldloc.3
0x181be  call     class [mscorlib]System.Collections.Generic.IList`1<class [System.Web.OData]System.Web.OData.Routing.Conventions.IODataRoutingConvention> [System.Web.OData]System.Web.OData.Routing.Conventions.ODataRoutingConventions::CreateDefault()
0x181c3  stfld    class [mscorlib]System.Collections.Generic.IList`1<class [System.Web.OData]System.Web.OData.Routing.Conventions.IODataRoutingConvention> <>c__DisplayClass1_1::ifdConventions
0x181c8  ldloc.3
0x181c9  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class [System.Web.OData]System.Web.OData.Routing.Conventions.IODataRoutingConvention> <>c__DisplayClass1_1::ifdConventions
0x181ce  ldc.i4.0
0x181cf  newobj   instance void Microsoft.Crm.Extensibility.ODataV4.Routing.CrmODataIFDRoutingConvention::.ctor()
0x181d4  callvirt instance void class [mscorlib]System.Collections.Generic.IList`1<class [System.Web.OData]System.Web.OData.Routing.Conventions.IODataRoutingConvention>::Insert(int32, var<u1>)
0x181d9  ldarg.0
0x181da  ldstr    aCrmodataroutei// "CrmODataRouteifd"
0x181df  ldloc.s  4
0x181e1  ldloc.3
0x181e2  ldftn    instance void <>c__DisplayClass1_1::<Register>b__5(class [Microsoft.OData.Core]Microsoft.OData.IContainerBuilder builder)
0x181e8  newobj   instance void class [mscorlib]System.Action`1<class [Microsoft.OData.Core]Microsoft.OData.IContainerBuilder>::.ctor(object, native int)
0x181ed  call     class [System.Web.OData]System.Web.OData.Routing.ODataRoute [System.Web.OData]System.Web.OData.Extensions.HttpConfigurationExtensions::MapODataServiceRoute(class [System.Web.Http]System.Web.Http.HttpConfiguration, string, string, class [mscorlib]System.Action`1<class [Microsoft.OData.Core]Microsoft.OData.IContainerBuilder>)
0x181f2  pop
0x181f3  ldarg.0
0x181f4  callvirt instance class [System.Web.Http]System.Web.Http.Controllers.ServicesContainer [System.Web.Http]System.Web.Http.HttpConfiguration::get_Services()
0x181f9  ldtoken  [System.Web.Http]System.Web.Http.Validation.IBodyModelValidator
0x181fe  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18203  newobj   instance void Microsoft.Crm.Extensibility.ODataV4.CrmODataBodyModelValidator::.ctor()
0x18208  callvirt instance void [System.Web.Http]System.Web.Http.Controllers.ServicesContainer::Replace(class [mscorlib]System.Type, object)
0x1820d  ldarg.0
0x1820e  callvirt instance class [System.Web.Http]System.Web.Http.Controllers.ServicesContainer [System.Web.Http]System.Web.Http.HttpConfiguration::get_Services()
0x18213  ldtoken  [System.Web.Http]System.Web.Http.ExceptionHandling.IExceptionHandler
0x18218  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1821d  newobj   instance void Microsoft.Crm.Extensibility.OData.CrmODataExceptionHandler::.ctor()
0x18222  callvirt instance void [System.Web.Http]System.Web.Http.Controllers.ServicesContainer::Replace(class [mscorlib]System.Type, object)
0x18227  ldarg.0
0x18228  callvirt instance class [System.Web.Http]System.Web.Http.Controllers.ServicesContainer [System.Web.Http]System.Web.Http.HttpConfiguration::get_Services()
0x1822d  ldtoken  [System.Web.Http]System.Web.Http.ExceptionHandling.IExceptionLogger
0x18232  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18237  newobj   instance void Microsoft.Crm.Extensibility.OData.CrmODataExceptionLogger::.ctor()
0x1823c  callvirt instance void [System.Web.Http]System.Web.Http.Controllers.ServicesContainer::Replace(class [mscorlib]System.Type, object)
0x18241  ldarg.0
0x18242  callvirt instance class [System.Web.Http]System.Web.Http.Controllers.ServicesContainer [System.Web.Http]System.Web.Http.HttpConfiguration::get_Services()
0x18247  ldtoken  [System.Web.Http]System.Web.Http.Dispatcher.IHttpControllerActivator
0x1824c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18251  newobj   instance void Microsoft.Crm.Extensibility.OData.XrmControllerActivator::.ctor()
0x18256  callvirt instance void [System.Web.Http]System.Web.Http.Controllers.ServicesContainer::Replace(class [mscorlib]System.Type, object)
0x1825b  ldarg.0
0x1825c  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Net.Http]System.Net.Http.DelegatingHandler> [System.Web.Http]System.Web.Http.HttpConfiguration::get_MessageHandlers()
0x18261  newobj   instance void Microsoft.Crm.Extensibility.ODataV4.Throttling.ODataThrottlingConfigurationFactory::.ctor()
0x18266  newobj   instance void Microsoft.Crm.Extensibility.ODataV4.Throttling.ODataThrottlingHandler::.ctor(class Microsoft.Crm.Extensibility.ODataV4.Throttling.IThrottlingConfigurationFactory throttlingConfigurationFactory)
0x1826b  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Net.Http]System.Net.Http.DelegatingHandler>::Add(var<u1>)
0x18270  ldarg.0
0x18271  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Net.Http]System.Net.Http.DelegatingHandler> [System.Web.Http]System.Web.Http.HttpConfiguration::get_MessageHandlers()
0x18276  newobj   instance void Microsoft.Crm.Extensibility.ODataV4.CrmDelegatingHandler::.ctor()
0x1827b  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Net.Http]System.Net.Http.DelegatingHandler>::Add(var<u1>)
0x18280  ldarg.0
0x18281  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Net.Http]System.Net.Http.DelegatingHandler> [System.Web.Http]System.Web.Http.HttpConfiguration::get_MessageHandlers()
0x18286  newobj   instance void Microsoft.Crm.Extensibility.OData.CrmETagMessageHandler::.ctor()
0x1828b  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Net.Http]System.Net.Http.DelegatingHandler>::Add(var<u1>)
0x18290  ldarg.0
0x18291  call     void Microsoft.Crm.Extensibility.OData.CrmODataConfigurator::AddODataMediaTypeFormatters(class [System.Web.Http]System.Web.Http.HttpConfiguration config)
0x18296  ldstr    asc_383DE// "*"
0x1829b  ldstr    asc_383DE// "*"
0x182a0  ldstr    asc_383DE// "*"
0x182a5  ldstr    aPreferenceAppl// "Preference-Applied,OData-EntityId,Locat"...
0x182aa  newobj   instance void Microsoft.Crm.Extensibility.ODataV4.CrmCorsAppSettingsAttribute::.ctor(string origins, string headers, string methods, string exposedHeaders)
0x182af  stloc.2
0x182b0  ldarg.0
0x182b1  ldloc.2
0x182b2  call     void [System.Web.Http.Cors]System.Web.Http.CorsHttpConfigurationExtensions::EnableCors(class [System.Web.Http]System.Web.Http.HttpConfiguration, class [System.Web.Http.Cors]System.Web.Http.Cors.ICorsPolicyProvider)
0x182b7  ret
```
