# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::RenderLookupItemForRead

- ea: `0x207b0`
- end: `0x209d4`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::RenderLookupItemForRead`
- size: `548`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x20450`

## callees

- `0x207b0`

## string_xrefs

- `0x2082e`: `ms-crm-Lookup-Item-Read`
- `0x208cd`: `Mscrm.ReadFormUtilities.keyDownHandler(new Sys.UI.DomEvent(event));`
- `0x2081c`: `ms-crm-Lookup-PartyItem-Unresolved-Read`
- `0x2088f`: `Mscrm.ReadFormUtilities.openLookup({0}, new Sys.UI.DomEvent(event))`
- `0x20927`: `openDisabledLui()`

## pseudocode

```c

```

## disassembly

```asm
0x207b0  ldarg.1
0x207b1  ldstr    aSpanContentedi// "<SPAN contentEditable=\"false\" title="...
0x207b6  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x207bb  ldarg.2
0x207bc  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LookupItem::get_Name()
0x207c1  ldarg.1
0x207c2  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string, class [mscorlib]System.IO.TextWriter)
0x207c7  ldarg.1
0x207c8  ldstr    asc_49832// "\""
0x207cd  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x207d2  ldarg.2
0x207d3  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LookupItem::get_Style()
0x207d8  brfalse.s loc_20839
0x207da  ldarg.2
0x207db  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LookupItem::get_Style()
0x207e0  callvirt instance int32 [mscorlib]System.String::get_Length()
0x207e5  ldc.i4.0
0x207e6  ble.s    loc_20839
0x207e8  ldarg.2
0x207e9  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LookupItem::get_Resolved()
0x207ee  stloc.0
0x207ef  ldloca.s 0
0x207f1  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x207f6  brfalse.s loc_20829
0x207f8  ldarg.2
0x207f9  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LookupItem::get_Resolved()
0x207fe  stloc.0
0x207ff  ldc.i4.0
0x20800  stloc.1
0x20801  ldloca.s 0
0x20803  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::GetValueOrDefault()
0x20808  ldloc.1
0x20809  beq.s    loc_2080E
0x2080b  ldc.i4.0
0x2080c  br.s     loc_20815
0x2080e  ldloca.s 0
0x20810  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x20815  brfalse.s loc_20829
0x20817  ldstr    aClass// "class"
0x2081c  ldstr    aMsCrmLookupPar// "ms-crm-Lookup-PartyItem-Unresolved-Read"
0x20821  ldarg.1
0x20822  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x20827  br.s     loc_20839
0x20829  ldstr    aClass// "class"
0x2082e  ldstr    aMsCrmLookupIte// "ms-crm-Lookup-Item-Read"
0x20833  ldarg.1
0x20834  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x20839  ldstr    aRole// "role"
0x2083e  ldstr    aLink// "link"
0x20843  ldarg.1
0x20844  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x20849  ldarg.2
0x2084a  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LookupItem::get_Callback()
0x2084f  brfalse  loc_208D8
0x20854  ldarg.2
0x20855  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LookupItem::get_Resolved()
0x2085a  stloc.0
0x2085b  ldloca.s 0
0x2085d  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x20862  brtrue.s loc_2086B
0x20864  ldstr    aTrue// "true"
0x20869  br.s     loc_20884
0x2086b  ldarg.2
0x2086c  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LookupItem::get_Resolved()
0x20871  stloc.0
0x20872  ldloca.s 0
0x20874  constrained. valuetype [mscorlib]System.Nullable`1<bool>
0x2087a  callvirt instance string [mscorlib]System.Object::ToString()
0x2087f  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x20884  stloc.2
0x20885  ldstr    aOnclick// "onclick"
0x2088a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2088f  ldstr    aMscrmReadformu_4// "Mscrm.ReadFormUtilities.openLookup({0},"...
0x20894  ldc.i4.1
0x20895  newarr   [mscorlib]System.Object
0x2089a  dup
0x2089b  ldc.i4.0
0x2089c  ldloc.2
0x2089d  stelem.ref
0x2089e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x208a3  ldarg.1
0x208a4  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x208a9  ldarg.1
0x208aa  ldstr    aTabindex// "tabindex"
0x208af  ldstr    a0// "0"
0x208b4  ldc.i4.0
0x208b5  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x208ba  ldarg.1
0x208bb  ldstr    aResolved// "resolved"
0x208c0  ldloc.2
0x208c1  ldc.i4.0
0x208c2  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x208c7  ldarg.1
0x208c8  ldstr    aOnkeydown// "onkeydown"
0x208cd  ldstr    aMscrmReadformu_1// "Mscrm.ReadFormUtilities.keyDownHandler("...
0x208d2  ldc.i4.0
0x208d3  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x208d8  ldarg.2
0x208d9  callvirt instance bool [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LookupItem::get_ShowPreviewOnRightClick()
0x208de  brfalse.s loc_208F1
0x208e0  ldarg.1
0x208e1  ldstr    aOncontextmenu// "oncontextmenu"
0x208e6  ldstr    aHandlegridrigh_0// "handleGridRightClick()"
0x208eb  ldc.i4.0
0x208ec  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x208f1  ldarg.2
0x208f2  callvirt instance bool [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x208f7  brfalse.s loc_20932
0x208f9  ldarg.2
0x208fa  callvirt instance int32 [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::get_TabIndex()
0x208ff  ldc.i4.0
0x20900  blt.s    loc_20932
0x20902  ldarg.1
0x20903  ldstr    aTabindex_2// "TabIndex"
0x20908  ldarg.2
0x20909  callvirt instance int32 [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::get_TabIndex()
0x2090e  stloc.3
0x2090f  ldloca.s 3
0x20911  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x20916  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x2091b  ldc.i4.0
0x2091c  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x20921  ldarg.1
0x20922  ldstr    aOnkeydown// "onkeydown"
0x20927  ldstr    aOpendisabledlu_0// "openDisabledLui()"
0x2092c  ldc.i4.0
0x2092d  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x20932  ldarg.2
0x20933  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LookupItem::get_Data()
0x20938  brfalse.s loc_2094B
0x2093a  ldstr    aData// "data"
0x2093f  ldarg.2
0x20940  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LookupItem::get_Data()
0x20945  ldarg.1
0x20946  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x2094b  ldarg.1
0x2094c  ldarg.2
0x2094d  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::get_Expandos()
0x20952  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x20957  ldarg.1
0x20958  ldc.i4.s 0x3E
0x2095a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x2095f  ldarg.3
0x20960  brfalse.s loc_2096D
0x20962  ldarg.1
0x20963  ldstr    aSpanContentedi_1// "<SPAN contentEditable=\"false\" unselec"...
0x20968  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2096d  ldarg.2
0x2096e  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LookupItem::get_Icon()
0x20973  brfalse.s loc_209AE
0x20975  ldarg.2
0x20976  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LookupItem::get_Icon()
0x2097b  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::IsEmpty()
0x20980  brtrue.s loc_209AE
0x20982  ldarg.1
0x20983  ldstr    aImgAltClassMsC// "<img alt=\"\" class=\"ms-crm-Lookup-Ite"...
0x20988  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2098d  ldarg.1
0x2098e  ldarg.2
0x2098f  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LookupItem::get_Icon()
0x20994  callvirt instance string [mscorlib]System.Object::ToString()
0x20999  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x2099e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x209a3  ldarg.1
0x209a4  ldstr    asc_319EC// "\">"
0x209a9  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x209ae  ldarg.2
0x209af  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LookupItem::get_Name()
0x209b4  ldarg.1
0x209b5  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string, class [mscorlib]System.IO.TextWriter)
0x209ba  ldarg.3
0x209bb  brfalse.s loc_209C8
0x209bd  ldarg.1
0x209be  ldstr    aSpan_3// "</SPAN>"
0x209c3  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x209c8  ldarg.1
0x209c9  ldstr    aSpan_3// "</SPAN>"
0x209ce  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x209d3  ret
```
