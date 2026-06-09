# Microsoft.Crm.Asynchronous.BulkDeleteOperationChild::CreateFailureRow

- ea: `0x2fb0`
- end: `0x3095`
- name: `Microsoft.Crm.Asynchronous.BulkDeleteOperationChild::CreateFailureRow`
- size: `229`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x2ea0`

## callees

- `0x1270`
- `0x1490`
- `0x2fb0`

## string_xrefs

- `0x303c`: `Error in Delete. recordID {0}`

## pseudocode

```c

```

## disassembly

```asm
0x2fb0  ldarg.0
0x2fb1  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BulkDeleteOperationChild::_organizationId
0x2fb6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x2fbb  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2fc0  ldarg.3
0x2fc1  ldc.i4.1
0x2fc2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x2fc7  dup
0x2fc8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x2fcd  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_PhysicalName()
0x2fd2  stloc.0
0x2fd3  dup
0x2fd4  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PhysicalName()
0x2fd9  stloc.1
0x2fda  dup
0x2fdb  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryField()
0x2fe0  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_PhysicalName()
0x2fe5  stloc.2
0x2fe6  dup
0x2fe7  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x2fec  stloc.3
0x2fed  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsActivity()
0x2ff2  brfalse.s loc_3034
0x2ff4  ldarg.0
0x2ff5  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BulkDeleteOperationChild::_organizationId
0x2ffa  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x2fff  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3004  ldstr    aActivitypointe// "activitypointer"
0x3009  ldc.i4.1
0x300a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x300f  dup
0x3010  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PhysicalName()
0x3015  stloc.1
0x3016  dup
0x3017  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x301c  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_PlatformName()
0x3021  stloc.0
0x3022  dup
0x3023  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryField()
0x3028  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_PhysicalName()
0x302d  stloc.2
0x302e  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x3033  stloc.3
0x3034  ldarg.0
0x3035  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BulkDeleteOperationChild::_organizationId
0x303a  ldc.i4.s 0x15
0x303c  ldstr    aErrorInDeleteR_0// "Error in Delete. recordID {0}"
0x3041  ldc.i4.1
0x3042  newarr   [mscorlib]System.Object
0x3047  dup
0x3048  ldc.i4.0
0x3049  ldarg.2
0x304a  box      [mscorlib]System.Guid
0x304f  stelem.ref
0x3050  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3055  ldarg.0
0x3056  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteDataAccess Microsoft.Crm.Asynchronous.BulkDeleteOperationChild::_bulkDeleteDataAccess
0x305b  ldarg.1
0x305c  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_RequestId()
0x3061  stloc.s  4
0x3063  ldloca.s 4
0x3065  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x306a  callvirt instance void Microsoft.Crm.Asynchronous.BulkDeleteDataAccess::UpdateFailureCount(valuetype [mscorlib]System.Guid asyncOperationId)
0x306f  ldarg.0
0x3070  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteDataAccess Microsoft.Crm.Asynchronous.BulkDeleteOperationChild::_bulkDeleteDataAccess
0x3075  ldarg.1
0x3076  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_RequestId()
0x307b  stloc.s  4
0x307d  ldloca.s 4
0x307f  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x3084  ldarg.s  6
0x3086  ldarg.s  5
0x3088  ldarg.s  4
0x308a  ldarg.2
0x308b  ldloc.3
0x308c  ldloc.1
0x308d  ldloc.0
0x308e  ldloc.2
0x308f  callvirt instance void Microsoft.Crm.Asynchronous.BulkDeleteDataAccess::LogDeletionFailure(valuetype [mscorlib]System.Guid asyncOperationId, int32 crmErrorCode, string errorDescription, int32 orderedQueryIndex, valuetype [mscorlib]System.Guid regardingObjectId, int32 objectTypeCode, string entityPhysicalName, string primaryKeyPhysicalName, string primaryfieldPhysicalName)
0x3094  ret
```
