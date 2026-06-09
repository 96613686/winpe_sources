# Microsoft.Crm.BusinessEntities.BusinessEntity::ReadAttribute

- ea: `0x9c730`
- end: `0x9c7a4`
- name: `Microsoft.Crm.BusinessEntities.BusinessEntity::ReadAttribute`
- size: `116`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x9c710`

## callees

- `0x10d20`
- `0x10d70`
- `0x10db0`
- `0x9c020`
- `0x9c730`
- `0xa6ab0`
- `0xa8a70`
- `0xa8b80`
- `0xa8cd0`

## string_xrefs

- `0x9c74b`: `create`
- `0x9c76b`: `update`

## pseudocode

```c

```

## disassembly

```asm
0x9c730  ldarg.3
0x9c731  ldarg.0
0x9c732  newobj   instance void Microsoft.Crm.BusinessEntities.AttributeInfo::.ctor(string attributeName, class Microsoft.Crm.BusinessEntities.IBusinessEntity entity)
0x9c737  stloc.0
0x9c738  ldarg.2
0x9c739  callvirt instance string Microsoft.Crm.BusinessEntities.IEntityDeserializationStrategy::get_CurrentMethodName()
0x9c73e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x9c743  brtrue.s loc_9C79B
0x9c745  ldarg.2
0x9c746  callvirt instance string Microsoft.Crm.BusinessEntities.IEntityDeserializationStrategy::get_CurrentMethodName()
0x9c74b  ldstr    aCreate// "create"
0x9c750  ldc.i4.5
0x9c751  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x9c756  brfalse.s loc_9C765
0x9c758  ldloc.0
0x9c759  callvirt instance class Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.BusinessEntities.AttributeInfoBase::get_Metadata()
0x9c75e  callvirt instance bool Microsoft.Crm.Metadata.AttributeMetadata::get_ValidForCreate()
0x9c763  brfalse.s loc_9C792
0x9c765  ldarg.2
0x9c766  callvirt instance string Microsoft.Crm.BusinessEntities.IEntityDeserializationStrategy::get_CurrentMethodName()
0x9c76b  ldstr    aUpdate// "update"
0x9c770  ldc.i4.5
0x9c771  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x9c776  brfalse.s loc_9C79B
0x9c778  ldloc.0
0x9c779  callvirt instance class Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.BusinessEntities.AttributeInfoBase::get_Metadata()
0x9c77e  callvirt instance bool Microsoft.Crm.Metadata.AttributeMetadata::get_ValidForUpdate()
0x9c783  brtrue.s loc_9C79B
0x9c785  ldloc.0
0x9c786  callvirt instance class Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.BusinessEntities.AttributeInfoBase::get_Metadata()
0x9c78b  callvirt instance bool Microsoft.Crm.Metadata.AttributeMetadata::get_IsPrimaryKey()
0x9c790  brtrue.s loc_9C79B
0x9c792  ldloc.0
0x9c793  ldarg.1
0x9c794  ldarg.2
0x9c795  callvirt instance void Microsoft.Crm.BusinessEntities.AttributeInfoBase::SkipDeserialize(class Microsoft.Crm.BusinessEntities.EntityDeserializationContext context, class Microsoft.Crm.BusinessEntities.IEntityDeserializationStrategy deserializationStrategy)
0x9c79a  ret
0x9c79b  ldloc.0
0x9c79c  ldarg.1
0x9c79d  ldarg.2
0x9c79e  callvirt instance void Microsoft.Crm.BusinessEntities.AttributeInfoBase::Deserialize(class Microsoft.Crm.BusinessEntities.EntityDeserializationContext context, class Microsoft.Crm.BusinessEntities.IEntityDeserializationStrategy deserializationStrategy)
0x9c7a3  ret
```
