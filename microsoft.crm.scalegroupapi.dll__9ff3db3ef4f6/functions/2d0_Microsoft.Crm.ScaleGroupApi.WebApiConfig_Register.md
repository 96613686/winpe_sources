# Microsoft.Crm.ScaleGroupApi.WebApiConfig::Register

- ea: `0x2d0`
- end: `0x3d2`
- name: `Microsoft.Crm.ScaleGroupApi.WebApiConfig::Register`
- size: `258`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0xa10`

## callees

- `0x10`
- `0xe50`
- `0x2100`
- `0x23a0`

## string_xrefs

- `0x347`: `DefaultApiOrgScopeNoId`
- `0x38b`: `application/xml`

## pseudocode

```c

```

## disassembly

```asm
0x2d0  ldarg.0
0x2d1  callvirt instance class [System.Web.Http]System.Web.Http.HttpRouteCollection [System.Web.Http]System.Web.Http.HttpConfiguration::get_Routes()
0x2d6  ldstr    aDefaultapi// "DefaultApi"
0x2db  ldstr    aControllerIdDe// "{controller}/{id}/default.aspx"
0x2e0  newobj   instance void <>f__AnonymousType0::.ctor()
0x2e5  call     class [System.Web.Http]System.Web.Http.Routing.IHttpRoute [System.Web.Http]System.Web.Http.HttpRouteCollectionExtensions::MapHttpRoute(class [System.Web.Http]System.Web.Http.HttpRouteCollection, string, string, object)
0x2ea  pop
0x2eb  ldarg.0
0x2ec  callvirt instance class [System.Web.Http]System.Web.Http.HttpRouteCollection [System.Web.Http]System.Web.Http.HttpConfiguration::get_Routes()
0x2f1  ldstr    aDefaultapinoid// "DefaultApiNoId"
0x2f6  ldstr    aControllerDefa// "{controller}/default.aspx"
0x2fb  newobj   instance void <>f__AnonymousType0::.ctor()
0x300  call     class [System.Web.Http]System.Web.Http.Routing.IHttpRoute [System.Web.Http]System.Web.Http.HttpRouteCollectionExtensions::MapHttpRoute(class [System.Web.Http]System.Web.Http.HttpRouteCollection, string, string, object)
0x305  pop
0x306  ldarg.0
0x307  callvirt instance class [System.Web.Http]System.Web.Http.HttpRouteCollection [System.Web.Http]System.Web.Http.HttpConfiguration::get_Routes()
0x30c  ldstr    aDefaultapiorgs// "DefaultApiOrgScope"
0x311  ldstr    aOrganizationOr// "Organization/{organizationId}/{controll"...
0x316  newobj   instance void <>f__AnonymousType0::.ctor()
0x31b  call     class [System.Web.Http]System.Web.Http.Routing.IHttpRoute [System.Web.Http]System.Web.Http.HttpRouteCollectionExtensions::MapHttpRoute(class [System.Web.Http]System.Web.Http.HttpRouteCollection, string, string, object)
0x320  pop
0x321  ldarg.0
0x322  callvirt instance class [System.Web.Http]System.Web.Http.HttpRouteCollection [System.Web.Http]System.Web.Http.HttpConfiguration::get_Routes()
0x327  ldstr    aDefaultapisolu// "DefaultApiSolutionGet"
0x32c  ldstr    aOrganizationOr_0// "Organization/{organizationId}/Solution/"...
0x331  ldstr    aSolution// "Solution"
0x336  newobj   instance void class <>f__AnonymousType1`1<string>::.ctor(var<u1>)
0x33b  call     class [System.Web.Http]System.Web.Http.Routing.IHttpRoute [System.Web.Http]System.Web.Http.HttpRouteCollectionExtensions::MapHttpRoute(class [System.Web.Http]System.Web.Http.HttpRouteCollection, string, string, object)
0x340  pop
0x341  ldarg.0
0x342  callvirt instance class [System.Web.Http]System.Web.Http.HttpRouteCollection [System.Web.Http]System.Web.Http.HttpConfiguration::get_Routes()
0x347  ldstr    aDefaultapiorgs_0// "DefaultApiOrgScopeNoId"
0x34c  ldstr    aOrganizationOr_1// "Organization/{organizationId}/{controll"...
0x351  newobj   instance void <>f__AnonymousType0::.ctor()
0x356  call     class [System.Web.Http]System.Web.Http.Routing.IHttpRoute [System.Web.Http]System.Web.Http.HttpRouteCollectionExtensions::MapHttpRoute(class [System.Web.Http]System.Web.Http.HttpRouteCollection, string, string, object)
0x35b  pop
0x35c  ldarg.0
0x35d  callvirt instance class [System.Net.Http.Formatting]System.Net.Http.Formatting.MediaTypeFormatterCollection [System.Web.Http]System.Web.Http.HttpConfiguration::get_Formatters()
0x362  callvirt instance class [System.Net.Http.Formatting]System.Net.Http.Formatting.JsonMediaTypeFormatter [System.Net.Http.Formatting]System.Net.Http.Formatting.MediaTypeFormatterCollection::get_JsonFormatter()
0x367  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue> [System.Net.Http.Formatting]System.Net.Http.Formatting.MediaTypeFormatter::get_SupportedMediaTypes()
0x36c  ldstr    aTextHtml// "text/html"
0x371  newobj   instance void [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue::.ctor(string)
0x376  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue>::Add(var<u1>)
0x37b  ldarg.0
0x37c  callvirt instance class [System.Net.Http.Formatting]System.Net.Http.Formatting.MediaTypeFormatterCollection [System.Web.Http]System.Web.Http.HttpConfiguration::get_Formatters()
0x381  callvirt instance class [System.Net.Http.Formatting]System.Net.Http.Formatting.JsonMediaTypeFormatter [System.Net.Http.Formatting]System.Net.Http.Formatting.MediaTypeFormatterCollection::get_JsonFormatter()
0x386  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue> [System.Net.Http.Formatting]System.Net.Http.Formatting.MediaTypeFormatter::get_SupportedMediaTypes()
0x38b  ldstr    aApplicationXml// "application/xml"
0x390  newobj   instance void [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue::.ctor(string)
0x395  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue>::Add(var<u1>)
0x39a  ldarg.0
0x39b  callvirt instance class [System.Web.Http]System.Web.Http.Filters.HttpFilterCollection [System.Web.Http]System.Web.Http.HttpConfiguration::get_Filters()
0x3a0  newobj   instance void Microsoft.Crm.ScaleGroupApi.AzureAdWebApiAuthorizeAttribute::.ctor()
0x3a5  callvirt instance void [System.Web.Http]System.Web.Http.Filters.HttpFilterCollection::Add(class [System.Web.Http]System.Web.Http.Filters.IFilter)
0x3aa  ldarg.0
0x3ab  callvirt instance class [System.Web.Http]System.Web.Http.Filters.HttpFilterCollection [System.Web.Http]System.Web.Http.HttpConfiguration::get_Filters()
0x3b0  newobj   instance void Microsoft.Crm.ScaleGroupApi.Filters.ScaleGroupApiAuditFilterAttribute::.ctor()
0x3b5  callvirt instance void [System.Web.Http]System.Web.Http.Filters.HttpFilterCollection::Add(class [System.Web.Http]System.Web.Http.Filters.IFilter)
0x3ba  ldarg.0
0x3bb  callvirt instance class [System.Web.Http]System.Web.Http.Filters.HttpFilterCollection [System.Web.Http]System.Web.Http.HttpConfiguration::get_Filters()
0x3c0  newobj   instance void Microsoft.Crm.ScaleGroupApi.Filters.ScaleGroupApiExceptionFilterAttribute::.ctor()
0x3c5  callvirt instance void [System.Web.Http]System.Web.Http.Filters.HttpFilterCollection::Add(class [System.Web.Http]System.Web.Http.Filters.IFilter)
0x3ca  ldarg.0
0x3cb  ldc.i4.2
0x3cc  callvirt instance void [System.Web.Http]System.Web.Http.HttpConfiguration::set_IncludeErrorDetailPolicy(valuetype [System.Web.Http]System.Web.Http.IncludeErrorDetailPolicy)
0x3d1  ret
```
