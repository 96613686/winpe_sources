# Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::ResolveComponent

- ea: `0xba130`
- end: `0xba826`
- name: `Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::ResolveComponent`
- size: `1782`
- prototype: ``
- caller_count: `3`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0xbaf80`
- `0xbed30`
- `0xbf300`

## callees

- `0x7060`
- `0x70b0`
- `0x46e30`
- `0xb81f0`
- `0xb8200`
- `0xb8220`
- `0xb8240`
- `0xb8260`
- `0xb8270`
- `0xb8280`
- `0xb8290`
- `0xb82a0`
- `0xb82c0`
- `0xb8320`
- `0xb8340`
- `0xb8360`
- `0xb8390`
- `0xb8460`
- `0xb8e20`
- `0xb9430`
- `0xb9460`
- `0xba130`
- `0xba830`

## string_xrefs

- `0xba1b7`: `requiredcomponenttype`
- `0xba33b`: `requiredcomponenttype`
- `0xba382`: `requiredcomponenttype`
- `0xba20f`: `requiredcomponentbasesolutionid`
- `0xba148`: `requiredcomponentobjectid`
- `0xba353`: `requiredcomponentobjectid`
- `0xba136`: `dependentcomponentobjectid`
- `0xba1a5`: `dependentcomponenttype`
- `0xba1f8`: `dependentcomponentbasesolutionid`
- `0xba2ad`: `dependentcomponentparentid`
- `0xba2c4`: `requiredcomponentparentid`
- `0xba3c0`: `requiredcomponentparentid`

## pseudocode

```c

