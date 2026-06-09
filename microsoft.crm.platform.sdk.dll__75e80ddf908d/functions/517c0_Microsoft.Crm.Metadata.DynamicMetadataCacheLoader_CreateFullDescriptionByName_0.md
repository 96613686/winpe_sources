# Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::CreateFullDescriptionByName_0

- ea: `0x517c0`
- end: `0x51afb`
- name: `Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::CreateFullDescriptionByName_0`
- size: `827`
- prototype: ``
- caller_count: `3`
- callee_count: `20`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x517b0`
- `0x5b660`
- `0x5d5e0`

## callees

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
- `0x517c0`
- `0xa94d0`

## string_xrefs

- `0x519bd`: `Privilege`
- `0x519d2`: `PrivilegeObjectTypeCode`

## pseudocode

```c

```

## disassembly

```asm
0x517c0  ldarg.0
0x517c1  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x517c6  stloc.0
0x517c7  ldloc.0
0x517c8  ldc.i4   0x7A787910
0x517cd  bgt.un   loc_51861
0x517d2  ldloc.0
0x517d3  ldc.i4   0x2FB17EF0
0x517d8  bgt.un.s loc_51818
0x517da  ldloc.0
0x517db  ldc.i4   0x1ACCD85B
0x517e0  bgt.un.s loc_517FD
0x517e2  ldloc.0
0x517e3  ldc.i4   0x1971E30A
0x517e8  beq      loc_51A25
0x517ed  ldloc.0
0x517ee  ldc.i4   0x1ACCD85B
0x517f3  beq      loc_5197D
0x517f8  br       loc_51ADC
0x517fd  ldloc.0
0x517fe  ldc.i4   0x21E27D10
0x51803  beq      loc_519FB
0x51808  ldloc.0
0x51809  ldc.i4   0x2FB17EF0
0x5180e  beq      loc_51992
0x51813  br       loc_51ADC
0x51818  ldloc.0
0x51819  ldc.i4   0x4F6B9560
0x5181e  bgt.un.s loc_5183B
0x51820  ldloc.0
0x51821  ldc.i4   0x3578225F
0x51826  beq      loc_5193E
0x5182b  ldloc.0
0x5182c  ldc.i4   0x4F6B9560
0x51831  beq      loc_519E6
0x51836  br       loc_51ADC
0x5183b  ldloc.0
0x5183c  ldc.i4   0x62FA988F
0x51841  beq      loc_51914
0x51846  ldloc.0
0x51847  ldc.i4   0x6E61547A
0x5184c  beq      loc_519D1
0x51851  ldloc.0
0x51852  ldc.i4   0x7A787910
0x51857  beq      loc_51968
0x5185c  br       loc_51ADC
0x51861  ldloc.0
0x51862  ldc.i4   0x9F56E047
0x51867  bgt.un.s loc_518A4
0x51869  ldloc.0
0x5186a  ldc.i4   0x80D2874B
0x5186f  bgt.un.s loc_5188C
0x51871  ldloc.0
0x51872  ldc.i4   0x7B5DF6A6
0x51877  beq      loc_51929
0x5187c  ldloc.0
0x5187d  ldc.i4   0x80D2874B
0x51882  beq      loc_51A4F
0x51887  br       loc_51ADC
0x5188c  ldloc.0
0x5188d  ldc.i4   0x946992DC
0x51892  beq.s    loc_518FF
0x51894  ldloc.0
0x51895  ldc.i4   0x9F56E047
0x5189a  beq      loc_51A10
0x5189f  br       loc_51ADC
0x518a4  ldloc.0
0x518a5  ldc.i4   0xC0670678
0x518aa  bgt.un.s loc_518C7
0x518ac  ldloc.0
0x518ad  ldc.i4   0xA6468091
0x518b2  beq      loc_51A3A
0x518b7  ldloc.0
0x518b8  ldc.i4   0xC0670678
0x518bd  beq      loc_519A7
0x518c2  br       loc_51ADC
0x518c7  ldloc.0
0x518c8  ldc.i4   0xC09B32FA
0x518cd  beq      loc_51953
0x518d2  ldloc.0
0x518d3  ldc.i4   0xCEEE0703
0x518d8  beq.s    loc_518EA
0x518da  ldloc.0
0x518db  ldc.i4   0xF92D43AC
0x518e0  beq      loc_519BC
0x518e5  br       loc_51ADC
0x518ea  ldarg.0
0x518eb  ldstr    aManagedpropert_5// "ManagedProperty"
0x518f0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x518f5  brtrue   loc_51A5E
0x518fa  br       loc_51ADC
0x518ff  ldarg.0
0x51900  ldstr    aOptionset_0// "OptionSet"
0x51905  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5190a  brtrue   loc_51A65
0x5190f  br       loc_51ADC
0x51914  ldarg.0
0x51915  ldstr    aAttribute// "Attribute"
0x5191a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5191f  brtrue   loc_51A6C
0x51924  br       loc_51ADC
0x51929  ldarg.0
0x5192a  ldstr    aAttributelooku// "AttributeLookupValue"
0x5192f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x51934  brtrue   loc_51A73
0x51939  br       loc_51ADC
0x5193e  ldarg.0
0x5193f  ldstr    aAttributepickl// "AttributePicklistValue"
0x51944  call     bool [mscorlib]System.String::op_Equality(string, string)
0x51949  brtrue   loc_51A7A
0x5194e  br       loc_51ADC
0x51953  ldarg.0
0x51954  ldstr    aEntity_0// "Entity"
0x51959  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5195e  brtrue   loc_51A81
0x51963  br       loc_51ADC
0x51968  ldarg.0
0x51969  ldstr    aLocalizedlabel// "LocalizedLabel"
0x5196e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x51973  brtrue   loc_51A88
0x51978  br       loc_51ADC
0x5197d  ldarg.0
0x5197e  ldstr    aRelationship_0// "Relationship"
0x51983  call     bool [mscorlib]System.String::op_Equality(string, string)
0x51988  brtrue   loc_51A8F
0x5198d  br       loc_51ADC
0x51992  ldarg.0
0x51993  ldstr    aRelationshipex_0// "RelationshipExtraCondition"
0x51998  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5199d  brtrue   loc_51A96
0x519a2  br       loc_51ADC
0x519a7  ldarg.0
0x519a8  ldstr    aViewattribute// "ViewAttribute"
0x519ad  call     bool [mscorlib]System.String::op_Equality(string, string)
0x519b2  brtrue   loc_51A9D
0x519b7  br       loc_51ADC
0x519bc  ldarg.0
0x519bd  ldstr    aPrivilege// "Privilege"
0x519c2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x519c7  brtrue   loc_51AA4
0x519cc  br       loc_51ADC
0x519d1  ldarg.0
0x519d2  ldstr    aPrivilegeobjec// "PrivilegeObjectTypeCode"
0x519d7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x519dc  brtrue   loc_51AAB
0x519e1  br       loc_51ADC
0x519e6  ldarg.0
0x519e7  ldstr    aEntityrelation_0// "EntityRelationship"
0x519ec  call     bool [mscorlib]System.String::op_Equality(string, string)
0x519f1  brtrue   loc_51AB2
0x519f6  br       loc_51ADC
0x519fb  ldarg.0
0x519fc  ldstr    aEntityrelation_4// "EntityRelationshipRole"
0x51a01  call     bool [mscorlib]System.String::op_Equality(string, string)
0x51a06  brtrue   loc_51AB9
0x51a0b  br       loc_51ADC
0x51a10  ldarg.0
0x51a11  ldstr    aEntityrelation_6// "EntityRelationshipRelationships"
0x51a16  call     bool [mscorlib]System.String::op_Equality(string, string)
0x51a1b  brtrue   loc_51AC0
0x51a20  br       loc_51ADC
0x51a25  ldarg.0
0x51a26  ldstr    aOrganization// "Organization"
0x51a2b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x51a30  brtrue   loc_51AC7
0x51a35  br       loc_51ADC
0x51a3a  ldarg.0
0x51a3b  ldstr    aEntitykey_0// "EntityKey"
0x51a40  call     bool [mscorlib]System.String::op_Equality(string, string)
0x51a45  brtrue   loc_51ACE
0x51a4a  br       loc_51ADC
0x51a4f  ldarg.0
0x51a50  ldstr    aEntitykeyattri// "EntityKeyAttribute"
0x51a55  call     bool [mscorlib]System.String::op_Equality(string, string)
0x51a5a  brtrue.s loc_51AD5
0x51a5c  br.s     loc_51ADC
0x51a5e  ldarg.1
0x51a5f  newobj   instance void Microsoft.Crm.Metadata.ManagedPropertyDescriptionFull::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext organizationContext)
0x51a64  ret
0x51a65  ldarg.1
0x51a66  newobj   instance void Microsoft.Crm.Metadata.OptionSetDescriptionFull::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext organizationContext)
0x51a6b  ret
0x51a6c  ldarg.1
0x51a6d  newobj   instance void Microsoft.Crm.Metadata.AttributeDescriptionFull::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext organizationContext)
0x51a72  ret
0x51a73  ldarg.1
0x51a74  newobj   instance void Microsoft.Crm.Metadata.AttributeLookupValueDescriptionFull::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext organizationContext)
0x51a79  ret
0x51a7a  ldarg.1
0x51a7b  newobj   instance void Microsoft.Crm.Metadata.AttributePicklistValueDescriptionFull::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext organizationContext)
0x51a80  ret
0x51a81  ldarg.1
0x51a82  newobj   instance void Microsoft.Crm.Metadata.EntityDescriptionFull::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext organizationContext)
0x51a87  ret
0x51a88  ldarg.1
0x51a89  newobj   instance void Microsoft.Crm.Metadata.LocalizedLabelDescriptionFull::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext organizationContext)
0x51a8e  ret
0x51a8f  ldarg.1
0x51a90  newobj   instance void Microsoft.Crm.Metadata.RelationshipDescriptionFull::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext organizationContext)
0x51a95  ret
0x51a96  ldarg.1
0x51a97  newobj   instance void Microsoft.Crm.Metadata.RelationshipExtraConditionDescriptionFull::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext organizationContext)
0x51a9c  ret
0x51a9d  ldarg.1
0x51a9e  newobj   instance void Microsoft.Crm.Metadata.ViewInfoDescriptionFull::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext organizationContext)
0x51aa3  ret
0x51aa4  ldarg.1
0x51aa5  newobj   instance void Microsoft.Crm.Metadata.PrivilegeDescriptionFull::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext organizationContext)
0x51aaa  ret
0x51aab  ldarg.1
0x51aac  newobj   instance void Microsoft.Crm.Metadata.PrivilegeObjectTypeCodeDescriptionFull::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext organizationContext)
0x51ab1  ret
0x51ab2  ldarg.1
0x51ab3  newobj   instance void Microsoft.Crm.Metadata.EntityRelationshipDescriptionFull::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext organizationContext)
0x51ab8  ret
0x51ab9  ldarg.1
0x51aba  newobj   instance void Microsoft.Crm.Metadata.EntityRelationshipRoleDescriptionFull::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext organizationContext)
0x51abf  ret
0x51ac0  ldarg.1
0x51ac1  newobj   instance void Microsoft.Crm.Metadata.EntityRelationshipRelationshipsDescriptionFull::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext organizationContext)
0x51ac6  ret
0x51ac7  ldarg.1
0x51ac8  newobj   instance void Microsoft.Crm.Metadata.OrganizationDescriptionFull::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext organizationContext)
0x51acd  ret
0x51ace  ldarg.1
0x51acf  newobj   instance void Microsoft.Crm.Metadata.EntityKeyDescriptionFull::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext organizationContext)
0x51ad4  ret
0x51ad5  ldarg.1
0x51ad6  newobj   instance void Microsoft.Crm.Metadata.EntityKeyAttributeDescriptionFull::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext organizationContext)
0x51adb  ret
0x51adc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x51ae1  ldstr    aName0IsNotVali// "Name {0} is not valid for a metadata de"...
0x51ae6  ldc.i4.1
0x51ae7  newarr   [mscorlib]System.Object
0x51aec  dup
0x51aed  ldc.i4.0
0x51aee  ldarg.0
0x51aef  stelem.ref
0x51af0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x51af5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x51afa  throw
```
