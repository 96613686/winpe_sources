# Microsoft.Crm.Metadata.EntityRelationshipRelationshipsDescription::FillPropertiesFromDataReader

- ea: `0x360e0`
- end: `0x3618e`
- name: `Microsoft.Crm.Metadata.EntityRelationshipRelationshipsDescription::FillPropertiesFromDataReader`
- size: `174`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x36540`

## callees

- `0x18a90`
- `0x360e0`
- `0x362b0`
- `0x362d0`
- `0x362f0`

## string_xrefs

- `0x360e9`: `EntityRelationshipRelationshipsId`
- `0x3610b`: `EntityRelationshipRelationshipsId`

## pseudocode

```c

```

## disassembly

```asm
0x360e0  ldarg.0
0x360e1  ldarg.1
0x360e2  ldarg.2
0x360e3  call     instance void Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::FillPropertiesFromDataReader(class [System.Data]System.Data.IDataReader reader, [opt] class Microsoft.Crm.Metadata.MetadataForMetadata metadataForMetadata)
0x360e8  ldarg.1
0x360e9  ldstr    aEntityrelation_12// "EntityRelationshipRelationshipsId"
0x360ee  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x360f3  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x360f8  ldtoken  [mscorlib]System.DBNull
0x360fd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x36102  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x36107  brfalse.s loc_3611F
0x36109  ldarg.0
0x3610a  ldarg.1
0x3610b  ldstr    aEntityrelation_12// "EntityRelationshipRelationshipsId"
0x36110  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x36115  unbox.any [mscorlib]System.Guid
0x3611a  callvirt instance void Microsoft.Crm.Metadata.EntityRelationshipRelationshipsDescription::set_EntityRelationshipRelationshipsId(valuetype [mscorlib]System.Guid value)
0x3611f  ldarg.1
0x36120  ldstr    aEntityrelation_1// "EntityRelationshipId"
0x36125  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3612a  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3612f  ldtoken  [mscorlib]System.DBNull
0x36134  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x36139  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3613e  brfalse.s loc_36156
0x36140  ldarg.0
0x36141  ldarg.1
0x36142  ldstr    aEntityrelation_1// "EntityRelationshipId"
0x36147  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3614c  unbox.any [mscorlib]System.Guid
0x36151  callvirt instance void Microsoft.Crm.Metadata.EntityRelationshipRelationshipsDescription::set_EntityRelationshipId(valuetype [mscorlib]System.Guid value)
0x36156  ldarg.1
0x36157  ldstr    aRelationshipid_0// "RelationshipId"
0x3615c  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x36161  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x36166  ldtoken  [mscorlib]System.DBNull
0x3616b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x36170  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x36175  brfalse.s loc_3618D
0x36177  ldarg.0
0x36178  ldarg.1
0x36179  ldstr    aRelationshipid_0// "RelationshipId"
0x3617e  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x36183  unbox.any [mscorlib]System.Guid
0x36188  callvirt instance void Microsoft.Crm.Metadata.EntityRelationshipRelationshipsDescription::set_RelationshipId(valuetype [mscorlib]System.Guid value)
0x3618d  ret
```
