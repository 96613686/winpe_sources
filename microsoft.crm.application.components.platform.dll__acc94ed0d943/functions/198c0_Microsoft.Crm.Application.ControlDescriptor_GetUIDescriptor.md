# Microsoft.Crm.Application.ControlDescriptor::GetUIDescriptor

- ea: `0x198c0`
- end: `0x19d4d`
- name: `Microsoft.Crm.Application.ControlDescriptor::GetUIDescriptor`
- size: `1165`
- prototype: ``
- caller_count: `3`
- callee_count: `32`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1eed0`
- `0x20850`
- `0xa33a0`

## callees

- `0x19590`
- `0x19610`
- `0x19680`
- `0x196a0`
- `0x19710`
- `0x19790`
- `0x197a0`
- `0x197b0`
- `0x197c0`
- `0x197d0`
- `0x19810`
- `0x19820`
- `0x19830`
- `0x198c0`
- `0x19d50`
- `0x19dd0`
- `0x1a6d0`
- `0x1a770`
- `0x1a800`
- `0x1a860`
- `0x1a8c0`
- `0x1a8f0`
- `0x1a960`
- `0x1a9a0`
- `0x1aa40`
- `0x1f7c0`
- `0x1f800`
- `0x20390`
- `0x20420`
- `0x20430`
- `0x39c00`
- `0x39f70`

## string_xrefs

- `0x19a96`: `isKMConfigured`
- `0x19abb`: `externalServiceUrl`

## pseudocode

```c

