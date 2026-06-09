# Microsoft.Crm.Application.Controls.Toc.TocPage::ConfigureHeader

- ea: `0xc9c40`
- end: `0xc9d50`
- name: `Microsoft.Crm.Application.Controls.Toc.TocPage::ConfigureHeader`
- size: `272`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0xc9c40`

## string_xrefs

- `0xc9d12`: `/help_toc.xml`
- `0xc9c4c`: `/_static/help/common/help.css`
- `0xc9c5c`: `/_static/help/common/help.js`
- `0xc9c6c`: `HELP_VERSION_PATH`
- `0xc9d2e`: `HELP_TOC_XML`

## pseudocode

```c

```

## disassembly

```asm
0xc9c40  ldarg.0
0xc9c41  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AnonymousHelpPage::ConfigureHeader()
0xc9c46  ldarg.0
0xc9c47  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AnonymousHeader [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AnonymousPage::get_CurrentHeader()
0xc9c4c  ldstr    aStaticHelpComm// "/_static/help/common/help.css"
0xc9c51  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xc9c56  ldarg.0
0xc9c57  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AnonymousHeader [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AnonymousPage::get_CurrentHeader()
0xc9c5c  ldstr    aStaticHelpComm_0// "/_static/help/common/help.js"
0xc9c61  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xc9c66  ldarg.0
0xc9c67  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AnonymousHeader [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AnonymousPage::get_CurrentHeader()
0xc9c6c  ldstr    aHelpVersionPat// "HELP_VERSION_PATH"
0xc9c71  ldarg.0
0xc9c72  call     instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AnonymousHelpPage::get_HelpVersionPathWithSlash()
0xc9c77  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xc9c7c  ldarg.0
0xc9c7d  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0xc9c82  ldstr    aHelpHelpTocXsl// "/help/help_toc.xsl"
0xc9c87  callvirt instance string [System.Web]System.Web.UI.Page::MapPath(string)
0xc9c8c  newobj   instance void [mscorlib]System.IO.StreamReader::.ctor(string)
0xc9c91  stloc.2
0xc9c92  ldarg.0
0xc9c93  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AnonymousHeader [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AnonymousPage::get_CurrentHeader()
0xc9c98  ldstr    aHelpTocXsl// "HELP_TOC_XSL"
0xc9c9d  ldloc.2
0xc9c9e  callvirt instance string [mscorlib]System.IO.TextReader::ReadToEnd()
0xc9ca3  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmXmlEncode(string)
0xc9ca8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xc9cad  leave.s  loc_C9CB9
0xc9caf  ldloc.2
0xc9cb0  brfalse.s loc_C9CB8
0xc9cb2  ldloc.2
0xc9cb3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc9cb8  endfinally
0xc9cb9  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsLive()
0xc9cbe  stloc.0
0xc9cbf  ldarg.0
0xc9cc0  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xc9cc5  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xc9cca  ldstr    aHelplcid// "helpLcid"
0xc9ccf  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xc9cd4  stloc.1
0xc9cd5  ldarg.0
0xc9cd6  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0xc9cdb  ldc.i4.6
0xc9cdc  newarr   [mscorlib]System.String
0xc9ce1  dup
0xc9ce2  ldc.i4.0
0xc9ce3  ldstr    aHelp_0// "/help/"
0xc9ce8  stelem.ref
0xc9ce9  dup
0xc9cea  ldc.i4.1
0xc9ceb  ldarg.0
0xc9cec  call     instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AnonymousHelpPage::get_HelpVersionPathWithSlash()
0xc9cf1  stelem.ref
0xc9cf2  dup
0xc9cf3  ldc.i4.2
0xc9cf4  ldloc.1
0xc9cf5  stelem.ref
0xc9cf6  dup
0xc9cf7  ldc.i4.3
0xc9cf8  ldstr    asc_13CDBE// "/"
0xc9cfd  stelem.ref
0xc9cfe  dup
0xc9cff  ldc.i4.4
0xc9d00  ldloc.0
0xc9d01  brtrue.s loc_C9D0A
0xc9d03  ldstr    aOp// "OP"
0xc9d08  br.s     loc_C9D0F
0xc9d0a  ldstr    aLive// "LIVE"
0xc9d0f  stelem.ref
0xc9d10  dup
0xc9d11  ldc.i4.5
0xc9d12  ldstr    aHelpTocXml// "/help_toc.xml"
0xc9d17  stelem.ref
0xc9d18  call     string [mscorlib]System.String::Concat(string[])
0xc9d1d  callvirt instance string [System.Web]System.Web.UI.Page::MapPath(string)
0xc9d22  newobj   instance void [mscorlib]System.IO.StreamReader::.ctor(string)
0xc9d27  stloc.3
0xc9d28  ldarg.0
0xc9d29  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AnonymousHeader [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AnonymousPage::get_CurrentHeader()
0xc9d2e  ldstr    aHelpTocXml_0// "HELP_TOC_XML"
0xc9d33  ldloc.3
0xc9d34  callvirt instance string [mscorlib]System.IO.TextReader::ReadToEnd()
0xc9d39  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmXmlEncode(string)
0xc9d3e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xc9d43  leave.s  loc_C9D4F
0xc9d45  ldloc.3
0xc9d46  brfalse.s loc_C9D4E
0xc9d48  ldloc.3
0xc9d49  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc9d4e  endfinally
0xc9d4f  ret
```