```

## disassembly

```asm
0xba130  ldloca.s 0
0xba132  ldarg.2
0xba133  brtrue.s loc_BA147
0xba135  ldarg.1
0xba136  ldstr    aDependentcompo_0// "dependentcomponentobjectid"
0xba13b  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xba140  unbox.any [mscorlib]System.Guid
0xba145  br.s     loc_BA157
0xba147  ldarg.1
0xba148  ldstr    aRequiredcompon_2// "requiredcomponentobjectid"
0xba14d  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xba152  unbox.any [mscorlib]System.Guid
0xba157  call     instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0xba15c  ldloca.s 0
0xba15e  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0xba163  brfalse  loc_BA821
0xba168  ldloca.s 0
0xba16a  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0xba16f  stloc.1
0xba170  ldloca.s 1
0xba172  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xba177  call     instance bool [mscorlib]System.Guid::Equals(valuetype [mscorlib]System.Guid)
0xba17c  brtrue   loc_BA821
0xba181  ldarg.0
0xba182  ldloca.s 0
0xba184  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0xba189  stloc.1
0xba18a  ldloca.s 1
0xba18c  ldstr    aB// "B"
0xba191  call     instance string [mscorlib]System.Guid::ToString(string)
0xba196  call     instance class Microsoft.Crm.Application.Controls.SystemCustomization.DependencyValueObject Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::GetNodeInQueue(string objectId)
0xba19b  stloc.2
0xba19c  ldloc.2
0xba19d  brfalse.s loc_BA1A1
0xba19f  ldloc.2
0xba1a0  ret
0xba1a1  ldarg.2
0xba1a2  brtrue.s loc_BA1B6
0xba1a4  ldarg.1
0xba1a5  ldstr    aDependentcompo_1// "dependentcomponenttype"
0xba1aa  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xba1af  unbox.any [mscorlib]System.Int32
0xba1b4  br.s     loc_BA1C6
0xba1b6  ldarg.1
0xba1b7  ldstr    aRequiredcompon_0// "requiredcomponenttype"
0xba1bc  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xba1c1  unbox.any [mscorlib]System.Int32
0xba1c6  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetObjectTypeCode(int32)
0xba1cb  stloc.3
0xba1cc  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xba1d1  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsMocaOfflineFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xba1d6  brtrue.s loc_BA1EA
0xba1d8  ldloc.3
0xba1d9  ldc.i4   0x268A
0xba1de  beq.s    loc_BA1E8
0xba1e0  ldloc.3
0xba1e1  ldc.i4   0x268B
0xba1e6  bne.un.s loc_BA1EA
0xba1e8  ldnull
0xba1e9  ret
0xba1ea  ldloc.3
0xba1eb  call     bool Microsoft.Crm.Utility.SolutionUtil::IsComponentTypeVisible(int32 type)
0xba1f0  brtrue.s loc_BA1F4
0xba1f2  ldnull
0xba1f3  ret
0xba1f4  ldarg.2
0xba1f5  brtrue.s loc_BA20E
0xba1f7  ldarg.1
0xba1f8  ldstr    aDependentcompo_2// "dependentcomponentbasesolutionid"
0xba1fd  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xba202  isinst   valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0xba207  unbox.any valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0xba20c  br.s     loc_BA223
0xba20e  ldarg.1
0xba20f  ldstr    aRequiredcompon_1// "requiredcomponentbasesolutionid"
0xba214  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xba219  isinst   valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0xba21e  unbox.any valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0xba223  stloc.s  4
0xba225  ldloca.s 4
0xba227  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0xba22c  brfalse.s loc_BA244
0xba22e  ldloca.s 4
0xba230  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0xba235  stloc.1
0xba236  ldloca.s 1
0xba238  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xba23d  call     instance bool [mscorlib]System.Guid::Equals(valuetype [mscorlib]System.Guid)
0xba242  brfalse.s loc_BA250
0xba244  ldloca.s 4
0xba246  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::DefaultSolutionId
0xba24b  call     instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0xba250  newobj   instance void Microsoft.Crm.Application.Controls.SystemCustomization.DependencyValueObject::.ctor()
0xba255  stloc.2
0xba256  ldloc.2
0xba257  ldloca.s 0
0xba259  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0xba25e  stloc.1
0xba25f  ldloca.s 1
0xba261  ldstr    aB// "B"
0xba266  call     instance string [mscorlib]System.Guid::ToString(string)
0xba26b  callvirt instance void Microsoft.Crm.Application.Controls.SystemCustomization.DependencyValueObject::set_ObjectId(string value)
0xba270  ldloc.2
0xba271  ldloca.s 3
0xba273  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xba278  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xba27d  callvirt instance void Microsoft.Crm.Application.Controls.SystemCustomization.DependencyValueObject::set_ObjectType(string value)
0xba282  ldloc.2
0xba283  ldloc.3
0xba284  ldc.i4.1
0xba285  call     string Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32 objectTypeCode, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle formatStyle)
0xba28a  callvirt instance void Microsoft.Crm.Application.Controls.SystemCustomization.DependencyValueObject::set_TypeName(string value)
0xba28f  ldloc.2
0xba290  ldloca.s 4
0xba292  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0xba297  stloc.1
0xba298  ldloca.s 1
0xba29a  ldstr    aB// "B"
0xba29f  call     instance string [mscorlib]System.Guid::ToString(string)
0xba2a4  callvirt instance void Microsoft.Crm.Application.Controls.SystemCustomization.DependencyValueObject::set_SolutionId(string value)
0xba2a9  ldarg.2
0xba2aa  brtrue.s loc_BA2C3
0xba2ac  ldarg.1
0xba2ad  ldstr    aDependentcompo_3// "dependentcomponentparentid"
0xba2b2  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xba2b7  isinst   valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0xba2bc  unbox.any valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0xba2c1  br.s     loc_BA2D8
0xba2c3  ldarg.1
0xba2c4  ldstr    aRequiredcompon_3// "requiredcomponentparentid"
0xba2c9  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xba2ce  isinst   valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0xba2d3  unbox.any valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0xba2d8  stloc.s  5
0xba2da  ldloca.s 5
0xba2dc  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0xba2e1  brfalse.s loc_BA32F
0xba2e3  ldloca.s 5
0xba2e5  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xba2ea  box      [mscorlib]System.Guid
0xba2ef  constrained. valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0xba2f5  callvirt instance bool [mscorlib]System.Object::Equals(object)
0xba2fa  brtrue.s loc_BA32F
0xba2fc  ldloc.2
0xba2fd  ldloca.s 5
0xba2ff  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0xba304  stloc.1
0xba305  ldloca.s 1
0xba307  ldstr    aB// "B"
0xba30c  call     instance string [mscorlib]System.Guid::ToString(string)
0xba311  callvirt instance void Microsoft.Crm.Application.Controls.SystemCustomization.DependencyValueObject::set_ParentId(string value)
0xba316  ldloc.2
0xba317  ldc.i4   0x2649
0xba31c  stloc.s  6
0xba31e  ldloca.s 6
0xba320  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xba325  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xba32a  callvirt instance void Microsoft.Crm.Application.Controls.SystemCustomization.DependencyValueObject::set_ParentType(string value)
0xba32f  ldloc.3
0xba330  ldc.i4   0x261B
0xba335  bne.un   loc_BA445
0xba33a  ldarg.1
0xba33b  ldstr    aRequiredcompon_0// "requiredcomponenttype"
0xba340  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xba345  unbox.any [mscorlib]System.Int32
0xba34a  ldc.i4.2
0xba34b  bne.un   loc_BA445
0xba350  ldloca.s 7
0xba352  ldarg.1
0xba353  ldstr    aRequiredcompon_2// "requiredcomponentobjectid"
0xba358  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xba35d  unbox.any [mscorlib]System.Guid
0xba362  call     instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0xba367  ldloc.2
0xba368  ldloca.s 7
0xba36a  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0xba36f  stloc.1
0xba370  ldloca.s 1
0xba372  ldstr    aB// "B"
0xba377  call     instance string [mscorlib]System.Guid::ToString(string)
0xba37c  callvirt instance void Microsoft.Crm.Application.Controls.SystemCustomization.DependencyValueObject::set_ObjectId(string value)
0xba381  ldarg.1
0xba382  ldstr    aRequiredcompon_0// "requiredcomponenttype"
0xba387  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xba38c  unbox.any [mscorlib]System.Int32
0xba391  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetObjectTypeCode(int32)
0xba396  stloc.s  8
0xba398  ldloc.2
0xba399  ldloca.s 8
0xba39b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xba3a0  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xba3a5  callvirt instance void Microsoft.Crm.Application.Controls.SystemCustomization.DependencyValueObject::set_ObjectType(string value)
0xba3aa  ldarg.0
0xba3ab  ldloc.2
0xba3ac  call     instance void Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::PopulatePrimaryField(class Microsoft.Crm.Application.Controls.SystemCustomization.DependencyValueObject dependencyNode)
0xba3b1  ldarg.0
0xba3b2  ldarg.2
0xba3b3  ldloc.s  7
0xba3b5  ldloc.s  8
0xba3b7  ldloc.2
0xba3b8  call     instance void Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::PopulateNodeName(bool required, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> objectId, int32 objectTypeCode, class Microsoft.Crm.Application.Controls.SystemCustomization.DependencyValueObject node)
0xba3bd  ldloca.s 9
0xba3bf  ldarg.1
0xba3c0  ldstr    aRequiredcompon_3// "requiredcomponentparentid"
0xba3c5  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xba3ca  unbox.any [mscorlib]System.Guid
0xba3cf  call     instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0xba3d4  ldloca.s 9
0xba3d6  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0xba3db  stloc.1
0xba3dc  ldloca.s 1
0xba3de  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xba3e3  call     instance bool [mscorlib]System.Guid::Equals(valuetype [mscorlib]System.Guid)
0xba3e8  brfalse.s loc_BA3F7
0xba3ea  ldloc.2
0xba3eb  ldstr    asc_F537C// ""
0xba3f0  callvirt instance void Microsoft.Crm.Application.Controls.SystemCustomization.DependencyValueObject::set_ParentId(string value)
0xba3f5  br.s     loc_BA411
0xba3f7  ldloc.2
0xba3f8  ldloca.s 9
0xba3fa  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0xba3ff  stloc.1
0xba400  ldloca.s 1
0xba402  ldstr    aB// "B"
0xba407  call     instance string [mscorlib]System.Guid::ToString(string)
0xba40c  callvirt instance void Microsoft.Crm.Application.Controls.SystemCustomization.DependencyValueObject::set_ParentId(string value)
0xba411  ldc.i4   0x2654
0xba416  stloc.s  0xA
0xba418  ldloc.2
0xba419  ldloca.s 0xA
0xba41b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xba420  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xba425  callvirt instance void Microsoft.Crm.Application.Controls.SystemCustomization.DependencyValueObject::set_ParentType(string value)
0xba42a  ldarg.0
0xba42b  ldloc.2
0xba42c  call     instance void Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::PopulatePrimaryField(class Microsoft.Crm.Application.Controls.SystemCustomization.DependencyValueObject dependencyNode)
0xba431  ldloc.2
0xba432  ldloca.s 3
0xba434  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xba439  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xba43e  callvirt instance void Microsoft.Crm.Application.Controls.SystemCustomization.DependencyValueObject::set_ObjectType(string value)
0xba443  br.s     loc_BA456
0xba445  ldarg.0
0xba446  ldloc.2
0xba447  call     instance void Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::PopulatePrimaryField(class Microsoft.Crm.Application.Controls.SystemCustomization.DependencyValueObject dependencyNode)
0xba44c  ldarg.0
0xba44d  ldarg.2
0xba44e  ldloc.0
0xba44f  ldloc.3
0xba450  ldloc.2
0xba451  call     instance void Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::PopulateNodeName(bool required, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> objectId, int32 objectTypeCode, class Microsoft.Crm.Application.Controls.SystemCustomization.DependencyValueObject node)
0xba456  ldloca.s 4
0xba458  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0xba45d  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::ActiveSolutionId
0xba462  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xba467  brfalse.s loc_BA488
0xba469  ldloc.2
0xba46a  ldarg.0
0xba46b  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Application.Controls.SystemCustomization.NamePair> Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::IdNamePairs
0xba470  ldloca.s 4
0xba472  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0xba477  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Application.Controls.SystemCustomization.NamePair>::get_Item(void)
0xba47c  callvirt instance string Microsoft.Crm.Application.Controls.SystemCustomization.NamePair::get_DisplayName()
0xba481  callvirt instance void Microsoft.Crm.Application.Controls.SystemCustomization.DependencyValueObject::set_SolutionName(string value)
0xba486  br.s     loc_BA493
0xba488  ldloc.2
0xba489  ldsfld   string [mscorlib]System.String::Empty
0xba48e  callvirt instance void Microsoft.Crm.Application.Controls.SystemCustomization.DependencyValueObject::set_SolutionName(string value)
0xba493  ldloc.2
0xba494  callvirt instance string Microsoft.Crm.Application.Controls.SystemCustomization.DependencyValueObject::get_ParentId()
0xba499  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xba49e  brtrue.s loc_BA4C1
0xba4a0  ldloc.2
0xba4a1  ldarg.0
0xba4a2  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Application.Controls.SystemCustomization.NamePair> Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::IdNamePairs
0xba4a7  ldloc.2
0xba4a8  callvirt instance string Microsoft.Crm.Application.Controls.SystemCustomization.DependencyValueObject::get_ParentId()
0xba4ad  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xba4b2  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Application.Controls.SystemCustomization.NamePair>::get_Item(void)
0xba4b7  callvirt instance string Microsoft.Crm.Application.Controls.SystemCustomization.NamePair::get_DisplayName()
0xba4bc  callvirt instance void Microsoft.Crm.Application.Controls.SystemCustomization.DependencyValueObject::set_ParentName(string value)
0xba4c1  ldloc.2
0xba4c2  ldarg.1
0xba4c3  ldstr    aDependencytype// "dependencytype"
0xba4c8  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xba4cd  unbox.any [mscorlib]System.Int32
0xba4d2  stloc.s  6
0xba4d4  ldloca.s 6
0xba4d6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xba4db  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xba4e0  callvirt instance void Microsoft.Crm.Application.Controls.SystemCustomization.DependencyValueObject::set_DependencyType(string value)
0xba4e5  ldloc.2
0xba4e6  ldarg.1
0xba4e7  ldstr    aDependencytype// "dependencytype"
0xba4ec  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xba4f1  unbox.any [mscorlib]System.Int32
0xba4f6  call     string Microsoft.Crm.Utility.SolutionUtil::GetDependencyLabel(int32 dependency)
0xba4fb  callvirt instance void Microsoft.Crm.Application.Controls.SystemCustomization.DependencyValueObject::set_DependencyTypeName(string value)
0xba500  ldloc.3
0xba501  ldc.i4   0x40F
  ... truncated ...
```
