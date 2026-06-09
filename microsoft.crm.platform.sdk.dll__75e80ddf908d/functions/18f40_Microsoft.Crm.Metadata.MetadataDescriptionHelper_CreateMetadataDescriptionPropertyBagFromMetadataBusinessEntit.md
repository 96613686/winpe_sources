# Microsoft.Crm.Metadata.MetadataDescriptionHelper::CreateMetadataDescriptionPropertyBagFromMetadataBusinessEntity

- ea: `0x18f40`
- end: `0x192b7`
- name: `Microsoft.Crm.Metadata.MetadataDescriptionHelper::CreateMetadataDescriptionPropertyBagFromMetadataBusinessEntity`
- size: `887`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0xacfe0`

## callees

- `0x18f40`
- `0x24e60`
- `0x27f50`
- `0x28e30`
- `0x30300`
- `0x34090`
- `0x34d60`
- `0x35ac0`
- `0x364e0`
- `0x376d0`
- `0x38e30`
- `0x39ff0`
- `0x3b060`
- `0x3ba70`
- `0x3cb30`
- `0x3d790`
- `0x3ee90`
- `0x3fde0`
- `0x408a0`
- `0x41360`
- `0x6fe40`
- `0xa94d0`

## string_xrefs

- `0x19191`: `Privilege`
- `0x191a6`: `PrivilegeObjectTypeCode`
- `0x191bb`: `RoleTemplatePrivilege`
- `0x19298`: `Unexpected metadata entity name type {0} in CreateMetadataDescriptionPropertyBagFromMetadataBusinessEntity - either type is not supported or is not defined`

## pseudocode

```c

