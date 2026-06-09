# Microsoft.Crm.Application.ControlDescriptor::GetClientDescriptor

- ea: `0x19e60`
- end: `0x1a378`
- name: `Microsoft.Crm.Application.ControlDescriptor::GetClientDescriptor`
- size: `1304`
- prototype: ``
- caller_count: `3`
- callee_count: `36`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18870`
- `0x1f030`
- `0xa33e0`

## callees

- `0x19590`
- `0x19610`
- `0x19650`
- `0x19680`
- `0x196a0`
- `0x19710`
- `0x19790`
- `0x197a0`
- `0x197b0`
- `0x197c0`
- `0x197d0`
- `0x197e0`
- `0x19810`
- `0x19820`
- `0x19830`
- `0x19e00`
- `0x19e60`
- `0x1a380`
- `0x1a480`
- `0x1a6d0`
- `0x1a770`
- `0x1a800`
- `0x1a860`
- `0x1a8c0`
- `0x1a8f0`
- `0x1a960`
- `0x1a9a0`
- `0x1aa40`
- `0x1f780`
- `0x1f7c0`
- `0x1f800`
- `0x20390`
- `0x20420`
- `0x20430`
- `0x39c00`
- `0x39f70`

## string_xrefs

- `0x1a095`: `isKMConfigured`
- `0x1a0ba`: `externalServiceUrl`

## pseudocode

```c

