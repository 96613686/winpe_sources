# Microsoft.Crm.Metadata.AttributeInfo::SetDescriptionPropertiesForUpdate

- ea: `0x179b0`
- end: `0x17d41`
- name: `Microsoft.Crm.Metadata.AttributeInfo::SetDescriptionPropertiesForUpdate`
- size: `913`
- prototype: ``
- caller_count: `12`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1e420`
- `0x2c020`
- `0x2c3a0`
- `0x40f40`
- `0x43430`
- `0x436f0`
- `0x43b90`
- `0x44400`
- `0x44770`
- `0x4a620`
- `0x58e10`
- `0x757d0`

## callees

- `0x179b0`
- `0x17d50`
- `0x17f90`
- `0x17fc0`
- `0x18530`
- `0x18680`
- `0x18760`
- `0x187a0`
- `0x187b0`

## string_xrefs

- `0x17a73`: `linkedattributeid`

## pseudocode

```c

```

## disassembly

```asm
0x179b0  ldarg.0
0x179b1  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x179b6  ldarg.2
0x179b7  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_SourceType()
0x179bc  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_SourceType(int32)
0x179c1  ldarg.2
0x179c2  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_IsBaseCurrency()
0x179c7  brtrue.s loc_17A04
0x179c9  ldarg.0
0x179ca  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x179cf  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::get_InnerEntityData()
0x179d4  ldstr    aSourcetypemask// "sourcetypemask"
0x179d9  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNullOrNameInvalid(string)
0x179de  brtrue.s loc_17A04
0x179e0  ldarg.0
0x179e1  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x179e6  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_SourceTypeMask()
0x179eb  ldarg.2
0x179ec  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_SourceTypeMask()
0x179f1  beq.s    loc_17A04
0x179f3  ldarg.1
0x179f4  ldarg.0
0x179f5  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x179fa  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_SourceTypeMask()
0x179ff  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_SourceTypeMask(int32)
0x17a04  ldarg.0
0x17a05  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x17a0a  ldstr    aAutonumberform// "autonumberformat"
0x17a0f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::get_Item(string)
0x17a14  brfalse.s loc_17A27
0x17a16  ldarg.1
0x17a17  ldarg.0
0x17a18  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x17a1d  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_AutoNumberFormat()
0x17a22  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_AutoNumberFormat(string)
0x17a27  ldarg.0
0x17a28  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x17a2d  ldstr    aIssecured// "issecured"
0x17a32  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::get_Item(string)
0x17a37  brfalse.s loc_17A4A
0x17a39  ldarg.1
0x17a3a  ldarg.0
0x17a3b  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x17a40  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_IsSecured()
0x17a45  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_IsSecured(bool)
0x17a4a  ldarg.0
0x17a4b  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x17a50  ldstr    aLocked// "locked"
0x17a55  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::get_Item(string)
0x17a5a  brfalse.s loc_17A6D
0x17a5c  ldarg.1
0x17a5d  ldarg.0
0x17a5e  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x17a63  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_Locked()
0x17a68  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_Locked(bool)
0x17a6d  ldarg.0
0x17a6e  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x17a73  ldstr    aLinkedattribut// "linkedattributeid"
0x17a78  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::get_Item(string)
0x17a7d  brfalse.s loc_17A90
0x17a7f  ldarg.1
0x17a80  ldarg.0
0x17a81  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x17a86  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_LinkedAttributeId()
0x17a8b  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_LinkedAttributeId(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>)
0x17a90  ldarg.0
0x17a91  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x17a96  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::get_InnerEntityData()
0x17a9b  ldstr    aIsglobalfilter// "isglobalfilterenabled"
0x17aa0  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNullOrNameInvalid(string)
0x17aa5  brtrue.s loc_17ACA
0x17aa7  ldarg.0
0x17aa8  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x17aad  ldstr    aIsglobalfilter// "isglobalfilterenabled"
0x17ab2  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::get_Item(string)
0x17ab7  brfalse.s loc_17ACA
0x17ab9  ldarg.1
0x17aba  ldarg.0
0x17abb  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x17ac0  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_IsGlobalFilterEnabled()
0x17ac5  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_IsGlobalFilterEnabled(bool)
0x17aca  ldarg.0
0x17acb  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x17ad0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::get_InnerEntityData()
0x17ad5  ldstr    aIssortableenab// "issortableenabled"
0x17ada  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNullOrNameInvalid(string)
0x17adf  brtrue.s loc_17B04
0x17ae1  ldarg.0
0x17ae2  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x17ae7  ldstr    aIssortableenab// "issortableenabled"
0x17aec  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::get_Item(string)
0x17af1  brfalse.s loc_17B04
0x17af3  ldarg.1
0x17af4  ldarg.0
0x17af5  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x17afa  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_IsSortableEnabled()
0x17aff  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_IsSortableEnabled(bool)
0x17b04  ldarg.0
0x17b05  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x17b0a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::get_InnerEntityData()
0x17b0f  ldstr    aIsactive// "isactive"
0x17b14  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNullOrNameInvalid(string)
0x17b19  brtrue.s loc_17B3E
0x17b1b  ldarg.0
0x17b1c  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x17b21  ldstr    aIsactive// "isactive"
0x17b26  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::get_Item(string)
0x17b2b  brfalse.s loc_17B3E
0x17b2d  ldarg.1
0x17b2e  ldarg.0
0x17b2f  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x17b34  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_IsActive()
0x17b39  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_IsActive(bool)
0x17b3e  ldarg.0
0x17b3f  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x17b44  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::get_InnerEntityData()
0x17b49  ldstr    aIsdatasourcese// "isdatasourcesecret"
0x17b4e  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNullOrNameInvalid(string)
0x17b53  brtrue.s loc_17B78
0x17b55  ldarg.0
0x17b56  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x17b5b  ldstr    aIsdatasourcese// "isdatasourcesecret"
0x17b60  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::get_Item(string)
0x17b65  brfalse.s loc_17B78
0x17b67  ldarg.1
0x17b68  ldarg.0
0x17b69  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x17b6e  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_IsDataSourceSecret()
0x17b73  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_IsDataSourceSecret(bool)
0x17b78  ldarg.0
0x17b79  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x17b7e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::get_InnerEntityData()
0x17b83  ldstr    aExternalname// "externalname"
0x17b88  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNullOrNameInvalid(string)
0x17b8d  brtrue.s loc_17BB2
0x17b8f  ldarg.0
0x17b90  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x17b95  ldstr    aExternalname// "externalname"
0x17b9a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::get_Item(string)
0x17b9f  brfalse.s loc_17BB2
0x17ba1  ldarg.1
0x17ba2  ldarg.0
0x17ba3  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x17ba8  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_ExternalName()
0x17bad  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_ExternalName(string)
0x17bb2  ldarg.0
0x17bb3  call     instance bool Microsoft.Crm.Metadata.AttributeInfo::get_IsCalculatedField()
0x17bb8  brtrue.s loc_17C2B
0x17bba  ldarg.0
0x17bbb  call     instance bool Microsoft.Crm.Metadata.AttributeInfo::get_IsRollupField()
0x17bc0  brtrue.s loc_17C2B
0x17bc2  ldarg.0
0x17bc3  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x17bc8  ldstr    aAttributerequi// "attributerequiredlevelid"
0x17bcd  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::get_Item(string)
0x17bd2  brfalse.s loc_17BE5
0x17bd4  ldarg.1
0x17bd5  ldarg.0
0x17bd6  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x17bdb  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_RequiredLevel()
0x17be0  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_RequiredLevel(string)
0x17be5  ldarg.0
0x17be6  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x17beb  ldstr    aAttributeimemo// "attributeimemodeid"
0x17bf0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::get_Item(string)
0x17bf5  brfalse.s loc_17C08
0x17bf7  ldarg.1
0x17bf8  ldarg.0
0x17bf9  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x17bfe  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_IMEMode()
0x17c03  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_IMEMode(string)
0x17c08  ldarg.0
0x17c09  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x17c0e  ldstr    aIsauditenabled// "isauditenabled"
0x17c13  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::get_Item(string)
0x17c18  brfalse.s loc_17C2B
0x17c1a  ldarg.1
0x17c1b  ldarg.0
0x17c1c  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x17c21  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_IsAuditEnabled()
0x17c26  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_IsAuditEnabled(bool)
0x17c2b  ldarg.0
0x17c2c  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x17c31  ldstr    aDisplaymask// "displaymask"
0x17c36  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::get_Item(string)
0x17c3b  brfalse  loc_17D2A
0x17c40  ldarg.2
0x17c41  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_DisplayMask()
0x17c46  ldc.i4   0x4000000
0x17c4b  and
0x17c4c  ldc.i4.0
0x17c4d  cgt.un
0x17c4f  stloc.0
0x17c50  ldarg.0
0x17c51  call     instance bool Microsoft.Crm.Metadata.AttributeInfo::get_ValidForAdvancedFind()
0x17c56  ldloc.0
0x17c57  beq.s    loc_17CC7
0x17c59  ldarg.0
0x17c5a  call     instance bool Microsoft.Crm.Metadata.AttributeInfo::get_ValidForAdvancedFind()
0x17c5f  brfalse.s loc_17C95
0x17c61  ldarg.1
0x17c62  ldarg.1
0x17c63  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_DisplayMask()
0x17c68  ldc.i4   0x4000000
0x17c6d  or
0x17c6e  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_DisplayMask(int32)
0x17c73  ldarg.2
0x17c74  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_DisplayMask()
0x17c79  ldc.i4   0x2000000
0x17c7e  and
0x17c7f  brfalse.s loc_17CC7
0x17c81  ldarg.1
0x17c82  ldarg.1
0x17c83  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_DisplayMask()
0x17c88  ldc.i4   0xFDFFFFFF
0x17c8d  and
0x17c8e  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_DisplayMask(int32)
0x17c93  br.s     loc_17CC7
0x17c95  ldarg.1
0x17c96  ldarg.1
0x17c97  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_DisplayMask()
0x17c9c  ldc.i4   0xFBFFFFFF
0x17ca1  and
0x17ca2  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_DisplayMask(int32)
0x17ca7  ldarg.2
0x17ca8  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_DisplayMask()
0x17cad  ldc.i4   0x8000000
0x17cb2  and
0x17cb3  brtrue.s loc_17CC7
0x17cb5  ldarg.1
0x17cb6  ldarg.1
0x17cb7  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_DisplayMask()
0x17cbc  ldc.i4   0x2000000
0x17cc1  or
0x17cc2  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_DisplayMask(int32)
0x17cc7  ldarg.0
0x17cc8  call     instance string Microsoft.Crm.Metadata.AttributeInfo::get_TypeName()
0x17ccd  ldstr    aImage// "image"
0x17cd2  ldc.i4.4
0x17cd3  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x17cd8  brfalse.s loc_17D2A
0x17cda  ldarg.2
0x17cdb  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_DisplayMask()
0x17ce0  ldc.i4   0x1000000
0x17ce5  and
0x17ce6  ldc.i4.0
0x17ce7  cgt.un
0x17ce9  ldarg.0
0x17cea  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x17cef  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_DisplayMask()
0x17cf4  ldc.i4   0x1000000
0x17cf9  and
0x17cfa  ldc.i4.0
0x17cfb  cgt.un
0x17cfd  stloc.1
0x17cfe  ldloc.1
0x17cff  beq.s    loc_17D2A
0x17d01  ldloc.1
0x17d02  brfalse.s loc_17D18
0x17d04  ldarg.1
0x17d05  ldarg.1
0x17d06  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_DisplayMask()
0x17d0b  ldc.i4   0x1000000
0x17d10  or
0x17d11  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_DisplayMask(int32)
0x17d16  br.s     loc_17D2A
0x17d18  ldarg.1
0x17d19  ldarg.1
0x17d1a  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_DisplayMask()
0x17d1f  ldc.i4   0xFEFFFFFF
0x17d24  and
0x17d25  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_DisplayMask(int32)
0x17d2a  ldarg.0
0x17d2b  ldarg.1
0x17d2c  call     instance void Microsoft.Crm.Metadata.AttributeInfo::SetManagedProperties(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag updateDescription)
0x17d31  ldarg.0
0x17d32  ldarg.1
0x17d33  ldarg.2
0x17d34  call     instance void Microsoft.Crm.Metadata.AttributeInfo::SetRollupAndCalcFieldProperties(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag updateDescription, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag existingDescription)
0x17d39  ldarg.0
0x17d3a  ldarg.1
0x17d3b  call     instance void Microsoft.Crm.Metadata.AttributeInfo::SetReferencedEntityObjectTypeCodeProperty(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag updateDescription)
0x17d40  ret
```