```

## disassembly

```asm
0x198c0  ldsfld   string [mscorlib]System.String::Empty
0x198c5  stloc.0
0x198c6  ldarg.0
0x198c7  call     instance class Microsoft.Crm.Application.CellDescriptor Microsoft.Crm.Application.ControlDescriptor::get_ParentCellDescriptor()
0x198cc  brfalse.s loc_198DF
0x198ce  ldarg.0
0x198cf  call     instance class Microsoft.Crm.Application.CellDescriptor Microsoft.Crm.Application.ControlDescriptor::get_ParentCellDescriptor()
0x198d4  callvirt instance class Microsoft.Crm.Application.LabelDescriptor Microsoft.Crm.Application.FormPartWithLabelDescriptor::get_UserLabel()
0x198d9  callvirt instance string Microsoft.Crm.Application.LabelDescriptor::get_Description()
0x198de  stloc.0
0x198df  ldloc.0
0x198e0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x198e5  brfalse.s loc_198F7
0x198e7  ldarg.0
0x198e8  ldfld    string Microsoft.Crm.Application.ControlDescriptor::_label
0x198ed  dup
0x198ee  brtrue.s loc_198F6
0x198f0  pop
0x198f1  ldsfld   string [mscorlib]System.String::Empty
0x198f6  stloc.0
0x198f7  ldarg.0
0x198f8  call     instance string Microsoft.Crm.Application.ControlDescriptor::get_ClassId()
0x198fd  stloc.1
0x198fe  ldarg.0
0x198ff  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.ControlDescriptor::get_Metadata()
0x19904  brfalse.s loc_1992B
0x19906  ldarg.0
0x19907  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.ControlDescriptor::get_Metadata()
0x1990c  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Format()
0x19911  ldstr    aPhone// "phone"
0x19916  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1991b  brfalse.s loc_1992B
0x1991d  ldarg.0
0x1991e  call     instance bool Microsoft.Crm.Application.ControlDescriptor::CanUpdateClassIdForPhoneNumberControl()
0x19923  brfalse.s loc_1992B
0x19925  ldstr    a8c10015aB33949// "{8C10015A-B339-4982-9474-A95FE05631A5}"
0x1992a  stloc.1
0x1992b  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x19930  stloc.2
0x19931  ldarg.0
0x19932  call     instance class Microsoft.Crm.Application.ParameterCollection Microsoft.Crm.Application.ControlDescriptor::get_Parameters()
0x19937  callvirt instance class [mscorlib]System.Collections.IEnumerator class Microsoft.Crm.Application.ReadOnlyListCollection`1<class Microsoft.Crm.Application.ParameterDescriptor>::GetEnumerator()
0x1993c  stloc.3
0x1993d  br.s     loc_19960
0x1993f  ldloc.3
0x19940  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x19945  castclass Microsoft.Crm.Application.ParameterDescriptor
0x1994a  stloc.s  4
0x1994c  ldloc.2
0x1994d  ldloc.s  4
0x1994f  callvirt instance string Microsoft.Crm.Application.ParameterDescriptor::get_Name()
0x19954  ldloc.s  4
0x19956  callvirt instance string Microsoft.Crm.Application.ParameterDescriptor::get_Value()
0x1995b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x19960  ldloc.3
0x19961  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x19966  brtrue.s loc_1993F
0x19968  leave.s  loc_1997E
0x1996a  ldloc.3
0x1996b  isinst   [mscorlib]System.IDisposable
0x19970  stloc.s  5
0x19972  ldloc.s  5
0x19974  brfalse.s loc_1997D
0x19976  ldloc.s  5
0x19978  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1997d  endfinally
0x1997e  ldloc.1
0x1997f  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x19984  ldstr    a270bd3dbD9af47// "{270BD3DB-D9AF-4782-9025-509E298DEC0A}"
0x19989  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1998e  brtrue.s loc_1999C
0x19990  ldarg.0
0x19991  call     instance valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.FormControlType Microsoft.Crm.Application.ControlDescriptor::get_ControlType()
0x19996  ldc.i4.3
0x19997  bne.un   loc_19A71
0x1999c  ldarg.0
0x1999d  call     instance bool Microsoft.Crm.Application.ControlDescriptor::get_IsUnbound()
0x199a2  brfalse.s loc_199D9
0x199a4  ldarg.0
0x199a5  call     instance string Microsoft.Crm.Application.ControlDescriptor::SetDefaultViewIdForUnboundLookup()
0x199aa  stloc.s  6
0x199ac  ldloc.2
0x199ad  ldstr    aDefaultviewid// "DefaultViewId"
0x199b2  ldloc.s  6
0x199b4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x199b9  ldarg.0
0x199ba  call     instance string Microsoft.Crm.Application.ControlDescriptor::SetUnboundLookupStyle()
0x199bf  stloc.s  9
0x199c1  ldloc.s  9
0x199c3  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x199c8  brtrue.s loc_199EE
0x199ca  ldloc.2
0x199cb  ldstr    aUnboundlookups// "UnboundLookupStyle"
0x199d0  ldloc.s  9
0x199d2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x199d7  br.s     loc_199EE
0x199d9  ldarg.0
0x199da  call     instance string Microsoft.Crm.Application.ControlDescriptor::SetDefaultViewId()
0x199df  stloc.s  6
0x199e1  ldloc.2
0x199e2  ldstr    aDefaultviewid_0// "defaultviewid"
0x199e7  ldloc.s  6
0x199e9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x199ee  ldsfld   string [mscorlib]System.String::Empty
0x199f3  stloc.s  7
0x199f5  ldarg.0
0x199f6  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.ControlDescriptor::get_Metadata()
0x199fb  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LookupAttributeMetadata
0x19a00  stloc.s  8
0x19a02  ldloc.s  8
0x19a04  brfalse.s loc_19A49
0x19a06  ldloc.s  8
0x19a08  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<int32> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LookupAttributeMetadata::get_LookupTypes()
0x19a0d  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<int32>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x19a12  call     instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<int32>::ToArray()
0x19a17  stloc.s  0xA
0x19a19  ldarg.0
0x19a1a  ldloc.s  0xA
0x19a1c  call     instance void Microsoft.Crm.Application.ControlDescriptor::SetLookupTypes(int32[] typesToSet)
0x19a21  ldarg.0
0x19a22  call     instance int32 Microsoft.Crm.Application.ControlDescriptor::get_DefaultType()
0x19a27  brtrue.s loc_19A40
0x19a29  ldarg.0
0x19a2a  ldfld    int32[] Microsoft.Crm.Application.ControlDescriptor::_lookupTypes
0x19a2f  ldlen
0x19a30  brfalse.s loc_19A40
0x19a32  ldarg.0
0x19a33  ldarg.0
0x19a34  ldfld    int32[] Microsoft.Crm.Application.ControlDescriptor::_lookupTypes
0x19a39  ldc.i4.0
0x19a3a  ldelem.i4
0x19a3b  call     instance void Microsoft.Crm.Application.ControlDescriptor::set_DefaultType(int32 value)
0x19a40  ldloc.s  8
0x19a42  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LookupAttributeMetadata::get_LookupStyle()
0x19a47  stloc.s  7
0x19a49  ldloc.2
0x19a4a  ldstr    aDefaulttype// "defaulttype"
0x19a4f  ldarg.0
0x19a50  call     instance int32 Microsoft.Crm.Application.ControlDescriptor::get_DefaultType()
0x19a55  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x19a5a  call     string [mscorlib]System.Convert::ToString(int32, class [mscorlib]System.IFormatProvider)
0x19a5f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x19a64  ldloc.2
0x19a65  ldstr    aLookupstyle// "lookupstyle"
0x19a6a  ldloc.s  7
0x19a6c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x19a71  ldloc.1
0x19a72  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x19a77  ldstr    aE616a57f20e045// "{E616A57F-20E0-4534-8662-A101B5DDF4E0}"
0x19a7c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x19a81  brtrue.s loc_19A95
0x19a83  ldloc.1
0x19a84  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x19a89  ldstr    a7ccd14941f7a4e// "{7CCD1494-1F7A-4E3A-8BDE-F32069DAEB9F}"
0x19a8e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x19a93  brfalse.s loc_19B08
0x19a95  ldloc.2
0x19a96  ldstr    aIskmconfigured// "isKMConfigured"
0x19a9b  ldarg.0
0x19a9c  call     instance bool Microsoft.Crm.Application.ControlDescriptor::get_IsKnowledgeMangementParatureConfigured()
0x19aa1  brtrue.s loc_19AAB
0x19aa3  ldarg.0
0x19aa4  call     instance bool Microsoft.Crm.Application.ControlDescriptor::get_IsKnowledgeManagementNativeCrmConfigured()
0x19aa9  br.s     loc_19AAC
0x19aab  ldc.i4.1
0x19aac  stloc.s  0xC
0x19aae  ldloca.s 0xC
0x19ab0  call     instance string [mscorlib]System.Boolean::ToString()
0x19ab5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x19aba  ldloc.2
0x19abb  ldstr    aExternalservic// "externalServiceUrl"
0x19ac0  ldarg.0
0x19ac1  call     instance string Microsoft.Crm.Application.ControlDescriptor::getExternalServiceUrl()
0x19ac6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x19acb  ldloc.2
0x19acc  ldstr    aPortaldomain// "portalDomain"
0x19ad1  ldarg.0
0x19ad2  call     instance string Microsoft.Crm.Application.ControlDescriptor::GetSupportUrl()
0x19ad7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x19adc  ldstr    aSearchwidgetSe// "/SearchWidget/SearchWidgetWallContent.a"...
0x19ae1  ldarg.0
0x19ae2  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.ControlDescriptor::_context
0x19ae7  call     class Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.Utility.CrmUri::CreateWebResourceUri(string path, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x19aec  stloc.s  0xB
0x19aee  ldloc.s  0xB
0x19af0  ldc.i4.1
0x19af1  callvirt instance void Microsoft.Crm.Application.Utility.CrmUri::set_UseVersionStamp(bool value)
0x19af6  ldloc.2
0x19af7  ldstr    aWallcontentpag// "wallContentPageUrl"
0x19afc  ldloc.s  0xB
0x19afe  callvirt instance string [mscorlib]System.Object::ToString()
0x19b03  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x19b08  ldarg.0
0x19b09  call     instance string Microsoft.Crm.Application.ControlDescriptor::get_DataFieldName()
0x19b0e  brtrue   loc_19C43
0x19b13  ldloc.1
0x19b14  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x19b19  ldstr    a9fdf5f9188b147// "{9FDF5F91-88B1-47F4-AD53-C11EFC01A01D}"
0x19b1e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x19b23  brtrue.s loc_19B49
0x19b25  ldloc.1
0x19b26  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x19b2b  ldstr    a587cdf98C1d54b// "{587CDF98-C1D5-4BDE-8473-14A0BC7644A7}"
0x19b30  call     bool [mscorlib]System.String::op_Equality(string, string)
0x19b35  brtrue.s loc_19B49
0x19b37  ldloc.1
0x19b38  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x19b3d  ldstr    a080677db86ec45// "{080677DB-86EC-4544-AC42-F927E74B491F}"
0x19b42  call     bool [mscorlib]System.String::op_Equality(string, string)
0x19b47  brfalse.s loc_19B51
0x19b49  ldarg.0
0x19b4a  ldloc.2
0x19b4b  ldc.i4.1
0x19b4c  call     instance void Microsoft.Crm.Application.ControlDescriptor::SetWebResourceUrl(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> parameters, bool setWebResourceHash)
0x19b51  ldarg.0
0x19b52  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.ControlDescriptor::get_UniqueId()
0x19b57  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x19b5c  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x19b61  brfalse  loc_19BF3
0x19b66  ldarg.0
0x19b67  call     instance bool Microsoft.Crm.Application.ControlDescriptor::UniqueIdAndMatchingControlDescriptionExists()
0x19b6c  brfalse  loc_19BF3
0x19b71  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.CustomControlUIControlDescriptor::.ctor()
0x19b76  dup
0x19b77  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.FormControlClassId::CustomControl
0x19b7c  stfld    valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.UIControlDescriptor::ClassId
0x19b81  dup
0x19b82  ldloc.1
0x19b83  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x19b88  stfld    valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.CustomControlUIControlDescriptor::DataAttributeClassId
0x19b8d  dup
0x19b8e  ldarg.0
0x19b8f  call     instance string Microsoft.Crm.Application.ControlDescriptor::get_ID()
0x19b94  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ControlDescriptorBase::Id
0x19b99  dup
0x19b9a  ldarg.0
0x19b9b  call     instance string Microsoft.Crm.Application.ControlDescriptor::get_ID()
0x19ba0  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ControlDescriptorBase::Name
0x19ba5  dup
0x19ba6  ldloc.0
0x19ba7  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ControlDescriptorBase::Label
0x19bac  dup
0x19bad  ldloc.2
0x19bae  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.UIControlDescriptor::Parameters
0x19bb3  dup
0x19bb4  ldarg.0
0x19bb5  call     instance bool Microsoft.Crm.Application.ControlDescriptor::get_Disabled()
0x19bba  stfld    bool [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.UIControlDescriptor::Disabled
0x19bbf  dup
0x19bc0  ldarg.0
0x19bc1  call     instance bool Microsoft.Crm.Application.FormPartWithLabelDescriptor::get_ShowLabel()
0x19bc6  stfld    bool [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ControlDescriptorBase::ShowLabel
0x19bcb  dup
0x19bcc  ldarg.0
0x19bcd  call     instance bool Microsoft.Crm.Application.ControlDescriptor::get_Visible()
0x19bd2  stfld    bool [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ControlDescriptorBase::Visible
0x19bd7  dup
0x19bd8  ldarg.0
0x19bd9  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.ControlDescriptor::get_UniqueId()
0x19bde  stloc.s  0xD
0x19be0  ldloca.s 0xD
0x19be2  constrained. [mscorlib]System.Guid
0x19be8  callvirt instance string [mscorlib]System.Object::ToString()
0x19bed  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.CustomControlUIControlDescriptor::UniqueId
0x19bf2  ret
0x19bf3  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.UIControlDescriptor::.ctor()
0x19bf8  dup
0x19bf9  ldloc.1
0x19bfa  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x19bff  stfld    valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.UIControlDescriptor::ClassId
0x19c04  dup
0x19c05  ldarg.0
0x19c06  call     instance string Microsoft.Crm.Application.ControlDescriptor::get_ID()
0x19c0b  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ControlDescriptorBase::Id
0x19c10  dup
0x19c11  ldloc.0
0x19c12  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ControlDescriptorBase::Label
0x19c17  dup
0x19c18  ldloc.2
0x19c19  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.UIControlDescriptor::Parameters
0x19c1e  dup
0x19c1f  ldarg.0
0x19c20  call     instance bool Microsoft.Crm.Application.ControlDescriptor::get_Disabled()
0x19c25  stfld    bool [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.UIControlDescriptor::Disabled
0x19c2a  dup
0x19c2b  ldarg.0
0x19c2c  call     instance bool Microsoft.Crm.Application.FormPartWithLabelDescriptor::get_ShowLabel()
0x19c31  stfld    bool [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ControlDescriptorBase::ShowLabel
0x19c36  dup
0x19c37  ldarg.0
0x19c38  call     instance bool Microsoft.Crm.Application.ControlDescriptor::get_Visible()
0x19c3d  stfld    bool [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ControlDescriptorBase::Visible
0x19c42  ret
0x19c43  ldarg.0
0x19c44  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.ControlDescriptor::get_UniqueId()
0x19c49  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x19c4e  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x19c53  brfalse  loc_19CF1
0x19c58  ldarg.0
0x19c59  call     instance bool Microsoft.Crm.Application.ControlDescriptor::UniqueIdAndMatchingControlDescriptionExists()
  ... truncated ...
```
