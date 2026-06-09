# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl::SetOptions

- ea: `0x23f20`
- end: `0x241a3`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl::SetOptions`
- size: `643`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x23ca0`
- `0x241b0`

## callees

- `0x17cf0`
- `0x182d0`
- `0x237c0`
- `0x237d0`
- `0x23c90`
- `0x23da0`
- `0x23f20`

## pseudocode

```c

```

## disassembly

```asm
0x23f20  ldarg.0
0x23f21  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmFormUIControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlUIWrapper::get_InnerControl()
0x23f26  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select
0x23f2b  stloc.0
0x23f2c  ldloc.0
0x23f2d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::Clear()
0x23f32  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x23f37  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x23f3c  stloc.1
0x23f3d  ldarg.0
0x23f3e  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl::get_OptionsMetadata()
0x23f43  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Entity()
0x23f48  ldstr    aStatecode// "statecode"
0x23f4d  ldc.i4.1
0x23f4e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x23f53  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StateAttributeMetadata
0x23f58  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IStateOptionsByValueCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StateAttributeMetadata::get_StateOptions()
0x23f5d  stloc.2
0x23f5e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x23f63  stloc.3
0x23f64  ldarg.0
0x23f65  call     instance int32[] Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl::get_States()
0x23f6a  stloc.s  4
0x23f6c  ldc.i4.0
0x23f6d  stloc.s  5
0x23f6f  br       loc_24118
0x23f74  ldloc.s  4
0x23f76  ldloc.s  5
0x23f78  ldelem.i4
0x23f79  stloc.s  6
0x23f7b  ldloc.2
0x23f7c  ldloc.s  6
0x23f7e  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEnumOptionsByValueCollection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StateOption>::get_Item(!!T0)
0x23f83  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Labels()
0x23f88  ldloc.1
0x23f89  ldloc.3
0x23f8a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x23f8f  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0x23f94  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup::.ctor(string)
0x23f99  stloc.s  7
0x23f9b  ldloc.s  7
0x23f9d  ldstr    aState// "state"
0x23fa2  ldloca.s 6
0x23fa4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x23fa9  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x23fae  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string, string)
0x23fb3  ldnull
0x23fb4  stloc.s  8
0x23fb6  ldarg.0
0x23fb7  ldfld    int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl::_currentstatus
0x23fbc  ldc.i4.m1
0x23fbd  beq.s    loc_24000
0x23fbf  ldloc.3
0x23fc0  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x23fc5  ldarg.0
0x23fc6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x23fcb  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Entity()
0x23fd0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0x23fd5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(valuetype [mscorlib]System.Guid)
0x23fda  ldstr    aStatuscode// "statuscode"
0x23fdf  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x23fe4  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StatusAttributeMetadata
0x23fe9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEnumOptionByValueDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumAttributeMetadata::get_Options()
0x23fee  ldarg.0
0x23fef  ldfld    int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl::_currentstatus
0x23ff4  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<int32, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>::get_Item(void)
0x23ff9  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StatusOption
0x23ffe  stloc.s  8
0x24000  ldarg.0
0x24001  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl::get_OptionsMetadata()
0x24006  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StatusAttributeMetadata
0x2400b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumAttributeMetadata::get_OptionSet()
0x24010  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEnumOptionCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata::get_OptionsInDisplayOrder()
0x24015  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>::GetEnumerator()
0x2401a  stloc.s  9
0x2401c  br       loc_240E1
0x24021  ldloc.s  9
0x24023  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>::get_Current()
0x24028  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StatusOption
0x2402d  stloc.s  0xA
0x2402f  ldloc.s  6
0x24031  ldloc.s  0xA
0x24033  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StatusOption::get_State()
0x24038  bne.un   loc_240E1
0x2403d  ldloc.s  8
0x2403f  brfalse.s loc_240B2
0x24041  ldarg.0
0x24042  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x24047  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Entity()
0x2404c  ldloc.3
0x2404d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x24052  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::IsStateModelAware(valuetype [mscorlib]System.Guid)
0x24057  brfalse.s loc_240B2
0x24059  ldarg.0
0x2405a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x2405f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Entity()
0x24064  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_EnforceStateTransitions()
0x24069  brfalse.s loc_240B2
0x2406b  ldloc.s  8
0x2406d  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<int32> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StatusOption::get_AllowedStatusTransition()
0x24072  ldloc.s  0xA
0x24074  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Value()
0x24079  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<int32>::IndexOf(var<u1>)
0x2407e  ldc.i4.m1
0x2407f  beq.s    loc_240E1
0x24081  ldloc.s  7
0x24083  ldloc.s  0xA
0x24085  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Labels()
0x2408a  ldloc.1
0x2408b  ldloc.3
0x2408c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x24091  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0x24096  ldloc.s  0xA
0x24098  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Value()
0x2409d  stloc.s  0xB
0x2409f  ldloca.s 0xB
0x240a1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x240a6  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x240ab  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup::AddItem(string, string)
0x240b0  br.s     loc_240E1
0x240b2  ldloc.s  7
0x240b4  ldloc.s  0xA
0x240b6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Labels()
0x240bb  ldloc.1
0x240bc  ldloc.3
0x240bd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x240c2  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0x240c7  ldloc.s  0xA
0x240c9  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Value()
0x240ce  stloc.s  0xB
0x240d0  ldloca.s 0xB
0x240d2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x240d7  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x240dc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup::AddItem(string, string)
0x240e1  ldloc.s  9
0x240e3  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x240e8  brtrue   loc_24021
0x240ed  leave.s  loc_240FB
0x240ef  ldloc.s  9
0x240f1  brfalse.s loc_240FA
0x240f3  ldloc.s  9
0x240f5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x240fa  endfinally
0x240fb  ldloc.s  7
0x240fd  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup::get_Options()
0x24102  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x24107  ldc.i4.0
0x24108  ble.s    loc_24112
0x2410a  ldarg.0
0x2410b  ldloc.s  7
0x2410d  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistControl::AddOptionGroup(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup newGroup)
0x24112  ldloc.s  5
0x24114  ldc.i4.1
0x24115  add
0x24116  stloc.s  5
0x24118  ldloc.s  5
0x2411a  ldloc.s  4
0x2411c  ldlen
0x2411d  conv.i4
0x2411e  blt      loc_23F74
0x24123  ldloc.0
0x24124  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::get_OptionGroups()
0x24129  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x2412e  ldc.i4.2
0x2412f  bne.un.s loc_241A2
0x24131  ldloc.0
0x24132  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::get_OptionGroups()
0x24137  ldc.i4.1
0x24138  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x2413d  isinst   [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup
0x24142  ldloc.0
0x24143  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::Clear()
0x24148  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup::get_Options()
0x2414d  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x24152  stloc.s  0xC
0x24154  br.s     loc_24182
0x24156  ldloc.s  0xC
0x24158  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x2415d  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Option
0x24162  stloc.s  0xD
0x24164  ldarg.0
0x24165  ldloc.s  0xD
0x24167  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Option::get_Text()
0x2416c  ldloc.s  0xD
0x2416e  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Option::get_Value()
0x24173  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x24178  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x2417d  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistControl::AddItem(string text, int32 value)
0x24182  ldloc.s  0xC
0x24184  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x24189  brtrue.s loc_24156
0x2418b  leave.s  loc_241A2
0x2418d  ldloc.s  0xC
0x2418f  isinst   [mscorlib]System.IDisposable
0x24194  stloc.s  0xE
0x24196  ldloc.s  0xE
0x24198  brfalse.s loc_241A1
0x2419a  ldloc.s  0xE
0x2419c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x241a1  endfinally
0x241a2  ret
```
