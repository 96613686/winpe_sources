# Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormControl::SetUniqueId

- ea: `0x7030`
- end: `0x70dd`
- name: `Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormControl::SetUniqueId`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x6990`

## callees

- `0x6a30`

## string_xrefs

- `0x709a`: `quickFormTemplate_{0}`

## pseudocode

```c

```

## disassembly

```asm
0x7030  ldarg.1
0x7031  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x7036  ldc.i4.0
0x7037  ceq
0x7039  ldstr    aTheControlUniq_0// "The control unique Id input parameter f"...
0x703e  ldc.i4.1
0x703f  newarr   [mscorlib]System.Object
0x7044  dup
0x7045  ldc.i4.0
0x7046  ldarg.1
0x7047  stelem.ref
0x7048  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string, object[])
0x704d  ldarg.0
0x704e  ldarg.1
0x704f  stfld    string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormControl::_uniqueId
0x7054  ldarg.0
0x7055  ldarg.0
0x7056  ldfld    string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormControl::_uniqueId
0x705b  ldc.i4.2
0x705c  newarr   [mscorlib]System.Char
0x7061  dup
0x7062  ldc.i4.0
0x7063  ldc.i4.s 0x7B
0x7065  stelem.i2
0x7066  dup
0x7067  ldc.i4.1
0x7068  ldc.i4.s 0x7D
0x706a  stelem.i2
0x706b  callvirt instance string [mscorlib]System.String::Trim(char[])
0x7070  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7075  callvirt instance string [mscorlib]System.String::ToLower(class [mscorlib]System.Globalization.CultureInfo)
0x707a  stfld    string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormControl::_uniqueId
0x707f  ldarg.0
0x7080  ldarg.0
0x7081  ldfld    string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormControl::_uniqueId
0x7086  ldc.i4.s 0x2D
0x7088  ldc.i4.s 0x5F
0x708a  callvirt instance string [mscorlib]System.String::Replace(char, char)
0x708f  stfld    string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormControl::_uniqueId
0x7094  ldarg.0
0x7095  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x709a  ldstr    aQuickformtempl// "quickFormTemplate_{0}"
0x709f  ldc.i4.1
0x70a0  newarr   [mscorlib]System.Object
0x70a5  dup
0x70a6  ldc.i4.0
0x70a7  ldarg.0
0x70a8  ldfld    string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormControl::_uniqueId
0x70ad  stelem.ref
0x70ae  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x70b3  stfld    string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormControl::_jqueryTemplateName
0x70b8  ldarg.0
0x70b9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x70be  ldstr    aQuickformdata0// "quickFormData_{0}"
0x70c3  ldc.i4.1
0x70c4  newarr   [mscorlib]System.Object
0x70c9  dup
0x70ca  ldc.i4.0
0x70cb  ldarg.0
0x70cc  ldfld    string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormControl::_uniqueId
0x70d1  stelem.ref
0x70d2  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x70d7  call     instance void Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormControl::set_CustomDataObjectKey(string value)
0x70dc  ret
```
