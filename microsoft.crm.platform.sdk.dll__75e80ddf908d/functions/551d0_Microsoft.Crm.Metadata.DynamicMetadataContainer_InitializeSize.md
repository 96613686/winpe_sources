# Microsoft.Crm.Metadata.DynamicMetadataContainer::InitializeSize

- ea: `0x551d0`
- end: `0x555af`
- name: `Microsoft.Crm.Metadata.DynamicMetadataContainer::InitializeSize`
- size: `991`
- prototype: ``
- caller_count: `0`
- callee_count: `42`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x450b0`
- `0x45160`
- `0x451b0`
- `0x45220`
- `0x452b0`
- `0x45390`
- `0x45400`
- `0x45470`
- `0x454e0`
- `0x45fd0`
- `0x460b0`
- `0x46640`
- `0x46720`
- `0x46770`
- `0x46980`
- `0x46a90`
- `0x46b50`
- `0x46c10`
- `0x54af0`
- `0x54b10`
- `0x54b30`
- `0x54b50`
- `0x54b70`
- `0x54bd0`
- `0x54bf0`
- `0x54c10`
- `0x54c70`
- `0x54c90`
- `0x54cb0`
- `0x54cd0`
- `0x54cf0`
- `0x54d10`
- `0x54d30`
- `0x54d50`
- `0x54d70`
- `0x54d90`
- `0x54df0`
- `0x54e10`
- `0x54f90`
- `0x54fb0`
- `0x551d0`
- `0xa94d0`

## string_xrefs

- `0x55436`: `Privilege`
- `0x553cd`: `PrivilegeObjectTypeCode`
- `0x553e2`: `RoleTemplatePrivilege`

## pseudocode

```c

