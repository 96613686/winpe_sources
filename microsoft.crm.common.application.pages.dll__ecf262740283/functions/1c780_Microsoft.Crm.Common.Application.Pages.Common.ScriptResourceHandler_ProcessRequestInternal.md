# Microsoft.Crm.Common.Application.Pages.Common.ScriptResourceHandler::ProcessRequestInternal

- ea: `0x1c780`
- end: `0x1c870`
- name: `Microsoft.Crm.Common.Application.Pages.Common.ScriptResourceHandler::ProcessRequestInternal`
- size: `240`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1c6a0`
- `0x1c780`

## string_xrefs

- `0x1c82a`: `\nfunction LoadScriptResx(targetWindow) {\nvar commonResources = `
- `0x1c865`: `targetWindow.errorTable = errorTable;\nif (typeof Object.assign != 'function'){\n	for(var property in commonResources){\n		targetWindow[property] = commonResources[property];\n	}\n} else {\n	Object.assign(targetWindow, commonResources);\n}\n}\nLoadScriptResx(window);`

## pseudocode

```c

```

## disassembly

```asm
0x1c780  ldarg.1
0x1c781  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x1c786  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1c78b  ldstr    aLcid// "lcid"
0x1c790  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1c795  dup
0x1c796  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1c79b  brfalse.s loc_1C7A8
0x1c79d  ldstr    aMissingRequire// "Missing required query string parameter"...
0x1c7a2  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x1c7a7  throw
0x1c7a8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1c7ad  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x1c7b2  newobj   instance void [mscorlib]System.Globalization.CultureInfo::.ctor(int32)
0x1c7b7  stloc.0
0x1c7b8  ldarg.1
0x1c7b9  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x1c7be  stloc.1
0x1c7bf  ldloc.1
0x1c7c0  ldstr    aTextJavascript// "text/javascript"
0x1c7c5  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0x1c7ca  ldloc.1
0x1c7cb  callvirt instance class [System.Web]System.Web.HttpCachePolicy [System.Web]System.Web.HttpResponse::get_Cache()
0x1c7d0  ldc.i4.4
0x1c7d1  callvirt instance void [System.Web]System.Web.HttpCachePolicy::SetCacheability(valuetype [System.Web]System.Web.HttpCacheability)
0x1c7d6  ldloc.1
0x1c7d7  callvirt instance class [System.Web]System.Web.HttpCachePolicy [System.Web]System.Web.HttpResponse::get_Cache()
0x1c7dc  callvirt instance class [System.Web]System.Web.HttpCacheVaryByParams [System.Web]System.Web.HttpCachePolicy::get_VaryByParams()
0x1c7e1  ldstr    aLcid// "lcid"
0x1c7e6  ldc.i4.1
0x1c7e7  callvirt instance void [System.Web]System.Web.HttpCacheVaryByParams::set_Item(string, bool)
0x1c7ec  ldloc.1
0x1c7ed  callvirt instance class [System.Web]System.Web.HttpCachePolicy [System.Web]System.Web.HttpResponse::get_Cache()
0x1c7f2  callvirt instance class [System.Web]System.Web.HttpCacheVaryByParams [System.Web]System.Web.HttpCachePolicy::get_VaryByParams()
0x1c7f7  ldstr    aVer// "ver"
0x1c7fc  ldc.i4.1
0x1c7fd  callvirt instance void [System.Web]System.Web.HttpCacheVaryByParams::set_Item(string, bool)
0x1c802  ldloc.1
0x1c803  call     int32 [Microsoft.Crm]Microsoft.Crm.CachingTime::get_StaticFileExpiration()
0x1c808  callvirt instance void [System.Web]System.Web.HttpResponse::set_Expires(int32)
0x1c80d  ldloc.1
0x1c80e  callvirt instance class [System.Web]System.Web.HttpCachePolicy [System.Web]System.Web.HttpResponse::get_Cache()
0x1c813  ldstr    aAcceptEncoding// "Accept-Encoding"
0x1c818  callvirt instance void [System.Web]System.Web.HttpCachePolicy::SetVaryByCustom(string)
0x1c81d  ldloc.1
0x1c81e  callvirt instance class [System.Web]System.Web.HttpCachePolicy [System.Web]System.Web.HttpResponse::get_Cache()
0x1c823  ldc.i4.1
0x1c824  callvirt instance void [System.Web]System.Web.HttpCachePolicy::SetOmitVaryStar(bool)
0x1c829  ldloc.1
0x1c82a  ldstr    aFunctionLoadsc// "\r\nfunction LoadScriptResx(targetWindo"...
0x1c82f  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x1c834  ldarg.0
0x1c835  ldloc.1
0x1c836  ldloc.0
0x1c837  call     class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ScriptResource::get_ScriptResources()
0x1c83c  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ScriptResourceHandler::WriteResourcesJson(class [System.Web]System.Web.HttpResponse response, class [mscorlib]System.Globalization.CultureInfo culture, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> resources)
0x1c841  ldloc.1
0x1c842  ldstr    aVarErrortable// ";\nvar errorTable = "
0x1c847  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x1c84c  ldarg.0
0x1c84d  ldloc.1
0x1c84e  ldloc.0
0x1c84f  call     class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ScriptResource::get_ErrorResources()
0x1c854  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ScriptResourceHandler::WriteResourcesJson(class [System.Web]System.Web.HttpResponse response, class [mscorlib]System.Globalization.CultureInfo culture, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> resources)
0x1c859  ldloc.1
0x1c85a  ldstr    asc_212FE// ";"
0x1c85f  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x1c864  ldloc.1
0x1c865  ldstr    aTargetwindowEr// "targetWindow.errorTable = errorTable;\r"...
0x1c86a  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x1c86f  ret
```
