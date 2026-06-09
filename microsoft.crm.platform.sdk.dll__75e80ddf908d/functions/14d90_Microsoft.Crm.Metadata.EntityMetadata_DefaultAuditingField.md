# Microsoft.Crm.Metadata.EntityMetadata::DefaultAuditingField

- ea: `0x14d90`
- end: `0x14e78`
- name: `Microsoft.Crm.Metadata.EntityMetadata::DefaultAuditingField`
- size: `232`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14f00`

## callees

- `0x10c70`
- `0x10c80`
- `0x10d90`
- `0x11320`
- `0x12ea0`
- `0x14d90`

## string_xrefs

- `0x14e02`: `CreatedBy`
- `0x14e2a`: `CreatedOnBehalfBy`
- `0x14e52`: `CreatedOn`

## pseudocode

```c

```

## disassembly

```asm
0x14d90  ldarg.1
0x14d91  ldstr    aAttribute_0// "attribute"
0x14d96  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x14d9b  ldarg.1
0x14d9c  callvirt instance bool Microsoft.Crm.Metadata.AttributeMetadata::get_IsPKAttribute()
0x14da1  brfalse.s loc_14DA5
0x14da3  ldc.i4.1
0x14da4  ret
0x14da5  ldarg.1
0x14da6  callvirt instance string Microsoft.Crm.Metadata.AttributeMetadata::get_PlatformName()
0x14dab  ldstr    aOwnerid// "ownerid"
0x14db0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x14db5  brtrue.s loc_14DED
0x14db7  ldarg.1
0x14db8  callvirt instance string Microsoft.Crm.Metadata.AttributeMetadata::get_PlatformName()
0x14dbd  ldstr    aOwneridtype// "owneridtype"
0x14dc2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x14dc7  brtrue.s loc_14DED
0x14dc9  ldarg.1
0x14dca  callvirt instance string Microsoft.Crm.Metadata.AttributeMetadata::get_PlatformName()
0x14dcf  ldstr    aOwningbusiness// "owningbusinessunit"
0x14dd4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x14dd9  brtrue.s loc_14DED
0x14ddb  ldarg.1
0x14ddc  callvirt instance string Microsoft.Crm.Metadata.AttributeMetadata::get_PlatformName()
0x14de1  ldstr    aOrganizationid_1// "organizationid"
0x14de6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x14deb  brfalse.s loc_14DEF
0x14ded  ldc.i4.1
0x14dee  ret
0x14def  ldarg.1
0x14df0  callvirt instance class Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Metadata.AttributeMetadata::get_Entity()
0x14df5  callvirt instance bool Microsoft.Crm.Metadata.EntityMetadata::get_IsAudited()
0x14dfa  brfalse.s loc_14E76
0x14dfc  ldarg.1
0x14dfd  callvirt instance string Microsoft.Crm.Metadata.AttributeMetadata::get_PhysicalName()
0x14e02  ldstr    aCreatedby// "CreatedBy"
0x14e07  call     bool [mscorlib]System.String::op_Equality(string, string)
0x14e0c  brfalse.s loc_14E10
0x14e0e  ldc.i4.1
0x14e0f  ret
0x14e10  ldarg.1
0x14e11  callvirt instance string Microsoft.Crm.Metadata.AttributeMetadata::get_PhysicalName()
0x14e16  ldstr    aModifiedby// "ModifiedBy"
0x14e1b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x14e20  brfalse.s loc_14E24
0x14e22  ldc.i4.1
0x14e23  ret
0x14e24  ldarg.1
0x14e25  callvirt instance string Microsoft.Crm.Metadata.AttributeMetadata::get_PhysicalName()
0x14e2a  ldstr    aCreatedonbehal// "CreatedOnBehalfBy"
0x14e2f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x14e34  brfalse.s loc_14E38
0x14e36  ldc.i4.1
0x14e37  ret
0x14e38  ldarg.1
0x14e39  callvirt instance string Microsoft.Crm.Metadata.AttributeMetadata::get_PhysicalName()
0x14e3e  ldstr    aModifiedonbeha// "ModifiedOnBehalfBy"
0x14e43  call     bool [mscorlib]System.String::op_Equality(string, string)
0x14e48  brfalse.s loc_14E4C
0x14e4a  ldc.i4.1
0x14e4b  ret
0x14e4c  ldarg.1
0x14e4d  callvirt instance string Microsoft.Crm.Metadata.AttributeMetadata::get_PhysicalName()
0x14e52  ldstr    aCreatedon_0// "CreatedOn"
0x14e57  call     bool [mscorlib]System.String::op_Equality(string, string)
0x14e5c  brfalse.s loc_14E60
0x14e5e  ldc.i4.1
0x14e5f  ret
0x14e60  ldarg.1
0x14e61  callvirt instance string Microsoft.Crm.Metadata.AttributeMetadata::get_PhysicalName()
0x14e66  ldstr    aModifiedon_0// "ModifiedOn"
0x14e6b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x14e70  brfalse.s loc_14E74
0x14e72  ldc.i4.1
0x14e73  ret
0x14e74  ldc.i4.0
0x14e75  ret
0x14e76  ldc.i4.0
0x14e77  ret
```
