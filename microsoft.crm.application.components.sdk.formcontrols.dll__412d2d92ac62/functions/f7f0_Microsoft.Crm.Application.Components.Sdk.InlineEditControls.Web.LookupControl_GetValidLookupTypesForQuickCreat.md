# Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LookupControl::GetValidLookupTypesForQuickCreate

- ea: `0xf7f0`
- end: `0xfa52`
- name: `Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LookupControl::GetValidLookupTypesForQuickCreate`
- size: `610`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0xf690`

## callees

- `0x1350`
- `0x1450`
- `0x2ea0`
- `0x2f20`
- `0xf7f0`

## string_xrefs

- `0xf83e`: `solutioncomponent`

## pseudocode

```c

```

## disassembly

```asm
0xf7f0  ldarg.0
0xf7f1  ldfld    string Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LookupControl::_entityLogicalName
0xf7f6  ldstr    aActivitypointe_1// "activitypointer"
0xf7fb  call     bool [mscorlib]System.String::op_Equality(string, string)
0xf800  brtrue.s loc_F84A
0xf802  ldarg.0
0xf803  ldfld    string Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LookupControl::_entityLogicalName
0xf808  ldstr    aQueueitem// "queueitem"
0xf80d  call     bool [mscorlib]System.String::op_Equality(string, string)
0xf812  brtrue.s loc_F84A
0xf814  ldarg.0
0xf815  ldfld    string Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LookupControl::_entityLogicalName
0xf81a  ldstr    aResource// "resource"
0xf81f  call     bool [mscorlib]System.String::op_Equality(string, string)
0xf824  brtrue.s loc_F84A
0xf826  ldarg.0
0xf827  ldfld    string Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LookupControl::_entityLogicalName
0xf82c  ldstr    aAsyncoperation// "asyncoperation"
0xf831  call     bool [mscorlib]System.String::op_Equality(string, string)
0xf836  brtrue.s loc_F84A
0xf838  ldarg.0
0xf839  ldfld    string Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LookupControl::_entityLogicalName
0xf83e  ldstr    aSolutioncompon// "solutioncomponent"
0xf843  call     bool [mscorlib]System.String::op_Equality(string, string)
0xf848  brfalse.s loc_F855
0xf84a  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<int32>::.ctor()
0xf84f  newobj   instance void class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<int32>::.ctor(class [mscorlib]System.Collections.Generic.IList`1<var<u1>>)
0xf854  ret
0xf855  ldarg.0
0xf856  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0xf85b  brfalse  loc_F9CB
0xf860  ldarg.0
0xf861  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_CurrentFormDescriptor()
0xf866  callvirt instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor::get_FormType()
0xf86b  ldc.i4.2
0xf86c  beq.s    loc_F88E
0xf86e  ldarg.0
0xf86f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_CurrentFormDescriptor()
0xf874  callvirt instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor::get_FormType()
0xf879  ldc.i4.4
0xf87a  beq.s    loc_F88E
0xf87c  ldarg.0
0xf87d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_CurrentFormDescriptor()
0xf882  callvirt instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor::get_FormType()
0xf887  ldc.i4.s 9
0xf889  bne.un   loc_F9C0
0xf88e  ldarg.0
0xf88f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0xf894  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Type()
0xf899  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_AttributeType()
0xf89e  ldc.i4.7
0xf89f  bne.un.s loc_F90F
0xf8a1  ldarg.0
0xf8a2  callvirt instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.LookupControl::get_LookupStyle()
0xf8a7  ldstr    aSingle// "single"
0xf8ac  call     bool [mscorlib]System.String::op_Equality(string, string)
0xf8b1  brfalse.s loc_F90F
0xf8b3  ldarg.0
0xf8b4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0xf8b9  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LookupAttributeMetadata
0xf8be  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<int32> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LookupAttributeMetadata::get_LookupTypes()
0xf8c3  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<int32>::get_Count()
0xf8c8  ldc.i4.1
0xf8c9  bne.un   loc_F9C0
0xf8ce  ldarg.0
0xf8cf  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf8d4  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf8d9  ldarg.0
0xf8da  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0xf8df  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LookupAttributeMetadata
0xf8e4  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<int32> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LookupAttributeMetadata::get_LookupTypes()
0xf8e9  ldc.i4.0
0xf8ea  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<int32>::get_Item(!!T0)
0xf8ef  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0xf8f4  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xf8f9  stfld    string Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LookupControl::_entityLogicalName
0xf8fe  ldarg.0
0xf8ff  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0xf904  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LookupAttributeMetadata
0xf909  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<int32> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LookupAttributeMetadata::get_LookupTypes()
0xf90e  ret
0xf90f  ldarg.0
0xf910  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0xf915  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Type()
0xf91a  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_AttributeType()
0xf91f  ldc.i4.1
0xf920  bne.un.s loc_F98F
0xf922  ldarg.0
0xf923  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0xf928  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0xf92d  ldstr    aParentcustomer// "parentcustomerid"
0xf932  call     bool [mscorlib]System.String::op_Equality(string, string)
0xf937  brfalse.s loc_F972
0xf939  ldarg.0
0xf93a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0xf93f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Entity()
0xf944  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xf949  ldstr    aContact// "contact"
0xf94e  call     bool [mscorlib]System.String::op_Equality(string, string)
0xf953  brfalse.s loc_F972
0xf955  ldarg.0
0xf956  ldstr    aAccount// "account"
0xf95b  stfld    string Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LookupControl::_entityLogicalName
0xf960  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<int32>::.ctor()
0xf965  dup
0xf966  ldc.i4.1
0xf967  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0xf96c  newobj   instance void class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<int32>::.ctor(class [mscorlib]System.Collections.Generic.IList`1<var<u1>>)
0xf971  ret
0xf972  ldarg.0
0xf973  ldstr    aContact// "contact"
0xf978  stfld    string Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LookupControl::_entityLogicalName
0xf97d  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<int32>::.ctor()
0xf982  dup
0xf983  ldc.i4.2
0xf984  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0xf989  newobj   instance void class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<int32>::.ctor(class [mscorlib]System.Collections.Generic.IList`1<var<u1>>)
0xf98e  ret
0xf98f  ldarg.0
0xf990  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0xf995  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Type()
0xf99a  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_AttributeType()
0xf99f  ldc.i4.s 0xB
0xf9a1  bne.un.s loc_F9C0
0xf9a3  ldarg.0
0xf9a4  ldstr    aContact// "contact"
0xf9a9  stfld    string Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LookupControl::_entityLogicalName
0xf9ae  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<int32>::.ctor()
0xf9b3  dup
0xf9b4  ldc.i4.2
0xf9b5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0xf9ba  newobj   instance void class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<int32>::.ctor(class [mscorlib]System.Collections.Generic.IList`1<var<u1>>)
0xf9bf  ret
0xf9c0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<int32>::.ctor()
0xf9c5  newobj   instance void class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<int32>::.ctor(class [mscorlib]System.Collections.Generic.IList`1<var<u1>>)
0xf9ca  ret
0xf9cb  ldarg.0
0xf9cc  callvirt instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.LookupControl::get_UnboundLookupTypes()
0xf9d1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xf9d6  brtrue.s loc_FA47
0xf9d8  ldarg.0
0xf9d9  callvirt instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.LookupControl::get_UnboundLookupTypes()
0xf9de  ldc.i4.1
0xf9df  newarr   [mscorlib]System.Char
0xf9e4  dup
0xf9e5  ldc.i4.0
0xf9e6  ldc.i4.s 0x2C
0xf9e8  stelem.i2
0xf9e9  callvirt instance string[] [mscorlib]System.String::Split(char[])
0xf9ee  stloc.0
0xf9ef  ldloc.0
0xf9f0  ldlen
0xf9f1  conv.i4
0xf9f2  newarr   [mscorlib]System.Int32
0xf9f7  stloc.1
0xf9f8  ldc.i4.0
0xf9f9  stloc.2
0xf9fa  br.s     loc_FA10
0xf9fc  ldloc.1
0xf9fd  ldloc.2
0xf9fe  ldloc.0
0xf9ff  ldloc.2
0xfa00  ldelem.ref
0xfa01  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xfa06  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0xfa0b  stelem.i4
0xfa0c  ldloc.2
0xfa0d  ldc.i4.1
0xfa0e  add
0xfa0f  stloc.2
0xfa10  ldloc.2
0xfa11  ldloc.0
0xfa12  ldlen
0xfa13  conv.i4
0xfa14  blt.s    loc_F9FC
0xfa16  ldarg.0
0xfa17  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xfa1c  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xfa21  ldloc.1
0xfa22  ldc.i4.0
0xfa23  ldelem.i4
0xfa24  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0xfa29  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xfa2e  stfld    string Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LookupControl::_entityLogicalName
0xfa33  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<int32>::.ctor()
0xfa38  dup
0xfa39  ldloc.1
0xfa3a  ldc.i4.0
0xfa3b  ldelem.i4
0xfa3c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0xfa41  newobj   instance void class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<int32>::.ctor(class [mscorlib]System.Collections.Generic.IList`1<var<u1>>)
0xfa46  ret
0xfa47  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<int32>::.ctor()
0xfa4c  newobj   instance void class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<int32>::.ctor(class [mscorlib]System.Collections.Generic.IList`1<var<u1>>)
0xfa51  ret
```
