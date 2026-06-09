# Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.UnboundDateTimeControl::RenderEditMode

- ea: `0x12b90`
- end: `0x12fe9`
- name: `Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.UnboundDateTimeControl::RenderEditMode`
- size: `1113`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x9860`
- `0x9d30`
- `0x12b90`

## pseudocode

```c

```

## disassembly

```asm
0x12b90  ldarg.1
0x12b91  ldstr    aDiv// "div"
0x12b96  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x12b9b  ldarg.1
0x12b9c  ldstr    aClass// "class"
0x12ba1  ldstr    aMsCrmInlineEdi_1// "ms-crm-Inline-Edit"
0x12ba6  ldc.i4.0
0x12ba7  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x12bac  ldarg.1
0x12bad  ldstr    aStyle// "style"
0x12bb2  ldstr    aDisplayNone_0// "display: none;"
0x12bb7  ldc.i4.0
0x12bb8  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x12bbd  ldarg.1
0x12bbe  ldc.i4.s 0x3E
0x12bc0  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x12bc5  ldarg.1
0x12bc6  ldstr    aTable// "table"
0x12bcb  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x12bd0  ldstr    aId// "id"
0x12bd5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x12bda  ldstr    a0I// "{0}_i"
0x12bdf  ldc.i4.1
0x12be0  newarr   [mscorlib]System.Object
0x12be5  dup
0x12be6  ldc.i4.0
0x12be7  ldarg.0
0x12be8  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x12bed  stelem.ref
0x12bee  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x12bf3  ldarg.1
0x12bf4  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x12bf9  ldarg.1
0x12bfa  ldstr    aCellspacing// "cellspacing"
0x12bff  ldstr    a0// "0"
0x12c04  ldc.i4.0
0x12c05  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x12c0a  ldarg.1
0x12c0b  ldstr    aCellpadding// "cellpadding"
0x12c10  ldstr    a0// "0"
0x12c15  ldc.i4.0
0x12c16  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x12c1b  ldstr    aAttrname// "attrname"
0x12c20  ldarg.0
0x12c21  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x12c26  ldarg.1
0x12c27  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x12c2c  ldstr    aAriaLabelledby// "aria-labelledby"
0x12c31  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x12c36  ldstr    a0C0W// "{0}_c {0}_w"
0x12c3b  ldc.i4.1
0x12c3c  newarr   [mscorlib]System.Object
0x12c41  dup
0x12c42  ldc.i4.0
0x12c43  ldarg.0
0x12c44  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x12c49  stelem.ref
0x12c4a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x12c4f  ldarg.1
0x12c50  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x12c55  ldarg.1
0x12c56  ldstr    aAttrpriv// "attrpriv"
0x12c5b  ldstr    a7// "7"
0x12c60  ldc.i4.0
0x12c61  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x12c66  ldarg.1
0x12c67  ldstr    aControlmode_0// "controlmode"
0x12c6c  ldstr    aNormal// "normal"
0x12c71  ldc.i4.0
0x12c72  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x12c77  ldarg.1
0x12c78  ldstr    aClass// "class"
0x12c7d  ldstr    aMsCrmDatetimeM// "ms-crm-DateTime ms-crm-InlineDateTime"
0x12c82  ldc.i4.0
0x12c83  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x12c88  ldarg.1
0x12c89  ldstr    aFormat// "format"
0x12c8e  ldstr    aDate// "date"
0x12c93  ldc.i4.0
0x12c94  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x12c99  ldarg.1
0x12c9a  ldc.i4.s 0x3E
0x12c9c  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x12ca1  ldarg.1
0x12ca2  ldstr    aColgroup// "colgroup"
0x12ca7  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x12cac  ldarg.1
0x12cad  ldc.i4.s 0x3E
0x12caf  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x12cb4  ldarg.1
0x12cb5  ldstr    aCol// "col"
0x12cba  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x12cbf  ldarg.1
0x12cc0  ldc.i4.s 0x3E
0x12cc2  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x12cc7  ldarg.1
0x12cc8  ldstr    aCol// "col"
0x12ccd  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x12cd2  ldarg.1
0x12cd3  ldstr    aCol// "col"
0x12cd8  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x12cdd  ldarg.1
0x12cde  ldstr    aWidth// "width"
0x12ce3  ldstr    a45// "45"
0x12ce8  ldc.i4.0
0x12ce9  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x12cee  ldarg.1
0x12cef  ldc.i4.s 0x3E
0x12cf1  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x12cf6  ldarg.1
0x12cf7  ldstr    aCol// "col"
0x12cfc  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x12d01  ldarg.0
0x12d02  call     instance string Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.DateTimeControl::get_DateTimeFormat()
0x12d07  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x12d0c  brtrue.s loc_12D48
0x12d0e  ldarg.0
0x12d0f  call     instance string Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.DateTimeControl::get_DateTimeFormat()
0x12d14  callvirt instance string [mscorlib]System.String::ToLower()
0x12d19  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DateTimeAttributeFormats::get_DateTime()
0x12d1e  callvirt instance string [mscorlib]System.String::ToLower()
0x12d23  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12d28  brfalse.s loc_12D48
0x12d2a  ldarg.1
0x12d2b  ldstr    aCol// "col"
0x12d30  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x12d35  ldarg.1
0x12d36  ldc.i4.s 0x3E
0x12d38  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x12d3d  ldarg.1
0x12d3e  ldstr    aCol// "col"
0x12d43  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x12d48  ldarg.1
0x12d49  ldstr    aColgroup// "colgroup"
0x12d4e  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x12d53  ldarg.1
0x12d54  ldstr    aTr_0// "tr"
0x12d59  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x12d5e  ldarg.1
0x12d5f  ldc.i4.s 0x3E
0x12d61  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x12d66  ldarg.1
0x12d67  ldstr    aTd_0// "td"
0x12d6c  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x12d71  ldarg.1
0x12d72  ldstr    aClass// "class"
0x12d77  ldstr    aMsCrmInputCont// "ms-crm-Input-Container ms-crm-DateTime-"...
0x12d7c  ldc.i4.0
0x12d7d  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x12d82  ldarg.1
0x12d83  ldc.i4.s 0x3E
0x12d85  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x12d8a  ldarg.1
0x12d8b  ldstr    aInput// "input"
0x12d90  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x12d95  ldarg.1
0x12d96  ldstr    aType// "type"
0x12d9b  ldstr    aText// "text"
0x12da0  ldc.i4.0
0x12da1  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x12da6  ldstr    aId// "id"
0x12dab  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x12db0  ldstr    a0Idateinput// "{0}_iDateInput"
0x12db5  ldc.i4.1
0x12db6  newarr   [mscorlib]System.Object
0x12dbb  dup
0x12dbc  ldc.i4.0
0x12dbd  ldarg.0
0x12dbe  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x12dc3  stelem.ref
0x12dc4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x12dc9  ldarg.1
0x12dca  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x12dcf  ldarg.1
0x12dd0  ldstr    aStyle// "style"
0x12dd5  ldstr    aImeModeAuto_0// "ime-mode: auto"
0x12dda  ldc.i4.0
0x12ddb  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x12de0  ldarg.1
0x12de1  ldstr    aClass// "class"
0x12de6  ldstr    aMsCrmInputMsCr// "ms-crm-Input ms-crm-DateTime-Container-"...
0x12deb  ldc.i4.0
0x12dec  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x12df1  ldstr    aAriaLabelledby// "aria-labelledby"
0x12df6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x12dfb  ldstr    a0_1// "{0}"
0x12e00  ldc.i4.1
0x12e01  newarr   [mscorlib]System.Object
0x12e06  dup
0x12e07  ldc.i4.0
0x12e08  ldarg.0
0x12e09  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x12e0e  stelem.ref
0x12e0f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x12e14  ldarg.1
0x12e15  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x12e1a  ldarg.1
0x12e1b  ldc.i4.s 0x3E
0x12e1d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x12e22  ldarg.1
0x12e23  ldstr    aInput// "input"
0x12e28  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x12e2d  ldarg.1
0x12e2e  ldstr    aTd_0// "td"
0x12e33  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x12e38  ldarg.1
0x12e39  ldstr    aTd_0// "td"
0x12e3e  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x12e43  ldarg.1
0x12e44  ldstr    aClass// "class"
0x12e49  ldstr    aMsCrmInlinedat// "ms-crm-InlineDateTime-HiddenCell"
0x12e4e  ldc.i4.0
0x12e4f  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x12e54  ldarg.1
0x12e55  ldc.i4.s 0x3E
0x12e57  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x12e5c  ldarg.1
0x12e5d  ldstr    aTd_0// "td"
0x12e62  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x12e67  ldarg.1
0x12e68  ldstr    aTd_0// "td"
0x12e6d  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x12e72  ldarg.1
0x12e73  ldstr    aClass// "class"
0x12e78  ldstr    aMsCrmInlinedat_0// "ms-crm-InlineDateTime-IconCell"
0x12e7d  ldc.i4.0
0x12e7e  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x12e83  ldarg.1
0x12e84  ldc.i4.s 0x3E
0x12e86  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x12e8b  ldarg.1
0x12e8c  ldstr    aImg// "img"
0x12e91  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x12e96  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x12e9b  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_UseImageStrips()
0x12ea0  brtrue.s loc_12EC6
0x12ea2  ldarg.1
0x12ea3  ldstr    aSrc// "src"
0x12ea8  ldstr    aImgsInlineedit_2// "/_imgs/inlineedit/calendar_icon.png"
0x12ead  ldc.i4.0
0x12eae  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x12eb3  ldarg.1
0x12eb4  ldstr    aClass// "class"
0x12eb9  ldstr    aMsCrmDatetimeM_0// "ms-crm-DateTime ms-crm-InlineDateTime-I"...
0x12ebe  ldc.i4.0
0x12ebf  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x12ec4  br.s     loc_12EE8
0x12ec6  ldarg.1
0x12ec7  ldstr    aSrc// "src"
0x12ecc  ldstr    aImgsImagestrip// "/_imgs/imagestrips/transparent_spacer.g"...
0x12ed1  ldc.i4.0
0x12ed2  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x12ed7  ldarg.1
0x12ed8  ldstr    aClass// "class"
0x12edd  ldstr    aMsCrmImagestri_1// "ms-crm-ImageStrip-inlineedit_calendar_i"...
0x12ee2  ldc.i4.0
0x12ee3  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x12ee8  ldarg.1
0x12ee9  ldstr    aAlt// "alt"
0x12eee  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x12ef3  ldstr    aWebFormsStyles// "Web._forms.styles.IMG.dtm.htc_27_0"
0x12ef8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x12efd  ldc.i4.0
0x12efe  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x12f03  ldstr    aId// "id"
0x12f08  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x12f0d  ldstr    a0Iimg// "{0}_iimg"
0x12f12  ldc.i4.1
0x12f13  newarr   [mscorlib]System.Object
0x12f18  dup
0x12f19  ldc.i4.0
0x12f1a  ldarg.0
0x12f1b  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x12f20  stelem.ref
0x12f21  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x12f26  ldarg.1
0x12f27  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x12f2c  ldarg.1
0x12f2d  ldc.i4.s 0x3E
0x12f2f  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x12f34  ldarg.1
0x12f35  ldstr    aDiv// "div"
0x12f3a  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x12f3f  ldstr    aId// "id"
0x12f44  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x12f49  ldstr    a0Icalcontainer// "{0}_iCalContainer"
0x12f4e  ldc.i4.1
0x12f4f  newarr   [mscorlib]System.Object
0x12f54  dup
0x12f55  ldc.i4.0
0x12f56  ldarg.0
0x12f57  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x12f5c  stelem.ref
0x12f5d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x12f62  ldarg.1
0x12f63  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x12f68  ldarg.1
0x12f69  ldstr    aStyle// "style"
0x12f6e  ldstr    aWidth0pxHeight// "width: 0px; height: 0px; position: rela"...
0x12f73  ldc.i4.0
  ... truncated ...
```