```

## disassembly

```asm
0x19e60  ldsfld   string [mscorlib]System.String::Empty
0x19e65  stloc.0
0x19e66  ldarg.0
0x19e67  call     instance class Microsoft.Crm.Application.CellDescriptor Microsoft.Crm.Application.ControlDescriptor::get_ParentCellDescriptor()
0x19e6c  brfalse.s loc_19E8C
0x19e6e  ldarg.0
0x19e6f  call     instance class Microsoft.Crm.Application.CellDescriptor Microsoft.Crm.Application.ControlDescriptor::get_ParentCellDescriptor()
0x19e74  callvirt instance class Microsoft.Crm.Application.LabelDescriptor Microsoft.Crm.Application.FormPartWithLabelDescriptor::get_UserLabel()
0x19e79  brfalse.s loc_19E8C
0x19e7b  ldarg.0
0x19e7c  call     instance class Microsoft.Crm.Application.CellDescriptor Microsoft.Crm.Application.ControlDescriptor::get_ParentCellDescriptor()
0x19e81  callvirt instance class Microsoft.Crm.Application.LabelDescriptor Microsoft.Crm.Application.FormPartWithLabelDescriptor::get_UserLabel()
0x19e86  callvirt instance string Microsoft.Crm.Application.LabelDescriptor::get_Description()
0x19e8b  stloc.0
0x19e8c  ldarg.0
0x19e8d  call     instance class Microsoft.Crm.Application.CellDescriptor Microsoft.Crm.Application.ControlDescriptor::get_ParentCellDescriptor()
0x19e92  brtrue.s loc_19E9B
0x19e94  ldsfld   string [mscorlib]System.String::Empty
0x19e99  br.s     loc_19EBA
0x19e9b  ldarg.0
0x19e9c  call     instance class Microsoft.Crm.Application.CellDescriptor Microsoft.Crm.Application.ControlDescriptor::get_ParentCellDescriptor()
0x19ea1  callvirt instance string Microsoft.Crm.Application.FormPartWithLabelDescriptor::get_Id()
0x19ea6  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x19eab  stloc.s  7
0x19ead  ldloca.s 7
0x19eaf  constrained. [mscorlib]System.Guid
0x19eb5  callvirt instance string [mscorlib]System.Object::ToString()
0x19eba  stloc.1
0x19ebb  ldloc.0
0x19ebc  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x19ec1  brfalse.s loc_19ED3
0x19ec3  ldarg.0
0x19ec4  ldfld    string Microsoft.Crm.Application.ControlDescriptor::_label
0x19ec9  dup
0x19eca  brtrue.s loc_19ED2
0x19ecc  pop
0x19ecd  ldsfld   string [mscorlib]System.String::Empty
0x19ed2  stloc.0
0x19ed3  ldarg.0
0x19ed4  call     instance string Microsoft.Crm.Application.ControlDescriptor::get_ClassId()
0x19ed9  stloc.2
0x19eda  ldarg.0
0x19edb  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.ControlDescriptor::get_Metadata()
0x19ee0  brfalse.s loc_19EFF
0x19ee2  ldarg.0
0x19ee3  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.ControlDescriptor::get_Metadata()
0x19ee8  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Format()
0x19eed  ldstr    aPhone// "phone"
0x19ef2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x19ef7  brfalse.s loc_19EFF
0x19ef9  ldstr    a8c10015aB33949// "{8C10015A-B339-4982-9474-A95FE05631A5}"
0x19efe  stloc.2
0x19eff  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x19f04  stloc.3
0x19f05  ldarg.0
0x19f06  call     instance class Microsoft.Crm.Application.ParameterCollection Microsoft.Crm.Application.ControlDescriptor::get_Parameters()
0x19f0b  callvirt instance class [mscorlib]System.Collections.IEnumerator class Microsoft.Crm.Application.ReadOnlyListCollection`1<class Microsoft.Crm.Application.ParameterDescriptor>::GetEnumerator()
0x19f10  stloc.s  8
0x19f12  br.s     loc_19F6F
0x19f14  ldloc.s  8
0x19f16  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x19f1b  castclass Microsoft.Crm.Application.ParameterDescriptor
0x19f20  stloc.s  9
0x19f22  ldloc.s  9
0x19f24  callvirt instance string Microsoft.Crm.Application.ParameterDescriptor::get_Name()
0x19f29  ldstr    aQuickforms// "QuickForms"
0x19f2e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x19f33  brfalse.s loc_19F5B
0x19f35  ldloc.3
0x19f36  ldloc.s  9
0x19f38  callvirt instance string Microsoft.Crm.Application.ParameterDescriptor::get_Name()
0x19f3d  ldstr    asc_B7F3A// ","
0x19f42  ldarg.0
0x19f43  ldloc.s  9
0x19f45  callvirt instance string Microsoft.Crm.Application.ParameterDescriptor::get_Value()
0x19f4a  call     instance string[] Microsoft.Crm.Application.ControlDescriptor::ParseQuickFormIds(string quickForms)
0x19f4f  call     string [mscorlib]System.String::Join(string, string[])
0x19f54  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x19f59  br.s     loc_19F6F
0x19f5b  ldloc.3
0x19f5c  ldloc.s  9
0x19f5e  callvirt instance string Microsoft.Crm.Application.ParameterDescriptor::get_Name()
0x19f63  ldloc.s  9
0x19f65  callvirt instance string Microsoft.Crm.Application.ParameterDescriptor::get_Value()
0x19f6a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x19f6f  ldloc.s  8
0x19f71  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x19f76  brtrue.s loc_19F14
0x19f78  leave.s  loc_19F8F
0x19f7a  ldloc.s  8
0x19f7c  isinst   [mscorlib]System.IDisposable
0x19f81  stloc.s  0xA
0x19f83  ldloc.s  0xA
0x19f85  brfalse.s loc_19F8E
0x19f87  ldloc.s  0xA
0x19f89  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x19f8e  endfinally
0x19f8f  ldloc.2
0x19f90  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x19f95  ldstr    a270bd3dbD9af47// "{270BD3DB-D9AF-4782-9025-509E298DEC0A}"
0x19f9a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x19f9f  brtrue.s loc_19FAD
0x19fa1  ldarg.0
0x19fa2  call     instance valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.FormControlType Microsoft.Crm.Application.ControlDescriptor::get_ControlType()
0x19fa7  ldc.i4.3
0x19fa8  bne.un   loc_1A082
0x19fad  ldarg.0
0x19fae  call     instance bool Microsoft.Crm.Application.ControlDescriptor::get_IsUnbound()
0x19fb3  brfalse.s loc_19FEA
0x19fb5  ldarg.0
0x19fb6  call     instance string Microsoft.Crm.Application.ControlDescriptor::SetDefaultViewIdForUnboundLookup()
0x19fbb  stloc.s  0xB
0x19fbd  ldloc.3
0x19fbe  ldstr    aDefaultviewid// "DefaultViewId"
0x19fc3  ldloc.s  0xB
0x19fc5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x19fca  ldarg.0
0x19fcb  call     instance string Microsoft.Crm.Application.ControlDescriptor::SetUnboundLookupStyle()
0x19fd0  stloc.s  0xE
0x19fd2  ldloc.s  0xE
0x19fd4  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x19fd9  brtrue.s loc_19FFF
0x19fdb  ldloc.3
0x19fdc  ldstr    aUnboundlookups// "UnboundLookupStyle"
0x19fe1  ldloc.s  0xE
0x19fe3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x19fe8  br.s     loc_19FFF
0x19fea  ldarg.0
0x19feb  call     instance string Microsoft.Crm.Application.ControlDescriptor::SetDefaultViewId()
0x19ff0  stloc.s  0xB
0x19ff2  ldloc.3
0x19ff3  ldstr    aDefaultviewid_0// "defaultviewid"
0x19ff8  ldloc.s  0xB
0x19ffa  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x19fff  ldsfld   string [mscorlib]System.String::Empty
0x1a004  stloc.s  0xC
0x1a006  ldarg.0
0x1a007  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.ControlDescriptor::get_Metadata()
0x1a00c  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LookupAttributeMetadata
0x1a011  stloc.s  0xD
0x1a013  ldloc.s  0xD
0x1a015  brfalse.s loc_1A05A
0x1a017  ldloc.s  0xD
0x1a019  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<int32> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LookupAttributeMetadata::get_LookupTypes()
0x1a01e  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<int32>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x1a023  call     instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<int32>::ToArray()
0x1a028  stloc.s  0xF
0x1a02a  ldarg.0
0x1a02b  ldloc.s  0xF
0x1a02d  call     instance void Microsoft.Crm.Application.ControlDescriptor::SetLookupTypes(int32[] typesToSet)
0x1a032  ldarg.0
0x1a033  call     instance int32 Microsoft.Crm.Application.ControlDescriptor::get_DefaultType()
0x1a038  brtrue.s loc_1A051
0x1a03a  ldarg.0
0x1a03b  ldfld    int32[] Microsoft.Crm.Application.ControlDescriptor::_lookupTypes
0x1a040  ldlen
0x1a041  brfalse.s loc_1A051
0x1a043  ldarg.0
0x1a044  ldarg.0
0x1a045  ldfld    int32[] Microsoft.Crm.Application.ControlDescriptor::_lookupTypes
0x1a04a  ldc.i4.0
0x1a04b  ldelem.i4
0x1a04c  call     instance void Microsoft.Crm.Application.ControlDescriptor::set_DefaultType(int32 value)
0x1a051  ldloc.s  0xD
0x1a053  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LookupAttributeMetadata::get_LookupStyle()
0x1a058  stloc.s  0xC
0x1a05a  ldloc.3
0x1a05b  ldstr    aDefaulttype// "defaulttype"
0x1a060  ldarg.0
0x1a061  call     instance int32 Microsoft.Crm.Application.ControlDescriptor::get_DefaultType()
0x1a066  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1a06b  call     string [mscorlib]System.Convert::ToString(int32, class [mscorlib]System.IFormatProvider)
0x1a070  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x1a075  ldloc.3
0x1a076  ldstr    aLookupstyle// "lookupstyle"
0x1a07b  ldloc.s  0xC
0x1a07d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x1a082  ldloc.2
0x1a083  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x1a088  ldstr    aE616a57f20e045// "{E616A57F-20E0-4534-8662-A101B5DDF4E0}"
0x1a08d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1a092  brfalse.s loc_1A107
0x1a094  ldloc.3
0x1a095  ldstr    aIskmconfigured// "isKMConfigured"
0x1a09a  ldarg.0
0x1a09b  call     instance bool Microsoft.Crm.Application.ControlDescriptor::get_IsKnowledgeMangementParatureConfigured()
0x1a0a0  brtrue.s loc_1A0AA
0x1a0a2  ldarg.0
0x1a0a3  call     instance bool Microsoft.Crm.Application.ControlDescriptor::get_IsKnowledgeManagementNativeCrmConfigured()
0x1a0a8  br.s     loc_1A0AB
0x1a0aa  ldc.i4.1
0x1a0ab  stloc.s  0x11
0x1a0ad  ldloca.s 0x11
0x1a0af  call     instance string [mscorlib]System.Boolean::ToString()
0x1a0b4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x1a0b9  ldloc.3
0x1a0ba  ldstr    aExternalservic// "externalServiceUrl"
0x1a0bf  ldarg.0
0x1a0c0  call     instance string Microsoft.Crm.Application.ControlDescriptor::getExternalServiceUrl()
0x1a0c5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x1a0ca  ldloc.3
0x1a0cb  ldstr    aPortaldomain// "portalDomain"
0x1a0d0  ldarg.0
0x1a0d1  call     instance string Microsoft.Crm.Application.ControlDescriptor::GetSupportUrl()
0x1a0d6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x1a0db  ldstr    aSearchwidgetSe// "/SearchWidget/SearchWidgetWallContent.a"...
0x1a0e0  ldarg.0
0x1a0e1  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.ControlDescriptor::_context
0x1a0e6  call     class Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.Utility.CrmUri::CreateWebResourceUri(string path, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x1a0eb  stloc.s  0x10
0x1a0ed  ldloc.s  0x10
0x1a0ef  ldc.i4.1
0x1a0f0  callvirt instance void Microsoft.Crm.Application.Utility.CrmUri::set_UseVersionStamp(bool value)
0x1a0f5  ldloc.3
0x1a0f6  ldstr    aWallcontentpag// "wallContentPageUrl"
0x1a0fb  ldloc.s  0x10
0x1a0fd  callvirt instance string [mscorlib]System.Object::ToString()
0x1a102  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x1a107  ldarg.0
0x1a108  call     instance bool Microsoft.Crm.Application.ControlDescriptor::get_IsRequired()
0x1a10d  brtrue.s loc_1A112
0x1a10f  ldc.i4.0
0x1a110  br.s     loc_1A113
0x1a112  ldc.i4.2
0x1a113  stloc.s  4
0x1a115  ldarg.0
0x1a116  call     instance class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ControlCreator Microsoft.Crm.Application.ControlDescriptor::get_ControlCreatorInstance()
0x1a11b  ldarg.0
0x1a11c  call     instance string Microsoft.Crm.Application.ControlDescriptor::get_ClassId()
0x1a121  callvirt instance valuetype [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ControlType [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ControlCreator::GetControlType(string)
0x1a126  stloc.s  5
0x1a128  ldc.i4.s 0xE
0x1a12a  stloc.s  6
0x1a12c  ldloc.s  5
0x1a12e  ldc.i4.s 0x2E
0x1a130  bne.un.s loc_1A13C
0x1a132  ldarg.0
0x1a133  call     instance valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeTypeCode Microsoft.Crm.Application.ControlDescriptor::GetCustomControlAttributeType()
0x1a138  stloc.s  6
0x1a13a  br.s     loc_1A146
0x1a13c  ldarg.0
0x1a13d  ldloc.s  5
0x1a13f  call     instance valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeTypeCode Microsoft.Crm.Application.ControlDescriptor::GetAttributeType(valuetype [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ControlType controlType)
0x1a144  stloc.s  6
0x1a146  ldarg.0
0x1a147  call     instance string Microsoft.Crm.Application.ControlDescriptor::get_DataFieldName()
0x1a14c  brtrue   loc_1A284
0x1a151  ldloc.2
0x1a152  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x1a157  ldstr    a9fdf5f9188b147// "{9FDF5F91-88B1-47F4-AD53-C11EFC01A01D}"
0x1a15c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1a161  brtrue.s loc_1A187
0x1a163  ldloc.2
0x1a164  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x1a169  ldstr    a587cdf98C1d54b// "{587CDF98-C1D5-4BDE-8473-14A0BC7644A7}"
0x1a16e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1a173  brtrue.s loc_1A187
0x1a175  ldloc.2
0x1a176  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x1a17b  ldstr    a080677db86ec45// "{080677DB-86EC-4544-AC42-F927E74B491F}"
0x1a180  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1a185  brfalse.s loc_1A18F
0x1a187  ldarg.0
0x1a188  ldloc.3
0x1a189  ldc.i4.0
0x1a18a  call     instance void Microsoft.Crm.Application.ControlDescriptor::SetWebResourceUrl(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> parameters, bool setWebResourceHash)
0x1a18f  ldarg.0
0x1a190  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.ControlDescriptor::get_UniqueId()
0x1a195  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1a19a  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1a19f  brfalse.s loc_1A211
0x1a1a1  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Descriptors.CustomControl::.ctor()
0x1a1a6  dup
0x1a1a7  ldloc.2
0x1a1a8  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1a1ad  stfld    valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Descriptors.Control::ClassId
0x1a1b2  dup
0x1a1b3  ldarg.0
0x1a1b4  call     instance string Microsoft.Crm.Application.ControlDescriptor::get_ID()
0x1a1b9  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Descriptors.ControlBase::Id
0x1a1be  dup
0x1a1bf  ldarg.0
0x1a1c0  call     instance string Microsoft.Crm.Application.ControlDescriptor::get_ID()
0x1a1c5  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Descriptors.ControlBase::Name
0x1a1ca  dup
0x1a1cb  ldloc.0
0x1a1cc  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Descriptors.ControlBase::Label
0x1a1d1  dup
0x1a1d2  ldloc.3
0x1a1d3  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Descriptors.Control::Parameters
0x1a1d8  dup
0x1a1d9  ldarg.0
0x1a1da  call     instance bool Microsoft.Crm.Application.ControlDescriptor::get_Disabled()
0x1a1df  stfld    bool [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Descriptors.Control::Disabled
0x1a1e4  dup
0x1a1e5  ldarg.0
0x1a1e6  call     instance bool Microsoft.Crm.Application.FormPartWithLabelDescriptor::get_ShowLabel()
0x1a1eb  stfld    bool [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Descriptors.ControlBase::ShowLabel
0x1a1f0  dup
0x1a1f1  ldarg.0
  ... truncated ...
```
