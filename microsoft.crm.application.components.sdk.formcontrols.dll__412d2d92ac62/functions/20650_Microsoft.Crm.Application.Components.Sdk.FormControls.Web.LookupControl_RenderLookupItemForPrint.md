# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::RenderLookupItemForPrint

- ea: `0x20650`
- end: `0x207ae`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::RenderLookupItemForPrint`
- size: `350`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x20590`

## callees

- `0x20650`

## string_xrefs

- `0x20701`: `openDisabledLui(new Sys.UI.DomEvent(event))`

## pseudocode

```c

```

## disassembly

```asm
0x20650  ldarg.1
0x20651  ldstr    aSpanContentedi// "<SPAN contentEditable=\"false\" title="...
0x20656  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2065b  ldarg.2
0x2065c  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LookupItem::get_Name()
0x20661  ldarg.1
0x20662  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string, class [mscorlib]System.IO.TextWriter)
0x20667  ldarg.1
0x20668  ldstr    asc_49832// "\""
0x2066d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x20672  ldarg.2
0x20673  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LookupItem::get_Style()
0x20678  brfalse.s loc_20699
0x2067a  ldarg.2
0x2067b  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LookupItem::get_Style()
0x20680  callvirt instance int32 [mscorlib]System.String::get_Length()
0x20685  ldc.i4.0
0x20686  ble.s    loc_20699
0x20688  ldstr    aClass// "class"
0x2068d  ldarg.2
0x2068e  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LookupItem::get_Style()
0x20693  ldarg.1
0x20694  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x20699  ldarg.2
0x2069a  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LookupItem::get_Callback()
0x2069f  brfalse.s loc_206B2
0x206a1  ldstr    aOnclick// "onclick"
0x206a6  ldarg.2
0x206a7  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LookupItem::get_Callback()
0x206ac  ldarg.1
0x206ad  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x206b2  ldarg.2
0x206b3  callvirt instance bool [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LookupItem::get_ShowPreviewOnRightClick()
0x206b8  brfalse.s loc_206CB
0x206ba  ldarg.1
0x206bb  ldstr    aOncontextmenu// "oncontextmenu"
0x206c0  ldstr    aHandlegridrigh// "handleGridRightClick(new Sys.UI.DomEven"...
0x206c5  ldc.i4.0
0x206c6  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x206cb  ldarg.2
0x206cc  callvirt instance bool [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x206d1  brfalse.s loc_2070C
0x206d3  ldarg.2
0x206d4  callvirt instance int32 [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::get_TabIndex()
0x206d9  ldc.i4.0
0x206da  blt.s    loc_2070C
0x206dc  ldarg.1
0x206dd  ldstr    aTabindex_2// "TabIndex"
0x206e2  ldarg.2
0x206e3  callvirt instance int32 [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::get_TabIndex()
0x206e8  stloc.0
0x206e9  ldloca.s 0
0x206eb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x206f0  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x206f5  ldc.i4.0
0x206f6  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x206fb  ldarg.1
0x206fc  ldstr    aOnkeydown// "onkeydown"
0x20701  ldstr    aOpendisabledlu// "openDisabledLui(new Sys.UI.DomEvent(eve"...
0x20706  ldc.i4.0
0x20707  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x2070c  ldarg.2
0x2070d  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LookupItem::get_Data()
0x20712  brfalse.s loc_20725
0x20714  ldstr    aData// "data"
0x20719  ldarg.2
0x2071a  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LookupItem::get_Data()
0x2071f  ldarg.1
0x20720  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x20725  ldarg.1
0x20726  ldarg.2
0x20727  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::get_Expandos()
0x2072c  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x20731  ldarg.1
0x20732  ldc.i4.s 0x3E
0x20734  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x20739  ldarg.3
0x2073a  brfalse.s loc_20747
0x2073c  ldarg.1
0x2073d  ldstr    aSpanContentedi_0// "<SPAN contentEditable=\"false\" unselec"...
0x20742  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x20747  ldarg.2
0x20748  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LookupItem::get_Icon()
0x2074d  brfalse.s loc_20788
0x2074f  ldarg.2
0x20750  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LookupItem::get_Icon()
0x20755  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::IsEmpty()
0x2075a  brtrue.s loc_20788
0x2075c  ldarg.1
0x2075d  ldstr    aImgAltClassMsC// "<img alt=\"\" class=\"ms-crm-Lookup-Ite"...
0x20762  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x20767  ldarg.1
0x20768  ldarg.2
0x20769  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LookupItem::get_Icon()
0x2076e  callvirt instance string [mscorlib]System.Object::ToString()
0x20773  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x20778  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2077d  ldarg.1
0x2077e  ldstr    asc_319EC// "\">"
0x20783  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x20788  ldarg.2
0x20789  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LookupItem::get_Name()
0x2078e  ldarg.1
0x2078f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string, class [mscorlib]System.IO.TextWriter)
0x20794  ldarg.3
0x20795  brfalse.s loc_207A2
0x20797  ldarg.1
0x20798  ldstr    aSpan_3// "</SPAN>"
0x2079d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x207a2  ldarg.1
0x207a3  ldstr    aSpan_3// "</SPAN>"
0x207a8  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x207ad  ret
```
