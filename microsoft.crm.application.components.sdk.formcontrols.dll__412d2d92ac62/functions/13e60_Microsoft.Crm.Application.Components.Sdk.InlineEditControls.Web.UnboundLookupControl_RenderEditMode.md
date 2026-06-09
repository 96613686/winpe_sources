# Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.UnboundLookupControl::RenderEditMode

- ea: `0x13e60`
- end: `0x14419`
- name: `Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.UnboundLookupControl::RenderEditMode`
- size: `1465`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x2ea0`

## pseudocode

```c

```

## disassembly

```asm
0x13e60  ldarg.1
0x13e61  ldstr    aDiv// "div"
0x13e66  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x13e6b  ldarg.1
0x13e6c  ldstr    aClass// "class"
0x13e71  ldstr    aMsCrmInlineEdi_3// "ms-crm-Inline-Edit ms-crm-Inline-Lookup"
0x13e76  ldc.i4.0
0x13e77  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x13e7c  ldarg.1
0x13e7d  ldstr    aStyle// "style"
0x13e82  ldstr    aDisplayNone_0// "display: none;"
0x13e87  ldc.i4.0
0x13e88  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x13e8d  ldarg.1
0x13e8e  ldstr    aLookuptypes// "lookuptypes"
0x13e93  ldarg.0
0x13e94  callvirt instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.LookupControl::get_UnboundLookupTypes()
0x13e99  ldc.i4.0
0x13e9a  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x13e9f  ldarg.1
0x13ea0  ldc.i4.s 0x3E
0x13ea2  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x13ea7  ldarg.1
0x13ea8  ldstr    aTable// "table"
0x13ead  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x13eb2  ldstr    aId// "id"
0x13eb7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x13ebc  ldstr    a0Lookuptable// "{0}_lookupTable"
0x13ec1  ldc.i4.1
0x13ec2  newarr   [mscorlib]System.Object
0x13ec7  dup
0x13ec8  ldc.i4.0
0x13ec9  ldarg.0
0x13eca  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x13ecf  stelem.ref
0x13ed0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x13ed5  ldarg.1
0x13ed6  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x13edb  ldarg.1
0x13edc  ldstr    aCellpadding// "cellpadding"
0x13ee1  ldstr    a0// "0"
0x13ee6  ldc.i4.0
0x13ee7  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x13eec  ldarg.1
0x13eed  ldstr    aCellspacing// "cellspacing"
0x13ef2  ldstr    a0// "0"
0x13ef7  ldc.i4.0
0x13ef8  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x13efd  ldstr    aLookupid// "lookupid"
0x13f02  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x13f07  ldstr    a0_1// "{0}"
0x13f0c  ldc.i4.1
0x13f0d  newarr   [mscorlib]System.Object
0x13f12  dup
0x13f13  ldc.i4.0
0x13f14  ldarg.0
0x13f15  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x13f1a  stelem.ref
0x13f1b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x13f20  ldarg.1
0x13f21  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x13f26  ldarg.1
0x13f27  ldstr    aClass// "class"
0x13f2c  ldstr    aMsCrmLookup// "ms-crm-Lookup"
0x13f31  ldc.i4.0
0x13f32  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x13f37  ldstr    aAriaLabelledby// "aria-labelledby"
0x13f3c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x13f41  ldstr    a0C0W// "{0}_c {0}_w"
0x13f46  ldc.i4.1
0x13f47  newarr   [mscorlib]System.Object
0x13f4c  dup
0x13f4d  ldc.i4.0
0x13f4e  ldarg.0
0x13f4f  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x13f54  stelem.ref
0x13f55  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x13f5a  ldarg.1
0x13f5b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x13f60  ldarg.1
0x13f61  ldstr    aControlmode_0// "controlmode"
0x13f66  ldstr    aNormal// "normal"
0x13f6b  ldc.i4.0
0x13f6c  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x13f71  ldarg.1
0x13f72  ldstr    aStyle// "style"
0x13f77  ldstr    aWidth100TableL_0// "width: 100%;table-layout: fixed;"
0x13f7c  ldc.i4.0
0x13f7d  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x13f82  ldarg.1
0x13f83  ldc.i4.s 0x3E
0x13f85  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x13f8a  ldarg.1
0x13f8b  ldstr    aTbody// "tbody"
0x13f90  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x13f95  ldarg.1
0x13f96  ldc.i4.s 0x3E
0x13f98  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x13f9d  ldarg.1
0x13f9e  ldstr    aTr_0// "tr"
0x13fa3  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x13fa8  ldarg.1
0x13fa9  ldc.i4.s 0x3E
0x13fab  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x13fb0  ldarg.1
0x13fb1  ldstr    aTd_0// "td"
0x13fb6  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x13fbb  ldarg.1
0x13fbc  ldstr    aValign// "valign"
0x13fc1  ldstr    aTop// "top"
0x13fc6  ldc.i4.0
0x13fc7  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x13fcc  ldarg.1
0x13fcd  ldc.i4.s 0x3E
0x13fcf  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x13fd4  ldarg.1
0x13fd5  ldstr    aDiv// "div"
0x13fda  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x13fdf  ldstr    aId// "id"
0x13fe4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x13fe9  ldstr    a0Lookupdiv// "{0}_lookupDiv"
0x13fee  ldc.i4.1
0x13fef  newarr   [mscorlib]System.Object
0x13ff4  dup
0x13ff5  ldc.i4.0
0x13ff6  ldarg.0
0x13ff7  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x13ffc  stelem.ref
0x13ffd  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x14002  ldarg.1
0x14003  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x14008  ldarg.1
0x14009  ldstr    aRole// "role"
0x1400e  ldstr    aList// "list"
0x14013  ldc.i4.0
0x14014  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x14019  ldarg.1
0x1401a  ldstr    aImeMode// "ime-mode"
0x1401f  ldstr    aAuto// "auto"
0x14024  ldc.i4.0
0x14025  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1402a  ldarg.1
0x1402b  ldstr    aClass// "class"
0x14030  ldstr    aMsCrmLookupMsC// "ms-crm-Lookup ms-crm-InlineLookupEdit"
0x14035  ldc.i4.0
0x14036  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1403b  ldarg.1
0x1403c  ldstr    aTabindex// "tabindex"
0x14041  ldstr    a0// "0"
0x14046  ldc.i4.0
0x14047  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1404c  ldarg.1
0x1404d  ldc.i4.s 0x3E
0x1404f  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x14054  ldarg.1
0x14055  ldstr    aUl// "ul"
0x1405a  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x1405f  ldarg.1
0x14060  ldstr    aClass// "class"
0x14065  ldstr    aMsCrmInlineloo// "ms-crm-InlineLookupEdit"
0x1406a  ldc.i4.0
0x1406b  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x14070  ldarg.1
0x14071  ldc.i4.s 0x3E
0x14073  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x14078  ldarg.1
0x14079  ldstr    aLi// "li"
0x1407e  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x14083  ldarg.1
0x14084  ldstr    aStyle// "style"
0x14089  ldstr    aDisplayInlineW// "display: inline; white-space: nowrap;"
0x1408e  ldc.i4.0
0x1408f  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x14094  ldarg.1
0x14095  ldc.i4.s 0x3E
0x14097  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x1409c  ldarg.1
0x1409d  ldstr    aSpan// "span"
0x140a2  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x140a7  ldarg.1
0x140a8  ldstr    aClass// "class"
0x140ad  ldstr    aMsCrmLookupIte_0// "ms-crm-Lookup-Item"
0x140b2  ldc.i4.0
0x140b3  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x140b8  ldarg.1
0x140b9  ldstr    aContenteditabl// "contentEditable"
0x140be  ldstr    aFalse// "false"
0x140c3  ldc.i4.0
0x140c4  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x140c9  ldarg.1
0x140ca  ldstr    aIsinlinelookup// "isInlineLookup"
0x140cf  ldstr    aTrue// "true"
0x140d4  ldc.i4.0
0x140d5  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x140da  ldarg.1
0x140db  ldc.i4.s 0x3E
0x140dd  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x140e2  ldarg.1
0x140e3  ldstr    aSpan// "span"
0x140e8  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x140ed  ldarg.1
0x140ee  ldstr    aClass// "class"
0x140f3  ldstr    aMsCrmLookupite// "ms-crm-LookupItem-Name"
0x140f8  ldc.i4.0
0x140f9  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x140fe  ldstr    aId// "id"
0x14103  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x14108  ldstr    a0Lookupeditspa// "{0}_lookupEditSpan"
0x1410d  ldc.i4.1
0x1410e  newarr   [mscorlib]System.Object
0x14113  dup
0x14114  ldc.i4.0
0x14115  ldarg.0
0x14116  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1411b  stelem.ref
0x1411c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x14121  ldarg.1
0x14122  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x14127  ldarg.1
0x14128  ldc.i4.s 0x3E
0x1412a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x1412f  ldarg.1
0x14130  ldstr    aSpan// "span"
0x14135  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x1413a  ldarg.1
0x1413b  ldstr    aSpan// "span"
0x14140  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x14145  ldarg.1
0x14146  ldstr    aLi// "li"
0x1414b  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x14150  ldarg.1
0x14151  ldstr    aUl// "ul"
0x14156  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x1415b  ldarg.1
0x1415c  ldstr    aDiv// "div"
0x14161  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x14166  ldarg.1
0x14167  ldstr    aLabel_0// "label"
0x1416c  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x14171  ldarg.1
0x14172  ldstr    aClass// "class"
0x14177  ldstr    aMsCrmHiddenNob// "ms-crm-Hidden-NoBehavior"
0x1417c  ldc.i4.0
0x1417d  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x14182  ldstr    aFor// "for"
0x14187  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1418c  ldstr    a0Ledit// "{0}_ledit"
0x14191  ldc.i4.1
0x14192  newarr   [mscorlib]System.Object
0x14197  dup
0x14198  ldc.i4.0
0x14199  ldarg.0
0x1419a  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1419f  stelem.ref
0x141a0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x141a5  ldarg.1
0x141a6  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x141ab  ldarg.1
0x141ac  ldc.i4.s 0x3E
0x141ae  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x141b3  ldarg.0
0x141b4  call     instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppControl::get_ControlLabel()
0x141b9  ldarg.1
0x141ba  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string, class [mscorlib]System.IO.TextWriter)
0x141bf  ldarg.1
0x141c0  ldstr    aLabel_0// "label"
0x141c5  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x141ca  ldarg.1
0x141cb  ldstr    aInput// "input"
0x141d0  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x141d5  ldarg.1
0x141d6  ldstr    aClass// "class"
0x141db  ldstr    aMsCrmInlineinp// "ms-crm-InlineInput ms-crm-InlineLookupE"...
0x141e0  ldc.i4.0
0x141e1  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x141e6  ldarg.1
0x141e7  ldstr    aImeMode// "ime-mode"
0x141ec  ldstr    aAuto// "auto"
0x141f1  ldc.i4.0
0x141f2  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x141f7  ldarg.1
0x141f8  ldstr    aType// "type"
0x141fd  ldstr    aText// "text"
0x14202  ldc.i4.0
0x14203  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x14208  ldstr    aId// "id"
0x1420d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x14212  ldstr    a0Ledit// "{0}_ledit"
0x14217  ldc.i4.1
0x14218  newarr   [mscorlib]System.Object
0x1421d  dup
0x1421e  ldc.i4.0
0x1421f  ldarg.0
0x14220  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x14225  stelem.ref
0x14226  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1422b  ldarg.1
0x1422c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x14231  ldarg.1
0x14232  ldstr    aMaxlength// "maxlength"
  ... truncated ...
```