```

## disassembly

```asm
0x551d0  ldarg.2
0x551d1  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x551d6  stloc.0
0x551d7  ldloc.0
0x551d8  ldc.i4   0x7A787910
0x551dd  bgt.un   loc_55271
0x551e2  ldloc.0
0x551e3  ldc.i4   0x2FB17EF0
0x551e8  bgt.un.s loc_55228
0x551ea  ldloc.0
0x551eb  ldc.i4   0x1D72D1E6
0x551f0  bgt.un.s loc_5520D
0x551f2  ldloc.0
0x551f3  ldc.i4   0x1ACCD85B
0x551f8  beq      loc_5538D
0x551fd  ldloc.0
0x551fe  ldc.i4   0x1D72D1E6
0x55203  beq      loc_553E1
0x55208  br       loc_5558F
0x5520d  ldloc.0
0x5520e  ldc.i4   0x21E27D10
0x55213  beq      loc_5540B
0x55218  ldloc.0
0x55219  ldc.i4   0x2FB17EF0
0x5521e  beq      loc_553A2
0x55223  br       loc_5558F
0x55228  ldloc.0
0x55229  ldc.i4   0x4F6B9560
0x5522e  bgt.un.s loc_5524B
0x55230  ldloc.0
0x55231  ldc.i4   0x3578225F
0x55236  beq      loc_5534E
0x5523b  ldloc.0
0x5523c  ldc.i4   0x4F6B9560
0x55241  beq      loc_553F6
0x55246  br       loc_5558F
0x5524b  ldloc.0
0x5524c  ldc.i4   0x62FA988F
0x55251  beq      loc_55324
0x55256  ldloc.0
0x55257  ldc.i4   0x6E61547A
0x5525c  beq      loc_553CC
0x55261  ldloc.0
0x55262  ldc.i4   0x7A787910
0x55267  beq      loc_55378
0x5526c  br       loc_5558F
0x55271  ldloc.0
0x55272  ldc.i4   0x9F56E047
0x55277  bgt.un.s loc_552B4
0x55279  ldloc.0
0x5527a  ldc.i4   0x80D2874B
0x5527f  bgt.un.s loc_5529C
0x55281  ldloc.0
0x55282  ldc.i4   0x7B5DF6A6
0x55287  beq      loc_55339
0x5528c  ldloc.0
0x5528d  ldc.i4   0x80D2874B
0x55292  beq      loc_5545F
0x55297  br       loc_5558F
0x5529c  ldloc.0
0x5529d  ldc.i4   0x946992DC
0x552a2  beq.s    loc_5530F
0x552a4  ldloc.0
0x552a5  ldc.i4   0x9F56E047
0x552aa  beq      loc_55420
0x552af  br       loc_5558F
0x552b4  ldloc.0
0x552b5  ldc.i4   0xC0670678
0x552ba  bgt.un.s loc_552D7
0x552bc  ldloc.0
0x552bd  ldc.i4   0xA6468091
0x552c2  beq      loc_5544A
0x552c7  ldloc.0
0x552c8  ldc.i4   0xC0670678
0x552cd  beq      loc_553B7
0x552d2  br       loc_5558F
0x552d7  ldloc.0
0x552d8  ldc.i4   0xC09B32FA
0x552dd  beq      loc_55363
0x552e2  ldloc.0
0x552e3  ldc.i4   0xCEEE0703
0x552e8  beq.s    loc_552FA
0x552ea  ldloc.0
0x552eb  ldc.i4   0xF92D43AC
0x552f0  beq      loc_55435
0x552f5  br       loc_5558F
0x552fa  ldarg.2
0x552fb  ldstr    aManagedpropert_5// "ManagedProperty"
0x55300  call     bool [mscorlib]System.String::op_Equality(string, string)
0x55305  brtrue   loc_55474
0x5530a  br       loc_5558F
0x5530f  ldarg.2
0x55310  ldstr    aOptionset_0// "OptionSet"
0x55315  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5531a  brtrue   loc_55481
0x5531f  br       loc_5558F
0x55324  ldarg.2
0x55325  ldstr    aAttribute// "Attribute"
0x5532a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5532f  brtrue   loc_5549A
0x55334  br       loc_5558F
0x55339  ldarg.2
0x5533a  ldstr    aAttributelooku// "AttributeLookupValue"
0x5533f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x55344  brtrue   loc_554A7
0x55349  br       loc_5558F
0x5534e  ldarg.2
0x5534f  ldstr    aAttributepickl// "AttributePicklistValue"
0x55354  call     bool [mscorlib]System.String::op_Equality(string, string)
0x55359  brtrue   loc_554B4
0x5535e  br       loc_5558F
0x55363  ldarg.2
0x55364  ldstr    aEntity_0// "Entity"
0x55369  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5536e  brtrue   loc_554C1
0x55373  br       loc_5558F
0x55378  ldarg.2
0x55379  ldstr    aLocalizedlabel// "LocalizedLabel"
0x5537e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x55383  brtrue   loc_555AE
0x55388  br       loc_5558F
0x5538d  ldarg.2
0x5538e  ldstr    aRelationship_0// "Relationship"
0x55393  call     bool [mscorlib]System.String::op_Equality(string, string)
0x55398  brtrue   loc_55500
0x5539d  br       loc_5558F
0x553a2  ldarg.2
0x553a3  ldstr    aRelationshipex_0// "RelationshipExtraCondition"
0x553a8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x553ad  brtrue   loc_5550D
0x553b2  br       loc_5558F
0x553b7  ldarg.2
0x553b8  ldstr    aViewattribute// "ViewAttribute"
0x553bd  call     bool [mscorlib]System.String::op_Equality(string, string)
0x553c2  brtrue   loc_5551A
0x553c7  br       loc_5558F
0x553cc  ldarg.2
0x553cd  ldstr    aPrivilegeobjec// "PrivilegeObjectTypeCode"
0x553d2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x553d7  brtrue   loc_55527
0x553dc  br       loc_5558F
0x553e1  ldarg.2
0x553e2  ldstr    aRoletemplatepr// "RoleTemplatePrivilege"
0x553e7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x553ec  brtrue   loc_55534
0x553f1  br       loc_5558F
0x553f6  ldarg.2
0x553f7  ldstr    aEntityrelation_0// "EntityRelationship"
0x553fc  call     bool [mscorlib]System.String::op_Equality(string, string)
0x55401  brtrue   loc_55541
0x55406  br       loc_5558F
0x5540b  ldarg.2
0x5540c  ldstr    aEntityrelation_4// "EntityRelationshipRole"
0x55411  call     bool [mscorlib]System.String::op_Equality(string, string)
0x55416  brtrue   loc_5554E
0x5541b  br       loc_5558F
0x55420  ldarg.2
0x55421  ldstr    aEntityrelation_6// "EntityRelationshipRelationships"
0x55426  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5542b  brtrue   loc_5555B
0x55430  br       loc_5558F
0x55435  ldarg.2
0x55436  ldstr    aPrivilege// "Privilege"
0x5543b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x55440  brtrue   loc_55568
0x55445  br       loc_5558F
0x5544a  ldarg.2
0x5544b  ldstr    aEntitykey_0// "EntityKey"
0x55450  call     bool [mscorlib]System.String::op_Equality(string, string)
0x55455  brtrue   loc_55575
0x5545a  br       loc_5558F
0x5545f  ldarg.2
0x55460  ldstr    aEntitykeyattri// "EntityKeyAttribute"
0x55465  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5546a  brtrue   loc_55582
0x5546f  br       loc_5558F
0x55474  ldarg.0
0x55475  ldarg.1
0x55476  newobj   instance void Microsoft.Crm.Metadata.ManagedPropertyByIdDictionary::.ctor(int32 capacity)
0x5547b  call     instance void Microsoft.Crm.Metadata.DynamicMetadataContainer::set_ManagedProperties(class Microsoft.Crm.Metadata.ManagedPropertyByIdDictionary value)
0x55480  ret
0x55481  ldarg.0
0x55482  ldarg.1
0x55483  newobj   instance void Microsoft.Crm.Metadata.OptionSetByIdDictionary::.ctor(int32 capacity)
0x55488  call     instance void Microsoft.Crm.Metadata.DynamicMetadataContainer::set_OptionSets(class Microsoft.Crm.Metadata.OptionSetByIdDictionary value)
0x5548d  ldarg.0
0x5548e  ldarg.1
0x5548f  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.EnumOptionByValueDictionary>::.ctor(int32)
0x55494  call     instance void Microsoft.Crm.Metadata.DynamicMetadataContainer::set_PicklistValuesByOptionSet(class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.EnumOptionByValueDictionary> value)
0x55499  ret
0x5549a  ldarg.0
0x5549b  ldarg.1
0x5549c  newobj   instance void Microsoft.Crm.Metadata.AttributeMetadataDictionary::.ctor(int32 capacity)
0x554a1  call     instance void Microsoft.Crm.Metadata.DynamicMetadataContainer::set_Attributes(class Microsoft.Crm.Metadata.AttributeMetadataDictionary value)
0x554a6  ret
0x554a7  ldarg.0
0x554a8  ldarg.1
0x554a9  newobj   instance void Microsoft.Crm.Metadata.AttributeLookupValueDictionary::.ctor(int32 capacity)
0x554ae  call     instance void Microsoft.Crm.Metadata.DynamicMetadataContainer::set_LookupValues(class Microsoft.Crm.Metadata.AttributeLookupValueDictionary value)
0x554b3  ret
0x554b4  ldarg.0
0x554b5  ldarg.1
0x554b6  newobj   instance void Microsoft.Crm.Metadata.EnumOptionDictionary::.ctor(int32 capacity)
0x554bb  call     instance void Microsoft.Crm.Metadata.DynamicMetadataContainer::set_PicklistValues(class Microsoft.Crm.Metadata.EnumOptionDictionary value)
0x554c0  ret
0x554c1  ldarg.0
0x554c2  ldarg.1
0x554c3  newobj   instance void Microsoft.Crm.Metadata.EntityMetadataDictionary::.ctor(int32 capacity)
0x554c8  call     instance void Microsoft.Crm.Metadata.DynamicMetadataContainer::set_Entities(class Microsoft.Crm.Metadata.EntityMetadataDictionary value)
0x554cd  ldarg.0
0x554ce  ldarg.1
0x554cf  newobj   instance void Microsoft.Crm.Metadata.EntityMetadataCollection::.ctor(int32 capacity)
0x554d4  call     instance void Microsoft.Crm.Metadata.DynamicMetadataContainer::set_EntitiesByLogicalName(class Microsoft.Crm.Metadata.EntityMetadataCollection value)
0x554d9  ldarg.0
0x554da  ldarg.1
0x554db  newobj   instance void Microsoft.Crm.Metadata.EntityMetadataCollection::.ctor(int32 capacity)
0x554e0  call     instance void Microsoft.Crm.Metadata.DynamicMetadataContainer::set_EntitiesByObjectTypeCode(class Microsoft.Crm.Metadata.EntityMetadataCollection value)
0x554e5  ldarg.0
0x554e6  ldarg.1
0x554e7  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.AttributeMetadataCollection>::.ctor(int32)
0x554ec  call     instance void Microsoft.Crm.Metadata.DynamicMetadataContainer::set_AttributesByEntityId(class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.AttributeMetadataCollection> value)
0x554f1  ldarg.0
0x554f2  ldarg.1
0x554f3  ldc.i4.1
0x554f4  add
0x554f5  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Metadata.PrivilegeCollection>::.ctor(int32)
0x554fa  call     instance void Microsoft.Crm.Metadata.DynamicMetadataContainer::set_privilegesByOtc(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Metadata.PrivilegeCollection> value)
0x554ff  ret
0x55500  ldarg.0
0x55501  ldarg.1
0x55502  newobj   instance void Microsoft.Crm.Metadata.RelationshipHashtable::.ctor(int32 capacity)
0x55507  call     instance void Microsoft.Crm.Metadata.DynamicMetadataContainer::set_Relationships(class Microsoft.Crm.Metadata.RelationshipHashtable value)
0x5550c  ret
0x5550d  ldarg.0
0x5550e  ldarg.1
0x5550f  newobj   instance void Microsoft.Crm.Metadata.RelationshipExtraConditionDictionary::.ctor(int32 capacity)
0x55514  call     instance void Microsoft.Crm.Metadata.DynamicMetadataContainer::set_RelationshipExtraConditions(class Microsoft.Crm.Metadata.RelationshipExtraConditionDictionary value)
0x55519  ret
0x5551a  ldarg.0
0x5551b  ldarg.1
0x5551c  newobj   instance void Microsoft.Crm.Metadata.ViewAttributeDictionary::.ctor(int32 capacity)
0x55521  call     instance void Microsoft.Crm.Metadata.DynamicMetadataContainer::set_ViewAttributes(class Microsoft.Crm.Metadata.ViewAttributeDictionary value)
0x55526  ret
0x55527  ldarg.0
0x55528  ldarg.1
0x55529  newobj   instance void Microsoft.Crm.Metadata.PrivilegeObjectTypeCodeDictionary::.ctor(int32 capacity)
0x5552e  call     instance void Microsoft.Crm.Metadata.DynamicMetadataContainer::set_PrivilegeObjectTypeCodes(class Microsoft.Crm.Metadata.PrivilegeObjectTypeCodeDictionary value)
0x55533  ret
0x55534  ldarg.0
0x55535  ldarg.1
0x55536  newobj   instance void Microsoft.Crm.Metadata.RoleTemplatePrivilegeDictionary::.ctor(int32 capacity)
0x5553b  call     instance void Microsoft.Crm.Metadata.DynamicMetadataContainer::set_RoleTemplatePrivileges(class Microsoft.Crm.Metadata.RoleTemplatePrivilegeDictionary value)
0x55540  ret
0x55541  ldarg.0
0x55542  ldarg.1
0x55543  newobj   instance void Microsoft.Crm.Metadata.EntityRelationshipByIdDictionary::.ctor(int32 capacity)
0x55548  call     instance void Microsoft.Crm.Metadata.DynamicMetadataContainer::set_EntityRelationships(class Microsoft.Crm.Metadata.EntityRelationshipByIdDictionary value)
0x5554d  ret
0x5554e  ldarg.0
0x5554f  ldarg.1
0x55550  newobj   instance void Microsoft.Crm.Metadata.EntityRelationshipRoleDictionary::.ctor(int32 capacity)
0x55555  call     instance void Microsoft.Crm.Metadata.DynamicMetadataContainer::set_EntityRelationshipRoles(class Microsoft.Crm.Metadata.EntityRelationshipRoleDictionary value)
0x5555a  ret
0x5555b  ldarg.0
0x5555c  ldarg.1
0x5555d  newobj   instance void Microsoft.Crm.Metadata.EntityRelationshipRelationshipsDictionary::.ctor(int32 capacity)
0x55562  call     instance void Microsoft.Crm.Metadata.DynamicMetadataContainer::set_EntityRelationshipRelationships(class Microsoft.Crm.Metadata.EntityRelationshipRelationshipsDictionary value)
0x55567  ret
0x55568  ldarg.0
0x55569  ldarg.1
0x5556a  newobj   instance void Microsoft.Crm.Metadata.PrivilegeDictionary::.ctor(int32 capacity)
0x5556f  call     instance void Microsoft.Crm.Metadata.DynamicMetadataContainer::set_privileges(class Microsoft.Crm.Metadata.PrivilegeDictionary value)
0x55574  ret
0x55575  ldarg.0
0x55576  ldarg.1
0x55577  newobj   instance void Microsoft.Crm.Metadata.EntityKeyByIdCollection::.ctor(int32 capacity)
0x5557c  call     instance void Microsoft.Crm.Metadata.DynamicMetadataContainer::set_EntityKeys(class Microsoft.Crm.Metadata.EntityKeyByIdCollection value)
0x55581  ret
0x55582  ldarg.0
0x55583  ldarg.1
0x55584  newobj   instance void Microsoft.Crm.Metadata.EntityKeyAttributeMetadataDictionary::.ctor(int32 capacity)
0x55589  call     instance void Microsoft.Crm.Metadata.DynamicMetadataContainer::set_EntityKeyAttributes(class Microsoft.Crm.Metadata.EntityKeyAttributeMetadataDictionary value)
0x5558e  ret
0x5558f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x55594  ldstr    aMetadataentity_1// "MetadataEntityName {0} is not valid"
0x55599  ldc.i4.1
0x5559a  newarr   [mscorlib]System.Object
0x5559f  dup
0x555a0  ldc.i4.0
0x555a1  ldarg.2
0x555a2  stelem.ref
0x555a3  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x555a8  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x555ad  throw
0x555ae  ret
```
