# Microsoft.Crm.Application.Components.UI.Number::Render

- ea: `0x20a80`
- end: `0x20c4f`
- name: `Microsoft.Crm.Application.Components.UI.Number::Render`
- size: `463`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x20270`

## callees

- `0x20940`
- `0x20960`
- `0x209a0`
- `0x209e0`
- `0x20a80`
- `0x23c20`
- `0x24120`
- `0x24280`
- `0x242c0`

## string_xrefs

- `0x20ae3`: ` ms-crm-ReadOnly ms-crm-Input`

## pseudocode

```c

```

## disassembly

```asm
0x20a80  ldarg.1
0x20a81  ldstr    aDivClassMsCrmI// "<div class=\"ms-crm-Input-Container\"><"...
0x20a86  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x20a8b  ldstr    aId// "id"
0x20a90  ldarg.0
0x20a91  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x20a96  ldarg.1
0x20a97  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x20a9c  ldarg.0
0x20a9d  callvirt instance int32 Microsoft.Crm.Application.Components.UI.CrmUIControl::get_TabIndex()
0x20aa2  brfalse.s loc_20AC8
0x20aa4  ldarg.1
0x20aa5  ldstr    aTabindex// "tabindex"
0x20aaa  ldarg.0
0x20aab  callvirt instance int32 Microsoft.Crm.Application.Components.UI.CrmUIControl::get_TabIndex()
0x20ab0  stloc.1
0x20ab1  ldloca.s 1
0x20ab3  ldstr    aD_1// "D"
0x20ab8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x20abd  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x20ac2  ldc.i4.0
0x20ac3  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x20ac8  ldarg.0
0x20ac9  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x20ace  brtrue.s loc_20AD8
0x20ad0  ldarg.0
0x20ad1  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControl::get_ReadOnly()
0x20ad6  brfalse.s loc_20B06
0x20ad8  ldstr    aClass_1// "class"
0x20add  ldarg.0
0x20ade  ldfld    string Microsoft.Crm.Application.Components.UI.Number::_numberInputClass
0x20ae3  ldstr    aMsCrmReadonlyM_0// " ms-crm-ReadOnly ms-crm-Input"
0x20ae8  call     string [mscorlib]System.String::Concat(string, string)
0x20aed  ldarg.1
0x20aee  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x20af3  ldarg.1
0x20af4  ldstr    aDisabled// "disabled"
0x20af9  ldstr    aTrue// "true"
0x20afe  ldc.i4.0
0x20aff  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x20b04  br.s     loc_20B21
0x20b06  ldstr    aClass_1// "class"
0x20b0b  ldarg.0
0x20b0c  ldfld    string Microsoft.Crm.Application.Components.UI.Number::_numberInputClass
0x20b11  ldstr    aMsCrmInput// " ms-crm-Input"
0x20b16  call     string [mscorlib]System.String::Concat(string, string)
0x20b1b  ldarg.1
0x20b1c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x20b21  ldarg.0
0x20b22  call     instance int32 Microsoft.Crm.Application.Components.UI.Number::get_Precision()
0x20b27  stloc.1
0x20b28  ldloca.s 1
0x20b2a  ldstr    aD_1// "D"
0x20b2f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x20b34  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x20b39  stloc.0
0x20b3a  ldarg.0
0x20b3b  call     instance float64 Microsoft.Crm.Application.Components.UI.Number::get_Value()
0x20b40  call     bool [mscorlib]System.Double::IsNaN(float64)
0x20b45  brtrue.s loc_20B88
0x20b47  ldarg.1
0x20b48  ldstr    aValue_0// "value"
0x20b4d  ldarg.0
0x20b4e  call     instance float64 Microsoft.Crm.Application.Components.UI.Number::get_Value()
0x20b53  box      [mscorlib]System.Double
0x20b58  ldarg.0
0x20b59  call     instance int32 Microsoft.Crm.Application.Components.UI.Number::get_Precision()
0x20b5e  ldc.i4.0
0x20b5f  ldsfld   string [mscorlib]System.String::Empty
0x20b64  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x20b69  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_SystemUserId()
0x20b6e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x20b73  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x20b78  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x20b7d  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Formatting.CrmFormatter::CrmFormatNumber(object, int32, bool, string, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x20b82  ldc.i4.0
0x20b83  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x20b88  ldarg.1
0x20b89  ldstr    aAcc// "acc"
0x20b8e  ldloc.0
0x20b8f  ldc.i4.0
0x20b90  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x20b95  ldarg.1
0x20b96  ldstr    aMin// "min"
0x20b9b  ldarg.0
0x20b9c  call     instance float64 Microsoft.Crm.Application.Components.UI.Number::get_MinValue()
0x20ba1  stloc.2
0x20ba2  ldloca.s 2
0x20ba4  ldstr    aF// "F"
0x20ba9  ldloc.0
0x20baa  call     string [mscorlib]System.String::Concat(string, string)
0x20baf  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x20bb4  call     instance string [mscorlib]System.Double::ToString(string, class [mscorlib]System.IFormatProvider)
0x20bb9  ldc.i4.0
0x20bba  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x20bbf  ldarg.1
0x20bc0  ldstr    aMax// "max"
0x20bc5  ldarg.0
0x20bc6  call     instance float64 Microsoft.Crm.Application.Components.UI.Number::get_MaxValue()
0x20bcb  stloc.2
0x20bcc  ldloca.s 2
0x20bce  ldstr    aF// "F"
0x20bd3  ldloc.0
0x20bd4  call     string [mscorlib]System.String::Concat(string, string)
0x20bd9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x20bde  call     instance string [mscorlib]System.Double::ToString(string, class [mscorlib]System.IFormatProvider)
0x20be3  ldc.i4.0
0x20be4  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x20be9  ldarg.0
0x20bea  ldfld    string Microsoft.Crm.Application.Components.UI.Number::_onChange
0x20bef  brfalse.s loc_20C10
0x20bf1  ldarg.0
0x20bf2  ldfld    string Microsoft.Crm.Application.Components.UI.Number::_onChange
0x20bf7  callvirt instance int32 [mscorlib]System.String::get_Length()
0x20bfc  ldc.i4.0
0x20bfd  ble.s    loc_20C10
0x20bff  ldstr    aOnchange_0// "onchange"
0x20c04  ldarg.0
0x20c05  ldfld    string Microsoft.Crm.Application.Components.UI.Number::_onChange
0x20c0a  ldarg.1
0x20c0b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x20c10  ldarg.0
0x20c11  ldfld    string Microsoft.Crm.Application.Components.UI.Number::_onKeyUp
0x20c16  brfalse.s loc_20C37
0x20c18  ldarg.0
0x20c19  ldfld    string Microsoft.Crm.Application.Components.UI.Number::_onKeyUp
0x20c1e  callvirt instance int32 [mscorlib]System.String::get_Length()
0x20c23  ldc.i4.0
0x20c24  ble.s    loc_20C37
0x20c26  ldstr    aOnkeyup// "onkeyup"
0x20c2b  ldarg.0
0x20c2c  ldfld    string Microsoft.Crm.Application.Components.UI.Number::_onKeyUp
0x20c31  ldarg.1
0x20c32  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x20c37  ldarg.1
0x20c38  ldarg.0
0x20c39  callvirt instance string Microsoft.Crm.Application.Components.UI.CrmUIControl::get_Expandos()
0x20c3e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x20c43  ldarg.1
0x20c44  ldstr    aDiv_8// "></div>"
0x20c49  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x20c4e  ret
```
