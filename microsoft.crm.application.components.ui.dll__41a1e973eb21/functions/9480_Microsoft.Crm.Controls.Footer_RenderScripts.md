# Microsoft.Crm.Controls.Footer::RenderScripts

- ea: `0x9480`
- end: `0x958f`
- name: `Microsoft.Crm.Controls.Footer::RenderScripts`
- size: `271`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x23a0`
- `0x23c0`
- `0x24a0`
- `0x3a60`
- `0x3ae0`
- `0x69f0`
- `0x8ad0`
- `0x8af0`
- `0x8b70`
- `0x9370`
- `0x9480`
- `0x142c0`

## string_xrefs

- `0x94de`: `/_static/_common/scripts/MicrosoftAjax.js`
- `0x9508`: `/_static/_common/scripts/crminternalutility.js`
- `0x94ac`: `/_static/_common/scripts/pageloader.js`
- `0x9542`: `/_static/_common/scripts/perceivedRibbon.js`

## pseudocode

```c

```

## disassembly

```asm
0x9480  ldarg.0
0x9481  ldarg.1
0x9482  call     instance void Microsoft.Crm.Controls.PageResourceManager::RenderScripts(class [System.Web]System.Web.UI.HtmlTextWriter output)
0x9487  call     string Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x948c  ldc.i4.1
0x948d  newarr   [mscorlib]System.Char
0x9492  dup
0x9493  ldc.i4.0
0x9494  ldc.i4.s 0x2F
0x9496  stelem.i2
0x9497  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x949c  stloc.0
0x949d  ldarg.0
0x949e  call     instance bool Microsoft.Crm.Controls.PageResourceManager::get_UsePageLoader()
0x94a3  brfalse.s loc_94CF
0x94a5  ldarg.1
0x94a6  ldstr    aScriptTypeText_0// "<script type='text/javascript' src='"
0x94ab  ldloc.0
0x94ac  ldstr    aStaticCommonSc_13// "/_static/_common/scripts/pageloader.js"
0x94b1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x94b6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x94bb  callvirt instance string [mscorlib]System.Object::ToString()
0x94c0  ldstr    aScript_0// "'></script>"
0x94c5  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x94ca  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x94cf  ldarg.0
0x94d0  call     instance bool Microsoft.Crm.Controls.PageResourceManager::get_LoadBaseScriptInDeferredScenario()
0x94d5  brfalse.s loc_952B
0x94d7  ldarg.1
0x94d8  ldstr    aScriptTypeText_0// "<script type='text/javascript' src='"
0x94dd  ldloc.0
0x94de  ldstr    aStaticCommonSc_6// "/_static/_common/scripts/MicrosoftAjax."...
0x94e3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x94e8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x94ed  callvirt instance string [mscorlib]System.Object::ToString()
0x94f2  ldstr    aScript_0// "'></script>"
0x94f7  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x94fc  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x9501  ldarg.1
0x9502  ldstr    aScriptTypeText_0// "<script type='text/javascript' src='"
0x9507  ldloc.0
0x9508  ldstr    aStaticCommonSc_11// "/_static/_common/scripts/crminternaluti"...
0x950d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9512  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9517  callvirt instance string [mscorlib]System.Object::ToString()
0x951c  ldstr    aScript_0// "'></script>"
0x9521  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x9526  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x952b  ldarg.0
0x952c  call     instance bool Microsoft.Crm.Controls.Footer::get_IsEntityRecordPage()
0x9531  brfalse.s loc_9565
0x9533  ldarg.0
0x9534  call     instance bool Microsoft.Crm.Controls.PageResourceManager::get_LoadRefreshFormInit()
0x9539  brtrue.s loc_9565
0x953b  ldarg.1
0x953c  ldstr    aScriptTypeText_0// "<script type='text/javascript' src='"
0x9541  ldloc.0
0x9542  ldstr    aStaticCommonSc_19// "/_static/_common/scripts/perceivedRibbo"...
0x9547  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x954c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9551  callvirt instance string [mscorlib]System.Object::ToString()
0x9556  ldstr    aScript_0// "'></script>"
0x955b  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x9560  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x9565  ldarg.0
0x9566  call     instance bool Microsoft.Crm.Controls.Footer::get_ChunkScripts()
0x956b  brtrue.s loc_957B
0x956d  ldarg.0
0x956e  ldarg.1
0x956f  ldarg.0
0x9570  call     instance bool Microsoft.Crm.Controls.Footer::get_LoadGlobalJSAndScriptResourceJS()
0x9575  call     instance void Microsoft.Crm.Controls.PageResourceManager::RenderAllScripts(class [System.Web]System.Web.UI.HtmlTextWriter output, bool loadGlobalJSAndScriptResourceJS)
0x957a  ret
0x957b  ldarg.0
0x957c  ldarg.1
0x957d  call     instance void Microsoft.Crm.Controls.Footer::WriteChunkedJsCode(class [mscorlib]System.IO.TextWriter writer)
0x9582  ldarg.0
0x9583  ldarg.1
0x9584  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x9589  call     instance void Microsoft.Crm.Controls.PageResourceManager::RenderScriptBlocks(class [mscorlib]System.IO.TextWriter writer)
0x958e  ret
```
