# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LanguagePicker::set_Value

- ea: `0x1eeb0`
- end: `0x1f03c`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LanguagePicker::set_Value`
- size: `396`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x17990`
- `0x17cf0`
- `0x1eeb0`
- `0x1f040`
- `0x237d0`

## pseudocode

```c

```

## disassembly

```asm
0x1eeb0  ldarg.0
0x1eeb1  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmFormUIControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlUIWrapper::get_InnerControl()
0x1eeb6  isinst   [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select
0x1eebb  stloc.0
0x1eebc  ldloca.s 1
0x1eebe  ldc.i4.m1
0x1eebf  call     instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x1eec4  ldarg.1
0x1eec5  brtrue.s loc_1EF05
0x1eec7  ldarg.0
0x1eec8  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_DataSource()
0x1eecd  brfalse.s loc_1EEDC
0x1eecf  ldarg.0
0x1eed0  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_DataSource()
0x1eed5  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_IsNew()
0x1eeda  brfalse.s loc_1EEEF
0x1eedc  ldloca.s 1
0x1eede  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x1eee3  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x1eee8  call     instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x1eeed  br.s     loc_1EF48
0x1eeef  ldloca.s 1
0x1eef1  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x1eef7  ldarg.0
0x1eef8  ldloc.0
0x1eef9  ldstr    a1_0// "1"
0x1eefe  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LanguagePicker::AddIsValueNullExpando(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select innerControl, string value)
0x1ef03  br.s     loc_1EF48
0x1ef05  ldarg.1
0x1ef06  isinst   [mscorlib]System.Int32
0x1ef0b  brfalse.s loc_1EF28
0x1ef0d  ldloca.s 1
0x1ef0f  ldarg.1
0x1ef10  unbox.any [mscorlib]System.Int32
0x1ef15  call     instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x1ef1a  ldarg.0
0x1ef1b  ldloc.0
0x1ef1c  ldstr    a0// "0"
0x1ef21  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LanguagePicker::AddIsValueNullExpando(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select innerControl, string value)
0x1ef26  br.s     loc_1EF48
0x1ef28  ldstr    aValue// "value"
0x1ef2d  ldstr    aWrongValueType// "Wrong value type is passed to the contr"...
0x1ef32  ldarg.0
0x1ef33  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1ef38  ldstr    aThisControlOnl_3// ". This control only accepts integers as"...
0x1ef3d  call     string [mscorlib]System.String::Concat(string, string, string)
0x1ef42  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string, string)
0x1ef47  throw
0x1ef48  ldloca.s 1
0x1ef4a  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x1ef4f  brtrue.s loc_1EF58
0x1ef51  ldsfld   string [mscorlib]System.String::Empty
0x1ef56  br.s     loc_1EF6D
0x1ef58  ldloca.s 1
0x1ef5a  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x1ef5f  stloc.s  4
0x1ef61  ldloca.s 4
0x1ef63  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1ef68  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1ef6d  stloc.2
0x1ef6e  ldc.i4.0
0x1ef6f  stloc.3
0x1ef70  ldloc.0
0x1ef71  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::get_OptionGroups()
0x1ef76  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x1ef7b  stloc.s  5
0x1ef7d  br.s     loc_1EFD6
0x1ef7f  ldloc.s  5
0x1ef81  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1ef86  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup
0x1ef8b  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup::get_Options()
0x1ef90  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x1ef95  stloc.s  6
0x1ef97  br.s     loc_1EFB6
0x1ef99  ldloc.s  6
0x1ef9b  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1efa0  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Option
0x1efa5  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Option::get_Value()
0x1efaa  ldloc.2
0x1efab  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1efb0  brfalse.s loc_1EFB6
0x1efb2  ldc.i4.1
0x1efb3  stloc.3
0x1efb4  leave.s  loc_1EFD6
0x1efb6  ldloc.s  6
0x1efb8  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1efbd  brtrue.s loc_1EF99
0x1efbf  leave.s  loc_1EFD6
0x1efc1  ldloc.s  6
0x1efc3  isinst   [mscorlib]System.IDisposable
0x1efc8  stloc.s  7
0x1efca  ldloc.s  7
0x1efcc  brfalse.s loc_1EFD5
0x1efce  ldloc.s  7
0x1efd0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1efd5  endfinally
0x1efd6  ldloc.s  5
0x1efd8  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1efdd  brtrue.s loc_1EF7F
0x1efdf  leave.s  loc_1EFF6
0x1efe1  ldloc.s  5
0x1efe3  isinst   [mscorlib]System.IDisposable
0x1efe8  stloc.s  7
0x1efea  ldloc.s  7
0x1efec  brfalse.s loc_1EFF5
0x1efee  ldloc.s  7
0x1eff0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1eff5  endfinally
0x1eff6  ldloc.3
0x1eff7  brtrue.s loc_1F02D
0x1eff9  ldloca.s 1
0x1effb  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x1f000  brfalse.s loc_1F01D
0x1f002  ldarg.0
0x1f003  ldloca.s 1
0x1f005  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x1f00a  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.ApplicationLanguage::GetLanguageDisplayName(int32)
0x1f00f  ldloca.s 1
0x1f011  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x1f016  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistControl::AddItem(string text, int32 value)
0x1f01b  br.s     loc_1F02D
0x1f01d  ldloc.0
0x1f01e  ldsfld   string [mscorlib]System.String::Empty
0x1f023  ldsfld   string [mscorlib]System.String::Empty
0x1f028  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddItem(string, string)
0x1f02d  ldloc.0
0x1f02e  ldloc.2
0x1f02f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::set_Selected(string)
0x1f034  ldarg.0
0x1f035  ldloc.1
0x1f036  stfld    valuetype [mscorlib]System.Nullable`1<int32> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LanguagePicker::_data
0x1f03b  ret
```
