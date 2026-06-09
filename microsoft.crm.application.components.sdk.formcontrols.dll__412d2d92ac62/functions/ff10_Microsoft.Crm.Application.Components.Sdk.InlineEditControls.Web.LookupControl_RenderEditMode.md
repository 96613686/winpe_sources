# Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LookupControl::RenderEditMode

- ea: `0xff10`
- end: `0x10636`
- name: `Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LookupControl::RenderEditMode`
- size: `1830`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1450`
- `0x2f20`
- `0xff10`
- `0x18c50`
- `0x18d00`

## pseudocode

```c

```

## disassembly

```asm
0xff10  ldarg.1
0xff11  ldstr    aDiv// "div"
0xff16  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0xff1b  ldarg.1
0xff1c  ldstr    aClass// "class"
0xff21  ldstr    aMsCrmInlineEdi_3// "ms-crm-Inline-Edit ms-crm-Inline-Lookup"
0xff26  ldc.i4.0
0xff27  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0xff2c  ldarg.1
0xff2d  ldstr    aStyle// "style"
0xff32  ldstr    aDisplayNone_0// "display: none;"
0xff37  ldc.i4.0
0xff38  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0xff3d  ldarg.0
0xff3e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0xff43  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LookupAttributeMetadata
0xff48  stloc.0
0xff49  ldloc.0
0xff4a  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<int32> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LookupAttributeMetadata::get_LookupTypes()
0xff4f  brfalse.s loc_FF81
0xff51  ldloc.0
0xff52  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<int32> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LookupAttributeMetadata::get_LookupTypes()
0xff57  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<int32>::get_Count()
0xff5c  ldc.i4.0
0xff5d  ble.s    loc_FF81
0xff5f  ldarg.1
0xff60  ldstr    aLookuptypes// "lookuptypes"
0xff65  ldloc.0
0xff66  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<int32> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LookupAttributeMetadata::get_LookupTypes()
0xff6b  ldc.i4.0
0xff6c  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<int32>::get_Item(!!T0)
0xff71  box      [mscorlib]System.Int32
0xff76  call     string [mscorlib]System.String::Concat(object)
0xff7b  ldc.i4.0
0xff7c  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0xff81  ldarg.1
0xff82  ldc.i4.s 0x3E
0xff84  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0xff89  ldarg.1
0xff8a  ldstr    aTable// "table"
0xff8f  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0xff94  ldstr    aId// "id"
0xff99  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xff9e  ldstr    a0Lookuptable// "{0}_lookupTable"
0xffa3  ldc.i4.1
0xffa4  newarr   [mscorlib]System.Object
0xffa9  dup
0xffaa  ldc.i4.0
0xffab  ldarg.0
0xffac  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0xffb1  stelem.ref
0xffb2  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xffb7  ldarg.1
0xffb8  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0xffbd  ldarg.1
0xffbe  ldstr    aCellpadding// "cellpadding"
0xffc3  ldstr    a0// "0"
0xffc8  ldc.i4.0
0xffc9  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0xffce  ldarg.1
0xffcf  ldstr    aCellspacing// "cellspacing"
0xffd4  ldstr    a0// "0"
0xffd9  ldc.i4.0
0xffda  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0xffdf  ldstr    aLookupid// "lookupid"
0xffe4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xffe9  ldstr    a0_1// "{0}"
0xffee  ldc.i4.1
0xffef  newarr   [mscorlib]System.Object
0xfff4  dup
0xfff5  ldc.i4.0
0xfff6  ldarg.0
0xfff7  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0xfffc  stelem.ref
0xfffd  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x10002  ldarg.1
0x10003  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x10008  ldarg.1
0x10009  ldstr    aClass// "class"
0x1000e  ldstr    aMsCrmLookup// "ms-crm-Lookup"
0x10013  ldc.i4.0
0x10014  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x10019  ldstr    aAriaLabelledby// "aria-labelledby"
0x1001e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x10023  ldstr    a0C0W// "{0}_c {0}_w"
0x10028  ldc.i4.1
0x10029  newarr   [mscorlib]System.Object
0x1002e  dup
0x1002f  ldc.i4.0
0x10030  ldarg.0
0x10031  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x10036  stelem.ref
0x10037  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1003c  ldarg.1
0x1003d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x10042  ldarg.1
0x10043  ldstr    aControlmode_0// "controlmode"
0x10048  ldstr    aNormal// "normal"
0x1004d  ldc.i4.0
0x1004e  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x10053  ldarg.1
0x10054  ldstr    aStyle// "style"
0x10059  ldstr    aWidth100TableL_0// "width: 100%;table-layout: fixed;"
0x1005e  ldc.i4.0
0x1005f  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x10064  ldarg.1
0x10065  ldc.i4.s 0x3E
0x10067  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x1006c  ldarg.1
0x1006d  ldstr    aTbody// "tbody"
0x10072  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x10077  ldarg.1
0x10078  ldc.i4.s 0x3E
0x1007a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x1007f  ldarg.1
0x10080  ldstr    aTr_0// "tr"
0x10085  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x1008a  ldarg.1
0x1008b  ldc.i4.s 0x3E
0x1008d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x10092  ldarg.1
0x10093  ldstr    aTd_0// "td"
0x10098  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x1009d  ldarg.1
0x1009e  ldstr    aValign// "valign"
0x100a3  ldstr    aTop// "top"
0x100a8  ldc.i4.0
0x100a9  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x100ae  ldarg.1
0x100af  ldc.i4.s 0x3E
0x100b1  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x100b6  ldarg.1
0x100b7  ldstr    aDiv// "div"
0x100bc  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x100c1  ldstr    aId// "id"
0x100c6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x100cb  ldstr    a0Lookupdiv// "{0}_lookupDiv"
0x100d0  ldc.i4.1
0x100d1  newarr   [mscorlib]System.Object
0x100d6  dup
0x100d7  ldc.i4.0
0x100d8  ldarg.0
0x100d9  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x100de  stelem.ref
0x100df  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x100e4  ldarg.1
0x100e5  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x100ea  ldstr    aMulti// "multi"
0x100ef  ldarg.0
0x100f0  callvirt instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.LookupControl::get_LookupStyle()
0x100f5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x100fa  brfalse.s loc_1010D
0x100fc  ldarg.1
0x100fd  ldstr    aRole// "role"
0x10102  ldstr    aList// "list"
0x10107  ldc.i4.0
0x10108  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1010d  ldarg.1
0x1010e  ldstr    aImeMode// "ime-mode"
0x10113  ldstr    aAuto// "auto"
0x10118  ldc.i4.0
0x10119  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1011e  ldarg.1
0x1011f  ldstr    aClass// "class"
0x10124  ldstr    aMsCrmLookupMsC// "ms-crm-Lookup ms-crm-InlineLookupEdit"
0x10129  ldc.i4.0
0x1012a  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1012f  ldarg.1
0x10130  ldstr    aTabindex// "tabindex"
0x10135  ldstr    a0// "0"
0x1013a  ldc.i4.0
0x1013b  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x10140  call     bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControlHelper::IsIE()
0x10145  brtrue.s loc_1014E
0x10147  call     bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControlHelper::IsSafari()
0x1014c  brfalse.s loc_10179
0x1014e  ldstr    aAriaLabelledby// "aria-labelledby"
0x10153  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x10158  ldstr    a0C0Lookupedit// "{0}_c {0}_lookupedit"
0x1015d  ldc.i4.1
0x1015e  newarr   [mscorlib]System.Object
0x10163  dup
0x10164  ldc.i4.0
0x10165  ldarg.0
0x10166  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1016b  stelem.ref
0x1016c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x10171  ldarg.1
0x10172  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x10177  br.s     loc_101A2
0x10179  ldstr    aAriaLabelledby// "aria-labelledby"
0x1017e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x10183  ldstr    a0Lookupedit// "{0}_lookupedit"
0x10188  ldc.i4.1
0x10189  newarr   [mscorlib]System.Object
0x1018e  dup
0x1018f  ldc.i4.0
0x10190  ldarg.0
0x10191  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x10196  stelem.ref
0x10197  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1019c  ldarg.1
0x1019d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x101a2  ldloc.0
0x101a3  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_AttributeRequiredLevelId()
0x101a8  ldc.i4.2
0x101a9  beq.s    loc_101B4
0x101ab  ldloc.0
0x101ac  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_AttributeRequiredLevelId()
0x101b1  ldc.i4.1
0x101b2  bne.un.s loc_101C5
0x101b4  ldarg.1
0x101b5  ldstr    aAriaRequired// "aria-required"
0x101ba  ldstr    aTrue// "true"
0x101bf  ldc.i4.0
0x101c0  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x101c5  ldarg.1
0x101c6  ldc.i4.s 0x3E
0x101c8  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x101cd  ldarg.1
0x101ce  ldstr    aUl// "ul"
0x101d3  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x101d8  ldarg.1
0x101d9  ldstr    aClass// "class"
0x101de  ldstr    aMsCrmInlineloo// "ms-crm-InlineLookupEdit"
0x101e3  ldc.i4.0
0x101e4  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x101e9  ldarg.1
0x101ea  ldc.i4.s 0x3E
0x101ec  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x101f1  ldarg.1
0x101f2  ldstr    aLi// "li"
0x101f7  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x101fc  ldarg.1
0x101fd  ldstr    aStyle// "style"
0x10202  ldstr    aDisplayInlineW// "display: inline; white-space: nowrap;"
0x10207  ldc.i4.0
0x10208  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1020d  ldarg.1
0x1020e  ldc.i4.s 0x3E
0x10210  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x10215  ldarg.1
0x10216  ldstr    aSpan// "span"
0x1021b  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x10220  ldarg.1
0x10221  ldstr    aClass// "class"
0x10226  ldstr    aMsCrmLookupIte_0// "ms-crm-Lookup-Item"
0x1022b  ldc.i4.0
0x1022c  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x10231  ldarg.1
0x10232  ldstr    aContenteditabl// "contentEditable"
0x10237  ldstr    aFalse// "false"
0x1023c  ldc.i4.0
0x1023d  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x10242  ldarg.1
0x10243  ldstr    aIsinlinelookup// "isInlineLookup"
0x10248  ldstr    aTrue// "true"
0x1024d  ldc.i4.0
0x1024e  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x10253  ldarg.1
0x10254  ldc.i4.s 0x3E
0x10256  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x1025b  ldarg.1
0x1025c  ldstr    aSpan// "span"
0x10261  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x10266  ldarg.1
0x10267  ldstr    aClass// "class"
0x1026c  ldstr    aMsCrmLookupite// "ms-crm-LookupItem-Name"
0x10271  ldc.i4.0
0x10272  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x10277  ldstr    aId// "id"
0x1027c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x10281  ldstr    a0Lookupeditspa// "{0}_lookupEditSpan"
0x10286  ldc.i4.1
0x10287  newarr   [mscorlib]System.Object
0x1028c  dup
0x1028d  ldc.i4.0
0x1028e  ldarg.0
0x1028f  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x10294  stelem.ref
0x10295  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1029a  ldarg.1
0x1029b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x102a0  ldarg.1
0x102a1  ldc.i4.s 0x3E
0x102a3  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x102a8  ldarg.1
0x102a9  ldstr    aSpan// "span"
0x102ae  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x102b3  ldarg.1
0x102b4  ldstr    aSpan// "span"
0x102b9  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x102be  ldarg.1
0x102bf  ldstr    aLi// "li"
0x102c4  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x102c9  ldarg.1
0x102ca  ldstr    aUl// "ul"
0x102cf  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x102d4  ldarg.1
0x102d5  ldstr    aDiv// "div"
  ... truncated ...
```
