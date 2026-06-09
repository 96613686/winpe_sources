# Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::GetInitializedNumber

- ea: `0xe3f0`
- end: `0xe475`
- name: `Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::GetInitializedNumber`
- size: `133`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xda80`
- `0xdb30`
- `0xdbc0`
- `0xdd50`
- `0xdfb0`

## callees

- `0xe3f0`

## pseudocode

```c

```

## disassembly

```asm
0xe3f0  newobj   instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TextBoxControl::.ctor()
0xe3f5  stloc.0
0xe3f6  ldloc.0
0xe3f7  ldarg.1
0xe3f8  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0xe3fd  ldloc.0
0xe3fe  ldstr    aMax// "max"
0xe403  ldarga.s 3
0xe405  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xe40a  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xe40f  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::AddExpando(string, string)
0xe414  ldloc.0
0xe415  ldstr    aMin// "min"
0xe41a  ldarga.s 2
0xe41c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xe421  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xe426  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::AddExpando(string, string)
0xe42b  ldloc.0
0xe42c  ldstr    a1// "1"
0xe431  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object)
0xe436  ldloc.0
0xe437  ldarga.s 3
0xe439  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xe43e  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xe443  callvirt instance int32 [mscorlib]System.String::get_Length()
0xe448  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TextBoxControl::set_MaxLength(int32)
0xe44d  ldarg.s  4
0xe44f  brtrue.s loc_E463
0xe451  ldloc.0
0xe452  ldstr    aOnchange// "onchange"
0xe457  ldstr    aMscrmRecurrenc_1// "Mscrm.RecurrenceDialog.numberChanged(ne"...
0xe45c  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::AddExpando(string, string)
0xe461  br.s     loc_E473
0xe463  ldloc.0
0xe464  ldstr    aOnchange// "onchange"
0xe469  ldstr    aMscrmRecurrenc_2// "Mscrm.RecurrenceDialog.monthChanged(new"...
0xe46e  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::AddExpando(string, string)
0xe473  ldloc.0
0xe474  ret
```
