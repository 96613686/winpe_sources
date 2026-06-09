# Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.DateTimeControl::RenderEditMode

- ea: `0x98a0`
- end: `0x9d25`
- name: `Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.DateTimeControl::RenderEditMode`
- size: `1157`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1450`
- `0x98a0`
- `0x9d30`

## pseudocode

```c

```

## disassembly

```asm
0x98a0  ldarg.0
0x98a1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x98a6  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DateTimeAttributeMetadata
0x98ab  stloc.0
0x98ac  ldarg.1
0x98ad  ldstr    aDiv// "div"
0x98b2  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x98b7  ldarg.1
0x98b8  ldstr    aClass// "class"
0x98bd  ldstr    aMsCrmInlineEdi_1// "ms-crm-Inline-Edit"
0x98c2  ldc.i4.0
0x98c3  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x98c8  ldarg.1
0x98c9  ldstr    aStyle// "style"
0x98ce  ldstr    aDisplayNone_0// "display: none;"
0x98d3  ldc.i4.0
0x98d4  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x98d9  ldarg.1
0x98da  ldc.i4.s 0x3E
0x98dc  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x98e1  ldarg.1
0x98e2  ldstr    aTable// "table"
0x98e7  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x98ec  ldstr    aId// "id"
0x98f1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x98f6  ldstr    a0I// "{0}_i"
0x98fb  ldc.i4.1
0x98fc  newarr   [mscorlib]System.Object
0x9901  dup
0x9902  ldc.i4.0
0x9903  ldarg.0
0x9904  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x9909  stelem.ref
0x990a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x990f  ldarg.1
0x9910  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x9915  ldarg.1
0x9916  ldstr    aCellspacing// "cellspacing"
0x991b  ldstr    a0// "0"
0x9920  ldc.i4.0
0x9921  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x9926  ldarg.1
0x9927  ldstr    aCellpadding// "cellpadding"
0x992c  ldstr    a0// "0"
0x9931  ldc.i4.0
0x9932  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x9937  ldstr    aAttrname// "attrname"
0x993c  ldloc.0
0x993d  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x9942  ldarg.1
0x9943  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x9948  ldstr    aAriaLabelledby// "aria-labelledby"
0x994d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9952  ldstr    a0C0W// "{0}_c {0}_w"
0x9957  ldc.i4.1
0x9958  newarr   [mscorlib]System.Object
0x995d  dup
0x995e  ldc.i4.0
0x995f  ldarg.0
0x9960  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x9965  stelem.ref
0x9966  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x996b  ldarg.1
0x996c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x9971  ldloc.0
0x9972  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_AttributeRequiredLevelId()
0x9977  ldc.i4.2
0x9978  beq.s    loc_9983
0x997a  ldloc.0
0x997b  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_AttributeRequiredLevelId()
0x9980  ldc.i4.1
0x9981  bne.un.s loc_9994
0x9983  ldarg.1
0x9984  ldstr    aAriaRequired// "aria-required"
0x9989  ldstr    aTrue// "true"
0x998e  ldc.i4.0
0x998f  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x9994  ldarg.1
0x9995  ldstr    aAttrpriv// "attrpriv"
0x999a  ldstr    a7// "7"
0x999f  ldc.i4.0
0x99a0  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x99a5  ldarg.1
0x99a6  ldstr    aControlmode_0// "controlmode"
0x99ab  ldstr    aNormal// "normal"
0x99b0  ldc.i4.0
0x99b1  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x99b6  ldarg.1
0x99b7  ldstr    aClass// "class"
0x99bc  ldstr    aMsCrmDatetimeM// "ms-crm-DateTime ms-crm-InlineDateTime"
0x99c1  ldc.i4.0
0x99c2  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x99c7  ldarg.1
0x99c8  ldstr    aFormat// "format"
0x99cd  ldstr    aDate// "date"
0x99d2  ldc.i4.0
0x99d3  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x99d8  ldarg.1
0x99d9  ldc.i4.s 0x3E
0x99db  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x99e0  ldarg.1
0x99e1  ldstr    aColgroup// "colgroup"
0x99e6  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x99eb  ldarg.1
0x99ec  ldc.i4.s 0x3E
0x99ee  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x99f3  ldarg.1
0x99f4  ldstr    aCol// "col"
0x99f9  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x99fe  ldarg.1
0x99ff  ldc.i4.s 0x3E
0x9a01  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x9a06  ldarg.1
0x9a07  ldstr    aCol// "col"
0x9a0c  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x9a11  ldarg.1
0x9a12  ldstr    aCol// "col"
0x9a17  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x9a1c  ldarg.1
0x9a1d  ldstr    aWidth// "width"
0x9a22  ldstr    a45// "45"
0x9a27  ldc.i4.0
0x9a28  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x9a2d  ldarg.1
0x9a2e  ldc.i4.s 0x3E
0x9a30  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x9a35  ldarg.1
0x9a36  ldstr    aCol// "col"
0x9a3b  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x9a40  ldloc.0
0x9a41  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Format()
0x9a46  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x9a4b  brtrue.s loc_9A7D
0x9a4d  ldloc.0
0x9a4e  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Format()
0x9a53  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DateTimeAttributeFormats::get_DateTime()
0x9a58  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9a5d  brfalse.s loc_9A7D
0x9a5f  ldarg.1
0x9a60  ldstr    aCol// "col"
0x9a65  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x9a6a  ldarg.1
0x9a6b  ldc.i4.s 0x3E
0x9a6d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x9a72  ldarg.1
0x9a73  ldstr    aCol// "col"
0x9a78  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x9a7d  ldarg.1
0x9a7e  ldstr    aColgroup// "colgroup"
0x9a83  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x9a88  ldarg.1
0x9a89  ldstr    aTr_0// "tr"
0x9a8e  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x9a93  ldarg.1
0x9a94  ldc.i4.s 0x3E
0x9a96  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x9a9b  ldarg.1
0x9a9c  ldstr    aTd_0// "td"
0x9aa1  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x9aa6  ldarg.1
0x9aa7  ldstr    aClass// "class"
0x9aac  ldstr    aMsCrmInputCont// "ms-crm-Input-Container ms-crm-DateTime-"...
0x9ab1  ldc.i4.0
0x9ab2  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x9ab7  ldarg.1
0x9ab8  ldc.i4.s 0x3E
0x9aba  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x9abf  ldarg.1
0x9ac0  ldstr    aInput// "input"
0x9ac5  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x9aca  ldarg.1
0x9acb  ldstr    aType// "type"
0x9ad0  ldstr    aText// "text"
0x9ad5  ldc.i4.0
0x9ad6  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x9adb  ldstr    aId// "id"
0x9ae0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9ae5  ldstr    a0Idateinput// "{0}_iDateInput"
0x9aea  ldc.i4.1
0x9aeb  newarr   [mscorlib]System.Object
0x9af0  dup
0x9af1  ldc.i4.0
0x9af2  ldarg.0
0x9af3  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x9af8  stelem.ref
0x9af9  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x9afe  ldarg.1
0x9aff  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x9b04  ldarg.1
0x9b05  ldstr    aStyle// "style"
0x9b0a  ldstr    aImeModeAuto_0// "ime-mode: auto"
0x9b0f  ldc.i4.0
0x9b10  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x9b15  ldstr    aAriaLabelledby// "aria-labelledby"
0x9b1a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9b1f  ldstr    a0C0W// "{0}_c {0}_w"
0x9b24  ldc.i4.1
0x9b25  newarr   [mscorlib]System.Object
0x9b2a  dup
0x9b2b  ldc.i4.0
0x9b2c  ldarg.0
0x9b2d  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x9b32  stelem.ref
0x9b33  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x9b38  ldarg.1
0x9b39  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x9b3e  ldarg.1
0x9b3f  ldstr    aClass// "class"
0x9b44  ldstr    aMsCrmInputMsCr// "ms-crm-Input ms-crm-DateTime-Container-"...
0x9b49  ldc.i4.0
0x9b4a  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x9b4f  ldarg.1
0x9b50  ldc.i4.s 0x3E
0x9b52  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x9b57  ldarg.1
0x9b58  ldstr    aInput// "input"
0x9b5d  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x9b62  ldarg.1
0x9b63  ldstr    aTd_0// "td"
0x9b68  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x9b6d  ldarg.1
0x9b6e  ldstr    aTd_0// "td"
0x9b73  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x9b78  ldarg.1
0x9b79  ldstr    aClass// "class"
0x9b7e  ldstr    aMsCrmInlinedat// "ms-crm-InlineDateTime-HiddenCell"
0x9b83  ldc.i4.0
0x9b84  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x9b89  ldarg.1
0x9b8a  ldc.i4.s 0x3E
0x9b8c  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x9b91  ldarg.1
0x9b92  ldstr    aTd_0// "td"
0x9b97  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x9b9c  ldarg.1
0x9b9d  ldstr    aTd_0// "td"
0x9ba2  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x9ba7  ldarg.1
0x9ba8  ldstr    aClass// "class"
0x9bad  ldstr    aMsCrmInlinedat_0// "ms-crm-InlineDateTime-IconCell"
0x9bb2  ldc.i4.0
0x9bb3  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x9bb8  ldarg.1
0x9bb9  ldc.i4.s 0x3E
0x9bbb  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x9bc0  ldarg.1
0x9bc1  ldstr    aImg// "img"
0x9bc6  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x9bcb  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x9bd0  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_UseImageStrips()
0x9bd5  brtrue.s loc_9BFB
0x9bd7  ldarg.1
0x9bd8  ldstr    aSrc// "src"
0x9bdd  ldstr    aImgsInlineedit_2// "/_imgs/inlineedit/calendar_icon.png"
0x9be2  ldc.i4.0
0x9be3  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x9be8  ldarg.1
0x9be9  ldstr    aClass// "class"
0x9bee  ldstr    aMsCrmDatetimeM_0// "ms-crm-DateTime ms-crm-InlineDateTime-I"...
0x9bf3  ldc.i4.0
0x9bf4  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x9bf9  br.s     loc_9C1D
0x9bfb  ldarg.1
0x9bfc  ldstr    aSrc// "src"
0x9c01  ldstr    aImgsImagestrip// "/_imgs/imagestrips/transparent_spacer.g"...
0x9c06  ldc.i4.0
0x9c07  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x9c0c  ldarg.1
0x9c0d  ldstr    aClass// "class"
0x9c12  ldstr    aMsCrmImagestri_1// "ms-crm-ImageStrip-inlineedit_calendar_i"...
0x9c17  ldc.i4.0
0x9c18  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x9c1d  ldarg.1
0x9c1e  ldstr    aTabindex// "tabindex"
0x9c23  ldstr    a1// "-1"
0x9c28  ldc.i4.0
0x9c29  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x9c2e  ldarg.1
0x9c2f  ldstr    aAlt// "alt"
0x9c34  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x9c39  ldstr    aWebFormsStyles// "Web._forms.styles.IMG.dtm.htc_27_0"
0x9c3e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9c43  ldc.i4.0
0x9c44  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x9c49  ldstr    aId// "id"
0x9c4e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9c53  ldstr    a0Iimg// "{0}_iimg"
0x9c58  ldc.i4.1
0x9c59  newarr   [mscorlib]System.Object
0x9c5e  dup
0x9c5f  ldc.i4.0
0x9c60  ldarg.0
0x9c61  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x9c66  stelem.ref
0x9c67  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x9c6c  ldarg.1
0x9c6d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x9c72  ldarg.1
0x9c73  ldc.i4.s 0x3E
0x9c75  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
  ... truncated ...
```
