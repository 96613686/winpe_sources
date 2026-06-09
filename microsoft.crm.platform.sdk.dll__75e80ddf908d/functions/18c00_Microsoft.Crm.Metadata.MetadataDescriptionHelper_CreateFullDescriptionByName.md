# Microsoft.Crm.Metadata.MetadataDescriptionHelper::CreateFullDescriptionByName

- ea: `0x18c00`
- end: `0x18f3b`
- name: `Microsoft.Crm.Metadata.MetadataDescriptionHelper::CreateFullDescriptionByName`
- size: `827`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18bb0`

## callees

- `0x18c00`
- `0x23dd0`
- `0x27dd0`
- `0x28ac0`
- `0x2eb20`
- `0x33ef0`
- `0x34ac0`
- `0x35860`
- `0x36360`
- `0x372f0`
- `0x38b10`
- `0x39c80`
- `0x3ade0`
- `0x3b910`
- `0x3c860`
- `0x3d5e0`
- `0x3ea70`
- `0x3fc00`
- `0x41190`
- `0xa94d0`

## string_xrefs

- `0x18dfd`: `Privilege`
- `0x18e12`: `PrivilegeObjectTypeCode`

## pseudocode

```c

```

## disassembly

```asm
0x18c00  ldarg.0
0x18c01  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x18c06  stloc.0
0x18c07  ldloc.0
0x18c08  ldc.i4   0x7A787910
0x18c0d  bgt.un   loc_18CA1
0x18c12  ldloc.0
0x18c13  ldc.i4   0x2FB17EF0
0x18c18  bgt.un.s loc_18C58
0x18c1a  ldloc.0
0x18c1b  ldc.i4   0x1ACCD85B
0x18c20  bgt.un.s loc_18C3D
0x18c22  ldloc.0
0x18c23  ldc.i4   0x1971E30A
0x18c28  beq      loc_18E65
0x18c2d  ldloc.0
0x18c2e  ldc.i4   0x1ACCD85B
0x18c33  beq      loc_18DBD
0x18c38  br       loc_18F1C
0x18c3d  ldloc.0
0x18c3e  ldc.i4   0x21E27D10
0x18c43  beq      loc_18E3B
0x18c48  ldloc.0
0x18c49  ldc.i4   0x2FB17EF0
0x18c4e  beq      loc_18DD2
0x18c53  br       loc_18F1C
0x18c58  ldloc.0
0x18c59  ldc.i4   0x4F6B9560
0x18c5e  bgt.un.s loc_18C7B
0x18c60  ldloc.0
0x18c61  ldc.i4   0x3578225F
0x18c66  beq      loc_18D7E
0x18c6b  ldloc.0
0x18c6c  ldc.i4   0x4F6B9560
0x18c71  beq      loc_18E26
0x18c76  br       loc_18F1C
0x18c7b  ldloc.0
0x18c7c  ldc.i4   0x62FA988F
0x18c81  beq      loc_18D54
0x18c86  ldloc.0
0x18c87  ldc.i4   0x6E61547A
0x18c8c  beq      loc_18E11
0x18c91  ldloc.0
0x18c92  ldc.i4   0x7A787910
0x18c97  beq      loc_18DA8
0x18c9c  br       loc_18F1C
0x18ca1  ldloc.0
0x18ca2  ldc.i4   0x9F56E047
0x18ca7  bgt.un.s loc_18CE4
0x18ca9  ldloc.0
0x18caa  ldc.i4   0x80D2874B
0x18caf  bgt.un.s loc_18CCC
0x18cb1  ldloc.0
0x18cb2  ldc.i4   0x7B5DF6A6
0x18cb7  beq      loc_18D69
0x18cbc  ldloc.0
0x18cbd  ldc.i4   0x80D2874B
0x18cc2  beq      loc_18E8F
0x18cc7  br       loc_18F1C
0x18ccc  ldloc.0
0x18ccd  ldc.i4   0x946992DC
0x18cd2  beq.s    loc_18D3F
0x18cd4  ldloc.0
0x18cd5  ldc.i4   0x9F56E047
0x18cda  beq      loc_18E50
0x18cdf  br       loc_18F1C
0x18ce4  ldloc.0
0x18ce5  ldc.i4   0xC0670678
0x18cea  bgt.un.s loc_18D07
0x18cec  ldloc.0
0x18ced  ldc.i4   0xA6468091
0x18cf2  beq      loc_18E7A
0x18cf7  ldloc.0
0x18cf8  ldc.i4   0xC0670678
0x18cfd  beq      loc_18DE7
0x18d02  br       loc_18F1C
0x18d07  ldloc.0
0x18d08  ldc.i4   0xC09B32FA
0x18d0d  beq      loc_18D93
0x18d12  ldloc.0
0x18d13  ldc.i4   0xCEEE0703
0x18d18  beq.s    loc_18D2A
0x18d1a  ldloc.0
0x18d1b  ldc.i4   0xF92D43AC
0x18d20  beq      loc_18DFC
0x18d25  br       loc_18F1C
0x18d2a  ldarg.0
0x18d2b  ldstr    aManagedpropert_5// "ManagedProperty"
0x18d30  call     bool [mscorlib]System.String::op_Equality(string, string)
0x18d35  brtrue   loc_18E9E
0x18d3a  br       loc_18F1C
0x18d3f  ldarg.0
0x18d40  ldstr    aOptionset_0// "OptionSet"
0x18d45  call     bool [mscorlib]System.String::op_Equality(string, string)
0x18d4a  brtrue   loc_18EA5
0x18d4f  br       loc_18F1C
0x18d54  ldarg.0
0x18d55  ldstr    aAttribute// "Attribute"
0x18d5a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x18d5f  brtrue   loc_18EAC
0x18d64  br       loc_18F1C
0x18d69  ldarg.0
0x18d6a  ldstr    aAttributelooku// "AttributeLookupValue"
0x18d6f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x18d74  brtrue   loc_18EB3
0x18d79  br       loc_18F1C
0x18d7e  ldarg.0
0x18d7f  ldstr    aAttributepickl// "AttributePicklistValue"
0x18d84  call     bool [mscorlib]System.String::op_Equality(string, string)
0x18d89  brtrue   loc_18EBA
0x18d8e  br       loc_18F1C
0x18d93  ldarg.0
0x18d94  ldstr    aEntity_0// "Entity"
0x18d99  call     bool [mscorlib]System.String::op_Equality(string, string)
0x18d9e  brtrue   loc_18EC1
0x18da3  br       loc_18F1C
0x18da8  ldarg.0
0x18da9  ldstr    aLocalizedlabel// "LocalizedLabel"
0x18dae  call     bool [mscorlib]System.String::op_Equality(string, string)
0x18db3  brtrue   loc_18EC8
0x18db8  br       loc_18F1C
0x18dbd  ldarg.0
0x18dbe  ldstr    aRelationship_0// "Relationship"
0x18dc3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x18dc8  brtrue   loc_18ECF
0x18dcd  br       loc_18F1C
0x18dd2  ldarg.0
0x18dd3  ldstr    aRelationshipex_0// "RelationshipExtraCondition"
0x18dd8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x18ddd  brtrue   loc_18ED6
0x18de2  br       loc_18F1C
0x18de7  ldarg.0
0x18de8  ldstr    aViewattribute// "ViewAttribute"
0x18ded  call     bool [mscorlib]System.String::op_Equality(string, string)
0x18df2  brtrue   loc_18EDD
0x18df7  br       loc_18F1C
0x18dfc  ldarg.0
0x18dfd  ldstr    aPrivilege// "Privilege"
0x18e02  call     bool [mscorlib]System.String::op_Equality(string, string)
0x18e07  brtrue   loc_18EE4
0x18e0c  br       loc_18F1C
0x18e11  ldarg.0
0x18e12  ldstr    aPrivilegeobjec// "PrivilegeObjectTypeCode"
0x18e17  call     bool [mscorlib]System.String::op_Equality(string, string)
0x18e1c  brtrue   loc_18EEB
0x18e21  br       loc_18F1C
0x18e26  ldarg.0
0x18e27  ldstr    aEntityrelation_0// "EntityRelationship"
0x18e2c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x18e31  brtrue   loc_18EF2
0x18e36  br       loc_18F1C
0x18e3b  ldarg.0
0x18e3c  ldstr    aEntityrelation_4// "EntityRelationshipRole"
0x18e41  call     bool [mscorlib]System.String::op_Equality(string, string)
0x18e46  brtrue   loc_18EF9
0x18e4b  br       loc_18F1C
0x18e50  ldarg.0
0x18e51  ldstr    aEntityrelation_6// "EntityRelationshipRelationships"
0x18e56  call     bool [mscorlib]System.String::op_Equality(string, string)
0x18e5b  brtrue   loc_18F00
0x18e60  br       loc_18F1C
0x18e65  ldarg.0
0x18e66  ldstr    aOrganization// "Organization"
0x18e6b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x18e70  brtrue   loc_18F07
0x18e75  br       loc_18F1C
0x18e7a  ldarg.0
0x18e7b  ldstr    aEntitykey_0// "EntityKey"
0x18e80  call     bool [mscorlib]System.String::op_Equality(string, string)
0x18e85  brtrue   loc_18F0E
0x18e8a  br       loc_18F1C
0x18e8f  ldarg.0
0x18e90  ldstr    aEntitykeyattri// "EntityKeyAttribute"
0x18e95  call     bool [mscorlib]System.String::op_Equality(string, string)
0x18e9a  brtrue.s loc_18F15
0x18e9c  br.s     loc_18F1C
0x18e9e  ldarg.1
0x18e9f  newobj   instance void Microsoft.Crm.Metadata.ManagedPropertyDescriptionFull::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext organizationContext)
0x18ea4  ret
0x18ea5  ldarg.1
0x18ea6  newobj   instance void Microsoft.Crm.Metadata.OptionSetDescriptionFull::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext organizationContext)
0x18eab  ret
0x18eac  ldarg.1
0x18ead  newobj   instance void Microsoft.Crm.Metadata.AttributeDescriptionFull::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext organizationContext)
0x18eb2  ret
0x18eb3  ldarg.1
0x18eb4  newobj   instance void Microsoft.Crm.Metadata.AttributeLookupValueDescriptionFull::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext organizationContext)
0x18eb9  ret
0x18eba  ldarg.1
0x18ebb  newobj   instance void Microsoft.Crm.Metadata.AttributePicklistValueDescriptionFull::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext organizationContext)
0x18ec0  ret
0x18ec1  ldarg.1
0x18ec2  newobj   instance void Microsoft.Crm.Metadata.EntityDescriptionFull::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext organizationContext)
0x18ec7  ret
0x18ec8  ldarg.1
0x18ec9  newobj   instance void Microsoft.Crm.Metadata.LocalizedLabelDescriptionFull::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext organizationContext)
0x18ece  ret
0x18ecf  ldarg.1
0x18ed0  newobj   instance void Microsoft.Crm.Metadata.RelationshipDescriptionFull::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext organizationContext)
0x18ed5  ret
0x18ed6  ldarg.1
0x18ed7  newobj   instance void Microsoft.Crm.Metadata.RelationshipExtraConditionDescriptionFull::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext organizationContext)
0x18edc  ret
0x18edd  ldarg.1
0x18ede  newobj   instance void Microsoft.Crm.Metadata.ViewInfoDescriptionFull::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext organizationContext)
0x18ee3  ret
0x18ee4  ldarg.1
0x18ee5  newobj   instance void Microsoft.Crm.Metadata.PrivilegeDescriptionFull::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext organizationContext)
0x18eea  ret
0x18eeb  ldarg.1
0x18eec  newobj   instance void Microsoft.Crm.Metadata.PrivilegeObjectTypeCodeDescriptionFull::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext organizationContext)
0x18ef1  ret
0x18ef2  ldarg.1
0x18ef3  newobj   instance void Microsoft.Crm.Metadata.EntityRelationshipDescriptionFull::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext organizationContext)
0x18ef8  ret
0x18ef9  ldarg.1
0x18efa  newobj   instance void Microsoft.Crm.Metadata.EntityRelationshipRoleDescriptionFull::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext organizationContext)
0x18eff  ret
0x18f00  ldarg.1
0x18f01  newobj   instance void Microsoft.Crm.Metadata.EntityRelationshipRelationshipsDescriptionFull::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext organizationContext)
0x18f06  ret
0x18f07  ldarg.1
0x18f08  newobj   instance void Microsoft.Crm.Metadata.OrganizationDescriptionFull::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext organizationContext)
0x18f0d  ret
0x18f0e  ldarg.1
0x18f0f  newobj   instance void Microsoft.Crm.Metadata.EntityKeyDescriptionFull::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext organizationContext)
0x18f14  ret
0x18f15  ldarg.1
0x18f16  newobj   instance void Microsoft.Crm.Metadata.EntityKeyAttributeDescriptionFull::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext organizationContext)
0x18f1b  ret
0x18f1c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18f21  ldstr    aName0IsNotVali// "Name {0} is not valid for a metadata de"...
0x18f26  ldc.i4.1
0x18f27  newarr   [mscorlib]System.Object
0x18f2c  dup
0x18f2d  ldc.i4.0
0x18f2e  ldarg.0
0x18f2f  stelem.ref
0x18f30  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x18f35  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x18f3a  throw
```
