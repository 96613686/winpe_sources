# Microsoft.Crm.Asynchronous.EntityKeyIndexCreateOperation::CreateEntityKeyIndex

- ea: `0x29c0`
- end: `0x2aa1`
- name: `Microsoft.Crm.Asynchronous.EntityKeyIndexCreateOperation::CreateEntityKeyIndex`
- size: `225`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x2600`

## callees

- `0x29c0`

## pseudocode

```c

```

## disassembly

```asm
0x29c0  ldloca.s 0
0x29c2  ldarg.1
0x29c3  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_Data()
0x29c8  call     instance void [mscorlib]System.Guid::.ctor(string)
0x29cd  ldarg.2
0x29ce  call     void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::Flush(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x29d3  ldarg.2
0x29d4  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x29d9  ldloc.0
0x29da  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityKeyMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntityKey(valuetype [mscorlib]System.Guid)
0x29df  stloc.1
0x29e0  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x29e5  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.IndexAndConstraintManagementService [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.IndexAndConstraintManagementService::get_Instance()
0x29ea  ldloc.1
0x29eb  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityKeyMetadata::get_Name()
0x29f0  callvirt instance string [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.IndexAndConstraintManagementService::CreateIndexNameFromEntityKeyName(string)
0x29f5  ldc.i4.0
0x29f6  ldc.i4.s 0x50
0x29f8  ldc.i4.1
0x29f9  ldc.i4.s 0xB
0x29fb  ldc.i4.0
0x29fc  ldc.i4.0
0x29fd  ldloc.1
0x29fe  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityKeyMetadata::get_EntityId()
0x2a03  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.IndexData::.ctor(valuetype [mscorlib]System.Guid, string, bool, int32, bool, int32, bool, bool, valuetype [mscorlib]System.Guid)
0x2a08  stloc.2
0x2a09  ldloc.1
0x2a0a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata[] [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityKeyMetadata::get_KeyAttributesSortedByIndexOrder()
0x2a0f  ldlen
0x2a10  conv.i4
0x2a11  stloc.s  4
0x2a13  ldc.i4.0
0x2a14  stloc.s  5
0x2a16  br.s     loc_2A4F
0x2a18  ldloc.1
0x2a19  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata[] [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityKeyMetadata::get_KeyAttributesSortedByIndexOrder()
0x2a1e  ldloc.s  5
0x2a20  ldelem.ref
0x2a21  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Id()
0x2a26  stloc.3
0x2a27  ldloc.2
0x2a28  ldloc.3
0x2a29  ldloc.s  5
0x2a2b  ldc.i4.0
0x2a2c  ldc.i4.0
0x2a2d  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.IndexAttribute::.ctor(valuetype [mscorlib]System.Guid, int32, bool, bool)
0x2a32  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.IndexData::AddIndexAttribute(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.IndexAttribute)
0x2a37  ldloc.2
0x2a38  ldloc.3
0x2a39  ldstr    aIsNotNull// "is not null"
0x2a3e  ldnull
0x2a3f  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.IndexFilter::.ctor(valuetype [mscorlib]System.Guid, string, string)
0x2a44  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.IndexData::AddIndexFilter(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.IndexFilter)
0x2a49  ldloc.s  5
0x2a4b  ldc.i4.1
0x2a4c  add
0x2a4d  stloc.s  5
0x2a4f  ldloc.s  5
0x2a51  ldloc.s  4
0x2a53  blt.s    loc_2A18
0x2a55  ldarg.2
0x2a56  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2a5b  ldloc.1
0x2a5c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityKeyMetadata::get_EntityId()
0x2a61  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(valuetype [mscorlib]System.Guid)
0x2a66  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x2a6b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Id()
0x2a70  stloc.3
0x2a71  ldloc.2
0x2a72  ldloc.3
0x2a73  ldloc.s  4
0x2a75  ldc.i4.1
0x2a76  ldc.i4.0
0x2a77  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.IndexAttribute::.ctor(valuetype [mscorlib]System.Guid, int32, bool, bool)
0x2a7c  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.IndexData::AddIndexAttribute(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.IndexAttribute)
0x2a81  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.IndexAndConstraintManagementService [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.IndexAndConstraintManagementService::get_Instance()
0x2a86  ldloc.2
0x2a87  ldloc.1
0x2a88  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityKeyMetadata::get_EntityId()
0x2a8d  ldc.i4.1
0x2a8e  ldc.i4.1
0x2a8f  newobj   instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.DatabaseIndexMetadataProvider::.ctor()
0x2a94  ldarg.2
0x2a95  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x2a9a  ldc.i4.1
0x2a9b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.IndexAndConstraintManagementService::CreateStandardSqlIndexOrConstraint(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.IndexData, valuetype [mscorlib]System.Guid, bool, bool, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.IIndexMetadataProvider, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext, valuetype [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.CrmIndexManagers)
0x2aa0  ret
```
