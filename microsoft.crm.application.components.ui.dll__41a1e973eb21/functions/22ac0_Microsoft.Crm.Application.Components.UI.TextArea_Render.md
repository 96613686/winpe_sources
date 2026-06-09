# Microsoft.Crm.Application.Components.UI.TextArea::Render

- ea: `0x22ac0`
- end: `0x22cde`
- name: `Microsoft.Crm.Application.Components.UI.TextArea::Render`
- size: `542`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callees

- `0x228e0`
- `0x22910`
- `0x22930`
- `0x22970`
- `0x22990`
- `0x229d0`
- `0x22ac0`
- `0x22ce0`
- `0x23c20`
- `0x24120`
- `0x24210`
- `0x24260`
- `0x24280`
- `0x242c0`

## string_xrefs

- `0x22ba7`: `SM_Customer_Service_Schedule_Dialog_Title_02`
- `0x22be7`: ` ms-crm-ReadOnly`
- `0x22bf3`: `readonly`
- `0x22bf8`: `readonly`

## pseudocode

```c

```

## disassembly

```asm
0x22ac0  ldarg.1
0x22ac1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x22ac6  ldstr    aDivClassMsCrmI_0// "<div class=\"ms-crm-Input-Container {0}"...
0x22acb  ldc.i4.3
0x22acc  newarr   [mscorlib]System.Object
0x22ad1  dup
0x22ad2  ldc.i4.0
0x22ad3  ldarg.0
0x22ad4  call     instance string Microsoft.Crm.Application.Components.UI.TextArea::get_ClassName()
0x22ad9  stelem.ref
0x22ada  dup
0x22adb  ldc.i4.1
0x22adc  ldarg.0
0x22add  ldfld    string Microsoft.Crm.Application.Components.UI.TextArea::_height
0x22ae2  stelem.ref
0x22ae3  dup
0x22ae4  ldc.i4.2
0x22ae5  ldarg.0
0x22ae6  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x22aeb  ldstr    aContainer// "_container"
0x22af0  call     string [mscorlib]System.String::Concat(string, string)
0x22af5  stelem.ref
0x22af6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x22afb  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x22b00  ldarg.1
0x22b01  ldstr    aTextarea// "<textarea "
0x22b06  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x22b0b  ldstr    aId// "id"
0x22b10  ldarg.0
0x22b11  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x22b16  ldarg.1
0x22b17  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x22b1c  ldarg.0
0x22b1d  callvirt instance int32 Microsoft.Crm.Application.Components.UI.CrmUIControl::get_TabIndex()
0x22b22  brfalse.s loc_22B48
0x22b24  ldarg.1
0x22b25  ldstr    aTabindex// "tabindex"
0x22b2a  ldarg.0
0x22b2b  callvirt instance int32 Microsoft.Crm.Application.Components.UI.CrmUIControl::get_TabIndex()
0x22b30  stloc.2
0x22b31  ldloca.s 2
0x22b33  ldstr    aD_1// "D"
0x22b38  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x22b3d  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x22b42  ldc.i4.0
0x22b43  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x22b48  ldarg.0
0x22b49  call     instance int32 Microsoft.Crm.Application.Components.UI.TextArea::get_MaxLength()
0x22b4e  ldc.i4.m1
0x22b4f  beq.s    loc_22B75
0x22b51  ldarg.1
0x22b52  ldstr    aMaxlength// "maxlength"
0x22b57  ldarg.0
0x22b58  call     instance int32 Microsoft.Crm.Application.Components.UI.TextArea::get_MaxLength()
0x22b5d  stloc.2
0x22b5e  ldloca.s 2
0x22b60  ldstr    aD_1// "D"
0x22b65  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x22b6a  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x22b6f  ldc.i4.0
0x22b70  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x22b75  ldarg.0
0x22b76  call     instance string Microsoft.Crm.Application.Components.UI.TextArea::get_Title()
0x22b7b  brfalse.s loc_22B90
0x22b7d  ldstr    aTitle_2// "title"
0x22b82  ldarg.0
0x22b83  call     instance string Microsoft.Crm.Application.Components.UI.TextArea::get_Title()
0x22b88  ldarg.1
0x22b89  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x22b8e  br.s     loc_22BBE
0x22b90  ldarg.0
0x22b91  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x22b96  ldstr    aTxtdescription// "txtdescription"
0x22b9b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x22ba0  brfalse.s loc_22BBE
0x22ba2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x22ba7  ldstr    aSmCustomerServ// "SM_Customer_Service_Schedule_Dialog_Tit"...
0x22bac  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x22bb1  stloc.3
0x22bb2  ldstr    aTitle_2// "title"
0x22bb7  ldloc.3
0x22bb8  ldarg.1
0x22bb9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x22bbe  ldstr    aMsCrmInput_0// "ms-crm-Input"
0x22bc3  stloc.0
0x22bc4  ldloc.0
0x22bc5  ldstr    asc_4C79A// " "
0x22bca  ldarg.0
0x22bcb  call     instance string Microsoft.Crm.Application.Components.UI.TextArea::get_TextAreaClassName()
0x22bd0  call     string [mscorlib]System.String::Concat(string, string, string)
0x22bd5  stloc.0
0x22bd6  ldarg.0
0x22bd7  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x22bdc  brtrue.s loc_22BE6
0x22bde  ldarg.0
0x22bdf  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControl::get_ReadOnly()
0x22be4  brfalse.s loc_22C03
0x22be6  ldloc.0
0x22be7  ldstr    aMsCrmReadonly// " ms-crm-ReadOnly"
0x22bec  call     string [mscorlib]System.String::Concat(string, string)
0x22bf1  stloc.0
0x22bf2  ldarg.1
0x22bf3  ldstr    aReadonly_1// "readonly"
0x22bf8  ldstr    aReadonly_1// "readonly"
0x22bfd  ldc.i4.0
0x22bfe  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x22c03  ldstr    aClass_1// "class"
0x22c08  ldloc.0
0x22c09  ldarg.1
0x22c0a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x22c0f  ldarg.0
0x22c10  ldstr    aStyle_2// "Style"
0x22c15  callvirt instance string Microsoft.Crm.Application.Components.UI.CrmUIControl::GetExpando(string name)
0x22c1a  stloc.1
0x22c1b  ldloc.1
0x22c1c  brfalse.s loc_22C59
0x22c1e  ldarg.0
0x22c1f  ldstr    aStyle_2// "Style"
0x22c24  ldnull
0x22c25  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string name, string value)
0x22c2a  ldarg.0
0x22c2b  ldstr    aStyle_2// "Style"
0x22c30  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x22c35  ldstr    a0Height1// "{0} ; height: {1}"
0x22c3a  ldc.i4.2
0x22c3b  newarr   [mscorlib]System.Object
0x22c40  dup
0x22c41  ldc.i4.0
0x22c42  ldloc.1
0x22c43  stelem.ref
0x22c44  dup
0x22c45  ldc.i4.1
0x22c46  ldarg.0
0x22c47  call     instance string Microsoft.Crm.Application.Components.UI.TextArea::GetTextAreaEffectiveHeight()
0x22c4c  stelem.ref
0x22c4d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x22c52  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string name, string value)
0x22c57  br.s     loc_22C82
0x22c59  ldstr    aStyle_0// "style"
0x22c5e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x22c63  ldstr    aHeight0// "height: {0}"
0x22c68  ldc.i4.1
0x22c69  newarr   [mscorlib]System.Object
0x22c6e  dup
0x22c6f  ldc.i4.0
0x22c70  ldarg.0
0x22c71  call     instance string Microsoft.Crm.Application.Components.UI.TextArea::GetTextAreaEffectiveHeight()
0x22c76  stelem.ref
0x22c77  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x22c7c  ldarg.1
0x22c7d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x22c82  ldarg.0
0x22c83  call     instance bool Microsoft.Crm.Application.Components.UI.TextArea::get_TrimValue()
0x22c88  brtrue.s loc_22CAA
0x22c8a  ldarg.1
0x22c8b  ldstr    aDefaulttrimval// "defaultTrimValue"
0x22c90  ldarg.0
0x22c91  call     instance bool Microsoft.Crm.Application.Components.UI.TextArea::get_TrimValue()
0x22c96  brtrue.s loc_22C9F
0x22c98  ldstr    aFalse// "false"
0x22c9d  br.s     loc_22CA4
0x22c9f  ldstr    aTrue// "true"
0x22ca4  ldc.i4.0
0x22ca5  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x22caa  ldarg.1
0x22cab  ldarg.0
0x22cac  callvirt instance string Microsoft.Crm.Application.Components.UI.CrmUIControl::get_Expandos()
0x22cb1  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x22cb6  ldarg.1
0x22cb7  ldc.i4.s 0x3E
0x22cb9  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x22cbe  ldarg.0
0x22cbf  call     instance string Microsoft.Crm.Application.Components.UI.TextArea::get_Text()
0x22cc4  brfalse.s loc_22CD2
0x22cc6  ldarg.0
0x22cc7  call     instance string Microsoft.Crm.Application.Components.UI.TextArea::get_Text()
0x22ccc  ldarg.1
0x22ccd  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string, class [mscorlib]System.IO.TextWriter)
0x22cd2  ldarg.1
0x22cd3  ldstr    aTextareaDiv// "</textarea></div>"
0x22cd8  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x22cdd  ret
```
