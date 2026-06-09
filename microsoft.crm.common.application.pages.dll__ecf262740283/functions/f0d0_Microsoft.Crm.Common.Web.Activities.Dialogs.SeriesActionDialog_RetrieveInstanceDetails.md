# Microsoft.Crm.Common.Web.Activities.Dialogs.SeriesActionDialog::RetrieveInstanceDetails

- ea: `0xf0d0`
- end: `0xf1da`
- name: `Microsoft.Crm.Common.Web.Activities.Dialogs.SeriesActionDialog::RetrieveInstanceDetails`
- size: `266`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0xe800`

## callees

- `0xf0d0`

## string_xrefs

- `0xf0ed`: `seriesid`
- `0xf106`: `seriesid`
- `0xf127`: `seriesid`
- `0xf135`: `seriesid`

## pseudocode

```c

```

## disassembly

```asm
0xf0d0  ldnull
0xf0d1  stloc.0
0xf0d2  ldnull
0xf0d3  stloc.1
0xf0d4  ldarg.1
0xf0d5  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xf0da  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xf0df  brfalse.s loc_F0E2
0xf0e1  ret
0xf0e2  ldarg.2
0xf0e3  brfalse.s loc_F0FE
0xf0e5  ldc.i4.2
0xf0e6  newarr   [mscorlib]System.String
0xf0eb  dup
0xf0ec  ldc.i4.0
0xf0ed  ldstr    aSeriesid_0// "seriesid"
0xf0f2  stelem.ref
0xf0f3  dup
0xf0f4  ldc.i4.1
0xf0f5  ldstr    aSubject// "subject"
0xf0fa  stelem.ref
0xf0fb  stloc.1
0xf0fc  br.s     loc_F10D
0xf0fe  ldc.i4.1
0xf0ff  newarr   [mscorlib]System.String
0xf104  dup
0xf105  ldc.i4.0
0xf106  ldstr    aSeriesid_0// "seriesid"
0xf10b  stelem.ref
0xf10c  stloc.1
0xf10d  ldstr    aAppointment// "appointment"
0xf112  ldarg.1
0xf113  ldloc.1
0xf114  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf119  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf11e  stloc.0
0xf11f  ldarg.0
0xf120  ldc.i4.1
0xf121  stfld    bool Microsoft.Crm.Common.Web.Activities.Dialogs.SeriesActionDialog::_setSeriesDetails
0xf126  ldloc.0
0xf127  ldstr    aSeriesid_0// "seriesid"
0xf12c  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xf131  brfalse.s loc_F149
0xf133  ldarg.0
0xf134  ldloc.0
0xf135  ldstr    aSeriesid_0// "seriesid"
0xf13a  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xf13f  unbox.any [mscorlib]System.Guid
0xf144  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Common.Web.Activities.Dialogs.SeriesActionDialog::_seriesId
0xf149  ldloc.0
0xf14a  ldstr    aSubject// "subject"
0xf14f  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xf154  brfalse  loc_F1D9
0xf159  ldarg.0
0xf15a  ldloc.0
0xf15b  ldstr    aSubject// "subject"
0xf160  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xf165  castclass [mscorlib]System.String
0xf16a  stfld    string Microsoft.Crm.Common.Web.Activities.Dialogs.SeriesActionDialog::_subject
0xf16f  ldarg.0
0xf170  ldfld    string Microsoft.Crm.Common.Web.Activities.Dialogs.SeriesActionDialog::_subject
0xf175  callvirt instance int32 [mscorlib]System.String::get_Length()
0xf17a  ldc.i4.s 0x14
0xf17c  ble.s    loc_F1D9
0xf17e  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0xf183  callvirt instance class [mscorlib]System.Globalization.TextInfo [mscorlib]System.Globalization.CultureInfo::get_TextInfo()
0xf188  callvirt instance bool [mscorlib]System.Globalization.TextInfo::get_IsRightToLeft()
0xf18d  dup
0xf18e  brtrue.s loc_F193
0xf190  ldc.i4.0
0xf191  br.s     loc_F1A1
0xf193  ldarg.0
0xf194  ldfld    string Microsoft.Crm.Common.Web.Activities.Dialogs.SeriesActionDialog::_subject
0xf199  callvirt instance int32 [mscorlib]System.String::get_Length()
0xf19e  ldc.i4.s 0x15
0xf1a0  sub
0xf1a1  stloc.2
0xf1a2  brtrue.s loc_F1AB
0xf1a4  ldstr    a0_0// "{0}..."
0xf1a9  br.s     loc_F1B0
0xf1ab  ldstr    a0_1// "...{0}"
0xf1b0  stloc.3
0xf1b1  ldarg.0
0xf1b2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf1b7  ldloc.3
0xf1b8  ldc.i4.1
0xf1b9  newarr   [mscorlib]System.Object
0xf1be  dup
0xf1bf  ldc.i4.0
0xf1c0  ldarg.0
0xf1c1  ldfld    string Microsoft.Crm.Common.Web.Activities.Dialogs.SeriesActionDialog::_subject
0xf1c6  ldloc.2
0xf1c7  ldc.i4.s 0x14
0xf1c9  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0xf1ce  stelem.ref
0xf1cf  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xf1d4  stfld    string Microsoft.Crm.Common.Web.Activities.Dialogs.SeriesActionDialog::_subject
0xf1d9  ret
```
