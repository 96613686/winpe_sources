# Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.MoneyControl::RenderEditMode

- ea: `0x10b60`
- end: `0x10e5d`
- name: `Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.MoneyControl::RenderEditMode`
- size: `765`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1450`
- `0x10b60`
- `0x18d40`

## pseudocode

```c

```

## disassembly

```asm
0x10b60  ldstr    aImeMode// "ime-mode"
0x10b65  stloc.0
0x10b66  ldarg.0
0x10b67  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x10b6c  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MoneyAttributeMetadata
0x10b71  stloc.1
0x10b72  ldarg.1
0x10b73  ldstr    aDiv// "div"
0x10b78  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x10b7d  ldarg.1
0x10b7e  ldstr    aClass// "class"
0x10b83  ldstr    aMsCrmInlineEdi_4// "ms-crm-Inline-Edit ms-crm-Inline-Curren"...
0x10b88  ldc.i4.0
0x10b89  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x10b8e  ldarg.1
0x10b8f  ldstr    aStyle// "style"
0x10b94  ldstr    aDisplayNone_0// "display: none;"
0x10b99  ldc.i4.0
0x10b9a  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x10b9f  ldarg.1
0x10ba0  ldc.i4.s 0x3E
0x10ba2  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x10ba7  ldarg.1
0x10ba8  ldstr    aTable// "table"
0x10bad  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x10bb2  ldstr    aId// "id"
0x10bb7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x10bbc  ldstr    a0ITable// "{0}_i_table"
0x10bc1  ldc.i4.1
0x10bc2  newarr   [mscorlib]System.Object
0x10bc7  dup
0x10bc8  ldc.i4.0
0x10bc9  ldarg.0
0x10bca  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x10bcf  stelem.ref
0x10bd0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x10bd5  ldarg.1
0x10bd6  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x10bdb  ldarg.1
0x10bdc  ldstr    aCellpadding// "cellpadding"
0x10be1  ldstr    a0// "0"
0x10be6  ldc.i4.0
0x10be7  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x10bec  ldarg.1
0x10bed  ldstr    aCellspacing// "cellspacing"
0x10bf2  ldstr    a0// "0"
0x10bf7  ldc.i4.0
0x10bf8  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x10bfd  ldarg.1
0x10bfe  ldstr    aDir// "dir"
0x10c03  ldstr    aLtr// "ltr"
0x10c08  ldc.i4.0
0x10c09  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x10c0e  ldarg.1
0x10c0f  ldstr    aClass// "class"
0x10c14  ldstr    aMsCrmCurrencyt// "ms-crm-CurrencyTable-Refresh"
0x10c19  ldc.i4.0
0x10c1a  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x10c1f  ldarg.1
0x10c20  ldstr    aStyle// "style"
0x10c25  ldstr    aBackgroundColo_0// "background-color: rgb(255, 255, 255);"
0x10c2a  ldc.i4.0
0x10c2b  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x10c30  ldarg.1
0x10c31  ldc.i4.s 0x3E
0x10c33  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x10c38  ldarg.1
0x10c39  ldstr    aTbody// "tbody"
0x10c3e  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x10c43  ldarg.1
0x10c44  ldc.i4.s 0x3E
0x10c46  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x10c4b  ldarg.1
0x10c4c  ldstr    aTr_0// "tr"
0x10c51  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x10c56  ldarg.1
0x10c57  ldc.i4.s 0x3E
0x10c59  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x10c5e  ldarg.1
0x10c5f  ldstr    aTd_0// "td"
0x10c64  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x10c69  ldarg.1
0x10c6a  ldstr    aClass// "class"
0x10c6f  ldstr    aMsCrmCurrencys// "ms-crm-CurrencySymbol-Refresh"
0x10c74  ldc.i4.0
0x10c75  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x10c7a  ldarg.1
0x10c7b  ldc.i4.s 0x3E
0x10c7d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x10c82  ldarg.1
0x10c83  ldstr    aSpan// "span"
0x10c88  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x10c8d  ldstr    aId// "id"
0x10c92  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x10c97  ldstr    a0ISymbol// "{0}_i_symbol"
0x10c9c  ldc.i4.1
0x10c9d  newarr   [mscorlib]System.Object
0x10ca2  dup
0x10ca3  ldc.i4.0
0x10ca4  ldarg.0
0x10ca5  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x10caa  stelem.ref
0x10cab  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x10cb0  ldarg.1
0x10cb1  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x10cb6  ldarg.1
0x10cb7  ldstr    aClass// "class"
0x10cbc  ldstr    aMsCrmMoneyCurr// "ms-crm-Money-CurrencySymbol"
0x10cc1  ldc.i4.0
0x10cc2  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x10cc7  ldarg.1
0x10cc8  ldc.i4.s 0x3E
0x10cca  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x10ccf  ldarg.1
0x10cd0  ldstr    aSpan// "span"
0x10cd5  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x10cda  ldarg.1
0x10cdb  ldstr    aTd_0// "td"
0x10ce0  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x10ce5  ldarg.1
0x10ce6  ldstr    aTd_0// "td"
0x10ceb  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x10cf0  ldarg.1
0x10cf1  ldc.i4.s 0x3E
0x10cf3  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x10cf8  ldarg.1
0x10cf9  ldstr    aDiv// "div"
0x10cfe  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x10d03  ldarg.1
0x10d04  ldstr    aStyle// "style"
0x10d09  ldstr    aWhiteSpaceNorm// "white-space: normal;"
0x10d0e  ldc.i4.0
0x10d0f  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x10d14  ldarg.1
0x10d15  ldc.i4.s 0x3E
0x10d17  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x10d1c  ldarg.1
0x10d1d  ldstr    aInput// "input"
0x10d22  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x10d27  ldarg.1
0x10d28  ldstr    aType// "type"
0x10d2d  ldstr    aText// "text"
0x10d32  ldc.i4.0
0x10d33  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x10d38  ldstr    aId// "id"
0x10d3d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x10d42  ldstr    a0I// "{0}_i"
0x10d47  ldc.i4.1
0x10d48  newarr   [mscorlib]System.Object
0x10d4d  dup
0x10d4e  ldc.i4.0
0x10d4f  ldarg.0
0x10d50  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x10d55  stelem.ref
0x10d56  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x10d5b  ldarg.1
0x10d5c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x10d61  ldstr    aAttrname// "attrname"
0x10d66  ldloc.1
0x10d67  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x10d6c  ldarg.1
0x10d6d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x10d72  ldarg.1
0x10d73  ldstr    aClass// "class"
0x10d78  ldstr    aMsCrmMoneyMsCr// "ms-crm-Money ms-crm-InlineInput"
0x10d7d  ldc.i4.0
0x10d7e  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x10d83  ldstr    aAriaLabelledby// "aria-labelledby"
0x10d88  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x10d8d  ldstr    a0C// "{0}_c"
0x10d92  ldc.i4.1
0x10d93  newarr   [mscorlib]System.Object
0x10d98  dup
0x10d99  ldc.i4.0
0x10d9a  ldarg.0
0x10d9b  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x10da0  stelem.ref
0x10da1  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x10da6  ldarg.1
0x10da7  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x10dac  ldloc.1
0x10dad  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_AttributeRequiredLevelId()
0x10db2  ldc.i4.2
0x10db3  beq.s    loc_10DBE
0x10db5  ldloc.1
0x10db6  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_AttributeRequiredLevelId()
0x10dbb  ldc.i4.1
0x10dbc  bne.un.s loc_10DCF
0x10dbe  ldarg.1
0x10dbf  ldstr    aAriaRequired// "aria-required"
0x10dc4  ldstr    aTrue// "true"
0x10dc9  ldc.i4.0
0x10dca  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x10dcf  call     bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControlHelper::IsMicrosoftEdge()
0x10dd4  brfalse.s loc_10DDC
0x10dd6  ldstr    aMsImeMode// "-ms-ime-mode"
0x10ddb  stloc.0
0x10ddc  ldarg.1
0x10ddd  ldstr    aStyle// "style"
0x10de2  ldstr    a01_4// "{0}: {1}"
0x10de7  ldloc.0
0x10de8  ldloc.1
0x10de9  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeIMEMode [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_AttributeImeModeId()
0x10dee  stloc.2
0x10def  ldloca.s 2
0x10df1  constrained. [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeIMEMode
0x10df7  callvirt instance string [mscorlib]System.Object::ToString()
0x10dfc  call     string [mscorlib]System.String::Format(string, object, object)
0x10e01  ldc.i4.0
0x10e02  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x10e07  ldarg.1
0x10e08  ldc.i4.s 0x3E
0x10e0a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x10e0f  ldarg.1
0x10e10  ldstr    aInput// "input"
0x10e15  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x10e1a  ldarg.1
0x10e1b  ldstr    aDiv// "div"
0x10e20  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x10e25  ldarg.1
0x10e26  ldstr    aTd_0// "td"
0x10e2b  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x10e30  ldarg.1
0x10e31  ldstr    aTr_0// "tr"
0x10e36  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x10e3b  ldarg.1
0x10e3c  ldstr    aTbody// "tbody"
0x10e41  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x10e46  ldarg.1
0x10e47  ldstr    aTable// "table"
0x10e4c  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x10e51  ldarg.1
0x10e52  ldstr    aDiv// "div"
0x10e57  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x10e5c  ret
```
