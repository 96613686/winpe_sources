# Microsoft.Crm.Sdk.Metadata.AttributeMetadataFactory::FillManagedProperties

- ea: `0x5610`
- end: `0x58d6`
- name: `Microsoft.Crm.Sdk.Metadata.AttributeMetadataFactory::FillManagedProperties`
- size: `710`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x5160`

## callees

- `0x5610`
- `0x5af0`

## string_xrefs

- `0x56ab`: `isrenameable`
- `0x56b9`: `isrenameable`
- `0x56c8`: `isrenameable`

## pseudocode

```c

```

## disassembly

```asm
0x5610  ldarg.0
0x5611  ldstr    aAttributerequi// "attributerequiredlevelid"
0x5616  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x561b  brtrue.s loc_564E
0x561d  ldarg.1
0x561e  ldarg.0
0x561f  call     valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeRequiredLevel Microsoft.Crm.Sdk.Metadata.AttributeMetadataFactory::GetAttributeRequiredLevel(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity attributeEntity)
0x5624  ldstr    aCanmodifyrequi// "canmodifyrequirementlevelsettings"
0x5629  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeRequiredLevelManagedProperty::.ctor(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeRequiredLevel, string)
0x562e  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::set_RequiredLevel(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeRequiredLevelManagedProperty)
0x5633  ldarg.1
0x5634  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeRequiredLevelManagedProperty [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_RequiredLevel()
0x5639  ldarg.0
0x563a  ldstr    aCanmodifyrequi// "canmodifyrequirementlevelsettings"
0x563f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x5644  unbox.any [mscorlib]System.Boolean
0x5649  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ManagedProperty`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeRequiredLevel>::set_CanBeChanged(bool)
0x564e  ldarg.0
0x564f  ldstr    aIscustomizable// "iscustomizable"
0x5654  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x5659  brtrue.s loc_56AA
0x565b  ldarg.1
0x565c  ldarg.0
0x565d  ldstr    aIscustomizable// "iscustomizable"
0x5662  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x5667  unbox.any [mscorlib]System.Boolean
0x566c  ldstr    aIscustomizable// "iscustomizable"
0x5671  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BooleanManagedProperty::.ctor(bool, string)
0x5676  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::set_IsCustomizable(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BooleanManagedProperty)
0x567b  ldarg.1
0x567c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BooleanManagedProperty [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_IsCustomizable()
0x5681  ldarg.1
0x5682  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_IsManaged()
0x5687  stloc.0
0x5688  ldloca.s 0
0x568a  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x568f  brfalse.s loc_56A4
0x5691  ldarg.1
0x5692  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_IsManaged()
0x5697  stloc.0
0x5698  ldloca.s 0
0x569a  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x569f  ldc.i4.0
0x56a0  ceq
0x56a2  br.s     loc_56A5
0x56a4  ldc.i4.1
0x56a5  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ManagedProperty`1<bool>::set_CanBeChanged(bool)
0x56aa  ldarg.0
0x56ab  ldstr    aIsrenameable// "isrenameable"
0x56b0  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x56b5  brtrue.s loc_5706
0x56b7  ldarg.1
0x56b8  ldarg.0
0x56b9  ldstr    aIsrenameable// "isrenameable"
0x56be  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x56c3  unbox.any [mscorlib]System.Boolean
0x56c8  ldstr    aIsrenameable// "isrenameable"
0x56cd  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BooleanManagedProperty::.ctor(bool, string)
0x56d2  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::set_IsRenameable(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BooleanManagedProperty)
0x56d7  ldarg.1
0x56d8  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BooleanManagedProperty [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_IsRenameable()
0x56dd  ldarg.1
0x56de  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_IsManaged()
0x56e3  stloc.0
0x56e4  ldloca.s 0
0x56e6  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x56eb  brfalse.s loc_5700
0x56ed  ldarg.1
0x56ee  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_IsManaged()
0x56f3  stloc.0
0x56f4  ldloca.s 0
0x56f6  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x56fb  ldc.i4.0
0x56fc  ceq
0x56fe  br.s     loc_5701
0x5700  ldc.i4.1
0x5701  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ManagedProperty`1<bool>::set_CanBeChanged(bool)
0x5706  ldarg.0
0x5707  ldstr    aCanmodifyaddit// "canmodifyadditionalsettings"
0x570c  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x5711  brtrue.s loc_5762
0x5713  ldarg.1
0x5714  ldarg.0
0x5715  ldstr    aCanmodifyaddit// "canmodifyadditionalsettings"
0x571a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x571f  unbox.any [mscorlib]System.Boolean
0x5724  ldstr    aCanmodifyaddit// "canmodifyadditionalsettings"
0x5729  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BooleanManagedProperty::.ctor(bool, string)
0x572e  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::set_CanModifyAdditionalSettings(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BooleanManagedProperty)
0x5733  ldarg.1
0x5734  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BooleanManagedProperty [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_CanModifyAdditionalSettings()
0x5739  ldarg.1
0x573a  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_IsManaged()
0x573f  stloc.0
0x5740  ldloca.s 0
0x5742  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x5747  brfalse.s loc_575C
0x5749  ldarg.1
0x574a  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_IsManaged()
0x574f  stloc.0
0x5750  ldloca.s 0
0x5752  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x5757  ldc.i4.0
0x5758  ceq
0x575a  br.s     loc_575D
0x575c  ldc.i4.1
0x575d  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ManagedProperty`1<bool>::set_CanBeChanged(bool)
0x5762  ldarg.0
0x5763  ldstr    aIsauditenabled// "isauditenabled"
0x5768  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x576d  brtrue.s loc_57AA
0x576f  ldarg.1
0x5770  ldarg.0
0x5771  ldstr    aIsauditenabled// "isauditenabled"
0x5776  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x577b  unbox.any [mscorlib]System.Boolean
0x5780  ldstr    aCanmodifyaudit// "canmodifyauditsettings"
0x5785  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BooleanManagedProperty::.ctor(bool, string)
0x578a  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::set_IsAuditEnabled(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BooleanManagedProperty)
0x578f  ldarg.1
0x5790  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BooleanManagedProperty [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_IsAuditEnabled()
0x5795  ldarg.0
0x5796  ldstr    aCanmodifyaudit// "canmodifyauditsettings"
0x579b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x57a0  unbox.any [mscorlib]System.Boolean
0x57a5  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ManagedProperty`1<bool>::set_CanBeChanged(bool)
0x57aa  ldarg.0
0x57ab  ldstr    aCanmodifybehav// "canmodifybehavior"
0x57b0  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x57b5  brtrue.s loc_5810
0x57b7  ldarg.1
0x57b8  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.DateTimeAttributeMetadata
0x57bd  stloc.1
0x57be  ldloc.1
0x57bf  brfalse.s loc_5810
0x57c1  ldloc.1
0x57c2  ldarg.0
0x57c3  ldstr    aCanmodifybehav// "canmodifybehavior"
0x57c8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x57cd  unbox.any [mscorlib]System.Boolean
0x57d2  ldstr    aCanmodifybehav// "canmodifybehavior"
0x57d7  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BooleanManagedProperty::.ctor(bool, string)
0x57dc  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.DateTimeAttributeMetadata::set_CanChangeDateTimeBehavior(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BooleanManagedProperty)
0x57e1  ldloc.1
0x57e2  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BooleanManagedProperty [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.DateTimeAttributeMetadata::get_CanChangeDateTimeBehavior()
0x57e7  ldarg.1
0x57e8  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_IsManaged()
0x57ed  stloc.0
0x57ee  ldloca.s 0
0x57f0  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x57f5  brfalse.s loc_580A
0x57f7  ldarg.1
0x57f8  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_IsManaged()
0x57fd  stloc.0
0x57fe  ldloca.s 0
0x5800  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x5805  ldc.i4.0
0x5806  ceq
0x5808  br.s     loc_580B
0x580a  ldc.i4.1
0x580b  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ManagedProperty`1<bool>::set_CanBeChanged(bool)
0x5810  ldarg.0
0x5811  ldstr    aIsglobalfilter// "isglobalfilterenabled"
0x5816  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x581b  brtrue.s loc_5873
0x581d  ldarg.1
0x581e  ldarg.0
0x581f  ldstr    aIsglobalfilter// "isglobalfilterenabled"
0x5824  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x5829  unbox.any [mscorlib]System.Boolean
0x582e  ldstr    aCanmodifygloba// "canmodifyglobalfiltersettings"
0x5833  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BooleanManagedProperty::.ctor(bool, string)
0x5838  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::set_IsGlobalFilterEnabled(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BooleanManagedProperty)
0x583d  ldarg.0
0x583e  ldstr    aCanmodifygloba// "canmodifyglobalfiltersettings"
0x5843  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x5848  brtrue.s loc_5867
0x584a  ldarg.1
0x584b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BooleanManagedProperty [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_IsGlobalFilterEnabled()
0x5850  ldarg.0
0x5851  ldstr    aCanmodifygloba// "canmodifyglobalfiltersettings"
0x5856  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x585b  unbox.any [mscorlib]System.Boolean
0x5860  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ManagedProperty`1<bool>::set_CanBeChanged(bool)
0x5865  br.s     loc_5873
0x5867  ldarg.1
0x5868  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BooleanManagedProperty [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_IsGlobalFilterEnabled()
0x586d  ldc.i4.1
0x586e  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ManagedProperty`1<bool>::set_CanBeChanged(bool)
0x5873  ldarg.0
0x5874  ldstr    aIssortableenab// "issortableenabled"
0x5879  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x587e  brtrue.s loc_58D5
0x5880  ldarg.1
0x5881  ldarg.0
0x5882  ldstr    aIssortableenab// "issortableenabled"
0x5887  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x588c  unbox.any [mscorlib]System.Boolean
0x5891  ldstr    aCanmodifyissor// "canmodifyissortablesettings"
0x5896  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BooleanManagedProperty::.ctor(bool, string)
0x589b  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::set_IsSortableEnabled(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BooleanManagedProperty)
0x58a0  ldarg.0
0x58a1  ldstr    aCanmodifyissor// "canmodifyissortablesettings"
0x58a6  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x58ab  brtrue.s loc_58C9
0x58ad  ldarg.1
0x58ae  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BooleanManagedProperty [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_IsSortableEnabled()
0x58b3  ldarg.0
0x58b4  ldstr    aCanmodifyissor// "canmodifyissortablesettings"
0x58b9  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x58be  unbox.any [mscorlib]System.Boolean
0x58c3  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ManagedProperty`1<bool>::set_CanBeChanged(bool)
0x58c8  ret
0x58c9  ldarg.1
0x58ca  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BooleanManagedProperty [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_IsSortableEnabled()
0x58cf  ldc.i4.1
0x58d0  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ManagedProperty`1<bool>::set_CanBeChanged(bool)
0x58d5  ret
```
