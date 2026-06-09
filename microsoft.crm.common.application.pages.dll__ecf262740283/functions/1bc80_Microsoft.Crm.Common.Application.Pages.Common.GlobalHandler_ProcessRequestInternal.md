# Microsoft.Crm.Common.Application.Pages.Common.GlobalHandler::ProcessRequestInternal

- ea: `0x1bc80`
- end: `0x1bec7`
- name: `Microsoft.Crm.Common.Application.Pages.Common.GlobalHandler::ProcessRequestInternal`
- size: `583`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1bed0`
- `0x1bf30`

## string_xrefs

- `0x1bd1e`: `/_static/_common/scripts/ScriptClientApi.js`
- `0x1bcf8`: `if(navigator.userAgent.indexOf("Trident/7.0") > -1 && navigator.userAgent.indexOf("rv:11.0") > -1){Sys.Browser.name="Microsoft Internet Explorer";Sys.Browser.agent=Sys.Browser.InternetExplorer;Sys.Browser.version=11;Sys.Browser.documentMode=document.documentMode;Sys.Browser.hasDebuggerStatement=true}`
- `0x1bd54`: `/_static/_common/scripts/ClientAPICommonUtilities.js`

## pseudocode

```c

```

## disassembly

```asm
0x1bc80  ldarg.1
0x1bc81  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x1bc86  ldstr    aTextJavascript// "text/javascript"
0x1bc8b  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0x1bc90  ldarg.1
0x1bc91  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x1bc96  callvirt instance class [System.Web]System.Web.HttpCachePolicy [System.Web]System.Web.HttpResponse::get_Cache()
0x1bc9b  ldc.i4.4
0x1bc9c  callvirt instance void [System.Web]System.Web.HttpCachePolicy::SetCacheability(valuetype [System.Web]System.Web.HttpCacheability)
0x1bca1  ldarg.1
0x1bca2  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x1bca7  callvirt instance class [System.Web]System.Web.HttpCachePolicy [System.Web]System.Web.HttpResponse::get_Cache()
0x1bcac  callvirt instance class [System.Web]System.Web.HttpCacheVaryByParams [System.Web]System.Web.HttpCachePolicy::get_VaryByParams()
0x1bcb1  ldstr    aVer// "ver"
0x1bcb6  ldc.i4.1
0x1bcb7  callvirt instance void [System.Web]System.Web.HttpCacheVaryByParams::set_Item(string, bool)
0x1bcbc  ldarg.1
0x1bcbd  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x1bcc2  call     int32 [Microsoft.Crm]Microsoft.Crm.CachingTime::get_StaticFileExpiration()
0x1bcc7  callvirt instance void [System.Web]System.Web.HttpResponse::set_Expires(int32)
0x1bccc  ldarg.1
0x1bccd  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x1bcd2  callvirt instance class [System.Web]System.Web.HttpCachePolicy [System.Web]System.Web.HttpResponse::get_Cache()
0x1bcd7  ldstr    aAcceptEncoding// "Accept-Encoding"
0x1bcdc  callvirt instance void [System.Web]System.Web.HttpCachePolicy::SetVaryByCustom(string)
0x1bce1  ldarg.1
0x1bce2  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x1bce7  callvirt instance class [System.Web]System.Web.HttpCachePolicy [System.Web]System.Web.HttpResponse::get_Cache()
0x1bcec  ldc.i4.1
0x1bced  callvirt instance void [System.Web]System.Web.HttpCachePolicy::SetOmitVaryStar(bool)
0x1bcf2  ldarg.1
0x1bcf3  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x1bcf8  ldstr    aIfNavigatorUse// "if(navigator.userAgent.indexOf(\"Triden"...
0x1bcfd  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x1bd02  ldarg.1
0x1bd03  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x1bd08  call     string [mscorlib]System.Environment::get_NewLine()
0x1bd0d  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x1bd12  ldarg.1
0x1bd13  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x1bd18  ldarg.1
0x1bd19  callvirt instance class [System.Web]System.Web.HttpServerUtility [System.Web]System.Web.HttpContext::get_Server()
0x1bd1e  ldstr    aStaticCommonSc_6// "/_static/_common/scripts/ScriptClientAp"...
0x1bd23  callvirt instance string [System.Web]System.Web.HttpServerUtility::MapPath(string)
0x1bd28  callvirt instance void [System.Web]System.Web.HttpResponse::WriteFile(string)
0x1bd2d  ldarg.1
0x1bd2e  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x1bd33  callvirt instance void [System.Web]System.Web.HttpResponse::Flush()
0x1bd38  ldarg.1
0x1bd39  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x1bd3e  call     string [mscorlib]System.Environment::get_NewLine()
0x1bd43  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x1bd48  ldarg.1
0x1bd49  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x1bd4e  ldarg.1
0x1bd4f  callvirt instance class [System.Web]System.Web.HttpServerUtility [System.Web]System.Web.HttpContext::get_Server()
0x1bd54  ldstr    aStaticCommonSc_18// "/_static/_common/scripts/ClientAPICommo"...
0x1bd59  callvirt instance string [System.Web]System.Web.HttpServerUtility::MapPath(string)
0x1bd5e  callvirt instance void [System.Web]System.Web.HttpResponse::WriteFile(string)
0x1bd63  ldarg.1
0x1bd64  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x1bd69  callvirt instance void [System.Web]System.Web.HttpResponse::Flush()
0x1bd6e  ldarg.1
0x1bd6f  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x1bd74  call     string [mscorlib]System.Environment::get_NewLine()
0x1bd79  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x1bd7e  ldarg.1
0x1bd7f  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x1bd84  ldarg.1
0x1bd85  call     string Microsoft.Crm.Common.Application.Pages.Common.GlobalHandler::GetGlobalJsPath(class [System.Web]System.Web.HttpContext context)
0x1bd8a  callvirt instance void [System.Web]System.Web.HttpResponse::WriteFile(string)
0x1bd8f  ldarg.1
0x1bd90  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x1bd95  callvirt instance void [System.Web]System.Web.HttpResponse::Flush()
0x1bd9a  ldarg.1
0x1bd9b  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x1bda0  call     string [mscorlib]System.Environment::get_NewLine()
0x1bda5  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x1bdaa  ldarg.1
0x1bdab  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x1bdb0  ldstr    aXrmUtilitySeti// "Xrm.Utility.setInstance(new Mscrm.XrmUt"...
0x1bdb5  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x1bdba  ldarg.1
0x1bdbb  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x1bdc0  call     string [mscorlib]System.Environment::get_NewLine()
0x1bdc5  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x1bdca  ldarg.1
0x1bdcb  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x1bdd0  ldstr    aXrmPanelSetins// "Xrm.Panel.setInstance(new Mscrm.XrmPane"...
0x1bdd5  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x1bdda  ldarg.1
0x1bddb  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x1bde0  call     string [mscorlib]System.Environment::get_NewLine()
0x1bde5  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x1bdea  ldarg.1
0x1bdeb  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x1bdf0  ldstr    aXrmInternalSet// "Xrm.Internal.setInstance(new Mscrm.XrmI"...
0x1bdf5  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x1bdfa  ldarg.1
0x1bdfb  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x1be00  call     string [mscorlib]System.Environment::get_NewLine()
0x1be05  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x1be0a  ldarg.1
0x1be0b  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x1be10  ldstr    aXrmDialogSetin// "Xrm.Dialog.setInstance(new Mscrm.XrmDia"...
0x1be15  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x1be1a  ldarg.1
0x1be1b  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x1be20  call     string [mscorlib]System.Environment::get_NewLine()
0x1be25  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x1be2a  ldarg.1
0x1be2b  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x1be30  ldstr    aXrmNavigationS// "Xrm.Navigation.setInstance(new Mscrm.Na"...
0x1be35  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x1be3a  ldarg.1
0x1be3b  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x1be40  call     string [mscorlib]System.Environment::get_NewLine()
0x1be45  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x1be4a  ldarg.1
0x1be4b  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x1be50  ldstr    aXrmPageContext// "Xrm.Page.context = new Mscrm.GlobalCont"...
0x1be55  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x1be5a  ldarg.1
0x1be5b  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x1be60  call     string [mscorlib]System.Environment::get_NewLine()
0x1be65  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x1be6a  ldarg.1
0x1be6b  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x1be70  ldstr    aXrmuiManagerSe// "XrmUI.Manager.setInstance(new Mscrm.Xrm"...
0x1be75  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x1be7a  ldarg.1
0x1be7b  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x1be80  call     string [mscorlib]System.Environment::get_NewLine()
0x1be85  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x1be8a  ldarg.1
0x1be8b  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x1be90  ldstr    aXrmEncodingSet// "Xrm.Encoding.setInstance(new Mscrm.XrmE"...
0x1be95  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x1be9a  ldarg.1
0x1be9b  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x1bea0  call     string [mscorlib]System.Environment::get_NewLine()
0x1bea5  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x1beaa  ldarg.0
0x1beab  ldarg.1
0x1beac  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x1beb1  call     instance void Microsoft.Crm.Common.Application.Pages.Common.GlobalHandler::Write_Crm_8_0_CompatibilityWrappers(class [System.Web]System.Web.HttpResponse response)
0x1beb6  ldarg.1
0x1beb7  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x1bebc  ldstr    aWindowGlobalas// "window.globalAshxLoaded = true;"
0x1bec1  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x1bec6  ret
```
