# Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::CreatePropertyBagDescriptionByName_1

- ea: `0x51b50`
- end: `0x51ed0`
- name: `Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::CreatePropertyBagDescriptionByName_1`
- size: `896`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x51b10`

## callees

- `0x24e90`
- `0x27f80`
- `0x28e60`
- `0x30330`
- `0x34070`
- `0x34d40`
- `0x35af0`
- `0x36510`
- `0x37700`
- `0x38e70`
- `0x3a020`
- `0x3b090`
- `0x3ba50`
- `0x3cb60`
- `0x3d7c0`
- `0x3eec0`
- `0x3fe10`
- `0x408d0`
- `0x41390`
- `0x51b50`
- `0x6fc40`
- `0xa94d0`

## string_xrefs

- `0x51d60`: `Privilege`
- `0x51d75`: `PrivilegeObjectTypeCode`
- `0x51d8a`: `RoleTemplatePrivilege`

## pseudocode

```c

```

## disassembly

```asm
0x51b50  ldarg.2
0x51b51  ldc.i4.1
0x51b52  newobj   instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::.ctor(class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntityMetadata, bool isOptimizedForMetadataCacheLoad)
0x51b57  stloc.0
0x51b58  ldarg.0
0x51b59  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x51b5e  stloc.1
0x51b5f  ldloc.1
0x51b60  ldc.i4   0x6E61547A
0x51b65  bgt.un   loc_51BF9
0x51b6a  ldloc.1
0x51b6b  ldc.i4   0x21E27D10
0x51b70  bgt.un.s loc_51BB0
0x51b72  ldloc.1
0x51b73  ldc.i4   0x1ACCD85B
0x51b78  bgt.un.s loc_51B95
0x51b7a  ldloc.1
0x51b7b  ldc.i4   0x1971E30A
0x51b80  beq      loc_51DDD
0x51b85  ldloc.1
0x51b86  ldc.i4   0x1ACCD85B
0x51b8b  beq      loc_51D20
0x51b90  br       loc_51EB1
0x51b95  ldloc.1
0x51b96  ldc.i4   0x1D72D1E6
0x51b9b  beq      loc_51D89
0x51ba0  ldloc.1
0x51ba1  ldc.i4   0x21E27D10
0x51ba6  beq      loc_51DB3
0x51bab  br       loc_51EB1
0x51bb0  ldloc.1
0x51bb1  ldc.i4   0x3578225F
0x51bb6  bgt.un.s loc_51BD3
0x51bb8  ldloc.1
0x51bb9  ldc.i4   0x2FB17EF0
0x51bbe  beq      loc_51D35
0x51bc3  ldloc.1
0x51bc4  ldc.i4   0x3578225F
0x51bc9  beq      loc_51CE1
0x51bce  br       loc_51EB1
0x51bd3  ldloc.1
0x51bd4  ldc.i4   0x4F6B9560
0x51bd9  beq      loc_51D9E
0x51bde  ldloc.1
0x51bdf  ldc.i4   0x62FA988F
0x51be4  beq      loc_51CB7
0x51be9  ldloc.1
0x51bea  ldc.i4   0x6E61547A
0x51bef  beq      loc_51D74
0x51bf4  br       loc_51EB1
0x51bf9  ldloc.1
0x51bfa  ldc.i4   0x9F56E047
0x51bff  bgt.un.s loc_51C47
0x51c01  ldloc.1
0x51c02  ldc.i4   0x7B5DF6A6
0x51c07  bgt.un.s loc_51C24
0x51c09  ldloc.1
0x51c0a  ldc.i4   0x7A787910
0x51c0f  beq      loc_51D0B
0x51c14  ldloc.1
0x51c15  ldc.i4   0x7B5DF6A6
0x51c1a  beq      loc_51CCC
0x51c1f  br       loc_51EB1
0x51c24  ldloc.1
0x51c25  ldc.i4   0x80D2874B
0x51c2a  beq      loc_51E07
0x51c2f  ldloc.1
0x51c30  ldc.i4   0x946992DC
0x51c35  beq.s    loc_51CA2
0x51c37  ldloc.1
0x51c38  ldc.i4   0x9F56E047
0x51c3d  beq      loc_51DC8
0x51c42  br       loc_51EB1
0x51c47  ldloc.1
0x51c48  ldc.i4   0xC0670678
0x51c4d  bgt.un.s loc_51C6A
0x51c4f  ldloc.1
0x51c50  ldc.i4   0xA6468091
0x51c55  beq      loc_51DF2
0x51c5a  ldloc.1
0x51c5b  ldc.i4   0xC0670678
0x51c60  beq      loc_51D4A
0x51c65  br       loc_51EB1
0x51c6a  ldloc.1
0x51c6b  ldc.i4   0xC09B32FA
0x51c70  beq      loc_51CF6
0x51c75  ldloc.1
0x51c76  ldc.i4   0xCEEE0703
0x51c7b  beq.s    loc_51C8D
0x51c7d  ldloc.1
0x51c7e  ldc.i4   0xF92D43AC
0x51c83  beq      loc_51D5F
0x51c88  br       loc_51EB1
0x51c8d  ldarg.0
0x51c8e  ldstr    aManagedpropert_5// "ManagedProperty"
0x51c93  call     bool [mscorlib]System.String::op_Equality(string, string)
0x51c98  brtrue   loc_51E1C
0x51c9d  br       loc_51EB1
0x51ca2  ldarg.0
0x51ca3  ldstr    aOptionset_0// "OptionSet"
0x51ca8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x51cad  brtrue   loc_51E24
0x51cb2  br       loc_51EB1
0x51cb7  ldarg.0
0x51cb8  ldstr    aAttribute// "Attribute"
0x51cbd  call     bool [mscorlib]System.String::op_Equality(string, string)
0x51cc2  brtrue   loc_51E2C
0x51cc7  br       loc_51EB1
0x51ccc  ldarg.0
0x51ccd  ldstr    aAttributelooku// "AttributeLookupValue"
0x51cd2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x51cd7  brtrue   loc_51E34
0x51cdc  br       loc_51EB1
0x51ce1  ldarg.0
0x51ce2  ldstr    aAttributepickl// "AttributePicklistValue"
0x51ce7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x51cec  brtrue   loc_51E3C
0x51cf1  br       loc_51EB1
0x51cf6  ldarg.0
0x51cf7  ldstr    aEntity_0// "Entity"
0x51cfc  call     bool [mscorlib]System.String::op_Equality(string, string)
0x51d01  brtrue   loc_51E44
0x51d06  br       loc_51EB1
0x51d0b  ldarg.0
0x51d0c  ldstr    aLocalizedlabel// "LocalizedLabel"
0x51d11  call     bool [mscorlib]System.String::op_Equality(string, string)
0x51d16  brtrue   loc_51E4C
0x51d1b  br       loc_51EB1
0x51d20  ldarg.0
0x51d21  ldstr    aRelationship_0// "Relationship"
0x51d26  call     bool [mscorlib]System.String::op_Equality(string, string)
0x51d2b  brtrue   loc_51E54
0x51d30  br       loc_51EB1
0x51d35  ldarg.0
0x51d36  ldstr    aRelationshipex_0// "RelationshipExtraCondition"
0x51d3b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x51d40  brtrue   loc_51E5C
0x51d45  br       loc_51EB1
0x51d4a  ldarg.0
0x51d4b  ldstr    aViewattribute// "ViewAttribute"
0x51d50  call     bool [mscorlib]System.String::op_Equality(string, string)
0x51d55  brtrue   loc_51E64
0x51d5a  br       loc_51EB1
0x51d5f  ldarg.0
0x51d60  ldstr    aPrivilege// "Privilege"
0x51d65  call     bool [mscorlib]System.String::op_Equality(string, string)
0x51d6a  brtrue   loc_51E6C
0x51d6f  br       loc_51EB1
0x51d74  ldarg.0
0x51d75  ldstr    aPrivilegeobjec// "PrivilegeObjectTypeCode"
0x51d7a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x51d7f  brtrue   loc_51E74
0x51d84  br       loc_51EB1
0x51d89  ldarg.0
0x51d8a  ldstr    aRoletemplatepr// "RoleTemplatePrivilege"
0x51d8f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x51d94  brtrue   loc_51E7C
0x51d99  br       loc_51EB1
0x51d9e  ldarg.0
0x51d9f  ldstr    aEntityrelation_0// "EntityRelationship"
0x51da4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x51da9  brtrue   loc_51E84
0x51dae  br       loc_51EB1
0x51db3  ldarg.0
0x51db4  ldstr    aEntityrelation_4// "EntityRelationshipRole"
0x51db9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x51dbe  brtrue   loc_51E8C
0x51dc3  br       loc_51EB1
0x51dc8  ldarg.0
0x51dc9  ldstr    aEntityrelation_6// "EntityRelationshipRelationships"
0x51dce  call     bool [mscorlib]System.String::op_Equality(string, string)
0x51dd3  brtrue   loc_51E94
0x51dd8  br       loc_51EB1
0x51ddd  ldarg.0
0x51dde  ldstr    aOrganization// "Organization"
0x51de3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x51de8  brtrue   loc_51E9C
0x51ded  br       loc_51EB1
0x51df2  ldarg.0
0x51df3  ldstr    aEntitykey_0// "EntityKey"
0x51df8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x51dfd  brtrue   loc_51EA3
0x51e02  br       loc_51EB1
0x51e07  ldarg.0
0x51e08  ldstr    aEntitykeyattri// "EntityKeyAttribute"
0x51e0d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x51e12  brtrue   loc_51EAA
0x51e17  br       loc_51EB1
0x51e1c  ldloc.0
0x51e1d  ldarg.1
0x51e1e  newobj   instance void Microsoft.Crm.Metadata.ManagedPropertyDescriptionPropertyBag::.ctor(class Microsoft.Crm.Metadata.MetadataBusinessEntity managedPropertyData, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x51e23  ret
0x51e24  ldloc.0
0x51e25  ldarg.1
0x51e26  newobj   instance void Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag::.ctor(class Microsoft.Crm.Metadata.MetadataBusinessEntity picklistData, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x51e2b  ret
0x51e2c  ldloc.0
0x51e2d  ldarg.1
0x51e2e  newobj   instance void Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::.ctor(class Microsoft.Crm.Metadata.MetadataBusinessEntity attributeData, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x51e33  ret
0x51e34  ldloc.0
0x51e35  ldarg.1
0x51e36  newobj   instance void Microsoft.Crm.Metadata.AttributeLookupValueDescriptionPropertyBag::.ctor(class Microsoft.Crm.Metadata.MetadataBusinessEntity lookupData, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x51e3b  ret
0x51e3c  ldloc.0
0x51e3d  ldarg.1
0x51e3e  newobj   instance void Microsoft.Crm.Metadata.AttributePicklistValueDescriptionPropertyBag::.ctor(class Microsoft.Crm.Metadata.MetadataBusinessEntity picklistData, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x51e43  ret
0x51e44  ldloc.0
0x51e45  ldarg.1
0x51e46  newobj   instance void Microsoft.Crm.Metadata.EntityDescriptionPropertyBag::.ctor(class Microsoft.Crm.Metadata.MetadataBusinessEntity entityData, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x51e4b  ret
0x51e4c  ldloc.0
0x51e4d  ldarg.1
0x51e4e  newobj   instance void Microsoft.Crm.Metadata.LocalizedLabelDescriptionPropertyBag::.ctor(class Microsoft.Crm.Metadata.MetadataBusinessEntity localizedLabelData, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x51e53  ret
0x51e54  ldloc.0
0x51e55  ldarg.1
0x51e56  newobj   instance void Microsoft.Crm.Metadata.RelationshipDescriptionPropertyBag::.ctor(class Microsoft.Crm.Metadata.MetadataBusinessEntity relationshipData, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x51e5b  ret
0x51e5c  ldloc.0
0x51e5d  ldarg.1
0x51e5e  newobj   instance void Microsoft.Crm.Metadata.RelationshipExtraConditionDescriptionPropertyBag::.ctor(class Microsoft.Crm.Metadata.MetadataBusinessEntity relationshipData, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x51e63  ret
0x51e64  ldloc.0
0x51e65  ldarg.1
0x51e66  newobj   instance void Microsoft.Crm.Metadata.ViewInfoDescriptionPropertyBag::.ctor(class Microsoft.Crm.Metadata.MetadataBusinessEntity viewInfoData, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x51e6b  ret
0x51e6c  ldloc.0
0x51e6d  ldarg.1
0x51e6e  newobj   instance void Microsoft.Crm.Metadata.PrivilegeDescriptionPropertyBag::.ctor(class Microsoft.Crm.Metadata.MetadataBusinessEntity privilegeData, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x51e73  ret
0x51e74  ldloc.0
0x51e75  ldarg.1
0x51e76  newobj   instance void Microsoft.Crm.Metadata.PrivilegeObjectTypeCodeDescriptionPropertyBag::.ctor(class Microsoft.Crm.Metadata.MetadataBusinessEntity privilegeData, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x51e7b  ret
0x51e7c  ldloc.0
0x51e7d  ldarg.1
0x51e7e  newobj   instance void Microsoft.Crm.Metadata.RoleTemplatePrivilegeDescriptionPropertyBag::.ctor(class Microsoft.Crm.Metadata.MetadataBusinessEntity roleTemplatePrivilegeData, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x51e83  ret
0x51e84  ldloc.0
0x51e85  ldarg.1
0x51e86  newobj   instance void Microsoft.Crm.Metadata.EntityRelationshipDescriptionPropertyBag::.ctor(class Microsoft.Crm.Metadata.MetadataBusinessEntity entityRelationshipData, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x51e8b  ret
0x51e8c  ldloc.0
0x51e8d  ldarg.1
0x51e8e  newobj   instance void Microsoft.Crm.Metadata.EntityRelationshipRoleDescriptionPropertyBag::.ctor(class Microsoft.Crm.Metadata.MetadataBusinessEntity entityRelationshipRoleData, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x51e93  ret
0x51e94  ldloc.0
0x51e95  ldarg.1
0x51e96  newobj   instance void Microsoft.Crm.Metadata.EntityRelationshipRelationshipsDescriptionPropertyBag::.ctor(class Microsoft.Crm.Metadata.MetadataBusinessEntity entityRelationshipRelationshipsData, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x51e9b  ret
0x51e9c  ldarg.1
0x51e9d  newobj   instance void Microsoft.Crm.Metadata.OrganizationDescriptionPropertyBag::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x51ea2  ret
0x51ea3  ldarg.1
0x51ea4  newobj   instance void Microsoft.Crm.Metadata.EntityKeyDescriptionPropertyBag::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x51ea9  ret
0x51eaa  ldarg.1
0x51eab  newobj   instance void Microsoft.Crm.Metadata.EntityKeyAttributeDescriptionPropertyBag::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x51eb0  ret
0x51eb1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x51eb6  ldstr    aName0IsNotVali// "Name {0} is not valid for a metadata de"...
0x51ebb  ldc.i4.1
0x51ebc  newarr   [mscorlib]System.Object
0x51ec1  dup
0x51ec2  ldc.i4.0
0x51ec3  ldarg.0
0x51ec4  stelem.ref
0x51ec5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x51eca  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x51ecf  throw
```