```

## disassembly

```asm
0x18f40  ldarg.0
0x18f41  callvirt instance string Microsoft.Crm.Metadata.MetadataBusinessEntity::get_MetadataEntityName()
0x18f46  stloc.0
0x18f47  ldloc.0
0x18f48  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x18f4d  stloc.1
0x18f4e  ldloc.1
0x18f4f  ldc.i4   0x6E61547A
0x18f54  bgt.un   loc_18FE8
0x18f59  ldloc.1
0x18f5a  ldc.i4   0x21E27D10
0x18f5f  bgt.un.s loc_18F9F
0x18f61  ldloc.1
0x18f62  ldc.i4   0x1ACCD85B
0x18f67  bgt.un.s loc_18F84
0x18f69  ldloc.1
0x18f6a  ldc.i4   0x1971E30A
0x18f6f  beq      loc_191CF
0x18f74  ldloc.1
0x18f75  ldc.i4   0x1ACCD85B
0x18f7a  beq      loc_1913C
0x18f7f  br       loc_19293
0x18f84  ldloc.1
0x18f85  ldc.i4   0x1D72D1E6
0x18f8a  beq      loc_191BA
0x18f8f  ldloc.1
0x18f90  ldc.i4   0x21E27D10
0x18f95  beq      loc_190FD
0x18f9a  br       loc_19293
0x18f9f  ldloc.1
0x18fa0  ldc.i4   0x3578225F
0x18fa5  bgt.un.s loc_18FC2
0x18fa7  ldloc.1
0x18fa8  ldc.i4   0x2FB17EF0
0x18fad  beq      loc_19151
0x18fb2  ldloc.1
0x18fb3  ldc.i4   0x3578225F
0x18fb8  beq      loc_190A9
0x18fbd  br       loc_19293
0x18fc2  ldloc.1
0x18fc3  ldc.i4   0x4F6B9560
0x18fc8  beq      loc_190D3
0x18fcd  ldloc.1
0x18fce  ldc.i4   0x62FA988F
0x18fd3  beq      loc_1907F
0x18fd8  ldloc.1
0x18fd9  ldc.i4   0x6E61547A
0x18fde  beq      loc_191A5
0x18fe3  br       loc_19293
0x18fe8  ldloc.1
0x18fe9  ldc.i4   0x9F56E047
0x18fee  bgt.un.s loc_19039
0x18ff0  ldloc.1
0x18ff1  ldc.i4   0x7B5DF6A6
0x18ff6  bgt.un.s loc_19013
0x18ff8  ldloc.1
0x18ff9  ldc.i4   0x7A787910
0x18ffe  beq      loc_19112
0x19003  ldloc.1
0x19004  ldc.i4   0x7B5DF6A6
0x19009  beq      loc_19094
0x1900e  br       loc_19293
0x19013  ldloc.1
0x19014  ldc.i4   0x80D2874B
0x19019  beq      loc_191F9
0x1901e  ldloc.1
0x1901f  ldc.i4   0x946992DC
0x19024  beq      loc_19127
0x19029  ldloc.1
0x1902a  ldc.i4   0x9F56E047
0x1902f  beq      loc_190E8
0x19034  br       loc_19293
0x19039  ldloc.1
0x1903a  ldc.i4   0xC0670678
0x1903f  bgt.un.s loc_1905C
0x19041  ldloc.1
0x19042  ldc.i4   0xA6468091
0x19047  beq      loc_191E4
0x1904c  ldloc.1
0x1904d  ldc.i4   0xC0670678
0x19052  beq      loc_19166
0x19057  br       loc_19293
0x1905c  ldloc.1
0x1905d  ldc.i4   0xC09B32FA
0x19062  beq.s    loc_190BE
0x19064  ldloc.1
0x19065  ldc.i4   0xCEEE0703
0x1906a  beq      loc_1917B
0x1906f  ldloc.1
0x19070  ldc.i4   0xF92D43AC
0x19075  beq      loc_19190
0x1907a  br       loc_19293
0x1907f  ldloc.0
0x19080  ldstr    aAttribute// "Attribute"
0x19085  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1908a  brtrue   loc_1920E
0x1908f  br       loc_19293
0x19094  ldloc.0
0x19095  ldstr    aAttributelooku// "AttributeLookupValue"
0x1909a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1909f  brtrue   loc_19215
0x190a4  br       loc_19293
0x190a9  ldloc.0
0x190aa  ldstr    aAttributepickl// "AttributePicklistValue"
0x190af  call     bool [mscorlib]System.String::op_Equality(string, string)
0x190b4  brtrue   loc_1921C
0x190b9  br       loc_19293
0x190be  ldloc.0
0x190bf  ldstr    aEntity_0// "Entity"
0x190c4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x190c9  brtrue   loc_19223
0x190ce  br       loc_19293
0x190d3  ldloc.0
0x190d4  ldstr    aEntityrelation_0// "EntityRelationship"
0x190d9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x190de  brtrue   loc_1922A
0x190e3  br       loc_19293
0x190e8  ldloc.0
0x190e9  ldstr    aEntityrelation_6// "EntityRelationshipRelationships"
0x190ee  call     bool [mscorlib]System.String::op_Equality(string, string)
0x190f3  brtrue   loc_19231
0x190f8  br       loc_19293
0x190fd  ldloc.0
0x190fe  ldstr    aEntityrelation_4// "EntityRelationshipRole"
0x19103  call     bool [mscorlib]System.String::op_Equality(string, string)
0x19108  brtrue   loc_19238
0x1910d  br       loc_19293
0x19112  ldloc.0
0x19113  ldstr    aLocalizedlabel// "LocalizedLabel"
0x19118  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1911d  brtrue   loc_1923F
0x19122  br       loc_19293
0x19127  ldloc.0
0x19128  ldstr    aOptionset_0// "OptionSet"
0x1912d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x19132  brtrue   loc_19246
0x19137  br       loc_19293
0x1913c  ldloc.0
0x1913d  ldstr    aRelationship_0// "Relationship"
0x19142  call     bool [mscorlib]System.String::op_Equality(string, string)
0x19147  brtrue   loc_1924D
0x1914c  br       loc_19293
0x19151  ldloc.0
0x19152  ldstr    aRelationshipex_0// "RelationshipExtraCondition"
0x19157  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1915c  brtrue   loc_19254
0x19161  br       loc_19293
0x19166  ldloc.0
0x19167  ldstr    aViewattribute// "ViewAttribute"
0x1916c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x19171  brtrue   loc_1925B
0x19176  br       loc_19293
0x1917b  ldloc.0
0x1917c  ldstr    aManagedpropert_5// "ManagedProperty"
0x19181  call     bool [mscorlib]System.String::op_Equality(string, string)
0x19186  brtrue   loc_19262
0x1918b  br       loc_19293
0x19190  ldloc.0
0x19191  ldstr    aPrivilege// "Privilege"
0x19196  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1919b  brtrue   loc_19269
0x191a0  br       loc_19293
0x191a5  ldloc.0
0x191a6  ldstr    aPrivilegeobjec// "PrivilegeObjectTypeCode"
0x191ab  call     bool [mscorlib]System.String::op_Equality(string, string)
0x191b0  brtrue   loc_19270
0x191b5  br       loc_19293
0x191ba  ldloc.0
0x191bb  ldstr    aRoletemplatepr// "RoleTemplatePrivilege"
0x191c0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x191c5  brtrue   loc_19277
0x191ca  br       loc_19293
0x191cf  ldloc.0
0x191d0  ldstr    aOrganization// "Organization"
0x191d5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x191da  brtrue   loc_1927E
0x191df  br       loc_19293
0x191e4  ldloc.0
0x191e5  ldstr    aEntitykey_0// "EntityKey"
0x191ea  call     bool [mscorlib]System.String::op_Equality(string, string)
0x191ef  brtrue   loc_19285
0x191f4  br       loc_19293
0x191f9  ldloc.0
0x191fa  ldstr    aEntitykeyattri// "EntityKeyAttribute"
0x191ff  call     bool [mscorlib]System.String::op_Equality(string, string)
0x19204  brtrue   loc_1928C
0x19209  br       loc_19293
0x1920e  ldarg.0
0x1920f  newobj   instance void Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::.ctor(class Microsoft.Crm.Metadata.MetadataBusinessEntity attributeData)
0x19214  ret
0x19215  ldarg.0
0x19216  newobj   instance void Microsoft.Crm.Metadata.AttributeLookupValueDescriptionPropertyBag::.ctor(class Microsoft.Crm.Metadata.MetadataBusinessEntity lookupData)
0x1921b  ret
0x1921c  ldarg.0
0x1921d  newobj   instance void Microsoft.Crm.Metadata.AttributePicklistValueDescriptionPropertyBag::.ctor(class Microsoft.Crm.Metadata.MetadataBusinessEntity picklistData)
0x19222  ret
0x19223  ldarg.0
0x19224  newobj   instance void Microsoft.Crm.Metadata.EntityDescriptionPropertyBag::.ctor(class Microsoft.Crm.Metadata.MetadataBusinessEntity entityData)
0x19229  ret
0x1922a  ldarg.0
0x1922b  newobj   instance void Microsoft.Crm.Metadata.EntityRelationshipDescriptionPropertyBag::.ctor(class Microsoft.Crm.Metadata.MetadataBusinessEntity entityRelationshipData)
0x19230  ret
0x19231  ldarg.0
0x19232  newobj   instance void Microsoft.Crm.Metadata.EntityRelationshipRelationshipsDescriptionPropertyBag::.ctor(class Microsoft.Crm.Metadata.MetadataBusinessEntity entityRelationshipRelationshipsData)
0x19237  ret
0x19238  ldarg.0
0x19239  newobj   instance void Microsoft.Crm.Metadata.EntityRelationshipRoleDescriptionPropertyBag::.ctor(class Microsoft.Crm.Metadata.MetadataBusinessEntity entityRelationshipRoleData)
0x1923e  ret
0x1923f  ldarg.0
0x19240  newobj   instance void Microsoft.Crm.Metadata.LocalizedLabelDescriptionPropertyBag::.ctor(class Microsoft.Crm.Metadata.MetadataBusinessEntity localizedLabelData)
0x19245  ret
0x19246  ldarg.0
0x19247  newobj   instance void Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag::.ctor(class Microsoft.Crm.Metadata.MetadataBusinessEntity picklistData)
0x1924c  ret
0x1924d  ldarg.0
0x1924e  newobj   instance void Microsoft.Crm.Metadata.RelationshipDescriptionPropertyBag::.ctor(class Microsoft.Crm.Metadata.MetadataBusinessEntity relationshipData)
0x19253  ret
0x19254  ldarg.0
0x19255  newobj   instance void Microsoft.Crm.Metadata.RelationshipExtraConditionDescriptionPropertyBag::.ctor(class Microsoft.Crm.Metadata.MetadataBusinessEntity relationshipData)
0x1925a  ret
0x1925b  ldarg.0
0x1925c  newobj   instance void Microsoft.Crm.Metadata.ViewInfoDescriptionPropertyBag::.ctor(class Microsoft.Crm.Metadata.MetadataBusinessEntity viewInfoData)
0x19261  ret
0x19262  ldarg.0
0x19263  newobj   instance void Microsoft.Crm.Metadata.ManagedPropertyDescriptionPropertyBag::.ctor(class Microsoft.Crm.Metadata.MetadataBusinessEntity managedPropertyData)
0x19268  ret
0x19269  ldarg.0
0x1926a  newobj   instance void Microsoft.Crm.Metadata.PrivilegeDescriptionPropertyBag::.ctor(class Microsoft.Crm.Metadata.MetadataBusinessEntity privilegeData)
0x1926f  ret
0x19270  ldarg.0
0x19271  newobj   instance void Microsoft.Crm.Metadata.PrivilegeObjectTypeCodeDescriptionPropertyBag::.ctor(class Microsoft.Crm.Metadata.MetadataBusinessEntity privilegeData)
0x19276  ret
0x19277  ldarg.0
0x19278  newobj   instance void Microsoft.Crm.Metadata.RoleTemplatePrivilegeDescriptionPropertyBag::.ctor(class Microsoft.Crm.Metadata.MetadataBusinessEntity roleTemplatePrivilegeData)
0x1927d  ret
0x1927e  ldarg.0
0x1927f  newobj   instance void Microsoft.Crm.Metadata.OrganizationDescriptionPropertyBag::.ctor(class Microsoft.Crm.Metadata.MetadataBusinessEntity data)
0x19284  ret
0x19285  ldarg.0
0x19286  newobj   instance void Microsoft.Crm.Metadata.EntityKeyDescriptionPropertyBag::.ctor(class Microsoft.Crm.Metadata.MetadataBusinessEntity entityKeyData)
0x1928b  ret
0x1928c  ldarg.0
0x1928d  newobj   instance void Microsoft.Crm.Metadata.EntityKeyAttributeDescriptionPropertyBag::.ctor(class Microsoft.Crm.Metadata.MetadataBusinessEntity entityKeyAttributeData)
0x19292  ret
0x19293  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x19298  ldstr    aUnexpectedMeta// "Unexpected metadata entity name type {0"...
0x1929d  ldc.i4.1
0x1929e  newarr   [mscorlib]System.Object
0x192a3  dup
0x192a4  ldc.i4.0
0x192a5  ldarg.0
0x192a6  callvirt instance string Microsoft.Crm.Metadata.MetadataBusinessEntity::get_MetadataEntityName()
0x192ab  stelem.ref
0x192ac  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x192b1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x192b6  throw
```
