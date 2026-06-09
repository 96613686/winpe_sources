# Microsoft.Crm.Web.MainPage::SetContentUrl

- ea: `0x25550`
- end: `0x265d0`
- name: `Microsoft.Crm.Web.MainPage::SetContentUrl`
- size: `4224`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x26b50`

## callees

- `0x8500`
- `0x85f0`
- `0x8660`
- `0x254c0`
- `0x25550`
- `0x265d0`
- `0x269c0`
- `0x10a280`
- `0x10a590`

## string_xrefs

- `0x2658c`: `Sys.Application.findComponent('crmPageManager').applicationLoadHandler();`
- `0x25860`: `taskBasedForm`
- `0x25fd7`: `SERVICECALENDAR`
- `0x26019`: `YAMMERCONFIG`
- `0x263e6`: `sitemappath`

## pseudocode

```c

```

## disassembly

```asm
0x25550  newobj   instance void <>c__DisplayClass32_0::.ctor()
0x25555  stloc.0
0x25556  ldsfld   string [mscorlib]System.String::Empty
0x2555b  stloc.1
0x2555c  ldsfld   string [mscorlib]System.String::Empty
0x25561  stloc.2
0x25562  ldsfld   string [mscorlib]System.String::Empty
0x25567  pop
0x25568  ldnull
0x25569  stloc.3
0x2556a  ldnull
0x2556b  stloc.s  4
0x2556d  ldnull
0x2556e  stloc.s  5
0x25570  ldarg.0
0x25571  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x25576  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x2557b  ldstr    aPagetype_0// "pageType"
0x25580  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x25585  stloc.s  6
0x25587  ldc.i4.0
0x25588  stloc.s  7
0x2558a  ldloc.0
0x2558b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x25590  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_CurrentAppId()
0x25595  stfld    valuetype [mscorlib]System.Guid <>c__DisplayClass32_0::appIdGuid
0x2559a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2559f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x255a4  stloc.s  8
0x255a6  ldloc.0
0x255a7  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass32_0::appIdGuid
0x255ac  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x255b1  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x255b6  brfalse  loc_2575E
0x255bb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x255c0  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AppModuleCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AppDataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x255c5  stloc.s  0xC
0x255c7  ldloc.s  0xC
0x255c9  brfalse.s loc_255EC
0x255cb  ldloc.s  0xC
0x255cd  ldloc.0
0x255ce  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass32_0::appIdGuid
0x255d3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x255d8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AppModuleMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AppModuleCache::LookupEntry(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x255dd  stloc.s  0xE
0x255df  ldloc.s  0xE
0x255e1  brfalse.s loc_255EC
0x255e3  ldloc.s  0xE
0x255e5  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AppModuleClientType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AppModuleMetadata::get_ClientType()
0x255ea  stloc.s  7
0x255ec  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x255f1  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x255f6  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x255fb  ldstr    aAppid// "appid"
0x25600  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x25605  brfalse.s loc_2562B
0x25607  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleTelemetryEvents [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleTelemetryEvents::get_Instance()
0x2560c  ldloc.s  8
0x2560e  ldloc.0
0x2560f  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass32_0::appIdGuid
0x25614  ldloc.s  7
0x25616  ldstr    aAppclicknondef// "AppClickNonDefault"
0x2561b  ldc.i4.0
0x2561c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x25621  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_UserId()
0x25626  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleTelemetryEvents::AppModuleClick(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, int32, string, bool, valuetype [mscorlib]System.Guid)
0x2562b  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x25630  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x25635  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_UrlReferrer()
0x2563a  ldnull
0x2563b  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x25640  brfalse.s loc_256BC
0x25642  ldc.i4.0
0x25643  stloc.s  0xF
0x25645  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x2564a  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x2564f  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_UrlReferrer()
0x25654  callvirt instance string[] [System]System.Uri::get_Segments()
0x25659  stloc.s  0x10
0x2565b  ldc.i4.0
0x2565c  stloc.s  0x11
0x2565e  br.s     loc_2568C
0x25660  ldloc.s  0x10
0x25662  ldloc.s  0x11
0x25664  ldelem.ref
0x25665  stloc.s  0x12
0x25667  ldloc.s  0x12
0x25669  ldstr    aApplandingtile// "applandingtilepage.aspx"
0x2566e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x25673  brtrue.s loc_25683
0x25675  ldloc.s  0x12
0x25677  ldstr    aMsdynAppmanage// "msdyn_appmanagementcontrol"
0x2567c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x25681  brfalse.s loc_25686
0x25683  ldc.i4.1
0x25684  stloc.s  0xF
0x25686  ldloc.s  0x11
0x25688  ldc.i4.1
0x25689  add
0x2568a  stloc.s  0x11
0x2568c  ldloc.s  0x11
0x2568e  ldloc.s  0x10
0x25690  ldlen
0x25691  conv.i4
0x25692  blt.s    loc_25660
0x25694  ldloc.s  0xF
0x25696  brfalse.s loc_256BC
0x25698  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleTelemetryEvents [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleTelemetryEvents::get_Instance()
0x2569d  ldloc.s  8
0x2569f  ldloc.0
0x256a0  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass32_0::appIdGuid
0x256a5  ldloc.s  7
0x256a7  ldstr    aAppclicklandin// "AppClickLandingPage"
0x256ac  ldc.i4.0
0x256ad  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x256b2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_UserId()
0x256b7  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleTelemetryEvents::AppModuleClick(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, int32, string, bool, valuetype [mscorlib]System.Guid)
0x256bc  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache::Instance()
0x256c1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x256c6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_UserId()
0x256cb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x256d0  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser>::LookupEntry(void, var<u1>)
0x256d5  stloc.s  0xD
0x256d7  ldloc.s  0xD
0x256d9  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_IsAdministrator()
0x256de  brtrue.s loc_256F2
0x256e0  ldloc.s  0xD
0x256e2  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_IsCustomizer()
0x256e7  brtrue.s loc_256F2
0x256e9  ldloc.s  0xD
0x256eb  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_IsSystemUser()
0x256f0  br.s     loc_256F3
0x256f2  ldc.i4.1
0x256f3  brtrue   loc_25782
0x256f8  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_ReadAppModule()
0x256fd  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x25702  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x25707  brfalse.s loc_25723
0x25709  ldloc.s  0xD
0x2570b  callvirt instance valuetype [mscorlib]System.Guid[] [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_AppModules()
0x25710  ldloc.0
0x25711  ldftn    instance bool <>c__DisplayClass32_0::<SetContentUrl>b__0(valuetype [mscorlib]System.Guid s)
0x25717  newobj   instance void class [mscorlib]System.Predicate`1<valuetype [mscorlib]System.Guid>::.ctor(object, native int)
0x2571c  call     T0x2B000008
0x25721  brtrue.s loc_25782
0x25723  ldarg.0
0x25724  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x25729  ldarg.0
0x2572a  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x2572f  call     bool Microsoft.Crm.Common.Web.RedirectUtility::RedirectToLandingPage(class [System.Web]System.Web.HttpRequest request, class [System.Web]System.Web.HttpResponse response)
0x25734  brfalse.s loc_2574D
0x25736  ldarg.0
0x25737  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x2573c  callvirt instance void [System.Web]System.Web.HttpResponse::Flush()
0x25741  ldarg.0
0x25742  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x25747  callvirt instance void [System.Web]System.Web.HttpResponse::End()
0x2574c  ret
0x2574d  ldc.i4   0x80050116
0x25752  ldc.i4.0
0x25753  newarr   [mscorlib]System.Object
0x25758  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x2575d  throw
0x2575e  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleTelemetryEvents [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleTelemetryEvents::get_Instance()
0x25763  ldloc.s  8
0x25765  ldloc.0
0x25766  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass32_0::appIdGuid
0x2576b  ldloc.s  7
0x2576d  ldstr    aAppclickdefaul// "AppClickDefault"
0x25772  ldc.i4.1
0x25773  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x25778  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_UserId()
0x2577d  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleTelemetryEvents::AppModuleClick(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, int32, string, bool, valuetype [mscorlib]System.Guid)
0x25782  ldloc.0
0x25783  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass32_0::appIdGuid
0x25788  ldarg.0
0x25789  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x2578e  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x25793  ldloc.s  7
0x25795  call     bool Microsoft.Crm.Common.Web.RedirectUtility::ShouldRenderUnifiedClient(valuetype [mscorlib]System.Guid appIdGuid, class [System]System.Collections.Specialized.NameValueCollection queryString, int32 clientType)
0x2579a  brfalse.s loc_257C6
0x2579c  ldarg.0
0x2579d  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x257a2  ldarg.0
0x257a3  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x257a8  call     bool Microsoft.Crm.Common.Web.RedirectUtility::RedirectToUnifiedClient(class [System.Web]System.Web.HttpRequest request, class [System.Web]System.Web.HttpResponse response)
0x257ad  brfalse.s loc_257C6
0x257af  ldarg.0
0x257b0  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x257b5  callvirt instance void [System.Web]System.Web.HttpResponse::Flush()
0x257ba  ldarg.0
0x257bb  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x257c0  callvirt instance void [System.Web]System.Web.HttpResponse::End()
0x257c5  ret
0x257c6  ldloc.s  6
0x257c8  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x257cd  brtrue   loc_25897
0x257d2  ldarg.0
0x257d3  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x257d8  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x257dd  ldstr    aExtraqs// "extraqs"
0x257e2  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x257e7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x257ec  brtrue   loc_25897
0x257f1  ldarg.0
0x257f2  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x257f7  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x257fc  ldstr    aExtraqs// "extraqs"
0x25801  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x25806  stloc.s  0x13
0x25808  ldloc.s  0x13
0x2580a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2580f  brtrue   loc_25897
0x25814  ldloc.s  0x13
0x25816  ldc.i4.0
0x25817  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x2581c  ldc.i4.s 0x3F
0x2581e  beq.s    loc_2582E
0x25820  ldstr    asc_1357B8// "?"
0x25825  ldloc.s  0x13
0x25827  call     string [mscorlib]System.String::Concat(string, string)
0x2582c  stloc.s  0x13
0x2582e  ldloc.s  0x13
0x25830  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x25835  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2583a  stloc.s  0x14
0x2583c  ldloc.s  0x14
0x2583e  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x25843  ldstr    aFormtype// "formtype"
0x25848  callvirt instance bool class [System]System.Collections.Generic.SortedDictionary`2<string, string>::ContainsKey(var<u1>)
0x2584d  brfalse.s loc_25897
0x2584f  ldloc.s  0x14
0x25851  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x25856  ldstr    aFormtype// "formtype"
0x2585b  callvirt instance var<u1> class [System]System.Collections.Generic.SortedDictionary`2<string, string>::get_Item(void)
0x25860  ldstr    aTaskbasedform// "taskBasedForm"
0x25865  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2586a  brfalse.s loc_25897
0x2586c  ldloc.s  0x14
0x2586e  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x25873  ldstr    aFormid_0// "formId"
0x25878  callvirt instance bool class [System]System.Collections.Generic.SortedDictionary`2<string, string>::ContainsKey(var<u1>)
0x2587d  brfalse.s loc_25897
0x2587f  ldarg.0
0x25880  ldloc.s  0x14
0x25882  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x25887  ldstr    aFormid_0// "formId"
0x2588c  callvirt instance var<u1> class [System]System.Collections.Generic.SortedDictionary`2<string, string>::get_Item(void)
0x25891  call     instance void Microsoft.Crm.Web.MainPage::RedirectToBpfConfigurator(string formId)
0x25896  ret
0x25897  ldsfld   string [mscorlib]System.String::Empty
0x2589c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x258a1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x258a6  stloc.s  9
0x258a8  ldarg.0
0x258a9  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x258ae  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x258b3  ldstr    aPage// "page"
0x258b8  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x258bd  stloc.2
0x258be  ldarg.0
0x258bf  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x258c4  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x258c9  ldstr    aArea// "area"
0x258ce  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x258d3  stloc.1
0x258d4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Caching.UserSiteMapCache [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Caching.UserSiteMapCache::Instance()
0x258d9  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x258de  ldstr    asc_11EF2A// ""
0x258e3  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMap [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Caching.UserSiteMapCache::LookupEntry(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser, string)
0x258e8  stloc.s  0xA
0x258ea  ldarg.0
0x258eb  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x258f0  ldstr    aBinvalidsitema// "_bInvalidSitemap"
0x258f5  ldloc.s  0xA
0x258f7  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMap::get_IsFromReferenceXml()
0x258fc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x25901  ldarg.0
0x25902  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x25907  ldstr    aBinvalidsitema_0// "_bInvalidSitemapErrorCode"
0x2590c  ldloc.s  0xA
0x2590e  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMap::get_IsAppAware()
0x25913  brtrue.s loc_2591C
0x25915  ldstr    a0x8063110e// "0x8063110e"
0x2591a  br.s     loc_25921
0x2591c  ldstr    a0x80050110// "0x80050110"
0x25921  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x25926  ldc.i4.0
0x25927  stloc.s  0xB
0x25929  ldloc.1
0x2592a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2592f  brtrue.s loc_25939
0x25931  ldloc.2
0x25932  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x25937  brfalse.s loc_2595D
0x25939  ldloc.s  0xA
0x2593b  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x25940  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapSubArea [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMap::GetDefaultUserSubArea(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser)
0x25945  dup
0x25946  stloc.s  4
  ... truncated ...
```
