# Microsoft.Crm.Controls.PageResourceManager::RenderAllScripts

- ea: `0x3ae0`
- end: `0x3cf9`
- name: `Microsoft.Crm.Controls.PageResourceManager::RenderAllScripts`
- size: `537`
- prototype: ``
- caller_count: `2`
- callee_count: `24`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x8510`
- `0x9480`

## callees

- `0x22f0`
- `0x2360`
- `0x23a0`
- `0x23e0`
- `0x2400`
- `0x2440`
- `0x2460`
- `0x2480`
- `0x24a0`
- `0x3ae0`
- `0x3d40`
- `0x3d60`
- `0x68b0`
- `0x68d0`
- `0x6980`
- `0x69f0`
- `0xa340`
- `0x142c0`
- `0x22620`
- `0x22630`
- `0x22640`
- `0x22650`
- `0x22660`
- `0x22720`

## string_xrefs

- `0x3af3`: `/_static/_common/scripts/MicrosoftAjax.js`
- `0x3aff`: `/_static/_common/scripts/EncodeDecode.js`
- `0x3b0b`: `/_static/_common/scripts/Microsoft.Crm.Client.Core.js`
- `0x3b9f`: `/_common/global.ashx`
- `0x3ba6`: `/help/common/global.ashx`
- `0x3be3`: `/_static/_common/scripts/jquery-2.1.1.min.js`
- `0x3bf7`: `/_static/_common/scripts/jsrender.min.js`
- `0x3c03`: `/_static/_common/scripts/crminternalutility.js`
- `0x3c31`: `<script>\n					window.trackClosures = 1;\n					var savedAddHandler=$addHandler;\n					$addHandler=function(a,d,e,g)\n					{\n						var trackRequired = true;\n						if (typeof window.closureEvents !== 'undefined' && window.closureEvents.length > 0) /* tracking is not required if closureEvent collection is empty */\n						{\n							if (typeof a.uniqueId != "undefined" && typeof window.closureEvents[a.uniqueId.toString()] === "undefined") /* Check if we have valid ClosureEvents index here. `
- `0x3c43`: `/_static/_common/scripts/jquery.tmpl.min.js`
- `0x3c92`: `/_static/_common/scripts/pageloader.js`

## pseudocode

```c

```

## disassembly

```asm
0x3ae0  ldarg.2
0x3ae1  brfalse  loc_3C0D
0x3ae6  ldarg.0
0x3ae7  call     instance bool Microsoft.Crm.Controls.PageResourceManager::get_AllowGlobalAshxToBeLoaded()
0x3aec  brfalse  loc_3BB8
0x3af1  ldarg.0
0x3af2  ldarg.1
0x3af3  ldstr    aStaticCommonSc_6// "/_static/_common/scripts/MicrosoftAjax."...
0x3af8  call     instance void Microsoft.Crm.Controls.PageResourceManager::WriteScriptReference(class [System.Web]System.Web.UI.HtmlTextWriter output, string script)
0x3afd  ldarg.0
0x3afe  ldarg.1
0x3aff  ldstr    aStaticCommonSc_7// "/_static/_common/scripts/EncodeDecode.j"...
0x3b04  call     instance void Microsoft.Crm.Controls.PageResourceManager::WriteScriptReference(class [System.Web]System.Web.UI.HtmlTextWriter output, string script)
0x3b09  ldarg.0
0x3b0a  ldarg.1
0x3b0b  ldstr    aStaticCommonSc_8// "/_static/_common/scripts/Microsoft.Crm."...
0x3b10  call     instance void Microsoft.Crm.Controls.PageResourceManager::WriteScriptReference(class [System.Web]System.Web.UI.HtmlTextWriter output, string script)
0x3b15  ldarg.1
0x3b16  callvirt instance void [mscorlib]System.IO.TextWriter::Flush()
0x3b1b  ldarg.0
0x3b1c  call     instance bool Microsoft.Crm.Controls.PageResourceManager::get_HelpContext()
0x3b21  brtrue.s loc_3B2F
0x3b23  call     class Microsoft.Crm.Application.Components.UI.SharedScript Microsoft.Crm.Application.Components.UI.SharedScript::get_ScriptResx()
0x3b28  ldarg.1
0x3b29  ldc.i4.0
0x3b2a  callvirt instance void Microsoft.Crm.Application.Components.UI.SharedScript::WriteScriptTag(class [mscorlib]System.IO.TextWriter output, [opt] bool encode)
0x3b2f  call     string Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x3b34  ldc.i4.1
0x3b35  newarr   [mscorlib]System.Char
0x3b3a  dup
0x3b3b  ldc.i4.0
0x3b3c  ldc.i4.s 0x2F
0x3b3e  stelem.i2
0x3b3f  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x3b44  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3b49  brfalse.s loc_3B71
0x3b4b  call     class Microsoft.Crm.Application.Components.UI.SharedScript Microsoft.Crm.Application.Components.UI.SharedScript::get_CrmServiceProxy()
0x3b50  ldarg.1
0x3b51  ldc.i4.1
0x3b52  callvirt instance void Microsoft.Crm.Application.Components.UI.SharedScript::WriteScriptTag(class [mscorlib]System.IO.TextWriter output, [opt] bool encode)
0x3b57  ldarg.1
0x3b58  callvirt instance void [mscorlib]System.IO.TextWriter::Flush()
0x3b5d  call     class Microsoft.Crm.Application.Components.UI.SharedScript Microsoft.Crm.Application.Components.UI.SharedScript::get_CrmServiceProxyFramework()
0x3b62  ldarg.1
0x3b63  ldc.i4.1
0x3b64  callvirt instance void Microsoft.Crm.Application.Components.UI.SharedScript::WriteScriptTag(class [mscorlib]System.IO.TextWriter output, [opt] bool encode)
0x3b69  ldarg.1
0x3b6a  callvirt instance void [mscorlib]System.IO.TextWriter::Flush()
0x3b6f  br.s     loc_3B95
0x3b71  call     class Microsoft.Crm.Application.Components.UI.SharedScript Microsoft.Crm.Application.Components.UI.SharedScript::get_CrmServiceProxyCDN()
0x3b76  ldarg.1
0x3b77  ldc.i4.1
0x3b78  callvirt instance void Microsoft.Crm.Application.Components.UI.SharedScript::WriteScriptTag(class [mscorlib]System.IO.TextWriter output, [opt] bool encode)
0x3b7d  ldarg.1
0x3b7e  callvirt instance void [mscorlib]System.IO.TextWriter::Flush()
0x3b83  call     class Microsoft.Crm.Application.Components.UI.SharedScript Microsoft.Crm.Application.Components.UI.SharedScript::get_CrmServiceProxyFrameworkCDN()
0x3b88  ldarg.1
0x3b89  ldc.i4.1
0x3b8a  callvirt instance void Microsoft.Crm.Application.Components.UI.SharedScript::WriteScriptTag(class [mscorlib]System.IO.TextWriter output, [opt] bool encode)
0x3b8f  ldarg.1
0x3b90  callvirt instance void [mscorlib]System.IO.TextWriter::Flush()
0x3b95  ldarg.0
0x3b96  ldarg.1
0x3b97  ldarg.0
0x3b98  call     instance bool Microsoft.Crm.Controls.PageResourceManager::get_HelpContext()
0x3b9d  brtrue.s loc_3BA6
0x3b9f  ldstr    aCommonGlobalAs_0// "/_common/global.ashx"
0x3ba4  br.s     loc_3BAB
0x3ba6  ldstr    aHelpCommonGlob// "/help/common/global.ashx"
0x3bab  call     instance void Microsoft.Crm.Controls.PageResourceManager::WriteScriptReference(class [System.Web]System.Web.UI.HtmlTextWriter output, string script)
0x3bb0  ldarg.1
0x3bb1  callvirt instance void [mscorlib]System.IO.TextWriter::Flush()
0x3bb6  br.s     loc_3BD1
0x3bb8  ldarg.0
0x3bb9  call     instance bool Microsoft.Crm.Controls.PageResourceManager::get_HelpContext()
0x3bbe  brtrue.s loc_3BD1
0x3bc0  ldarg.0
0x3bc1  ldarg.1
0x3bc2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Controls.ScriptResource::get_ScriptResourceInclude()
0x3bc7  callvirt instance string [mscorlib]System.Object::ToString()
0x3bcc  call     instance void Microsoft.Crm.Controls.PageResourceManager::WriteScriptReference(class [System.Web]System.Web.UI.HtmlTextWriter output, string script)
0x3bd1  ldarg.0
0x3bd2  call     instance bool Microsoft.Crm.Controls.PageResourceManager::get_LoadJQuery()
0x3bd7  brfalse.s loc_3BED
0x3bd9  ldarg.0
0x3bda  call     instance bool Microsoft.Crm.Controls.PageResourceManager::get_AllowJQueryToBeLoaded()
0x3bdf  brfalse.s loc_3BED
0x3be1  ldarg.0
0x3be2  ldarg.1
0x3be3  ldstr    aStaticCommonSc_9// "/_static/_common/scripts/jquery-2.1.1.m"...
0x3be8  call     instance void Microsoft.Crm.Controls.PageResourceManager::WriteScriptReference(class [System.Web]System.Web.UI.HtmlTextWriter output, string script)
0x3bed  ldarg.0
0x3bee  call     instance bool Microsoft.Crm.Controls.PageResourceManager::get_LoadJSRender()
0x3bf3  brfalse.s loc_3C01
0x3bf5  ldarg.0
0x3bf6  ldarg.1
0x3bf7  ldstr    aStaticCommonSc_10// "/_static/_common/scripts/jsrender.min.j"...
0x3bfc  call     instance void Microsoft.Crm.Controls.PageResourceManager::WriteScriptReference(class [System.Web]System.Web.UI.HtmlTextWriter output, string script)
0x3c01  ldarg.0
0x3c02  ldarg.1
0x3c03  ldstr    aStaticCommonSc_11// "/_static/_common/scripts/crminternaluti"...
0x3c08  call     instance void Microsoft.Crm.Controls.PageResourceManager::WriteScriptReference(class [System.Web]System.Web.UI.HtmlTextWriter output, string script)
0x3c0d  ldarg.0
0x3c0e  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Controls.PageResourceManager::_criticalScriptFile
0x3c13  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x3c18  ldc.i4.0
0x3c19  ble.s    loc_3C28
0x3c1b  ldarg.0
0x3c1c  ldarg.1
0x3c1d  ldarg.0
0x3c1e  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Controls.PageResourceManager::_criticalScriptFile
0x3c23  call     instance void Microsoft.Crm.Controls.PageResourceManager::WriteScriptReferences(class [System.Web]System.Web.UI.HtmlTextWriter output, class [mscorlib]System.Collections.Generic.List`1<string> scripts)
0x3c28  ldarg.0
0x3c29  call     instance bool Microsoft.Crm.Controls.PageResourceManager::get_LoadRefreshFormInit()
0x3c2e  brfalse.s loc_3C3B
0x3c30  ldarg.1
0x3c31  ldstr    aScriptWindowTr// "<script>\r\n\t\t\t\t\twindow.trackClosu"...
0x3c36  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x3c3b  ldarg.0
0x3c3c  call     instance bool Microsoft.Crm.Controls.PageResourceManager::get_LoadJQueryTemplate()
0x3c41  brfalse.s loc_3C6D
0x3c43  ldstr    aStaticCommonSc_12// "/_static/_common/scripts/jquery.tmpl.mi"...
0x3c48  stloc.0
0x3c49  ldarg.0
0x3c4a  call     instance bool Microsoft.Crm.Controls.PageResourceManager::get_LoadRefreshFormInit()
0x3c4f  brfalse.s loc_3C65
0x3c51  ldarg.0
0x3c52  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri> Microsoft.Crm.Controls.PageResourceManager::_scripts
0x3c57  ldloc.0
0x3c58  ldloc.0
0x3c59  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string)
0x3c5e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri>::Add(var<u1>, !!T0)
0x3c63  br.s     loc_3C6D
0x3c65  ldarg.0
0x3c66  ldarg.1
0x3c67  ldloc.0
0x3c68  call     instance void Microsoft.Crm.Controls.PageResourceManager::WriteScriptReference(class [System.Web]System.Web.UI.HtmlTextWriter output, string script)
0x3c6d  ldarg.0
0x3c6e  call     instance bool Microsoft.Crm.Controls.PageResourceManager::get_UsePageLoader()
0x3c73  brfalse.s loc_3CB5
0x3c75  call     string Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x3c7a  ldc.i4.1
0x3c7b  newarr   [mscorlib]System.Char
0x3c80  dup
0x3c81  ldc.i4.0
0x3c82  ldc.i4.s 0x2F
0x3c84  stelem.i2
0x3c85  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x3c8a  stloc.1
0x3c8b  ldarg.1
0x3c8c  ldstr    aScriptTypeText_0// "<script type='text/javascript' src='"
0x3c91  ldloc.1
0x3c92  ldstr    aStaticCommonSc_13// "/_static/_common/scripts/pageloader.js"
0x3c97  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x3c9c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3ca1  callvirt instance string [mscorlib]System.Object::ToString()
0x3ca6  ldstr    aScript_0// "'></script>"
0x3cab  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x3cb0  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x3cb5  ldarg.0
0x3cb6  call     instance bool Microsoft.Crm.Controls.PageResourceManager::get_OutlookStageContext()
0x3cbb  brfalse.s loc_3CD9
0x3cbd  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsForOutlookClient()
0x3cc2  brfalse.s loc_3CD9
0x3cc4  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsOnline()
0x3cc9  brfalse.s loc_3CD9
0x3ccb  ldarg.0
0x3ccc  ldarg.1
0x3ccd  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x3cd2  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::WriteDynamicallyLoadedScripts(class [mscorlib]System.IO.TextWriter output)
0x3cd7  br.s     loc_3CE5
0x3cd9  ldarg.0
0x3cda  ldarg.1
0x3cdb  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x3ce0  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::WriteScriptIncludes(class [mscorlib]System.IO.TextWriter output)
0x3ce5  ldarg.0
0x3ce6  ldarg.1
0x3ce7  call     instance void Microsoft.Crm.Controls.PageResourceManager::RenderScriptBlocksForOnLoad(class [System.Web]System.Web.UI.HtmlTextWriter output)
0x3cec  ldarg.0
0x3ced  ldarg.1
0x3cee  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x3cf3  call     instance void Microsoft.Crm.Controls.PageResourceManager::RenderScriptBlocks(class [mscorlib]System.IO.TextWriter writer)
0x3cf8  ret
```
