# Microsoft.Crm.Application.Components.UI.LookupItem::RenderLookupItem

- ea: `0x1ec60`
- end: `0x1f027`
- name: `Microsoft.Crm.Application.Components.UI.LookupItem::RenderLookupItem`
- size: `967`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1ec40`

## callees

- `0x1a3b0`
- `0x1a400`
- `0x1ec10`
- `0x1ec30`
- `0x1ec60`
- `0x23c20`
- `0x24120`
- `0x24210`
- `0x242c0`

## string_xrefs

- `0x1ee12`: `openDisabledLui(new Sys.UI.DomEvent(event))`
- `0x1ef00`: `<span id='lblread' style='position: absolute;top:-999999em;left:auto;width:1px;height:1px;overflow:hidden;'></span>`
- `0x1efa8`: `<span class="ms-crm-Hidden-NoBehavior" id="lblread"></span>`

## pseudocode

```c

```

## disassembly

```asm
0x1ec60  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x1ec65  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x1ec6a  callvirt instance class [System.Web]System.Web.HttpBrowserCapabilities [System.Web]System.Web.HttpRequest::get_Browser()
0x1ec6f  callvirt instance string [System.Web]System.Web.Configuration.HttpCapabilitiesBase::get_Browser()
0x1ec74  callvirt instance string [mscorlib]System.String::ToLower()
0x1ec79  callvirt instance string [mscorlib]System.Object::ToString()
0x1ec7e  ldstr    aFirefox// "firefox"
0x1ec83  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1ec88  brfalse  loc_1ED48
0x1ec8d  ldarg.1
0x1ec8e  ldc.i4.5
0x1ec8f  newarr   [mscorlib]System.String
0x1ec94  dup
0x1ec95  ldc.i4.0
0x1ec96  ldstr    aLabelFor// "<label for=\""
0x1ec9b  stelem.ref
0x1ec9c  dup
0x1ec9d  ldc.i4.1
0x1ec9e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1eca3  ldstr    aWebReportsOwne// "Web.Reports.Owner"
0x1eca8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1ecad  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x1ecb2  stelem.ref
0x1ecb3  dup
0x1ecb4  ldc.i4.2
0x1ecb5  ldstr    aLabelId// "_label\" id=\""
0x1ecba  stelem.ref
0x1ecbb  dup
0x1ecbc  ldc.i4.3
0x1ecbd  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1ecc2  ldstr    aWebReportsOwne// "Web.Reports.Owner"
0x1ecc7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1eccc  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x1ecd1  stelem.ref
0x1ecd2  dup
0x1ecd3  ldc.i4.4
0x1ecd4  ldstr    aLabel_1// "_label\">"
0x1ecd9  stelem.ref
0x1ecda  call     string [mscorlib]System.String::Concat(string[])
0x1ecdf  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1ece4  ldarg.1
0x1ece5  ldstr    aDivClassMsCrmD// "<div class=\"ms-crm-div-NotVisible\">"
0x1ecea  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1ecef  ldarg.1
0x1ecf0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1ecf5  ldstr    aWebReportsOwne// "Web.Reports.Owner"
0x1ecfa  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1ecff  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x1ed04  ldstr    asc_4C79A// " "
0x1ed09  call     string [mscorlib]System.String::Concat(string, string)
0x1ed0e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1ed13  ldarg.0
0x1ed14  ldfld    string Microsoft.Crm.Application.Components.UI.LookupItem::_name
0x1ed19  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x1ed1e  brtrue.s loc_1ED28
0x1ed20  ldarg.0
0x1ed21  ldfld    string Microsoft.Crm.Application.Components.UI.LookupItem::_name
0x1ed26  br.s     loc_1ED37
0x1ed28  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1ed2d  ldstr    aInlineeditcont_0// "InlineEditControls.InlineLookup.NoName"
0x1ed32  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1ed37  ldarg.1
0x1ed38  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string, class [mscorlib]System.IO.TextWriter)
0x1ed3d  ldarg.1
0x1ed3e  ldstr    aDiv// "</div>"
0x1ed43  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1ed48  ldarg.1
0x1ed49  ldstr    aLiStyleDisplay// "<LI style=\"display:inline;white-space:"...
0x1ed4e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1ed53  ldarg.0
0x1ed54  ldfld    string Microsoft.Crm.Application.Components.UI.LookupItem::_name
0x1ed59  ldarg.1
0x1ed5a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string, class [mscorlib]System.IO.TextWriter)
0x1ed5f  ldarg.1
0x1ed60  ldstr    asc_32802// "\""
0x1ed65  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1ed6a  ldarg.0
0x1ed6b  ldfld    string Microsoft.Crm.Application.Components.UI.LookupItem::_style
0x1ed70  brfalse.s loc_1ED91
0x1ed72  ldarg.0
0x1ed73  ldfld    string Microsoft.Crm.Application.Components.UI.LookupItem::_style
0x1ed78  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1ed7d  ldc.i4.0
0x1ed7e  ble.s    loc_1ED91
0x1ed80  ldstr    aClass_1// "class"
0x1ed85  ldarg.0
0x1ed86  ldfld    string Microsoft.Crm.Application.Components.UI.LookupItem::_style
0x1ed8b  ldarg.1
0x1ed8c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x1ed91  ldarg.0
0x1ed92  ldfld    string Microsoft.Crm.Application.Components.UI.LookupItem::_category
0x1ed97  brfalse.s loc_1EDAA
0x1ed99  ldstr    aCategory// "category"
0x1ed9e  ldarg.0
0x1ed9f  ldfld    string Microsoft.Crm.Application.Components.UI.LookupItem::_category
0x1eda4  ldarg.1
0x1eda5  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x1edaa  ldarg.0
0x1edab  ldfld    string Microsoft.Crm.Application.Components.UI.LookupItem::_callback
0x1edb0  brfalse.s loc_1EDC3
0x1edb2  ldstr    aOnclick_0// "onclick"
0x1edb7  ldarg.0
0x1edb8  ldfld    string Microsoft.Crm.Application.Components.UI.LookupItem::_callback
0x1edbd  ldarg.1
0x1edbe  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x1edc3  ldarg.0
0x1edc4  call     instance bool Microsoft.Crm.Application.Components.UI.LookupItem::get_ShowPreviewOnRightClick()
0x1edc9  brfalse.s loc_1EDDC
0x1edcb  ldarg.1
0x1edcc  ldstr    aOncontextmenu// "oncontextmenu"
0x1edd1  ldstr    aHandlegridrigh// "handleGridRightClick(new Sys.UI.DomEven"...
0x1edd6  ldc.i4.0
0x1edd7  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1eddc  ldarg.0
0x1eddd  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x1ede2  brfalse.s loc_1EE1D
0x1ede4  ldarg.0
0x1ede5  callvirt instance int32 Microsoft.Crm.Application.Components.UI.CrmUIControl::get_TabIndex()
0x1edea  ldc.i4.0
0x1edeb  blt.s    loc_1EE1D
0x1eded  ldarg.1
0x1edee  ldstr    aTabindex_1// "TabIndex"
0x1edf3  ldarg.0
0x1edf4  callvirt instance int32 Microsoft.Crm.Application.Components.UI.CrmUIControl::get_TabIndex()
0x1edf9  stloc.0
0x1edfa  ldloca.s 0
0x1edfc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1ee01  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1ee06  ldc.i4.0
0x1ee07  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1ee0c  ldarg.1
0x1ee0d  ldstr    aOnkeydown// "onkeydown"
0x1ee12  ldstr    aOpendisabledlu// "openDisabledLui(new Sys.UI.DomEvent(eve"...
0x1ee17  ldc.i4.0
0x1ee18  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1ee1d  ldarg.0
0x1ee1e  ldfld    string Microsoft.Crm.Application.Components.UI.LookupItem::_data
0x1ee23  brfalse.s loc_1EE36
0x1ee25  ldstr    aData_0// "data"
0x1ee2a  ldarg.0
0x1ee2b  ldfld    string Microsoft.Crm.Application.Components.UI.LookupItem::_data
0x1ee30  ldarg.1
0x1ee31  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x1ee36  ldarg.0
0x1ee37  ldfld    string Microsoft.Crm.Application.Components.UI.LookupItem::_isProcessEnabled
0x1ee3c  brfalse.s loc_1EE4F
0x1ee3e  ldstr    aIsprocessenabl// "isprocessenabled"
0x1ee43  ldarg.0
0x1ee44  ldfld    string Microsoft.Crm.Application.Components.UI.LookupItem::_isProcessEnabled
0x1ee49  ldarg.1
0x1ee4a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x1ee4f  ldarg.1
0x1ee50  ldarg.0
0x1ee51  callvirt instance string Microsoft.Crm.Application.Components.UI.CrmUIControl::get_Expandos()
0x1ee56  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1ee5b  ldarg.1
0x1ee5c  ldc.i4.s 0x3E
0x1ee5e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x1ee63  ldarg.0
0x1ee64  callvirt instance bool Microsoft.Crm.Application.Components.UI.LookupItem::get_IsMultiLookupItem()
0x1ee69  brfalse.s loc_1EE76
0x1ee6b  ldarg.1
0x1ee6c  ldstr    aSpanContentedi// "<SPAN contentEditable=\"false\" unselec"...
0x1ee71  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1ee76  ldarg.0
0x1ee77  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.Components.UI.LookupItem::_icon
0x1ee7c  brfalse.s loc_1EEB8
0x1ee7e  ldarg.0
0x1ee7f  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.Components.UI.LookupItem::_icon
0x1ee84  newobj   instance void Microsoft.Crm.Application.Components.UI.ImageStripImage::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri source)
0x1ee89  stloc.1
0x1ee8a  ldloc.1
0x1ee8b  ldstr    aAlt// "alt"
0x1ee90  ldsfld   string [mscorlib]System.String::Empty
0x1ee95  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string name, string value)
0x1ee9a  ldloc.1
0x1ee9b  ldstr    aMsCrmLookupIte// "ms-crm-Lookup-Item"
0x1eea0  callvirt instance void Microsoft.Crm.Application.Components.UI.ImageStripImage::set_CssClass(string value)
0x1eea5  ldloc.1
0x1eea6  ldarg.1
0x1eea7  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x1eeac  leave.s  loc_1EEB8
0x1eeae  ldloc.1
0x1eeaf  brfalse.s loc_1EEB7
0x1eeb1  ldloc.1
0x1eeb2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1eeb7  endfinally
0x1eeb8  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x1eebd  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x1eec2  brfalse  loc_1F008
0x1eec7  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x1eecc  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x1eed1  callvirt instance class [System.Web]System.Web.HttpBrowserCapabilities [System.Web]System.Web.HttpRequest::get_Browser()
0x1eed6  callvirt instance string [System.Web]System.Web.Configuration.HttpCapabilitiesBase::get_Browser()
0x1eedb  callvirt instance string [mscorlib]System.String::ToLower()
0x1eee0  callvirt instance string [mscorlib]System.Object::ToString()
0x1eee5  ldstr    aSafari// "safari"
0x1eeea  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1eeef  brfalse  loc_1EF9C
0x1eef4  ldarg.1
0x1eef5  ldstr    aSpanWrapperTru// "<SPAN wrapper='true' tabindex='0'>"
0x1eefa  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1eeff  ldarg.1
0x1ef00  ldstr    aSpanIdLblreadS// "<span id='lblread' style='position: abs"...
0x1ef05  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1ef0a  ldarg.1
0x1ef0b  ldstr    aSpanClassMsCrm_1// "<SPAN class='ms-crm-LookupItem-Name' wr"...
0x1ef10  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1ef15  ldarg.1
0x1ef16  ldarg.0
0x1ef17  ldfld    string Microsoft.Crm.Application.Components.UI.LookupItem::_name
0x1ef1c  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x1ef21  brtrue.s loc_1EF2B
0x1ef23  ldarg.0
0x1ef24  ldfld    string Microsoft.Crm.Application.Components.UI.LookupItem::_name
0x1ef29  br.s     loc_1EF3A
0x1ef2b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1ef30  ldstr    aInlineeditcont_0// "InlineEditControls.InlineLookup.NoName"
0x1ef35  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1ef3a  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x1ef3f  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1ef44  ldarg.1
0x1ef45  ldstr    asc_2B834// "'>"
0x1ef4a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1ef4f  ldarg.0
0x1ef50  ldfld    string Microsoft.Crm.Application.Components.UI.LookupItem::_name
0x1ef55  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x1ef5a  brtrue.s loc_1EF64
0x1ef5c  ldarg.0
0x1ef5d  ldfld    string Microsoft.Crm.Application.Components.UI.LookupItem::_name
0x1ef62  br.s     loc_1EF73
0x1ef64  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1ef69  ldstr    aInlineeditcont_0// "InlineEditControls.InlineLookup.NoName"
0x1ef6e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1ef73  ldarg.1
0x1ef74  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string, class [mscorlib]System.IO.TextWriter)
0x1ef79  ldarg.1
0x1ef7a  ldstr    aSpan_6// "</SPAN>"
0x1ef7f  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1ef84  ldarg.1
0x1ef85  ldstr    aSpan_6// "</SPAN>"
0x1ef8a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1ef8f  ldarg.1
0x1ef90  ldstr    aSpan_6// "</SPAN>"
0x1ef95  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1ef9a  br.s     loc_1F008
0x1ef9c  ldarg.1
0x1ef9d  ldstr    aSpanWrapperTru// "<SPAN wrapper='true' tabindex='0'>"
0x1efa2  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1efa7  ldarg.1
0x1efa8  ldstr    aSpanClassMsCrm_2// "<span class=\"ms-crm-Hidden-NoBehavior"...
0x1efad  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1efb2  ldarg.1
0x1efb3  ldstr    aSpanClassMsCrm_3// "<SPAN class='ms-crm-LookupItem-Name' wr"...
0x1efb8  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1efbd  ldarg.0
0x1efbe  ldfld    string Microsoft.Crm.Application.Components.UI.LookupItem::_name
0x1efc3  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x1efc8  brtrue.s loc_1EFD2
0x1efca  ldarg.0
0x1efcb  ldfld    string Microsoft.Crm.Application.Components.UI.LookupItem::_name
0x1efd0  br.s     loc_1EFE1
0x1efd2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1efd7  ldstr    aInlineeditcont_0// "InlineEditControls.InlineLookup.NoName"
0x1efdc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1efe1  ldarg.1
0x1efe2  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string, class [mscorlib]System.IO.TextWriter)
0x1efe7  ldarg.1
0x1efe8  ldstr    aSpan_6// "</SPAN>"
0x1efed  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1eff2  ldarg.1
0x1eff3  ldstr    aSpan_6// "</SPAN>"
0x1eff8  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1effd  ldarg.1
0x1effe  ldstr    aSpan_6// "</SPAN>"
0x1f003  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1f008  ldarg.0
0x1f009  callvirt instance bool Microsoft.Crm.Application.Components.UI.LookupItem::get_IsMultiLookupItem()
0x1f00e  brfalse.s loc_1F01B
0x1f010  ldarg.1
0x1f011  ldstr    aSpan_6// "</SPAN>"
0x1f016  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1f01b  ldarg.1
0x1f01c  ldstr    aSpanLi// "</SPAN></LI>"
0x1f021  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1f026  ret
```
