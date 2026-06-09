# Microsoft.Crm.Metadata.DynamicMetadataContainer::AddDescription

- ea: `0x55960`
- end: `0x55d53`
- name: `Microsoft.Crm.Metadata.DynamicMetadataContainer::AddDescription`
- size: `1011`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x293d0`
- `0x55960`
- `0x55d60`
- `0x55d90`
- `0x55dc0`
- `0x55e20`
- `0x55ee0`
- `0x55f50`
- `0x55fd0`
- `0x56060`
- `0x560e0`
- `0x56120`
- `0x561a0`
- `0x561d0`
- `0x56200`
- `0x56230`
- `0x562b0`
- `0x56330`
- `0x56360`
- `0xa94d0`

## string_xrefs

- `0x55b48`: `Privilege`
- `0x55b5d`: `PrivilegeObjectTypeCode`
- `0x55b72`: `RoleTemplatePrivilege`

## pseudocode

```c

```

## disassembly

```asm
0x55960  ldarg.1
0x55961  ldstr    aDescription// "description"
0x55966  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x5596b  ldarg.2
0x5596c  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x55971  stloc.0
0x55972  ldloc.0
0x55973  ldc.i4   0x6E61547A
0x55978  bgt.un   loc_55A01
0x5597d  ldloc.0
0x5597e  ldc.i4   0x2FB17EF0
0x55983  bgt.un.s loc_559C3
0x55985  ldloc.0
0x55986  ldc.i4   0x1D72D1E6
0x5598b  bgt.un.s loc_559A8
0x5598d  ldloc.0
0x5598e  ldc.i4   0x1ACCD85B
0x55993  beq      loc_55B08
0x55998  ldloc.0
0x55999  ldc.i4   0x1D72D1E6
0x5599e  beq      loc_55B71
0x559a3  br       loc_55D04
0x559a8  ldloc.0
0x559a9  ldc.i4   0x21E27D10
0x559ae  beq      loc_55B9B
0x559b3  ldloc.0
0x559b4  ldc.i4   0x2FB17EF0
0x559b9  beq      loc_55B1D
0x559be  br       loc_55D04
0x559c3  ldloc.0
0x559c4  ldc.i4   0x4F6B9560
0x559c9  bgt.un.s loc_559E6
0x559cb  ldloc.0
0x559cc  ldc.i4   0x3578225F
0x559d1  beq      loc_55ADE
0x559d6  ldloc.0
0x559d7  ldc.i4   0x4F6B9560
0x559dc  beq      loc_55B86
0x559e1  br       loc_55D04
0x559e6  ldloc.0
0x559e7  ldc.i4   0x62FA988F
0x559ec  beq      loc_55AB4
0x559f1  ldloc.0
0x559f2  ldc.i4   0x6E61547A
0x559f7  beq      loc_55B5C
0x559fc  br       loc_55D04
0x55a01  ldloc.0
0x55a02  ldc.i4   0x9F56E047
0x55a07  bgt.un.s loc_55A44
0x55a09  ldloc.0
0x55a0a  ldc.i4   0x80D2874B
0x55a0f  bgt.un.s loc_55A2C
0x55a11  ldloc.0
0x55a12  ldc.i4   0x7B5DF6A6
0x55a17  beq      loc_55AC9
0x55a1c  ldloc.0
0x55a1d  ldc.i4   0x80D2874B
0x55a22  beq      loc_55BDA
0x55a27  br       loc_55D04
0x55a2c  ldloc.0
0x55a2d  ldc.i4   0x946992DC
0x55a32  beq.s    loc_55A9F
0x55a34  ldloc.0
0x55a35  ldc.i4   0x9F56E047
0x55a3a  beq      loc_55BB0
0x55a3f  br       loc_55D04
0x55a44  ldloc.0
0x55a45  ldc.i4   0xC0670678
0x55a4a  bgt.un.s loc_55A67
0x55a4c  ldloc.0
0x55a4d  ldc.i4   0xA6468091
0x55a52  beq      loc_55BC5
0x55a57  ldloc.0
0x55a58  ldc.i4   0xC0670678
0x55a5d  beq      loc_55B32
0x55a62  br       loc_55D04
0x55a67  ldloc.0
0x55a68  ldc.i4   0xC09B32FA
0x55a6d  beq      loc_55AF3
0x55a72  ldloc.0
0x55a73  ldc.i4   0xCEEE0703
0x55a78  beq.s    loc_55A8A
0x55a7a  ldloc.0
0x55a7b  ldc.i4   0xF92D43AC
0x55a80  beq      loc_55B47
0x55a85  br       loc_55D04
0x55a8a  ldarg.2
0x55a8b  ldstr    aManagedpropert_5// "ManagedProperty"
0x55a90  call     bool [mscorlib]System.String::op_Equality(string, string)
0x55a95  brtrue   loc_55BEF
0x55a9a  br       loc_55D04
0x55a9f  ldarg.2
0x55aa0  ldstr    aOptionset_0// "OptionSet"
0x55aa5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x55aaa  brtrue   loc_55C00
0x55aaf  br       loc_55D04
0x55ab4  ldarg.2
0x55ab5  ldstr    aAttribute// "Attribute"
0x55aba  call     bool [mscorlib]System.String::op_Equality(string, string)
0x55abf  brtrue   loc_55C11
0x55ac4  br       loc_55D04
0x55ac9  ldarg.2
0x55aca  ldstr    aAttributelooku// "AttributeLookupValue"
0x55acf  call     bool [mscorlib]System.String::op_Equality(string, string)
0x55ad4  brtrue   loc_55C22
0x55ad9  br       loc_55D04
0x55ade  ldarg.2
0x55adf  ldstr    aAttributepickl// "AttributePicklistValue"
0x55ae4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x55ae9  brtrue   loc_55C33
0x55aee  br       loc_55D04
0x55af3  ldarg.2
0x55af4  ldstr    aEntity_0// "Entity"
0x55af9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x55afe  brtrue   loc_55C44
0x55b03  br       loc_55D04
0x55b08  ldarg.2
0x55b09  ldstr    aRelationship_0// "Relationship"
0x55b0e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x55b13  brtrue   loc_55C55
0x55b18  br       loc_55D04
0x55b1d  ldarg.2
0x55b1e  ldstr    aRelationshipex_0// "RelationshipExtraCondition"
0x55b23  call     bool [mscorlib]System.String::op_Equality(string, string)
0x55b28  brtrue   loc_55C66
0x55b2d  br       loc_55D04
0x55b32  ldarg.2
0x55b33  ldstr    aViewattribute// "ViewAttribute"
0x55b38  call     bool [mscorlib]System.String::op_Equality(string, string)
0x55b3d  brtrue   loc_55C77
0x55b42  br       loc_55D04
0x55b47  ldarg.2
0x55b48  ldstr    aPrivilege// "Privilege"
0x55b4d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x55b52  brtrue   loc_55C88
0x55b57  br       loc_55D04
0x55b5c  ldarg.2
0x55b5d  ldstr    aPrivilegeobjec// "PrivilegeObjectTypeCode"
0x55b62  call     bool [mscorlib]System.String::op_Equality(string, string)
0x55b67  brtrue   loc_55C99
0x55b6c  br       loc_55D04
0x55b71  ldarg.2
0x55b72  ldstr    aRoletemplatepr// "RoleTemplatePrivilege"
0x55b77  call     bool [mscorlib]System.String::op_Equality(string, string)
0x55b7c  brtrue   loc_55CAA
0x55b81  br       loc_55D04
0x55b86  ldarg.2
0x55b87  ldstr    aEntityrelation_0// "EntityRelationship"
0x55b8c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x55b91  brtrue   loc_55CBB
0x55b96  br       loc_55D04
0x55b9b  ldarg.2
0x55b9c  ldstr    aEntityrelation_4// "EntityRelationshipRole"
0x55ba1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x55ba6  brtrue   loc_55CCC
0x55bab  br       loc_55D04
0x55bb0  ldarg.2
0x55bb1  ldstr    aEntityrelation_6// "EntityRelationshipRelationships"
0x55bb6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x55bbb  brtrue   loc_55CDA
0x55bc0  br       loc_55D04
0x55bc5  ldarg.2
0x55bc6  ldstr    aEntitykey_0// "EntityKey"
0x55bcb  call     bool [mscorlib]System.String::op_Equality(string, string)
0x55bd0  brtrue   loc_55CE8
0x55bd5  br       loc_55D04
0x55bda  ldarg.2
0x55bdb  ldstr    aEntitykeyattri// "EntityKeyAttribute"
0x55be0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x55be5  brtrue   loc_55CF6
0x55bea  br       loc_55D04
0x55bef  ldarg.0
0x55bf0  ldarg.1
0x55bf1  isinst   Microsoft.Crm.Metadata.IManagedPropertyDescription
0x55bf6  call     instance void Microsoft.Crm.Metadata.DynamicMetadataContainer::AddManagedProperty(class Microsoft.Crm.Metadata.IManagedPropertyDescription managedProperty)
0x55bfb  leave    loc_55D52
0x55c00  ldarg.0
0x55c01  ldarg.1
0x55c02  isinst   Microsoft.Crm.Metadata.IOptionSetDescription
0x55c07  call     instance void Microsoft.Crm.Metadata.DynamicMetadataContainer::AddOptionSet(class Microsoft.Crm.Metadata.IOptionSetDescription optionSet)
0x55c0c  leave    loc_55D52
0x55c11  ldarg.0
0x55c12  ldarg.1
0x55c13  isinst   Microsoft.Crm.Metadata.IAttributeDescription
0x55c18  callvirt instance void Microsoft.Crm.Metadata.DynamicMetadataContainer::AddAttribute(class Microsoft.Crm.Metadata.IAttributeDescription attribute)
0x55c1d  leave    loc_55D52
0x55c22  ldarg.0
0x55c23  ldarg.1
0x55c24  isinst   Microsoft.Crm.Metadata.IAttributeLookupValueDescription
0x55c29  callvirt instance void Microsoft.Crm.Metadata.DynamicMetadataContainer::AddAttributeLookupValue(class Microsoft.Crm.Metadata.IAttributeLookupValueDescription lookupValue)
0x55c2e  leave    loc_55D52
0x55c33  ldarg.0
0x55c34  ldarg.1
0x55c35  isinst   Microsoft.Crm.Metadata.IAttributePicklistValueDescription
0x55c3a  callvirt instance void Microsoft.Crm.Metadata.DynamicMetadataContainer::AddAttributePicklistValue(class Microsoft.Crm.Metadata.IAttributePicklistValueDescription picklistValue)
0x55c3f  leave    loc_55D52
0x55c44  ldarg.0
0x55c45  ldarg.1
0x55c46  isinst   Microsoft.Crm.Metadata.IEntityDescription
0x55c4b  call     instance void Microsoft.Crm.Metadata.DynamicMetadataContainer::AddEntity(class Microsoft.Crm.Metadata.IEntityDescription entity)
0x55c50  leave    loc_55D52
0x55c55  ldarg.0
0x55c56  ldarg.1
0x55c57  isinst   Microsoft.Crm.Metadata.IRelationshipDescription
0x55c5c  callvirt instance void Microsoft.Crm.Metadata.DynamicMetadataContainer::AddRelationship(class Microsoft.Crm.Metadata.IRelationshipDescription relationship)
0x55c61  leave    loc_55D52
0x55c66  ldarg.0
0x55c67  ldarg.1
0x55c68  isinst   Microsoft.Crm.Metadata.IRelationshipExtraConditionDescription
0x55c6d  callvirt instance void Microsoft.Crm.Metadata.DynamicMetadataContainer::AddRelationshipExtraCondition(class Microsoft.Crm.Metadata.IRelationshipExtraConditionDescription relationshipExtraCondition)
0x55c72  leave    loc_55D52
0x55c77  ldarg.0
0x55c78  ldarg.1
0x55c79  isinst   Microsoft.Crm.Metadata.IViewInfoDescription
0x55c7e  call     instance void Microsoft.Crm.Metadata.DynamicMetadataContainer::AddViewAttribute(class Microsoft.Crm.Metadata.IViewInfoDescription viewAttribute)
0x55c83  leave    loc_55D52
0x55c88  ldarg.0
0x55c89  ldarg.1
0x55c8a  isinst   Microsoft.Crm.Metadata.IPrivilegeDescription
0x55c8f  call     instance void Microsoft.Crm.Metadata.DynamicMetadataContainer::AddPrivilege(class Microsoft.Crm.Metadata.IPrivilegeDescription description)
0x55c94  leave    loc_55D52
0x55c99  ldarg.0
0x55c9a  ldarg.1
0x55c9b  isinst   Microsoft.Crm.Metadata.IPrivilegeObjectTypeCodeDescription
0x55ca0  call     instance void Microsoft.Crm.Metadata.DynamicMetadataContainer::AddPrivilegeObjectTypeCode(class Microsoft.Crm.Metadata.IPrivilegeObjectTypeCodeDescription privilegeOtc)
0x55ca5  leave    loc_55D52
0x55caa  ldarg.0
0x55cab  ldarg.1
0x55cac  isinst   Microsoft.Crm.Metadata.IRoleTemplatePrivilegeDescription
0x55cb1  call     instance void Microsoft.Crm.Metadata.DynamicMetadataContainer::AddRoleTemplatePrivilege(class Microsoft.Crm.Metadata.IRoleTemplatePrivilegeDescription roleTemplatePrivilegeDescription)
0x55cb6  leave    loc_55D52
0x55cbb  ldarg.0
0x55cbc  ldarg.1
0x55cbd  isinst   Microsoft.Crm.Metadata.IEntityRelationshipDescription
0x55cc2  call     instance void Microsoft.Crm.Metadata.DynamicMetadataContainer::AddEntityRelationship(class Microsoft.Crm.Metadata.IEntityRelationshipDescription entityRelationshipDescription)
0x55cc7  leave    loc_55D52
0x55ccc  ldarg.0
0x55ccd  ldarg.1
0x55cce  isinst   Microsoft.Crm.Metadata.IEntityRelationshipRoleDescription
0x55cd3  callvirt instance void Microsoft.Crm.Metadata.DynamicMetadataContainer::AddEntityRelationshipRole(class Microsoft.Crm.Metadata.IEntityRelationshipRoleDescription entityRelationshipRoleDescription)
0x55cd8  leave.s  loc_55D52
0x55cda  ldarg.0
0x55cdb  ldarg.1
0x55cdc  isinst   Microsoft.Crm.Metadata.IEntityRelationshipRelationshipsDescription
0x55ce1  call     instance void Microsoft.Crm.Metadata.DynamicMetadataContainer::AddEntityRelationshipRelationships(class Microsoft.Crm.Metadata.IEntityRelationshipRelationshipsDescription entityRelationshipRelationshipsDescription)
0x55ce6  leave.s  loc_55D52
0x55ce8  ldarg.0
0x55ce9  ldarg.1
0x55cea  isinst   Microsoft.Crm.Metadata.IEntityKeyDescription
0x55cef  call     instance void Microsoft.Crm.Metadata.DynamicMetadataContainer::AddEntityKey(class Microsoft.Crm.Metadata.IEntityKeyDescription entityKeyDescription)
0x55cf4  leave.s  loc_55D52
0x55cf6  ldarg.0
0x55cf7  ldarg.1
0x55cf8  isinst   Microsoft.Crm.Metadata.IEntityKeyAttributeDescription
0x55cfd  call     instance void Microsoft.Crm.Metadata.DynamicMetadataContainer::AddEntityKeyAttribute(class Microsoft.Crm.Metadata.IEntityKeyAttributeDescription entityKeyAttributeDescription)
0x55d02  leave.s  loc_55D52
0x55d04  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x55d09  ldstr    aMetadataentity_1// "MetadataEntityName {0} is not valid"
0x55d0e  ldc.i4.1
0x55d0f  newarr   [mscorlib]System.Object
0x55d14  dup
0x55d15  ldc.i4.0
0x55d16  ldarg.2
0x55d17  stelem.ref
0x55d18  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x55d1d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x55d22  throw
0x55d23  stloc.1
0x55d24  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x55d29  ldstr    aFailedToProces// "Failed to process metadata description "...
0x55d2e  ldc.i4.2
0x55d2f  newarr   [mscorlib]System.Object
0x55d34  dup
0x55d35  ldc.i4.0
0x55d36  ldarg.2
0x55d37  stelem.ref
0x55d38  dup
0x55d39  ldc.i4.1
0x55d3a  ldarg.1
0x55d3b  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.IMetadataDescription::get_DescriptionId()
0x55d40  box      [mscorlib]System.Guid
0x55d45  stelem.ref
0x55d46  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x55d4b  ldloc.1
0x55d4c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, class [mscorlib]System.Exception)
0x55d51  throw
0x55d52  ret
```
