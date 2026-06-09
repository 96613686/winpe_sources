# Microsoft.Crm.Controls.Header::Render

- ea: `0x7b90`
- end: `0x7e44`
- name: `Microsoft.Crm.Controls.Header::Render`
- size: `692`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x2320`
- `0x24a0`
- `0x31e0`
- `0x3990`
- `0x3a60`
- `0x6400`
- `0x6f30`
- `0x6fc0`
- `0x7ae0`
- `0x7b90`
- `0x7e50`
- `0xbf00`
- `0x142c0`
- `0x22280`
- `0x222a0`
- `0x222c0`
- `0x223f0`
- `0x2a5f0`

## string_xrefs

- `0x7c32`: `<script type='text/javascript'>\n			var isKeyPressed=false;\n			var headElement = document.getElementsByTagName('head')[0];\n			var style_element = document.createElement('style');\n			style_element.id = 'focusStyle';\n			var focusCss = ':focus{outline:2px dashed !important; outline-offset: 1px !important;}::-moz-focus-inner{border:0;}';\n			var removefocusCss = ':focus{outline:0}::-moz-focus-inner{border:0;}';\n\n			document.addEventListener('keydown', function(e) {\n				isKeyPressed=t`
- `0x7c92`: `<script type='text/javascript'>window.addEventListener('error', function(e) { \n										try\n										{\n											var element = e.target;\n											var src = element.src;\n											var href = element.href;\n											var curUrl = src || href;\n											var CDNUrl = window.CDNURL || (window.top && window.top.CDNURL);\n											var fallBackQueryParam = '';\n											var queryParams = '';\n											var isBundle = false;\n\n											// We want this error handler to be`
- `0x7d0d`: `ClientPerfTraceDocumentReady`
- `0x7d23`: `Mscrm.PerformanceTracing.onDocumentReady()`
- `0x7d64`: `$addHandler(document,'readystatechange',Mscrm.PerformanceTracing.onDocumentReady);Sys.Application.add_load(Mscrm.PerformanceTracing.onApplicationLoad);`
- `0x7e17`: `<link rel="stylesheet" type="text/css" href="{0}" id="{1}" />`

## pseudocode

```c

```

## disassembly

```asm
0x7b90  ldarg.0
0x7b91  call     instance void Microsoft.Crm.Controls.Header::ConfigureForRendering()
0x7b96  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x7b9b  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x7ba0  ldstr    aTextHtml// "text/html"
0x7ba5  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0x7baa  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x7baf  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x7bb4  ldstr    aUtf8// "utf-8"
0x7bb9  callvirt instance void [System.Web]System.Web.HttpResponse::set_Charset(string)
0x7bbe  leave.s  loc_7BD7
0x7bc0  pop
0x7bc1  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x7bc6  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x7bcb  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x7bd0  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentEncoding(class [mscorlib]System.Text.Encoding)
0x7bd5  leave.s  loc_7BD7
0x7bd7  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x7bdc  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x7be1  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsIosDevice(class [System.Web]System.Web.HttpRequest)
0x7be6  brfalse.s loc_7BEE
0x7be8  ldarg.0
0x7be9  call     instance void Microsoft.Crm.Controls.Header::AddViewportMetaTag()
0x7bee  ldarg.0
0x7bef  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Controls.Header::_metaTags
0x7bf4  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<string>::GetEnumerator()
0x7bf9  stloc.3
0x7bfa  br.s     loc_7C0D
0x7bfc  ldloca.s 3
0x7bfe  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::get_Current()
0x7c03  stloc.s  4
0x7c05  ldarg.1
0x7c06  ldloc.s  4
0x7c08  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x7c0d  ldloca.s 3
0x7c0f  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::MoveNext()
0x7c14  brtrue.s loc_7BFC
0x7c16  leave.s  loc_7C26
0x7c18  ldloca.s 3
0x7c1a  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>
0x7c20  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7c25  endfinally
0x7c26  ldarg.1
0x7c27  ldstr    aScriptTypeText_2// "<script type='text/javascript'>var Load"...
0x7c2c  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x7c31  ldarg.1
0x7c32  ldstr    aScriptTypeText_3// "<script type='text/javascript'>\r\n\t\t"...
0x7c37  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x7c3c  call     string Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x7c41  ldc.i4.1
0x7c42  newarr   [mscorlib]System.Char
0x7c47  dup
0x7c48  ldc.i4.0
0x7c49  ldc.i4.s 0x2F
0x7c4b  stelem.i2
0x7c4c  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x7c51  stloc.0
0x7c52  ldarg.0
0x7c53  ldfld    bool Microsoft.Crm.Controls.Header::_isControlHeader
0x7c58  brtrue.s loc_7C84
0x7c5a  ldarg.1
0x7c5b  ldstr    aScriptTypeText_4// "<script type='text/javascript'>var CDNU"...
0x7c60  ldloc.0
0x7c61  ldsfld   string [mscorlib]System.String::Empty
0x7c66  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x7c6b  brtrue.s loc_7C74
0x7c6d  ldstr    asc_3EF4E// "''"
0x7c72  br.s     loc_7C7A
0x7c74  ldloc.0
0x7c75  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x7c7a  call     string [mscorlib]System.String::Format(string, object)
0x7c7f  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x7c84  ldloc.0
0x7c85  ldsfld   string [mscorlib]System.String::Empty
0x7c8a  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x7c8f  brfalse.s loc_7C9C
0x7c91  ldarg.1
0x7c92  ldstr    aScriptTypeText_5// "<script type='text/javascript'>window.a"...
0x7c97  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x7c9c  ldarg.0
0x7c9d  call     instance bool Microsoft.Crm.Controls.PageResourceManager::get_LoadRefreshFormInit()
0x7ca2  brtrue.s loc_7CE0
0x7ca4  ldarg.1
0x7ca5  ldstr    aScriptTypeText_6// "<script type='text/javascript'>\r\n\t\t"...
0x7caa  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x7caf  ldarg.0
0x7cb0  ldc.i4.1
0x7cb1  newarr   Microsoft.Crm.Application.Components.UI.ScriptBlock
0x7cb6  dup
0x7cb7  ldc.i4.0
0x7cb8  newobj   instance void Microsoft.Crm.Application.Components.UI.ScriptBlock::.ctor()
0x7cbd  dup
0x7cbe  ldstr    aSetpltmarker// "SetPLTMarker"
0x7cc3  callvirt instance void Microsoft.Crm.Application.Components.UI.ScriptBlock::set_Name(string value)
0x7cc8  dup
0x7cc9  ldc.i4.1
0x7cca  callvirt instance void Microsoft.Crm.Application.Components.UI.ScriptBlock::set_Priority(int32 value)
0x7ccf  dup
0x7cd0  ldstr    aIfWindowPostre// "if(!window.PostRenderTime){window.PostR"...
0x7cd5  callvirt instance void Microsoft.Crm.Application.Components.UI.ScriptBlock::set_JSBody(string value)
0x7cda  stelem.ref
0x7cdb  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptBlockForOnLoad(class Microsoft.Crm.Application.Components.UI.ScriptBlock[] scriptBlocks)
0x7ce0  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.Performance.Instrumentation.PerformanceContext::get_ClientPerformanceTraceLevel()
0x7ce5  ldc.i4.0
0x7ce6  ble      loc_7D6E
0x7ceb  ldarg.1
0x7cec  ldstr    aScriptTypeText_7// "<script type=\"text/javascript\">var _p"...
0x7cf1  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x7cf6  ldarg.0
0x7cf7  call     instance bool Microsoft.Crm.Controls.Header::get_DeferAllScripts()
0x7cfc  brfalse.s loc_7D5E
0x7cfe  ldarg.0
0x7cff  ldc.i4.2
0x7d00  newarr   Microsoft.Crm.Application.Components.UI.ScriptBlock
0x7d05  dup
0x7d06  ldc.i4.0
0x7d07  newobj   instance void Microsoft.Crm.Application.Components.UI.ScriptBlock::.ctor()
0x7d0c  dup
0x7d0d  ldstr    aClientperftrac// "ClientPerfTraceDocumentReady"
0x7d12  callvirt instance void Microsoft.Crm.Application.Components.UI.ScriptBlock::set_Name(string value)
0x7d17  dup
0x7d18  ldc.i4   0x82
0x7d1d  callvirt instance void Microsoft.Crm.Application.Components.UI.ScriptBlock::set_Priority(int32 value)
0x7d22  dup
0x7d23  ldstr    aMscrmPerforman// "Mscrm.PerformanceTracing.onDocumentRead"...
0x7d28  callvirt instance void Microsoft.Crm.Application.Components.UI.ScriptBlock::set_JSBody(string value)
0x7d2d  stelem.ref
0x7d2e  dup
0x7d2f  ldc.i4.1
0x7d30  newobj   instance void Microsoft.Crm.Application.Components.UI.ScriptBlock::.ctor()
0x7d35  dup
0x7d36  ldstr    aClientperftrac_0// "ClientPerfTraceApplicationLoad"
0x7d3b  callvirt instance void Microsoft.Crm.Application.Components.UI.ScriptBlock::set_Name(string value)
0x7d40  dup
0x7d41  ldc.i4   0x83
0x7d46  callvirt instance void Microsoft.Crm.Application.Components.UI.ScriptBlock::set_Priority(int32 value)
0x7d4b  dup
0x7d4c  ldstr    aMscrmPerforman_0// "Mscrm.PerformanceTracing.onApplicationL"...
0x7d51  callvirt instance void Microsoft.Crm.Application.Components.UI.ScriptBlock::set_JSBody(string value)
0x7d56  stelem.ref
0x7d57  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptBlockForOnLoad(class Microsoft.Crm.Application.Components.UI.ScriptBlock[] scriptBlocks)
0x7d5c  br.s     loc_7D6E
0x7d5e  ldarg.0
0x7d5f  ldstr    aClientperftrac_1// "ClientPerfTrace"
0x7d64  ldstr    aAddhandlerDocu// "$addHandler(document,'readystatechange'"...
0x7d69  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptBlock(string key, string scriptBlock)
0x7d6e  ldarg.0
0x7d6f  ldc.i4.1
0x7d70  call     instance void Microsoft.Crm.Controls.PageResourceManager::set_HasRendered(bool value)
0x7d75  ldarg.0
0x7d76  ldarg.1
0x7d77  call     instance void [System.Web]System.Web.UI.Control::Render(class [System.Web]System.Web.UI.HtmlTextWriter)
0x7d7c  ldarg.1
0x7d7d  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x7d82  stloc.1
0x7d83  ldarg.0
0x7d84  ldfld    string Microsoft.Crm.Controls.PageResourceManager::_title
0x7d89  brfalse.s loc_7DBB
0x7d8b  ldarg.0
0x7d8c  ldfld    string Microsoft.Crm.Controls.PageResourceManager::_title
0x7d91  callvirt instance int32 [mscorlib]System.String::get_Length()
0x7d96  ldc.i4.0
0x7d97  ble.s    loc_7DBB
0x7d99  ldloc.1
0x7d9a  ldstr    aTitle// "<title>"
0x7d9f  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x7da4  ldarg.0
0x7da5  ldfld    string Microsoft.Crm.Controls.PageResourceManager::_title
0x7daa  ldloc.1
0x7dab  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string, class [mscorlib]System.IO.TextWriter)
0x7db0  ldloc.1
0x7db1  ldstr    aTitle_0// "</title>"
0x7db6  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x7dbb  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x7dc0  callvirt instance class [System.Web]System.Web.IHttpHandler [System.Web]System.Web.HttpContext::get_CurrentHandler()
0x7dc5  isinst   Microsoft.Crm.Controls.UIPage
0x7dca  stloc.2
0x7dcb  ldloc.2
0x7dcc  brfalse.s loc_7E0A
0x7dce  ldloc.2
0x7dcf  callvirt instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Controls.UIPage::get_FooterControl()
0x7dd4  brfalse.s loc_7E0A
0x7dd6  ldloc.2
0x7dd7  callvirt instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Controls.UIPage::get_FooterControl()
0x7ddc  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri> Microsoft.Crm.Controls.PageResourceManager::_styles
0x7de1  brfalse.s loc_7E0A
0x7de3  ldarg.0
0x7de4  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri> Microsoft.Crm.Controls.PageResourceManager::_styles
0x7de9  ldloc.2
0x7dea  callvirt instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Controls.UIPage::get_FooterControl()
0x7def  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri> Microsoft.Crm.Controls.PageResourceManager::_styles
0x7df4  call     T0x2B000012
0x7df9  pop
0x7dfa  ldloc.2
0x7dfb  callvirt instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Controls.UIPage::get_FooterControl()
0x7e00  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri> Microsoft.Crm.Controls.PageResourceManager::_styles
0x7e05  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri>::Clear()
0x7e0a  ldarg.0
0x7e0b  ldarg.1
0x7e0c  ldarg.0
0x7e0d  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri> Microsoft.Crm.Controls.PageResourceManager::_styles
0x7e12  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri>::get_Values()
0x7e17  ldstr    aLinkRelStylesh// "<link rel=\"stylesheet\" type=\"text/cs"...
0x7e1c  ldnull
0x7e1d  ldftn    string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x7e23  newobj   instance void EncodingFunction::.ctor(object object, native int method)
0x7e28  call     instance void Microsoft.Crm.Controls.PageResourceManager::WriteList(class [mscorlib]System.IO.TextWriter output, class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri> list, string mask, class EncodingFunction encodingFunction)
0x7e2d  ldarg.0
0x7e2e  call     instance bool Microsoft.Crm.Controls.Header::get_DeferAllScripts()
0x7e33  brtrue.s loc_7E3D
0x7e35  ldarg.0
0x7e36  ldarg.1
0x7e37  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::RenderScripts(class [System.Web]System.Web.UI.HtmlTextWriter output)
0x7e3c  ret
0x7e3d  ldarg.0
0x7e3e  call     instance void Microsoft.Crm.Controls.Header::DeferToFooter()
0x7e43  ret
```
