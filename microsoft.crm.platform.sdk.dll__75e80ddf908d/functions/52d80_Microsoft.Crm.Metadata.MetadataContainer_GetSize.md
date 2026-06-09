# Microsoft.Crm.Metadata.MetadataContainer::GetSize

- ea: `0x52d80`
- end: `0x5311b`
- name: `Microsoft.Crm.Metadata.MetadataContainer::GetSize`
- size: `923`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x5afe0`
- `0x5b300`

## callees

- `0x52d80`
- `0xa94d0`

## string_xrefs

- `0x52fe6`: `Privilege`
- `0x52f7d`: `PrivilegeObjectTypeCode`
- `0x52f92`: `RoleTemplatePrivilege`

## pseudocode

```c

```

## disassembly

```asm
0x52d80  ldarg.1
0x52d81  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x52d86  stloc.0
0x52d87  ldloc.0
0x52d88  ldc.i4   0x7A787910
0x52d8d  bgt.un   loc_52E21
0x52d92  ldloc.0
0x52d93  ldc.i4   0x2FB17EF0
0x52d98  bgt.un.s loc_52DD8
0x52d9a  ldloc.0
0x52d9b  ldc.i4   0x1D72D1E6
0x52da0  bgt.un.s loc_52DBD
0x52da2  ldloc.0
0x52da3  ldc.i4   0x1ACCD85B
0x52da8  beq      loc_52F3D
0x52dad  ldloc.0
0x52dae  ldc.i4   0x1D72D1E6
0x52db3  beq      loc_52F91
0x52db8  br       loc_530FC
0x52dbd  ldloc.0
0x52dbe  ldc.i4   0x21E27D10
0x52dc3  beq      loc_52FBB
0x52dc8  ldloc.0
0x52dc9  ldc.i4   0x2FB17EF0
0x52dce  beq      loc_52F52
0x52dd3  br       loc_530FC
0x52dd8  ldloc.0
0x52dd9  ldc.i4   0x4F6B9560
0x52dde  bgt.un.s loc_52DFB
0x52de0  ldloc.0
0x52de1  ldc.i4   0x3578225F
0x52de6  beq      loc_52EFE
0x52deb  ldloc.0
0x52dec  ldc.i4   0x4F6B9560
0x52df1  beq      loc_52FA6
0x52df6  br       loc_530FC
0x52dfb  ldloc.0
0x52dfc  ldc.i4   0x62FA988F
0x52e01  beq      loc_52ED4
0x52e06  ldloc.0
0x52e07  ldc.i4   0x6E61547A
0x52e0c  beq      loc_52F7C
0x52e11  ldloc.0
0x52e12  ldc.i4   0x7A787910
0x52e17  beq      loc_52F28
0x52e1c  br       loc_530FC
0x52e21  ldloc.0
0x52e22  ldc.i4   0x9F56E047
0x52e27  bgt.un.s loc_52E64
0x52e29  ldloc.0
0x52e2a  ldc.i4   0x80D2874B
0x52e2f  bgt.un.s loc_52E4C
0x52e31  ldloc.0
0x52e32  ldc.i4   0x7B5DF6A6
0x52e37  beq      loc_52EE9
0x52e3c  ldloc.0
0x52e3d  ldc.i4   0x80D2874B
0x52e42  beq      loc_5300F
0x52e47  br       loc_530FC
0x52e4c  ldloc.0
0x52e4d  ldc.i4   0x946992DC
0x52e52  beq.s    loc_52EBF
0x52e54  ldloc.0
0x52e55  ldc.i4   0x9F56E047
0x52e5a  beq      loc_52FD0
0x52e5f  br       loc_530FC
0x52e64  ldloc.0
0x52e65  ldc.i4   0xC0670678
0x52e6a  bgt.un.s loc_52E87
0x52e6c  ldloc.0
0x52e6d  ldc.i4   0xA6468091
0x52e72  beq      loc_52FFA
0x52e77  ldloc.0
0x52e78  ldc.i4   0xC0670678
0x52e7d  beq      loc_52F67
0x52e82  br       loc_530FC
0x52e87  ldloc.0
0x52e88  ldc.i4   0xC09B32FA
0x52e8d  beq      loc_52F13
0x52e92  ldloc.0
0x52e93  ldc.i4   0xCEEE0703
0x52e98  beq.s    loc_52EAA
0x52e9a  ldloc.0
0x52e9b  ldc.i4   0xF92D43AC
0x52ea0  beq      loc_52FE5
0x52ea5  br       loc_530FC
0x52eaa  ldarg.1
0x52eab  ldstr    aManagedpropert_5// "ManagedProperty"
0x52eb0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x52eb5  brtrue   loc_53024
0x52eba  br       loc_530FC
0x52ebf  ldarg.1
0x52ec0  ldstr    aOptionset_0// "OptionSet"
0x52ec5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x52eca  brtrue   loc_53030
0x52ecf  br       loc_530FC
0x52ed4  ldarg.1
0x52ed5  ldstr    aAttribute// "Attribute"
0x52eda  call     bool [mscorlib]System.String::op_Equality(string, string)
0x52edf  brtrue   loc_5303C
0x52ee4  br       loc_530FC
0x52ee9  ldarg.1
0x52eea  ldstr    aAttributelooku// "AttributeLookupValue"
0x52eef  call     bool [mscorlib]System.String::op_Equality(string, string)
0x52ef4  brtrue   loc_53048
0x52ef9  br       loc_530FC
0x52efe  ldarg.1
0x52eff  ldstr    aAttributepickl// "AttributePicklistValue"
0x52f04  call     bool [mscorlib]System.String::op_Equality(string, string)
0x52f09  brtrue   loc_53054
0x52f0e  br       loc_530FC
0x52f13  ldarg.1
0x52f14  ldstr    aEntity_0// "Entity"
0x52f19  call     bool [mscorlib]System.String::op_Equality(string, string)
0x52f1e  brtrue   loc_53060
0x52f23  br       loc_530FC
0x52f28  ldarg.1
0x52f29  ldstr    aLocalizedlabel// "LocalizedLabel"
0x52f2e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x52f33  brtrue   loc_5306C
0x52f38  br       loc_530FC
0x52f3d  ldarg.1
0x52f3e  ldstr    aRelationship_0// "Relationship"
0x52f43  call     bool [mscorlib]System.String::op_Equality(string, string)
0x52f48  brtrue   loc_53078
0x52f4d  br       loc_530FC
0x52f52  ldarg.1
0x52f53  ldstr    aRelationshipex_0// "RelationshipExtraCondition"
0x52f58  call     bool [mscorlib]System.String::op_Equality(string, string)
0x52f5d  brtrue   loc_53084
0x52f62  br       loc_530FC
0x52f67  ldarg.1
0x52f68  ldstr    aViewattribute// "ViewAttribute"
0x52f6d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x52f72  brtrue   loc_53090
0x52f77  br       loc_530FC
0x52f7c  ldarg.1
0x52f7d  ldstr    aPrivilegeobjec// "PrivilegeObjectTypeCode"
0x52f82  call     bool [mscorlib]System.String::op_Equality(string, string)
0x52f87  brtrue   loc_5309C
0x52f8c  br       loc_530FC
0x52f91  ldarg.1
0x52f92  ldstr    aRoletemplatepr// "RoleTemplatePrivilege"
0x52f97  call     bool [mscorlib]System.String::op_Equality(string, string)
0x52f9c  brtrue   loc_530A8
0x52fa1  br       loc_530FC
0x52fa6  ldarg.1
0x52fa7  ldstr    aEntityrelation_0// "EntityRelationship"
0x52fac  call     bool [mscorlib]System.String::op_Equality(string, string)
0x52fb1  brtrue   loc_530B4
0x52fb6  br       loc_530FC
0x52fbb  ldarg.1
0x52fbc  ldstr    aEntityrelation_4// "EntityRelationshipRole"
0x52fc1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x52fc6  brtrue   loc_530C0
0x52fcb  br       loc_530FC
0x52fd0  ldarg.1
0x52fd1  ldstr    aEntityrelation_6// "EntityRelationshipRelationships"
0x52fd6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x52fdb  brtrue   loc_530CC
0x52fe0  br       loc_530FC
0x52fe5  ldarg.1
0x52fe6  ldstr    aPrivilege// "Privilege"
0x52feb  call     bool [mscorlib]System.String::op_Equality(string, string)
0x52ff0  brtrue   loc_530D8
0x52ff5  br       loc_530FC
0x52ffa  ldarg.1
0x52ffb  ldstr    aEntitykey_0// "EntityKey"
0x53000  call     bool [mscorlib]System.String::op_Equality(string, string)
0x53005  brtrue   loc_530E4
0x5300a  br       loc_530FC
0x5300f  ldarg.1
0x53010  ldstr    aEntitykeyattri// "EntityKeyAttribute"
0x53015  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5301a  brtrue   loc_530F0
0x5301f  br       loc_530FC
0x53024  ldarg.0
0x53025  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> Microsoft.Crm.Metadata.MetadataContainer::_managedProperties
0x5302a  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription>::get_Count()
0x5302f  ret
0x53030  ldarg.0
0x53031  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> Microsoft.Crm.Metadata.MetadataContainer::_optionSets
0x53036  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription>::get_Count()
0x5303b  ret
0x5303c  ldarg.0
0x5303d  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> Microsoft.Crm.Metadata.MetadataContainer::_attributes
0x53042  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription>::get_Count()
0x53047  ret
0x53048  ldarg.0
0x53049  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> Microsoft.Crm.Metadata.MetadataContainer::_lookupValues
0x5304e  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription>::get_Count()
0x53053  ret
0x53054  ldarg.0
0x53055  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> Microsoft.Crm.Metadata.MetadataContainer::_picklistValues
0x5305a  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription>::get_Count()
0x5305f  ret
0x53060  ldarg.0
0x53061  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> Microsoft.Crm.Metadata.MetadataContainer::_entities
0x53066  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription>::get_Count()
0x5306b  ret
0x5306c  ldarg.0
0x5306d  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> Microsoft.Crm.Metadata.MetadataContainer::_localizedLabels
0x53072  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription>::get_Count()
0x53077  ret
0x53078  ldarg.0
0x53079  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> Microsoft.Crm.Metadata.MetadataContainer::_relationships
0x5307e  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription>::get_Count()
0x53083  ret
0x53084  ldarg.0
0x53085  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> Microsoft.Crm.Metadata.MetadataContainer::_relationshipExtraConditions
0x5308a  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription>::get_Count()
0x5308f  ret
0x53090  ldarg.0
0x53091  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> Microsoft.Crm.Metadata.MetadataContainer::_viewAttributes
0x53096  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription>::get_Count()
0x5309b  ret
0x5309c  ldarg.0
0x5309d  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> Microsoft.Crm.Metadata.MetadataContainer::_privilegesObjectTypeCodes
0x530a2  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription>::get_Count()
0x530a7  ret
0x530a8  ldarg.0
0x530a9  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> Microsoft.Crm.Metadata.MetadataContainer::_roleTemplatePrivileges
0x530ae  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription>::get_Count()
0x530b3  ret
0x530b4  ldarg.0
0x530b5  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> Microsoft.Crm.Metadata.MetadataContainer::_entityRelationships
0x530ba  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription>::get_Count()
0x530bf  ret
0x530c0  ldarg.0
0x530c1  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> Microsoft.Crm.Metadata.MetadataContainer::_entityRelationshipRoles
0x530c6  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription>::get_Count()
0x530cb  ret
0x530cc  ldarg.0
0x530cd  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> Microsoft.Crm.Metadata.MetadataContainer::_entityRelationshipRelationships
0x530d2  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription>::get_Count()
0x530d7  ret
0x530d8  ldarg.0
0x530d9  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Metadata.Privilege> Microsoft.Crm.Metadata.MetadataContainer::_privileges
0x530de  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Metadata.Privilege>::get_Count()
0x530e3  ret
0x530e4  ldarg.0
0x530e5  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> Microsoft.Crm.Metadata.MetadataContainer::_entityKeys
0x530ea  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription>::get_Count()
0x530ef  ret
0x530f0  ldarg.0
0x530f1  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> Microsoft.Crm.Metadata.MetadataContainer::_entityKeyAttributes
0x530f6  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription>::get_Count()
0x530fb  ret
0x530fc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x53101  ldstr    aMetadataentity_1// "MetadataEntityName {0} is not valid"
0x53106  ldc.i4.1
0x53107  newarr   [mscorlib]System.Object
0x5310c  dup
0x5310d  ldc.i4.0
0x5310e  ldarg.1
0x5310f  stelem.ref
0x53110  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x53115  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x5311a  throw
```
