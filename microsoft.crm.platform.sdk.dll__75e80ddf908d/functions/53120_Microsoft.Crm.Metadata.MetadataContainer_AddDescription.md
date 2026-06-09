# Microsoft.Crm.Metadata.MetadataContainer::AddDescription

- ea: `0x53120`
- end: `0x53505`
- name: `Microsoft.Crm.Metadata.MetadataContainer::AddDescription`
- size: `997`
- prototype: ``
- caller_count: `4`
- callee_count: `20`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x5afe0`
- `0x5cb70`
- `0xac0e0`
- `0xac7e0`

## callees

- `0x293d0`
- `0x53120`
- `0x53820`
- `0x53840`
- `0x53860`
- `0x53880`
- `0x538a0`
- `0x538c0`
- `0x538e0`
- `0x53920`
- `0x53960`
- `0x539a0`
- `0x53a10`
- `0x53a30`
- `0x53a50`
- `0x53a70`
- `0x53a90`
- `0x53ab0`
- `0x53ad0`
- `0xa94d0`

## string_xrefs

- `0x5330d`: `PrivilegeObjectTypeCode`
- `0x53322`: `RoleTemplatePrivilege`

## pseudocode

```c

```

## disassembly

```asm
0x53120  ldarg.2
0x53121  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x53126  stloc.0
0x53127  ldloc.0
0x53128  ldc.i4   0x6E61547A
0x5312d  bgt.un   loc_531B6
0x53132  ldloc.0
0x53133  ldc.i4   0x2FB17EF0
0x53138  bgt.un.s loc_53178
0x5313a  ldloc.0
0x5313b  ldc.i4   0x1D72D1E6
0x53140  bgt.un.s loc_5315D
0x53142  ldloc.0
0x53143  ldc.i4   0x1ACCD85B
0x53148  beq      loc_532CD
0x5314d  ldloc.0
0x5314e  ldc.i4   0x1D72D1E6
0x53153  beq      loc_53321
0x53158  br       loc_534B4
0x5315d  ldloc.0
0x5315e  ldc.i4   0x21E27D10
0x53163  beq      loc_5334B
0x53168  ldloc.0
0x53169  ldc.i4   0x2FB17EF0
0x5316e  beq      loc_532E2
0x53173  br       loc_534B4
0x53178  ldloc.0
0x53179  ldc.i4   0x4F6B9560
0x5317e  bgt.un.s loc_5319B
0x53180  ldloc.0
0x53181  ldc.i4   0x3578225F
0x53186  beq      loc_5328E
0x5318b  ldloc.0
0x5318c  ldc.i4   0x4F6B9560
0x53191  beq      loc_53336
0x53196  br       loc_534B4
0x5319b  ldloc.0
0x5319c  ldc.i4   0x62FA988F
0x531a1  beq      loc_53264
0x531a6  ldloc.0
0x531a7  ldc.i4   0x6E61547A
0x531ac  beq      loc_5330C
0x531b1  br       loc_534B4
0x531b6  ldloc.0
0x531b7  ldc.i4   0x946992DC
0x531bc  bgt.un.s loc_531F9
0x531be  ldloc.0
0x531bf  ldc.i4   0x7B5DF6A6
0x531c4  bgt.un.s loc_531E1
0x531c6  ldloc.0
0x531c7  ldc.i4   0x7A787910
0x531cc  beq      loc_532B8
0x531d1  ldloc.0
0x531d2  ldc.i4   0x7B5DF6A6
0x531d7  beq      loc_53279
0x531dc  br       loc_534B4
0x531e1  ldloc.0
0x531e2  ldc.i4   0x80D2874B
0x531e7  beq      loc_5338A
0x531ec  ldloc.0
0x531ed  ldc.i4   0x946992DC
0x531f2  beq.s    loc_5324F
0x531f4  br       loc_534B4
0x531f9  ldloc.0
0x531fa  ldc.i4   0xA6468091
0x531ff  bgt.un.s loc_5321C
0x53201  ldloc.0
0x53202  ldc.i4   0x9F56E047
0x53207  beq      loc_53360
0x5320c  ldloc.0
0x5320d  ldc.i4   0xA6468091
0x53212  beq      loc_53375
0x53217  br       loc_534B4
0x5321c  ldloc.0
0x5321d  ldc.i4   0xC0670678
0x53222  beq      loc_532F7
0x53227  ldloc.0
0x53228  ldc.i4   0xC09B32FA
0x5322d  beq.s    loc_532A3
0x5322f  ldloc.0
0x53230  ldc.i4   0xCEEE0703
0x53235  bne.un   loc_534B4
0x5323a  ldarg.2
0x5323b  ldstr    aManagedpropert_5// "ManagedProperty"
0x53240  call     bool [mscorlib]System.String::op_Equality(string, string)
0x53245  brtrue   loc_5339F
0x5324a  br       loc_534B4
0x5324f  ldarg.2
0x53250  ldstr    aOptionset_0// "OptionSet"
0x53255  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5325a  brtrue   loc_533B0
0x5325f  br       loc_534B4
0x53264  ldarg.2
0x53265  ldstr    aAttribute// "Attribute"
0x5326a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5326f  brtrue   loc_533C1
0x53274  br       loc_534B4
0x53279  ldarg.2
0x5327a  ldstr    aAttributelooku// "AttributeLookupValue"
0x5327f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x53284  brtrue   loc_533D2
0x53289  br       loc_534B4
0x5328e  ldarg.2
0x5328f  ldstr    aAttributepickl// "AttributePicklistValue"
0x53294  call     bool [mscorlib]System.String::op_Equality(string, string)
0x53299  brtrue   loc_533E3
0x5329e  br       loc_534B4
0x532a3  ldarg.2
0x532a4  ldstr    aEntity_0// "Entity"
0x532a9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x532ae  brtrue   loc_533F4
0x532b3  br       loc_534B4
0x532b8  ldarg.2
0x532b9  ldstr    aLocalizedlabel// "LocalizedLabel"
0x532be  call     bool [mscorlib]System.String::op_Equality(string, string)
0x532c3  brtrue   loc_53405
0x532c8  br       loc_534B4
0x532cd  ldarg.2
0x532ce  ldstr    aRelationship_0// "Relationship"
0x532d3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x532d8  brtrue   loc_53416
0x532dd  br       loc_534B4
0x532e2  ldarg.2
0x532e3  ldstr    aRelationshipex_0// "RelationshipExtraCondition"
0x532e8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x532ed  brtrue   loc_53427
0x532f2  br       loc_534B4
0x532f7  ldarg.2
0x532f8  ldstr    aViewattribute// "ViewAttribute"
0x532fd  call     bool [mscorlib]System.String::op_Equality(string, string)
0x53302  brtrue   loc_53438
0x53307  br       loc_534B4
0x5330c  ldarg.2
0x5330d  ldstr    aPrivilegeobjec// "PrivilegeObjectTypeCode"
0x53312  call     bool [mscorlib]System.String::op_Equality(string, string)
0x53317  brtrue   loc_53449
0x5331c  br       loc_534B4
0x53321  ldarg.2
0x53322  ldstr    aRoletemplatepr// "RoleTemplatePrivilege"
0x53327  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5332c  brtrue   loc_5345A
0x53331  br       loc_534B4
0x53336  ldarg.2
0x53337  ldstr    aEntityrelation_0// "EntityRelationship"
0x5333c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x53341  brtrue   loc_5346B
0x53346  br       loc_534B4
0x5334b  ldarg.2
0x5334c  ldstr    aEntityrelation_4// "EntityRelationshipRole"
0x53351  call     bool [mscorlib]System.String::op_Equality(string, string)
0x53356  brtrue   loc_5347C
0x5335b  br       loc_534B4
0x53360  ldarg.2
0x53361  ldstr    aEntityrelation_6// "EntityRelationshipRelationships"
0x53366  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5336b  brtrue   loc_5348A
0x53370  br       loc_534B4
0x53375  ldarg.2
0x53376  ldstr    aEntitykey_0// "EntityKey"
0x5337b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x53380  brtrue   loc_53498
0x53385  br       loc_534B4
0x5338a  ldarg.2
0x5338b  ldstr    aEntitykeyattri// "EntityKeyAttribute"
0x53390  call     bool [mscorlib]System.String::op_Equality(string, string)
0x53395  brtrue   loc_534A6
0x5339a  br       loc_534B4
0x5339f  ldarg.0
0x533a0  ldarg.1
0x533a1  isinst   Microsoft.Crm.Metadata.IManagedPropertyDescription
0x533a6  call     instance void Microsoft.Crm.Metadata.MetadataContainer::AddManagedProperty(class Microsoft.Crm.Metadata.IManagedPropertyDescription managedProperty)
0x533ab  leave    loc_53504
0x533b0  ldarg.0
0x533b1  ldarg.1
0x533b2  isinst   Microsoft.Crm.Metadata.IOptionSetDescription
0x533b7  call     instance void Microsoft.Crm.Metadata.MetadataContainer::AddOptionSet(class Microsoft.Crm.Metadata.IOptionSetDescription optionSet)
0x533bc  leave    loc_53504
0x533c1  ldarg.0
0x533c2  ldarg.1
0x533c3  isinst   Microsoft.Crm.Metadata.IAttributeDescription
0x533c8  call     instance void Microsoft.Crm.Metadata.MetadataContainer::AddAttribute(class Microsoft.Crm.Metadata.IAttributeDescription attribute)
0x533cd  leave    loc_53504
0x533d2  ldarg.0
0x533d3  ldarg.1
0x533d4  isinst   Microsoft.Crm.Metadata.IAttributeLookupValueDescription
0x533d9  call     instance void Microsoft.Crm.Metadata.MetadataContainer::AddAttributeLookupValue(class Microsoft.Crm.Metadata.IAttributeLookupValueDescription lookupValue)
0x533de  leave    loc_53504
0x533e3  ldarg.0
0x533e4  ldarg.1
0x533e5  isinst   Microsoft.Crm.Metadata.IAttributePicklistValueDescription
0x533ea  call     instance void Microsoft.Crm.Metadata.MetadataContainer::AddAttributePicklistValue(class Microsoft.Crm.Metadata.IAttributePicklistValueDescription picklistValue)
0x533ef  leave    loc_53504
0x533f4  ldarg.0
0x533f5  ldarg.1
0x533f6  isinst   Microsoft.Crm.Metadata.IEntityDescription
0x533fb  call     instance void Microsoft.Crm.Metadata.MetadataContainer::AddEntity(class Microsoft.Crm.Metadata.IEntityDescription entity)
0x53400  leave    loc_53504
0x53405  ldarg.0
0x53406  ldarg.1
0x53407  isinst   Microsoft.Crm.Metadata.ILocalizedLabelDescription
0x5340c  call     instance void Microsoft.Crm.Metadata.MetadataContainer::AddLocalizedLabel(class Microsoft.Crm.Metadata.ILocalizedLabelDescription localizedLabel)
0x53411  leave    loc_53504
0x53416  ldarg.0
0x53417  ldarg.1
0x53418  isinst   Microsoft.Crm.Metadata.IRelationshipDescription
0x5341d  call     instance void Microsoft.Crm.Metadata.MetadataContainer::AddRelationship(class Microsoft.Crm.Metadata.IRelationshipDescription relationship)
0x53422  leave    loc_53504
0x53427  ldarg.0
0x53428  ldarg.1
0x53429  isinst   Microsoft.Crm.Metadata.IRelationshipExtraConditionDescription
0x5342e  call     instance void Microsoft.Crm.Metadata.MetadataContainer::AddRelationshipExtraCondition(class Microsoft.Crm.Metadata.IRelationshipExtraConditionDescription relationshipExtraCondition)
0x53433  leave    loc_53504
0x53438  ldarg.0
0x53439  ldarg.1
0x5343a  isinst   Microsoft.Crm.Metadata.IViewInfoDescription
0x5343f  call     instance void Microsoft.Crm.Metadata.MetadataContainer::AddViewAttribute(class Microsoft.Crm.Metadata.IViewInfoDescription viewInfo)
0x53444  leave    loc_53504
0x53449  ldarg.0
0x5344a  ldarg.1
0x5344b  isinst   Microsoft.Crm.Metadata.IPrivilegeObjectTypeCodeDescription
0x53450  call     instance void Microsoft.Crm.Metadata.MetadataContainer::AddPrivilegeObjectTypeCode(class Microsoft.Crm.Metadata.IPrivilegeObjectTypeCodeDescription privilegeOtc)
0x53455  leave    loc_53504
0x5345a  ldarg.0
0x5345b  ldarg.1
0x5345c  isinst   Microsoft.Crm.Metadata.IRoleTemplatePrivilegeDescription
0x53461  call     instance void Microsoft.Crm.Metadata.MetadataContainer::AddRoleTemplatePrivilege(class Microsoft.Crm.Metadata.IRoleTemplatePrivilegeDescription roleTemplatePrivilegeDescription)
0x53466  leave    loc_53504
0x5346b  ldarg.0
0x5346c  ldarg.1
0x5346d  isinst   Microsoft.Crm.Metadata.IEntityRelationshipDescription
0x53472  call     instance void Microsoft.Crm.Metadata.MetadataContainer::AddEntityRelationship(class Microsoft.Crm.Metadata.IEntityRelationshipDescription entityRelationshipDescription)
0x53477  leave    loc_53504
0x5347c  ldarg.0
0x5347d  ldarg.1
0x5347e  isinst   Microsoft.Crm.Metadata.IEntityRelationshipRoleDescription
0x53483  call     instance void Microsoft.Crm.Metadata.MetadataContainer::AddEntityRelationshipRole(class Microsoft.Crm.Metadata.IEntityRelationshipRoleDescription entityRelationshipRoleDescription)
0x53488  leave.s  loc_53504
0x5348a  ldarg.0
0x5348b  ldarg.1
0x5348c  isinst   Microsoft.Crm.Metadata.IEntityRelationshipRelationshipsDescription
0x53491  call     instance void Microsoft.Crm.Metadata.MetadataContainer::AddEntityRelationshipRelationships(class Microsoft.Crm.Metadata.IEntityRelationshipRelationshipsDescription entityRelationshipRelationshipsDescription)
0x53496  leave.s  loc_53504
0x53498  ldarg.0
0x53499  ldarg.1
0x5349a  isinst   Microsoft.Crm.Metadata.IEntityKeyDescription
0x5349f  call     instance void Microsoft.Crm.Metadata.MetadataContainer::AddEntityKey(class Microsoft.Crm.Metadata.IEntityKeyDescription entityKeyDescription)
0x534a4  leave.s  loc_53504
0x534a6  ldarg.0
0x534a7  ldarg.1
0x534a8  isinst   Microsoft.Crm.Metadata.IEntityKeyAttributeDescription
0x534ad  call     instance void Microsoft.Crm.Metadata.MetadataContainer::AddEntityKeyAttribute(class Microsoft.Crm.Metadata.IEntityKeyAttributeDescription entityKeyAttributeDescription)
0x534b2  leave.s  loc_53504
0x534b4  leave.s  loc_534E5
0x534b6  stloc.1
0x534b7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x534bc  ldstr    aFailedToProces// "Failed to process metadata description "...
0x534c1  ldc.i4.2
0x534c2  newarr   [mscorlib]System.Object
0x534c7  dup
0x534c8  ldc.i4.0
0x534c9  ldarg.2
0x534ca  stelem.ref
0x534cb  dup
0x534cc  ldc.i4.1
0x534cd  ldarg.1
0x534ce  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.IMetadataDescription::get_DescriptionId()
0x534d3  box      [mscorlib]System.Guid
0x534d8  stelem.ref
0x534d9  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x534de  ldloc.1
0x534df  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, class [mscorlib]System.Exception)
0x534e4  throw
0x534e5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x534ea  ldstr    aMetadataentity_1// "MetadataEntityName {0} is not valid"
0x534ef  ldc.i4.1
0x534f0  newarr   [mscorlib]System.Object
0x534f5  dup
0x534f6  ldc.i4.0
0x534f7  ldarg.2
0x534f8  stelem.ref
0x534f9  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x534fe  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x53503  throw
0x53504  ret
```
