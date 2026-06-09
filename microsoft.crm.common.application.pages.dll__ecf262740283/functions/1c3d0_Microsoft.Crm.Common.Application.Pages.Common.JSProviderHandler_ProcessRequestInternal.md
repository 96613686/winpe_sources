# Microsoft.Crm.Common.Application.Pages.Common.JSProviderHandler::ProcessRequestInternal

- ea: `0x1c3d0`
- end: `0x1c610`
- name: `Microsoft.Crm.Common.Application.Pages.Common.JSProviderHandler::ProcessRequestInternal`
- size: `576`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1c3d0`
- `0x1c610`
- `0x1d970`
- `0x1da30`
- `0x1dac0`

## pseudocode

```c

```

## disassembly

```asm
0x1c3d0  ldarg.1
0x1c3d1  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x1c3d6  ldstr    aTextJavascript// "text/javascript"
0x1c3db  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0x1c3e0  ldarg.1
0x1c3e1  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x1c3e6  callvirt instance class [System.Web]System.Web.HttpCachePolicy [System.Web]System.Web.HttpResponse::get_Cache()
0x1c3eb  ldc.i4.4
0x1c3ec  callvirt instance void [System.Web]System.Web.HttpCachePolicy::SetCacheability(valuetype [System.Web]System.Web.HttpCacheability)
0x1c3f1  ldarg.1
0x1c3f2  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x1c3f7  callvirt instance class [System.Web]System.Web.HttpCachePolicy [System.Web]System.Web.HttpResponse::get_Cache()
0x1c3fc  callvirt instance class [System.Web]System.Web.HttpCacheVaryByParams [System.Web]System.Web.HttpCachePolicy::get_VaryByParams()
0x1c401  ldstr    aVer// "ver"
0x1c406  ldc.i4.1
0x1c407  callvirt instance void [System.Web]System.Web.HttpCacheVaryByParams::set_Item(string, bool)
0x1c40c  ldarg.1
0x1c40d  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x1c412  callvirt instance class [System.Web]System.Web.HttpCachePolicy [System.Web]System.Web.HttpResponse::get_Cache()
0x1c417  callvirt instance class [System.Web]System.Web.HttpCacheVaryByParams [System.Web]System.Web.HttpCachePolicy::get_VaryByParams()
0x1c41c  ldstr    aIds// "ids"
0x1c421  ldc.i4.1
0x1c422  callvirt instance void [System.Web]System.Web.HttpCacheVaryByParams::set_Item(string, bool)
0x1c427  ldarg.1
0x1c428  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x1c42d  call     int32 [Microsoft.Crm]Microsoft.Crm.CachingTime::get_StaticFileExpiration()
0x1c432  callvirt instance void [System.Web]System.Web.HttpResponse::set_Expires(int32)
0x1c437  ldarg.1
0x1c438  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x1c43d  callvirt instance class [System.Web]System.Web.HttpCachePolicy [System.Web]System.Web.HttpResponse::get_Cache()
0x1c442  ldstr    aAcceptEncoding// "Accept-Encoding"
0x1c447  callvirt instance void [System.Web]System.Web.HttpCachePolicy::SetVaryByCustom(string)
0x1c44c  ldarg.1
0x1c44d  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x1c452  callvirt instance class [System.Web]System.Web.HttpCachePolicy [System.Web]System.Web.HttpResponse::get_Cache()
0x1c457  ldc.i4.1
0x1c458  callvirt instance void [System.Web]System.Web.HttpCachePolicy::SetOmitVaryStar(bool)
0x1c45d  ldarg.0
0x1c45e  ldarg.1
0x1c45f  call     instance class [mscorlib]System.Collections.Generic.List`1<int32> Microsoft.Crm.Common.Application.Pages.Common.JSProviderHandler::GetRequestedIds(class [System.Web]System.Web.HttpContext context)
0x1c464  stloc.0
0x1c465  ldloc.0
0x1c466  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<int32>::get_Count()
0x1c46b  brtrue   loc_1C4F5
0x1c470  call     class Microsoft.Crm.Common.Application.Pages.Common.JsProvider.JsFileManager Microsoft.Crm.Common.Application.Pages.Common.JsProvider.JsFileManager::get_Instance()
0x1c475  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Bundling.JsFile> Microsoft.Crm.Common.Application.Pages.Common.JsProvider.JsFileManager::get_AllJsFiles()
0x1c47a  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Bundling.JsFile>::GetEnumerator()
0x1c47f  stloc.2
0x1c480  br.s     loc_1C4E0
0x1c482  ldloc.2
0x1c483  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Bundling.JsFile>::get_Current()
0x1c488  stloc.3
0x1c489  ldarg.1
0x1c48a  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x1c48f  ldc.i4.5
0x1c490  newarr   [mscorlib]System.String
0x1c495  dup
0x1c496  ldc.i4.0
0x1c497  ldstr    asc_36E70// "// "
0x1c49c  stelem.ref
0x1c49d  dup
0x1c49e  ldc.i4.1
0x1c49f  ldloc.3
0x1c4a0  callvirt instance int32 [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Bundling.JsFile::get_HashKey()
0x1c4a5  stloc.s  4
0x1c4a7  ldloca.s 4
0x1c4a9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1c4ae  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1c4b3  stelem.ref
0x1c4b4  dup
0x1c4b5  ldc.i4.2
0x1c4b6  ldstr    asc_36E78// " : "
0x1c4bb  stelem.ref
0x1c4bc  dup
0x1c4bd  ldc.i4.3
0x1c4be  ldloc.3
0x1c4bf  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Bundling.JsFile::get_RelativePath()
0x1c4c4  ldc.i4.s 0x5C
0x1c4c6  ldc.i4.s 0x2F
0x1c4c8  callvirt instance string [mscorlib]System.String::Replace(char, char)
0x1c4cd  stelem.ref
0x1c4ce  dup
0x1c4cf  ldc.i4.4
0x1c4d0  call     string [mscorlib]System.Environment::get_NewLine()
0x1c4d5  stelem.ref
0x1c4d6  call     string [mscorlib]System.String::Concat(string[])
0x1c4db  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x1c4e0  ldloc.2
0x1c4e1  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1c4e6  brtrue.s loc_1C482
0x1c4e8  leave.s  loc_1C4F4
0x1c4ea  ldloc.2
0x1c4eb  brfalse.s loc_1C4F3
0x1c4ed  ldloc.2
0x1c4ee  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1c4f3  endfinally
0x1c4f4  ret
0x1c4f5  call     class Microsoft.Crm.Common.Application.Pages.Common.JsProvider.JsFileManager Microsoft.Crm.Common.Application.Pages.Common.JsProvider.JsFileManager::get_Instance()
0x1c4fa  ldloc.0
0x1c4fb  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Bundling.JsFile> Microsoft.Crm.Common.Application.Pages.Common.JsProvider.JsFileManager::GetJsFilesOrdered(class [mscorlib]System.Collections.Generic.IEnumerable`1<int32> ids)
0x1c500  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Bundling.JsFile>::GetEnumerator()
0x1c505  stloc.2
0x1c506  br       loc_1C5AA
0x1c50b  ldloc.2
0x1c50c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Bundling.JsFile>::get_Current()
0x1c511  stloc.s  5
0x1c513  ldloc.s  5
0x1c515  brfalse  loc_1C5AA
0x1c51a  ldarg.1
0x1c51b  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x1c520  ldc.i4.5
0x1c521  newarr   [mscorlib]System.String
0x1c526  dup
0x1c527  ldc.i4.0
0x1c528  ldstr    asc_36E70// "// "
0x1c52d  stelem.ref
0x1c52e  dup
0x1c52f  ldc.i4.1
0x1c530  ldloc.s  5
0x1c532  callvirt instance int32 [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Bundling.JsFile::get_HashKey()
0x1c537  stloc.s  4
0x1c539  ldloca.s 4
0x1c53b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1c540  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1c545  stelem.ref
0x1c546  dup
0x1c547  ldc.i4.2
0x1c548  ldstr    asc_36E78// " : "
0x1c54d  stelem.ref
0x1c54e  dup
0x1c54f  ldc.i4.3
0x1c550  ldloc.s  5
0x1c552  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Bundling.JsFile::get_RelativePath()
0x1c557  ldc.i4.s 0x5C
0x1c559  ldc.i4.s 0x2F
0x1c55b  callvirt instance string [mscorlib]System.String::Replace(char, char)
0x1c560  stelem.ref
0x1c561  dup
0x1c562  ldc.i4.4
0x1c563  call     string [mscorlib]System.Environment::get_NewLine()
0x1c568  stelem.ref
0x1c569  call     string [mscorlib]System.String::Concat(string[])
0x1c56e  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x1c573  ldarg.1
0x1c574  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x1c579  ldloc.s  5
0x1c57b  callvirt instance unsigned int8[] [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Bundling.JsFile::get_Content()
0x1c580  callvirt instance void [System.Web]System.Web.HttpResponse::BinaryWrite(unsigned int8[])
0x1c585  ldarg.1
0x1c586  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x1c58b  ldstr    asc_212FE// ";"
0x1c590  call     string [mscorlib]System.Environment::get_NewLine()
0x1c595  call     string [mscorlib]System.String::Concat(string, string)
0x1c59a  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x1c59f  ldarg.1
0x1c5a0  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x1c5a5  callvirt instance void [System.Web]System.Web.HttpResponse::Flush()
0x1c5aa  ldloc.2
0x1c5ab  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1c5b0  brtrue   loc_1C50B
0x1c5b5  leave.s  loc_1C5C1
0x1c5b7  ldloc.2
0x1c5b8  brfalse.s loc_1C5C0
0x1c5ba  ldloc.2
0x1c5bb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1c5c0  endfinally
0x1c5c1  ldarg.1
0x1c5c2  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x1c5c7  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Params()
0x1c5cc  ldstr    aIds// "ids"
0x1c5d1  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1c5d6  call     int32 [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Bundling.JsFile::GetHashKey(string)
0x1c5db  stloc.1
0x1c5dc  ldarg.1
0x1c5dd  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x1c5e2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1c5e7  ldstr    aWindowJsgroupl// "window.JsGroupLoadTime_{0} = (new Date("...
0x1c5ec  ldc.i4.1
0x1c5ed  newarr   [mscorlib]System.Object
0x1c5f2  dup
0x1c5f3  ldc.i4.0
0x1c5f4  ldloc.1
0x1c5f5  box      [mscorlib]System.Int32
0x1c5fa  stelem.ref
0x1c5fb  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1c600  call     string [mscorlib]System.Environment::get_NewLine()
0x1c605  call     string [mscorlib]System.String::Concat(string, string)
0x1c60a  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x1c60f  ret
```
