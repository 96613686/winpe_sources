# Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.TextAreaControl::RenderEditMode

- ea: `0x11b70`
- end: `0x11d56`
- name: `Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.TextAreaControl::RenderEditMode`
- size: `486`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1450`
- `0x11b70`
- `0x18c50`
- `0x18d00`
- `0x18d40`

## pseudocode

```c

```

## disassembly

```asm
0x11b70  ldstr    aImeMode// "ime-mode"
0x11b75  stloc.0
0x11b76  ldarg.0
0x11b77  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x11b7c  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.TextAttributeMetadata
0x11b81  stloc.1
0x11b82  ldarg.1
0x11b83  ldstr    aDiv// "div"
0x11b88  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x11b8d  ldarg.1
0x11b8e  ldstr    aClass// "class"
0x11b93  ldstr    aMsCrmInlineEdi_1// "ms-crm-Inline-Edit"
0x11b98  ldc.i4.0
0x11b99  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x11b9e  ldarg.1
0x11b9f  ldstr    aStyle// "style"
0x11ba4  ldstr    aDisplayNone_0// "display: none;"
0x11ba9  ldc.i4.0
0x11baa  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x11baf  ldarg.1
0x11bb0  ldc.i4.s 0x3E
0x11bb2  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x11bb7  ldarg.1
0x11bb8  ldstr    aTextarea// "textarea"
0x11bbd  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x11bc2  ldstr    aId// "id"
0x11bc7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x11bcc  ldstr    a0I// "{0}_i"
0x11bd1  ldc.i4.1
0x11bd2  newarr   [mscorlib]System.Object
0x11bd7  dup
0x11bd8  ldc.i4.0
0x11bd9  ldarg.0
0x11bda  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x11bdf  stelem.ref
0x11be0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x11be5  ldarg.1
0x11be6  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x11beb  ldarg.1
0x11bec  ldstr    aClass// "class"
0x11bf1  ldstr    aMsCrmInlineinp_0// "ms-crm-InlineInput"
0x11bf6  ldc.i4.0
0x11bf7  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x11bfc  call     bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControlHelper::IsMicrosoftEdge()
0x11c01  brfalse.s loc_11C09
0x11c03  ldstr    aMsImeMode// "-ms-ime-mode"
0x11c08  stloc.0
0x11c09  ldarg.1
0x11c0a  ldstr    aStyle// "style"
0x11c0f  ldstr    a01_4// "{0}: {1}"
0x11c14  ldloc.0
0x11c15  ldloc.1
0x11c16  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeIMEMode [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_AttributeImeModeId()
0x11c1b  stloc.2
0x11c1c  ldloca.s 2
0x11c1e  constrained. [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeIMEMode
0x11c24  callvirt instance string [mscorlib]System.Object::ToString()
0x11c29  call     string [mscorlib]System.String::Format(string, object, object)
0x11c2e  ldc.i4.0
0x11c2f  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x11c34  call     bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControlHelper::IsSafari()
0x11c39  brfalse.s loc_11C64
0x11c3b  ldstr    aAriaLabel// "aria-label"
0x11c40  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x11c45  ldstr    a0_1// "{0}"
0x11c4a  ldc.i4.1
0x11c4b  newarr   [mscorlib]System.Object
0x11c50  dup
0x11c51  ldc.i4.0
0x11c52  ldarg.0
0x11c53  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x11c58  stelem.ref
0x11c59  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x11c5e  ldarg.1
0x11c5f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x11c64  call     bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControlHelper::IsIE()
0x11c69  brfalse.s loc_11C96
0x11c6b  ldstr    aAriaLabelledby// "aria-labelledby"
0x11c70  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x11c75  ldstr    a0C// "{0}_c"
0x11c7a  ldc.i4.1
0x11c7b  newarr   [mscorlib]System.Object
0x11c80  dup
0x11c81  ldc.i4.0
0x11c82  ldarg.0
0x11c83  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x11c88  stelem.ref
0x11c89  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x11c8e  ldarg.1
0x11c8f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x11c94  br.s     loc_11CBF
0x11c96  ldstr    aAriaLabelledby// "aria-labelledby"
0x11c9b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x11ca0  ldstr    a0C0D_0// "{0}_c {0}_d"
0x11ca5  ldc.i4.1
0x11ca6  newarr   [mscorlib]System.Object
0x11cab  dup
0x11cac  ldc.i4.0
0x11cad  ldarg.0
0x11cae  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x11cb3  stelem.ref
0x11cb4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x11cb9  ldarg.1
0x11cba  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x11cbf  ldloc.1
0x11cc0  brfalse.s loc_11CE1
0x11cc2  ldarg.1
0x11cc3  ldstr    aMaxlength// "maxlength"
0x11cc8  ldloc.1
0x11cc9  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.TextAttributeMetadata::get_MaxLength()
0x11cce  stloc.3
0x11ccf  ldloca.s 3
0x11cd1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x11cd6  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x11cdb  ldc.i4.0
0x11cdc  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x11ce1  ldarg.1
0x11ce2  ldstr    aRole// "role"
0x11ce7  ldstr    aTextbox// "textbox"
0x11cec  ldc.i4.0
0x11ced  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x11cf2  ldarg.1
0x11cf3  ldstr    aAriaMultiline// "aria-multiline"
0x11cf8  ldstr    aTrue// "true"
0x11cfd  ldc.i4.0
0x11cfe  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x11d03  ldstr    aAttrname// "attrname"
0x11d08  ldloc.1
0x11d09  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x11d0e  ldarg.1
0x11d0f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x11d14  ldloc.1
0x11d15  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_AttributeRequiredLevelId()
0x11d1a  ldc.i4.2
0x11d1b  beq.s    loc_11D26
0x11d1d  ldloc.1
0x11d1e  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_AttributeRequiredLevelId()
0x11d23  ldc.i4.1
0x11d24  bne.un.s loc_11D37
0x11d26  ldarg.1
0x11d27  ldstr    aAriaRequired// "aria-required"
0x11d2c  ldstr    aTrue// "true"
0x11d31  ldc.i4.0
0x11d32  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x11d37  ldarg.1
0x11d38  ldc.i4.s 0x3E
0x11d3a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x11d3f  ldarg.1
0x11d40  ldstr    aTextarea// "textarea"
0x11d45  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x11d4a  ldarg.1
0x11d4b  ldstr    aDiv// "div"
0x11d50  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x11d55  ret
```
