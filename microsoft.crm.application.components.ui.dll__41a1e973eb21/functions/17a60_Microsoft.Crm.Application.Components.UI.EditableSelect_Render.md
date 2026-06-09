# Microsoft.Crm.Application.Components.UI.EditableSelect::Render

- ea: `0x17a60`
- end: `0x17c4c`
- name: `Microsoft.Crm.Application.Components.UI.EditableSelect::Render`
- size: `492`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x179c0`
- `0x17a60`
- `0x17c50`
- `0x17cf0`
- `0x23c20`
- `0x24120`
- `0x241d0`
- `0x241f0`
- `0x24280`
- `0x242c0`

## string_xrefs

- `0x17b0a`: `Recommended_Fields_Background_Color`

## pseudocode

```c

```

## disassembly

```asm
0x17a60  ldarg.1
0x17a61  ldstr    aSpan_3// "<span "
0x17a66  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x17a6b  ldarg.0
0x17a6c  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x17a71  brfalse.s loc_17A9F
0x17a73  ldstr    aId// "id"
0x17a78  ldarg.0
0x17a79  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x17a7e  ldarg.1
0x17a7f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x17a84  ldstr    aName_0// "name"
0x17a89  ldarg.0
0x17a8a  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x17a8f  ldstr    aInput// "Input"
0x17a94  call     string [mscorlib]System.String::Concat(string, string)
0x17a99  ldarg.1
0x17a9a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x17a9f  ldarg.0
0x17aa0  call     instance string Microsoft.Crm.Application.Components.UI.EditableSelect::get_ButtonTitle()
0x17aa5  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x17aaa  brtrue.s loc_17ABD
0x17aac  ldstr    aButtontitle// "ButtonTitle"
0x17ab1  ldarg.0
0x17ab2  call     instance string Microsoft.Crm.Application.Components.UI.EditableSelect::get_ButtonTitle()
0x17ab7  ldarg.1
0x17ab8  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x17abd  ldarg.1
0x17abe  ldstr    aClass_1// "class"
0x17ac3  ldstr    aMsCrmSelectbox// "ms-crm-SelectBox"
0x17ac8  ldc.i4.0
0x17ac9  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x17ace  ldstr    asc_3280A// ""
0x17ad3  stloc.0
0x17ad4  ldarg.0
0x17ad5  callvirt instance int32 Microsoft.Crm.Application.Components.UI.CrmUIControl::get_Required()
0x17ada  stloc.1
0x17adb  ldloc.1
0x17adc  switch   loc_17B15, loc_17B15, loc_17AF3, loc_17B05
0x17af1  br.s     loc_17B15
0x17af3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x17af8  ldstr    aRequiredFields// "Required_Fields_Background_Color"
0x17afd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x17b02  stloc.0
0x17b03  br.s     loc_17B15
0x17b05  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x17b0a  ldstr    aRecommendedFie// "Recommended_Fields_Background_Color"
0x17b0f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x17b14  stloc.0
0x17b15  ldstr    aDefaultbgcolor// "defaultbgcolor"
0x17b1a  ldloc.0
0x17b1b  ldarg.1
0x17b1c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x17b21  ldstr    aDropdownfontsi// "dropdownfontsize"
0x17b26  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x17b2b  ldstr    aEditableselect// "EditableSelect.DropDown.FontSize"
0x17b30  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x17b35  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x17b3a  ldarg.1
0x17b3b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x17b40  ldstr    aDefaultimemode// "defaultimemode"
0x17b45  ldarg.0
0x17b46  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeIMEMode Microsoft.Crm.Application.Components.UI.CrmUIControl::get_ImeMode()
0x17b4b  stloc.2
0x17b4c  ldloca.s 2
0x17b4e  constrained. [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeIMEMode
0x17b54  callvirt instance string [mscorlib]System.Object::ToString()
0x17b59  ldarg.1
0x17b5a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x17b5f  ldarg.0
0x17b60  callvirt instance int32 Microsoft.Crm.Application.Components.UI.CrmUIControl::get_TabIndex()
0x17b65  brfalse.s loc_17B8B
0x17b67  ldarg.1
0x17b68  ldstr    aTabbingindex// "tabbingIndex"
0x17b6d  ldarg.0
0x17b6e  callvirt instance int32 Microsoft.Crm.Application.Components.UI.CrmUIControl::get_TabIndex()
0x17b73  stloc.1
0x17b74  ldloca.s 1
0x17b76  ldstr    aD_1// "D"
0x17b7b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x17b80  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x17b85  ldc.i4.0
0x17b86  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x17b8b  ldstr    aValue_0// "value"
0x17b90  ldarg.0
0x17b91  ldfld    string Microsoft.Crm.Application.Components.UI.EditableSelect::_selected
0x17b96  ldarg.1
0x17b97  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x17b9c  ldarg.1
0x17b9d  ldstr    aAllowvalueedit// "allowValueEdit"
0x17ba2  ldstr    aTrue// "true"
0x17ba7  ldc.i4.0
0x17ba8  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x17bad  ldarg.0
0x17bae  ldfld    string Microsoft.Crm.Application.Components.UI.EditableSelect::_onChange
0x17bb3  brfalse.s loc_17BD3
0x17bb5  ldarg.0
0x17bb6  ldfld    string Microsoft.Crm.Application.Components.UI.EditableSelect::_onChange
0x17bbb  callvirt instance int32 [mscorlib]System.String::get_Length()
0x17bc0  brfalse.s loc_17BD3
0x17bc2  ldstr    aChangehandler// "changeHandler"
0x17bc7  ldarg.0
0x17bc8  ldfld    string Microsoft.Crm.Application.Components.UI.EditableSelect::_onChange
0x17bcd  ldarg.1
0x17bce  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x17bd3  ldarg.0
0x17bd4  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x17bd9  brtrue.s loc_17BE3
0x17bdb  ldarg.0
0x17bdc  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControl::get_ReadOnly()
0x17be1  brfalse.s loc_17BF4
0x17be3  ldarg.1
0x17be4  ldstr    aSetdisabled// "setdisabled"
0x17be9  ldstr    a1// "1"
0x17bee  ldc.i4.0
0x17bef  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x17bf4  ldarg.0
0x17bf5  ldfld    string Microsoft.Crm.Application.Components.UI.EditableSelect::_style
0x17bfa  brfalse.s loc_17C1A
0x17bfc  ldarg.0
0x17bfd  ldfld    string Microsoft.Crm.Application.Components.UI.EditableSelect::_style
0x17c02  callvirt instance int32 [mscorlib]System.String::get_Length()
0x17c07  brfalse.s loc_17C1A
0x17c09  ldstr    aStyle_0// "style"
0x17c0e  ldarg.0
0x17c0f  ldfld    string Microsoft.Crm.Application.Components.UI.EditableSelect::_style
0x17c14  ldarg.1
0x17c15  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x17c1a  ldarg.1
0x17c1b  ldarg.0
0x17c1c  callvirt instance string Microsoft.Crm.Application.Components.UI.CrmUIControl::get_Expandos()
0x17c21  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x17c26  ldarg.1
0x17c27  ldstr    asc_2B7B6// ">"
0x17c2c  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x17c31  ldarg.0
0x17c32  ldarg.1
0x17c33  ldloc.0
0x17c34  call     instance void Microsoft.Crm.Application.Components.UI.EditableSelect::RenderEditableInputElement(class [System.Web]System.Web.UI.HtmlTextWriter writer, string bgColor)
0x17c39  ldarg.0
0x17c3a  ldarg.1
0x17c3b  call     instance void Microsoft.Crm.Application.Components.UI.EditableSelect::RenderOptionTable(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0x17c40  ldarg.1
0x17c41  ldstr    aSpan// "</span>"
0x17c46  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x17c4b  ret
```
