# Microsoft.Crm.Metadata.MetadataContainer::InitializeSize

- ea: `0x529d0`
- end: `0x52d7d`
- name: `Microsoft.Crm.Metadata.MetadataContainer::InitializeSize`
- size: `941`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x5afe0`
- `0x5b300`

## callees

- `0x529d0`
- `0xa94d0`

## string_xrefs

- `0x52c36`: `Privilege`
- `0x52bcd`: `PrivilegeObjectTypeCode`
- `0x52be2`: `RoleTemplatePrivilege`

## pseudocode

```c

```

## disassembly

```asm
0x529d0  ldarg.2
0x529d1  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x529d6  stloc.0
0x529d7  ldloc.0
0x529d8  ldc.i4   0x7A787910
0x529dd  bgt.un   loc_52A71
0x529e2  ldloc.0
0x529e3  ldc.i4   0x2FB17EF0
0x529e8  bgt.un.s loc_52A28
0x529ea  ldloc.0
0x529eb  ldc.i4   0x1D72D1E6
0x529f0  bgt.un.s loc_52A0D
0x529f2  ldloc.0
0x529f3  ldc.i4   0x1ACCD85B
0x529f8  beq      loc_52B8D
0x529fd  ldloc.0
0x529fe  ldc.i4   0x1D72D1E6
0x52a03  beq      loc_52BE1
0x52a08  br       loc_52D5E
0x52a0d  ldloc.0
0x52a0e  ldc.i4   0x21E27D10
0x52a13  beq      loc_52C0B
0x52a18  ldloc.0
0x52a19  ldc.i4   0x2FB17EF0
0x52a1e  beq      loc_52BA2
0x52a23  br       loc_52D5E
0x52a28  ldloc.0
0x52a29  ldc.i4   0x4F6B9560
0x52a2e  bgt.un.s loc_52A4B
0x52a30  ldloc.0
0x52a31  ldc.i4   0x3578225F
0x52a36  beq      loc_52B4E
0x52a3b  ldloc.0
0x52a3c  ldc.i4   0x4F6B9560
0x52a41  beq      loc_52BF6
0x52a46  br       loc_52D5E
0x52a4b  ldloc.0
0x52a4c  ldc.i4   0x62FA988F
0x52a51  beq      loc_52B24
0x52a56  ldloc.0
0x52a57  ldc.i4   0x6E61547A
0x52a5c  beq      loc_52BCC
0x52a61  ldloc.0
0x52a62  ldc.i4   0x7A787910
0x52a67  beq      loc_52B78
0x52a6c  br       loc_52D5E
0x52a71  ldloc.0
0x52a72  ldc.i4   0x9F56E047
0x52a77  bgt.un.s loc_52AB4
0x52a79  ldloc.0
0x52a7a  ldc.i4   0x80D2874B
0x52a7f  bgt.un.s loc_52A9C
0x52a81  ldloc.0
0x52a82  ldc.i4   0x7B5DF6A6
0x52a87  beq      loc_52B39
0x52a8c  ldloc.0
0x52a8d  ldc.i4   0x80D2874B
0x52a92  beq      loc_52C5F
0x52a97  br       loc_52D5E
0x52a9c  ldloc.0
0x52a9d  ldc.i4   0x946992DC
0x52aa2  beq.s    loc_52B0F
0x52aa4  ldloc.0
0x52aa5  ldc.i4   0x9F56E047
0x52aaa  beq      loc_52C20
0x52aaf  br       loc_52D5E
0x52ab4  ldloc.0
0x52ab5  ldc.i4   0xC0670678
0x52aba  bgt.un.s loc_52AD7
0x52abc  ldloc.0
0x52abd  ldc.i4   0xA6468091
0x52ac2  beq      loc_52C4A
0x52ac7  ldloc.0
0x52ac8  ldc.i4   0xC0670678
0x52acd  beq      loc_52BB7
0x52ad2  br       loc_52D5E
0x52ad7  ldloc.0
0x52ad8  ldc.i4   0xC09B32FA
0x52add  beq      loc_52B63
0x52ae2  ldloc.0
0x52ae3  ldc.i4   0xCEEE0703
0x52ae8  beq.s    loc_52AFA
0x52aea  ldloc.0
0x52aeb  ldc.i4   0xF92D43AC
0x52af0  beq      loc_52C35
0x52af5  br       loc_52D5E
0x52afa  ldarg.2
0x52afb  ldstr    aManagedpropert_5// "ManagedProperty"
0x52b00  call     bool [mscorlib]System.String::op_Equality(string, string)
0x52b05  brtrue   loc_52C74
0x52b0a  br       loc_52D5E
0x52b0f  ldarg.2
0x52b10  ldstr    aOptionset_0// "OptionSet"
0x52b15  call     bool [mscorlib]System.String::op_Equality(string, string)
0x52b1a  brtrue   loc_52C81
0x52b1f  br       loc_52D5E
0x52b24  ldarg.2
0x52b25  ldstr    aAttribute// "Attribute"
0x52b2a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x52b2f  brtrue   loc_52C8E
0x52b34  br       loc_52D5E
0x52b39  ldarg.2
0x52b3a  ldstr    aAttributelooku// "AttributeLookupValue"
0x52b3f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x52b44  brtrue   loc_52C9B
0x52b49  br       loc_52D5E
0x52b4e  ldarg.2
0x52b4f  ldstr    aAttributepickl// "AttributePicklistValue"
0x52b54  call     bool [mscorlib]System.String::op_Equality(string, string)
0x52b59  brtrue   loc_52CA8
0x52b5e  br       loc_52D5E
0x52b63  ldarg.2
0x52b64  ldstr    aEntity_0// "Entity"
0x52b69  call     bool [mscorlib]System.String::op_Equality(string, string)
0x52b6e  brtrue   loc_52CB5
0x52b73  br       loc_52D5E
0x52b78  ldarg.2
0x52b79  ldstr    aLocalizedlabel// "LocalizedLabel"
0x52b7e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x52b83  brtrue   loc_52CC2
0x52b88  br       loc_52D5E
0x52b8d  ldarg.2
0x52b8e  ldstr    aRelationship_0// "Relationship"
0x52b93  call     bool [mscorlib]System.String::op_Equality(string, string)
0x52b98  brtrue   loc_52CCF
0x52b9d  br       loc_52D5E
0x52ba2  ldarg.2
0x52ba3  ldstr    aRelationshipex_0// "RelationshipExtraCondition"
0x52ba8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x52bad  brtrue   loc_52CDC
0x52bb2  br       loc_52D5E
0x52bb7  ldarg.2
0x52bb8  ldstr    aViewattribute// "ViewAttribute"
0x52bbd  call     bool [mscorlib]System.String::op_Equality(string, string)
0x52bc2  brtrue   loc_52CE9
0x52bc7  br       loc_52D5E
0x52bcc  ldarg.2
0x52bcd  ldstr    aPrivilegeobjec// "PrivilegeObjectTypeCode"
0x52bd2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x52bd7  brtrue   loc_52CF6
0x52bdc  br       loc_52D5E
0x52be1  ldarg.2
0x52be2  ldstr    aRoletemplatepr// "RoleTemplatePrivilege"
0x52be7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x52bec  brtrue   loc_52D03
0x52bf1  br       loc_52D5E
0x52bf6  ldarg.2
0x52bf7  ldstr    aEntityrelation_0// "EntityRelationship"
0x52bfc  call     bool [mscorlib]System.String::op_Equality(string, string)
0x52c01  brtrue   loc_52D10
0x52c06  br       loc_52D5E
0x52c0b  ldarg.2
0x52c0c  ldstr    aEntityrelation_4// "EntityRelationshipRole"
0x52c11  call     bool [mscorlib]System.String::op_Equality(string, string)
0x52c16  brtrue   loc_52D1D
0x52c1b  br       loc_52D5E
0x52c20  ldarg.2
0x52c21  ldstr    aEntityrelation_6// "EntityRelationshipRelationships"
0x52c26  call     bool [mscorlib]System.String::op_Equality(string, string)
0x52c2b  brtrue   loc_52D2A
0x52c30  br       loc_52D5E
0x52c35  ldarg.2
0x52c36  ldstr    aPrivilege// "Privilege"
0x52c3b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x52c40  brtrue   loc_52D37
0x52c45  br       loc_52D5E
0x52c4a  ldarg.2
0x52c4b  ldstr    aEntitykey_0// "EntityKey"
0x52c50  call     bool [mscorlib]System.String::op_Equality(string, string)
0x52c55  brtrue   loc_52D44
0x52c5a  br       loc_52D5E
0x52c5f  ldarg.2
0x52c60  ldstr    aEntitykeyattri// "EntityKeyAttribute"
0x52c65  call     bool [mscorlib]System.String::op_Equality(string, string)
0x52c6a  brtrue   loc_52D51
0x52c6f  br       loc_52D5E
0x52c74  ldarg.0
0x52c75  ldarg.1
0x52c76  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription>::.ctor(int32)
0x52c7b  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> Microsoft.Crm.Metadata.MetadataContainer::_managedProperties
0x52c80  ret
0x52c81  ldarg.0
0x52c82  ldarg.1
0x52c83  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription>::.ctor(int32)
0x52c88  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> Microsoft.Crm.Metadata.MetadataContainer::_optionSets
0x52c8d  ret
0x52c8e  ldarg.0
0x52c8f  ldarg.1
0x52c90  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription>::.ctor(int32)
0x52c95  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> Microsoft.Crm.Metadata.MetadataContainer::_attributes
0x52c9a  ret
0x52c9b  ldarg.0
0x52c9c  ldarg.1
0x52c9d  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription>::.ctor(int32)
0x52ca2  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> Microsoft.Crm.Metadata.MetadataContainer::_lookupValues
0x52ca7  ret
0x52ca8  ldarg.0
0x52ca9  ldarg.1
0x52caa  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription>::.ctor(int32)
0x52caf  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> Microsoft.Crm.Metadata.MetadataContainer::_picklistValues
0x52cb4  ret
0x52cb5  ldarg.0
0x52cb6  ldarg.1
0x52cb7  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription>::.ctor(int32)
0x52cbc  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> Microsoft.Crm.Metadata.MetadataContainer::_entities
0x52cc1  ret
0x52cc2  ldarg.0
0x52cc3  ldarg.1
0x52cc4  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription>::.ctor(int32)
0x52cc9  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> Microsoft.Crm.Metadata.MetadataContainer::_localizedLabels
0x52cce  ret
0x52ccf  ldarg.0
0x52cd0  ldarg.1
0x52cd1  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription>::.ctor(int32)
0x52cd6  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> Microsoft.Crm.Metadata.MetadataContainer::_relationships
0x52cdb  ret
0x52cdc  ldarg.0
0x52cdd  ldarg.1
0x52cde  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription>::.ctor(int32)
0x52ce3  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> Microsoft.Crm.Metadata.MetadataContainer::_relationshipExtraConditions
0x52ce8  ret
0x52ce9  ldarg.0
0x52cea  ldarg.1
0x52ceb  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription>::.ctor(int32)
0x52cf0  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> Microsoft.Crm.Metadata.MetadataContainer::_viewAttributes
0x52cf5  ret
0x52cf6  ldarg.0
0x52cf7  ldarg.1
0x52cf8  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription>::.ctor(int32)
0x52cfd  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> Microsoft.Crm.Metadata.MetadataContainer::_privilegesObjectTypeCodes
0x52d02  ret
0x52d03  ldarg.0
0x52d04  ldarg.1
0x52d05  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription>::.ctor(int32)
0x52d0a  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> Microsoft.Crm.Metadata.MetadataContainer::_roleTemplatePrivileges
0x52d0f  ret
0x52d10  ldarg.0
0x52d11  ldarg.1
0x52d12  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription>::.ctor(int32)
0x52d17  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> Microsoft.Crm.Metadata.MetadataContainer::_entityRelationships
0x52d1c  ret
0x52d1d  ldarg.0
0x52d1e  ldarg.1
0x52d1f  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription>::.ctor(int32)
0x52d24  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> Microsoft.Crm.Metadata.MetadataContainer::_entityRelationshipRoles
0x52d29  ret
0x52d2a  ldarg.0
0x52d2b  ldarg.1
0x52d2c  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription>::.ctor(int32)
0x52d31  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> Microsoft.Crm.Metadata.MetadataContainer::_entityRelationshipRelationships
0x52d36  ret
0x52d37  ldarg.0
0x52d38  ldarg.1
0x52d39  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Metadata.Privilege>::.ctor(int32)
0x52d3e  stfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Metadata.Privilege> Microsoft.Crm.Metadata.MetadataContainer::_privileges
0x52d43  ret
0x52d44  ldarg.0
0x52d45  ldarg.1
0x52d46  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription>::.ctor(int32)
0x52d4b  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> Microsoft.Crm.Metadata.MetadataContainer::_entityKeys
0x52d50  ret
0x52d51  ldarg.0
0x52d52  ldarg.1
0x52d53  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription>::.ctor(int32)
0x52d58  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> Microsoft.Crm.Metadata.MetadataContainer::_entityKeyAttributes
0x52d5d  ret
0x52d5e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x52d63  ldstr    aMetadataentity_1// "MetadataEntityName {0} is not valid"
0x52d68  ldc.i4.1
0x52d69  newarr   [mscorlib]System.Object
0x52d6e  dup
0x52d6f  ldc.i4.0
0x52d70  ldarg.2
0x52d71  stelem.ref
0x52d72  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x52d77  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x52d7c  throw
```
