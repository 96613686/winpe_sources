# Microsoft.Crm.Extensibility.ODataV4.Routing.CrmODataRoutingConvention::SelectActionImplementation

- ea: `0x2d8c0`
- end: `0x2d9fc`
- name: `Microsoft.Crm.Extensibility.ODataV4.Routing.CrmODataRoutingConvention::SelectActionImplementation`
- size: `316`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x350b0`

## callees

- `0xc850`
- `0x2c550`
- `0x2d8c0`
- `0x2df60`
- `0x2e160`

## string_xrefs

- `0x2d905`: `odataPath`
- `0x2d990`: `Http Method '{0}' is not valid for path '{1}' with path template {2}`

## pseudocode

```c

```

## disassembly

```asm
0x2d8c0  ldarg.1
0x2d8c1  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment> [System.Web.OData]System.Web.OData.Routing.ODataPath::get_Segments()
0x2d8c6  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment>::get_Count()
0x2d8cb  ldc.i4.0
0x2d8cc  ble.s    loc_2D8E0
0x2d8ce  ldarg.1
0x2d8cf  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment> [System.Web.OData]System.Web.OData.Routing.ODataPath::get_Segments()
0x2d8d4  call     T0x2B0000EA
0x2d8d9  isinst   Microsoft.Crm.Extensibility.ODataV4.Routing.CrmODataUnresolvedPathSegment
0x2d8de  brtrue.s loc_2D8F7
0x2d8e0  ldarg.2
0x2d8e1  callvirt instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.Controllers.HttpControllerContext::get_Request()
0x2d8e6  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Properties()
0x2d8eb  ldstr    aRoutingexcepti// "RoutingException"
0x2d8f0  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::ContainsKey(var<u1>)
0x2d8f5  brfalse.s loc_2D8FD
0x2d8f7  ldstr    aErrorhandlerac// "ErrorHandlerAction"
0x2d8fc  ret
0x2d8fd  ldarg.1
0x2d8fe  brtrue.s loc_2D915
0x2d900  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Extensibility.ODataV4.Routing.CrmODataRoutingConvention::Logger
0x2d905  ldstr    aOdatapath_0// "odataPath"
0x2d90a  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x2d90f  call     class [mscorlib]System.Exception Microsoft.Crm.Extensibility.OdataTelemetryUtil::EnsureTrace(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger logger, class [mscorlib]System.Exception exception)
0x2d914  throw
0x2d915  ldarg.1
0x2d916  callvirt instance string [System.Web.OData]System.Web.OData.Routing.ODataPath::get_PathTemplate()
0x2d91b  ldstr    aUnresolved// "unresolved"
0x2d920  callvirt instance bool [mscorlib]System.String::Contains(string)
0x2d925  brfalse.s loc_2D947
0x2d927  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Extensibility.ODataV4.Routing.CrmODataRoutingConvention::Logger
0x2d92c  ldc.i4   0x190
0x2d931  ldstr    aRequestMessage// "Request message has unresolved paramete"...
0x2d936  ldc.i4.0
0x2d937  newarr   [mscorlib]System.Object
0x2d93c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException::.ctor(valuetype [System]System.Net.HttpStatusCode, string, object[])
0x2d941  call     class [mscorlib]System.Exception Microsoft.Crm.Extensibility.OdataTelemetryUtil::EnsureTrace(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger logger, class [mscorlib]System.Exception exception)
0x2d946  throw
0x2d947  ldarg.2
0x2d948  brtrue.s loc_2D95F
0x2d94a  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Extensibility.ODataV4.Routing.CrmODataRoutingConvention::Logger
0x2d94f  ldstr    aControllercont// "controllerContext"
0x2d954  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x2d959  call     class [mscorlib]System.Exception Microsoft.Crm.Extensibility.OdataTelemetryUtil::EnsureTrace(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger logger, class [mscorlib]System.Exception exception)
0x2d95e  throw
0x2d95f  ldarg.3
0x2d960  brtrue.s loc_2D977
0x2d962  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Extensibility.ODataV4.Routing.CrmODataRoutingConvention::Logger
0x2d967  ldstr    aActionmap// "actionMap"
0x2d96c  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x2d971  call     class [mscorlib]System.Exception Microsoft.Crm.Extensibility.OdataTelemetryUtil::EnsureTrace(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger logger, class [mscorlib]System.Exception exception)
0x2d976  throw
0x2d977  ldarg.0
0x2d978  ldarg.1
0x2d979  ldarg.2
0x2d97a  callvirt instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.Controllers.HttpControllerContext::get_Request()
0x2d97f  callvirt instance class [System.Net.Http]System.Net.Http.HttpMethod [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Method()
0x2d984  call     instance bool Microsoft.Crm.Extensibility.ODataV4.Routing.CrmODataRoutingConvention::IsValidHttpMethodForPath(class [System.Web.OData]System.Web.OData.Routing.ODataPath odataPath, class [System.Net.Http]System.Net.Http.HttpMethod httpMethod)
0x2d989  brtrue.s loc_2D9CA
0x2d98b  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Extensibility.ODataV4.Routing.CrmODataRoutingConvention::Logger
0x2d990  ldstr    aHttpMethod0IsN// "Http Method '{0}' is not valid for path"...
0x2d995  ldc.i4.3
0x2d996  newarr   [mscorlib]System.Object
0x2d99b  dup
0x2d99c  ldc.i4.0
0x2d99d  ldarg.2
0x2d99e  brtrue.s loc_2D9A3
0x2d9a0  ldnull
0x2d9a1  br.s     loc_2D9B5
0x2d9a3  ldarg.2
0x2d9a4  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.Controllers.HttpControllerContext::get_Request()
0x2d9a9  dup
0x2d9aa  brtrue.s loc_2D9B0
0x2d9ac  pop
0x2d9ad  ldnull
0x2d9ae  br.s     loc_2D9B5
0x2d9b0  call     instance class [System.Net.Http]System.Net.Http.HttpMethod [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Method()
0x2d9b5  stelem.ref
0x2d9b6  dup
0x2d9b7  ldc.i4.1
0x2d9b8  ldarg.1
0x2d9b9  stelem.ref
0x2d9ba  dup
0x2d9bb  ldc.i4.2
0x2d9bc  ldarg.1
0x2d9bd  callvirt instance string [System.Web.OData]System.Web.OData.Routing.ODataPath::get_PathTemplate()
0x2d9c2  stelem.ref
0x2d9c3  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogWarning(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x2d9c8  ldnull
0x2d9c9  ret
0x2d9ca  ldarg.0
0x2d9cb  ldarg.1
0x2d9cc  callvirt instance string [System.Web.OData]System.Web.OData.Routing.ODataPath::get_PathTemplate()
0x2d9d1  ldarg.2
0x2d9d2  callvirt instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.Controllers.HttpControllerContext::get_Request()
0x2d9d7  callvirt instance class [System.Net.Http]System.Net.Http.HttpMethod [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Method()
0x2d9dc  ldarg.3
0x2d9dd  call     instance string Microsoft.Crm.Extensibility.ODataV4.Routing.CrmODataRoutingConvention::SelectActionInternal(string pathTemplate, class [System.Net.Http]System.Net.Http.HttpMethod httpMethod, class [System.Core]System.Linq.ILookup`2<string, class [System.Web.Http]System.Web.Http.Controllers.HttpActionDescriptor> actionMap)
0x2d9e2  stloc.0
0x2d9e3  ldloc.0
0x2d9e4  brfalse.s loc_2D9FA
0x2d9e6  ldarg.1
0x2d9e7  ldarg.2
0x2d9e8  ldarg.2
0x2d9e9  callvirt instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.Controllers.HttpControllerContext::get_Request()
0x2d9ee  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel [System.Web.OData]System.Web.OData.Extensions.HttpRequestMessageExtensions::GetModel(class [System.Net.Http]System.Net.Http.HttpRequestMessage)
0x2d9f3  call     void Microsoft.Crm.Extensibility.ODataV4.Routing.CrmODataRouteDataProvider::ProvideRouteData(class [System.Web.OData]System.Web.OData.Routing.ODataPath path, class [System.Web.Http]System.Web.Http.Controllers.HttpControllerContext controllerContext, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x2d9f8  ldloc.0
0x2d9f9  ret
0x2d9fa  ldnull
0x2d9fb  ret
```
