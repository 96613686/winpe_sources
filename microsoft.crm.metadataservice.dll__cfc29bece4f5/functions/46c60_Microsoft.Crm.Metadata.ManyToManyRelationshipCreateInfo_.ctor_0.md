# Microsoft.Crm.Metadata.ManyToManyRelationshipCreateInfo::.ctor_0

- ea: `0x46c60`
- end: `0x46d63`
- name: `Microsoft.Crm.Metadata.ManyToManyRelationshipCreateInfo::.ctor_0`
- size: `259`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x47380`

## callees

- `0x46b70`
- `0x46c60`
- `0x48cb0`
- `0x49550`
- `0x49560`
- `0x49570`
- `0x49590`
- `0x499f0`

## string_xrefs

- `0x46c92`: `createData`
- `0x46ca2`: `createData.EntityOneRelationshipRole`
- `0x46cb2`: `createData.EntityTwoRelationshipRole`

## pseudocode

```c

```

## disassembly

```asm
0x46c60  ldarg.0
0x46c61  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x46c66  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.ManyToManyRelationshipCreateInfo::_intersectEntityId
0x46c6b  ldarg.0
0x46c6c  ldc.i4.1
0x46c6d  stfld    bool Microsoft.Crm.Metadata.ManyToManyRelationshipCreateInfo::_isCustomizable
0x46c72  ldarg.0
0x46c73  ldc.i4.1
0x46c74  stfld    bool Microsoft.Crm.Metadata.ManyToManyRelationshipCreateInfo::_isCustomrelationship
0x46c79  ldarg.0
0x46c7a  ldarg.1
0x46c7b  callvirt instance class Microsoft.Crm.Metadata.EntityRelationshipRoleData Microsoft.Crm.Metadata.ManyToManyRelationshipCreateData::get_EntityOneRelationshipRole()
0x46c80  ldarg.1
0x46c81  callvirt instance class Microsoft.Crm.Metadata.EntityRelationshipRoleData Microsoft.Crm.Metadata.ManyToManyRelationshipCreateData::get_EntityTwoRelationshipRole()
0x46c86  ldarg.1
0x46c87  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> Microsoft.Crm.Metadata.ManyToManyRelationshipCreateData::get_IsValidForAdvancedFind()
0x46c8c  call     instance void Microsoft.Crm.Metadata.ManyToManyRelationshipInfo::.ctor(class Microsoft.Crm.Metadata.EntityRelationshipRoleData entityOneRoleData, class Microsoft.Crm.Metadata.EntityRelationshipRoleData entityTwoRoleData, valuetype [mscorlib]System.Nullable`1<bool> isValidForAdvancedFind)
0x46c91  ldarg.1
0x46c92  ldstr    aCreatedata// "createData"
0x46c97  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x46c9c  ldarg.1
0x46c9d  callvirt instance class Microsoft.Crm.Metadata.EntityRelationshipRoleData Microsoft.Crm.Metadata.ManyToManyRelationshipCreateData::get_EntityOneRelationshipRole()
0x46ca2  ldstr    aCreatedataEnti// "createData.EntityOneRelationshipRole"
0x46ca7  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x46cac  ldarg.1
0x46cad  callvirt instance class Microsoft.Crm.Metadata.EntityRelationshipRoleData Microsoft.Crm.Metadata.ManyToManyRelationshipCreateData::get_EntityTwoRelationshipRole()
0x46cb2  ldstr    aCreatedataEnti_0// "createData.EntityTwoRelationshipRole"
0x46cb7  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x46cbc  ldarg.1
0x46cbd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.EntityRelationshipData::get_EntityRelationshipDescription()
0x46cc2  ldstr    aSchemaname// "schemaname"
0x46cc7  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x46ccc  brtrue.s loc_46CE9
0x46cce  ldarg.0
0x46ccf  ldarg.1
0x46cd0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.EntityRelationshipData::get_EntityRelationshipDescription()
0x46cd5  ldstr    aSchemaname// "schemaname"
0x46cda  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x46cdf  castclass [mscorlib]System.String
0x46ce4  stfld    string Microsoft.Crm.Metadata.ManyToManyRelationshipCreateInfo::_schemaName
0x46ce9  ldarg.1
0x46cea  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.EntityRelationshipData::get_EntityRelationshipDescription()
0x46cef  ldstr    aIscustomizable// "iscustomizable"
0x46cf4  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x46cf9  brtrue.s loc_46D16
0x46cfb  ldarg.0
0x46cfc  ldarg.1
0x46cfd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.EntityRelationshipData::get_EntityRelationshipDescription()
0x46d02  ldstr    aIscustomizable// "iscustomizable"
0x46d07  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x46d0c  unbox.any [mscorlib]System.Boolean
0x46d11  stfld    bool Microsoft.Crm.Metadata.ManyToManyRelationshipCreateInfo::_isCustomizable
0x46d16  ldarg.0
0x46d17  ldarg.1
0x46d18  callvirt instance string Microsoft.Crm.Metadata.ManyToManyRelationshipCreateData::get_IntersectEntitySchemaName()
0x46d1d  stfld    string Microsoft.Crm.Metadata.ManyToManyRelationshipCreateInfo::_intersectEntitySchemaName
0x46d22  ldarg.0
0x46d23  ldarg.1
0x46d24  callvirt instance class Microsoft.Crm.Metadata.EntityRelationshipRoleData Microsoft.Crm.Metadata.ManyToManyRelationshipCreateData::get_EntityOneRelationshipRole()
0x46d29  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.EntityRelationshipRoleData::get_EntityRelationshipRoleDescription()
0x46d2e  ldstr    aEntityid// "entityid"
0x46d33  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x46d38  unbox.any [mscorlib]System.Guid
0x46d3d  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.ManyToManyRelationshipCreateInfo::_entityOneId
0x46d42  ldarg.0
0x46d43  ldarg.1
0x46d44  callvirt instance class Microsoft.Crm.Metadata.EntityRelationshipRoleData Microsoft.Crm.Metadata.ManyToManyRelationshipCreateData::get_EntityTwoRelationshipRole()
0x46d49  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.EntityRelationshipRoleData::get_EntityRelationshipRoleDescription()
0x46d4e  ldstr    aEntityid// "entityid"
0x46d53  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x46d58  unbox.any [mscorlib]System.Guid
0x46d5d  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.ManyToManyRelationshipCreateInfo::_entityTwoId
0x46d62  ret
```
