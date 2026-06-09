# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistLookupControl::PopulateControl

- ea: `0x23ac0`
- end: `0x23c43`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistLookupControl::PopulateControl`
- size: `387`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x23a60`

## callees

- `0x182d0`
- `0x185d0`
- `0x239c0`
- `0x239e0`
- `0x23a00`
- `0x23a20`
- `0x23ac0`

## pseudocode

```c

```

## disassembly

```asm
0x23ac0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x23ac5  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x23aca  ldarg.0
0x23acb  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x23ad0  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_ReferencedEntityObjectTypeCode()
0x23ad5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x23ada  stloc.0
0x23adb  ldarg.0
0x23adc  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistLookupControl::get_TextField()
0x23ae1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x23ae6  brtrue.s loc_23AF0
0x23ae8  ldarg.0
0x23ae9  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistLookupControl::get_TextField()
0x23aee  br.s     loc_23AFB
0x23af0  ldloc.0
0x23af1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryField()
0x23af6  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x23afb  stloc.1
0x23afc  ldarg.0
0x23afd  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistLookupControl::get_ValueField()
0x23b02  stloc.2
0x23b03  ldloc.2
0x23b04  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x23b09  brfalse.s loc_23B5C
0x23b0b  ldloc.0
0x23b0c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x23b11  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.IDictionary::get_Values()
0x23b16  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x23b1b  stloc.3
0x23b1c  br.s     loc_23B3E
0x23b1e  ldloc.3
0x23b1f  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x23b24  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata
0x23b29  stloc.s  4
0x23b2b  ldloc.s  4
0x23b2d  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_IsPKAttribute()
0x23b32  brfalse.s loc_23B3E
0x23b34  ldloc.s  4
0x23b36  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x23b3b  stloc.2
0x23b3c  leave.s  loc_23B5C
0x23b3e  ldloc.3
0x23b3f  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x23b44  brtrue.s loc_23B1E
0x23b46  leave.s  loc_23B5C
0x23b48  ldloc.3
0x23b49  isinst   [mscorlib]System.IDisposable
0x23b4e  stloc.s  5
0x23b50  ldloc.s  5
0x23b52  brfalse.s loc_23B5B
0x23b54  ldloc.s  5
0x23b56  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x23b5b  endfinally
0x23b5c  ldarg.0
0x23b5d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistLookupControl::get_DataEntities()
0x23b62  brfalse  loc_23BF9
0x23b67  ldarg.0
0x23b68  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistLookupControl::get_DataEntities()
0x23b6d  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x23b72  ldc.i4.0
0x23b73  ble      loc_23BF9
0x23b78  ldarg.0
0x23b79  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistLookupControl::get_DataEntities()
0x23b7e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::GetEnumerator()
0x23b83  stloc.s  7
0x23b85  br.s     loc_23BBD
0x23b87  ldloc.s  7
0x23b89  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Current()
0x23b8e  dup
0x23b8f  ldloc.2
0x23b90  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x23b95  unbox.any [mscorlib]System.Guid
0x23b9a  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GuidToString(valuetype [mscorlib]System.Guid)
0x23b9f  stloc.s  8
0x23ba1  ldloc.1
0x23ba2  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x23ba7  castclass [mscorlib]System.String
0x23bac  stloc.s  9
0x23bae  ldarg.0
0x23baf  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistLookupControl::_innerSelect
0x23bb4  ldloc.s  9
0x23bb6  ldloc.s  8
0x23bb8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddItem(string, string)
0x23bbd  ldloc.s  7
0x23bbf  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x23bc4  brtrue.s loc_23B87
0x23bc6  leave.s  loc_23BD4
0x23bc8  ldloc.s  7
0x23bca  brfalse.s loc_23BD3
0x23bcc  ldloc.s  7
0x23bce  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x23bd3  endfinally
0x23bd4  ldarg.0
0x23bd5  call     instance object Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::get_Value()
0x23bda  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0x23bdf  stloc.s  6
0x23be1  ldloc.s  6
0x23be3  brfalse.s loc_23C05
0x23be5  ldarg.0
0x23be6  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistLookupControl::_innerSelect
0x23beb  ldloc.s  6
0x23bed  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_ID()
0x23bf2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::set_Selected(string)
0x23bf7  br.s     loc_23C05
0x23bf9  ldarg.0
0x23bfa  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistLookupControl::_innerSelect
0x23bff  ldc.i4.1
0x23c00  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0x23c05  ldarg.0
0x23c06  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistLookupControl::get_ClassName()
0x23c0b  callvirt instance int32 [mscorlib]System.String::get_Length()
0x23c10  ldc.i4.0
0x23c11  ble.s    loc_23C42
0x23c13  ldarg.0
0x23c14  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistLookupControl::_innerSelect
0x23c19  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::get_ClassNames()
0x23c1e  ldarg.0
0x23c1f  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistLookupControl::get_ClassName()
0x23c24  callvirt instance bool [mscorlib]System.Collections.ArrayList::Contains(object)
0x23c29  brtrue.s loc_23C42
0x23c2b  ldarg.0
0x23c2c  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistLookupControl::_innerSelect
0x23c31  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::get_ClassNames()
0x23c36  ldarg.0
0x23c37  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistLookupControl::get_ClassName()
0x23c3c  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x23c41  pop
0x23c42  ret
```
