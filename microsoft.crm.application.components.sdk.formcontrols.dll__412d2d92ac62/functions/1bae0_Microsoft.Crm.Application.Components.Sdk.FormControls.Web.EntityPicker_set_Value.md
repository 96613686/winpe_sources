# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EntityPicker::set_Value

- ea: `0x1bae0`
- end: `0x1bc84`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EntityPicker::set_Value`
- size: `420`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x17990`
- `0x17cf0`
- `0x1bae0`
- `0x1bc90`
- `0x237d0`

## pseudocode

```c

```

## disassembly

```asm
0x1bae0  ldarg.0
0x1bae1  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmFormUIControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlUIWrapper::get_InnerControl()
0x1bae6  isinst   [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select
0x1baeb  stloc.0
0x1baec  ldloca.s 1
0x1baee  ldc.i4.m1
0x1baef  call     instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x1baf4  ldarg.1
0x1baf5  brtrue.s loc_1BB2C
0x1baf7  ldarg.0
0x1baf8  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_DataSource()
0x1bafd  brfalse.s loc_1BB0C
0x1baff  ldarg.0
0x1bb00  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_DataSource()
0x1bb05  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_IsNew()
0x1bb0a  brfalse.s loc_1BB16
0x1bb0c  ldloca.s 1
0x1bb0e  ldc.i4.0
0x1bb0f  call     instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x1bb14  br.s     loc_1BB6F
0x1bb16  ldloca.s 1
0x1bb18  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x1bb1e  ldarg.0
0x1bb1f  ldloc.0
0x1bb20  ldstr    a1_0// "1"
0x1bb25  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EntityPicker::AddIsValueNullExpando(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select innerControl, string value)
0x1bb2a  br.s     loc_1BB6F
0x1bb2c  ldarg.1
0x1bb2d  isinst   [mscorlib]System.Int32
0x1bb32  brfalse.s loc_1BB4F
0x1bb34  ldloca.s 1
0x1bb36  ldarg.1
0x1bb37  unbox.any [mscorlib]System.Int32
0x1bb3c  call     instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x1bb41  ldarg.0
0x1bb42  ldloc.0
0x1bb43  ldstr    a0// "0"
0x1bb48  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EntityPicker::AddIsValueNullExpando(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select innerControl, string value)
0x1bb4d  br.s     loc_1BB6F
0x1bb4f  ldstr    aValue// "value"
0x1bb54  ldstr    aWrongValueType// "Wrong value type is passed to the contr"...
0x1bb59  ldarg.0
0x1bb5a  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1bb5f  ldstr    aThisControlOnl_3// ". This control only accepts integers as"...
0x1bb64  call     string [mscorlib]System.String::Concat(string, string, string)
0x1bb69  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string, string)
0x1bb6e  throw
0x1bb6f  ldloca.s 1
0x1bb71  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x1bb76  brtrue.s loc_1BB7F
0x1bb78  ldsfld   string [mscorlib]System.String::Empty
0x1bb7d  br.s     loc_1BB94
0x1bb7f  ldloca.s 1
0x1bb81  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x1bb86  stloc.s  4
0x1bb88  ldloca.s 4
0x1bb8a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1bb8f  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1bb94  stloc.2
0x1bb95  ldc.i4.0
0x1bb96  stloc.3
0x1bb97  ldloc.0
0x1bb98  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::get_OptionGroups()
0x1bb9d  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x1bba2  stloc.s  5
0x1bba4  br.s     loc_1BBFD
0x1bba6  ldloc.s  5
0x1bba8  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1bbad  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup
0x1bbb2  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup::get_Options()
0x1bbb7  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x1bbbc  stloc.s  6
0x1bbbe  br.s     loc_1BBDD
0x1bbc0  ldloc.s  6
0x1bbc2  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1bbc7  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Option
0x1bbcc  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Option::get_Value()
0x1bbd1  ldloc.2
0x1bbd2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1bbd7  brfalse.s loc_1BBDD
0x1bbd9  ldc.i4.1
0x1bbda  stloc.3
0x1bbdb  leave.s  loc_1BBFD
0x1bbdd  ldloc.s  6
0x1bbdf  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1bbe4  brtrue.s loc_1BBC0
0x1bbe6  leave.s  loc_1BBFD
0x1bbe8  ldloc.s  6
0x1bbea  isinst   [mscorlib]System.IDisposable
0x1bbef  stloc.s  7
0x1bbf1  ldloc.s  7
0x1bbf3  brfalse.s loc_1BBFC
0x1bbf5  ldloc.s  7
0x1bbf7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1bbfc  endfinally
0x1bbfd  ldloc.s  5
0x1bbff  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1bc04  brtrue.s loc_1BBA6
0x1bc06  leave.s  loc_1BC1D
0x1bc08  ldloc.s  5
0x1bc0a  isinst   [mscorlib]System.IDisposable
0x1bc0f  stloc.s  7
0x1bc11  ldloc.s  7
0x1bc13  brfalse.s loc_1BC1C
0x1bc15  ldloc.s  7
0x1bc17  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1bc1c  endfinally
0x1bc1d  ldloc.3
0x1bc1e  brtrue.s loc_1BC75
0x1bc20  ldloca.s 1
0x1bc22  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x1bc27  brfalse.s loc_1BC65
0x1bc29  ldloca.s 1
0x1bc2b  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x1bc30  brfalse.s loc_1BC65
0x1bc32  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1bc37  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1bc3c  stloc.s  8
0x1bc3e  ldarg.0
0x1bc3f  ldloc.s  8
0x1bc41  ldloca.s 1
0x1bc43  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x1bc48  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x1bc4d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_EntityInfo()
0x1bc52  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription::get_Name()
0x1bc57  ldloca.s 1
0x1bc59  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x1bc5e  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistControl::AddItem(string text, int32 value)
0x1bc63  br.s     loc_1BC75
0x1bc65  ldloc.0
0x1bc66  ldsfld   string [mscorlib]System.String::Empty
0x1bc6b  ldsfld   string [mscorlib]System.String::Empty
0x1bc70  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddItem(string, string)
0x1bc75  ldloc.0
0x1bc76  ldloc.2
0x1bc77  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::set_Selected(string)
0x1bc7c  ldarg.0
0x1bc7d  ldloc.1
0x1bc7e  stfld    valuetype [mscorlib]System.Nullable`1<int32> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EntityPicker::_data
0x1bc83  ret
```
