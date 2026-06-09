# Microsoft.Crm.Asynchronous.BulkDeleteOperation::CreateFailureRow

- ea: `0x1fb0`
- end: `0x2142`
- name: `Microsoft.Crm.Asynchronous.BulkDeleteOperation::CreateFailureRow`
- size: `402`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1ba0`
- `0x1e80`

## callees

- `0x1270`
- `0x1490`
- `0x1fb0`

## string_xrefs

- `0x20d0`: `Error in Delete. recordID {0}`
- `0x2125`: `Creating a bulk delete failure row inside exception handler failed: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x1fb0  ldarg.0
0x1fb1  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BulkDeleteOperation::_organizationId
0x1fb6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x1fbb  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1fc0  ldarg.3
0x1fc1  ldc.i4.1
0x1fc2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x1fc7  stloc.0
0x1fc8  ldsfld   string [mscorlib]System.String::Empty
0x1fcd  stloc.1
0x1fce  ldsfld   string [mscorlib]System.String::Empty
0x1fd3  stloc.2
0x1fd4  ldsfld   string [mscorlib]System.String::Empty
0x1fd9  stloc.3
0x1fda  ldc.i4.0
0x1fdb  stloc.s  4
0x1fdd  ldloc.0
0x1fde  brfalse  loc_20C8
0x1fe3  ldloc.0
0x1fe4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x1fe9  brtrue.s loc_1FF2
0x1feb  ldsfld   string [mscorlib]System.String::Empty
0x1ff0  br.s     loc_1FFD
0x1ff2  ldloc.0
0x1ff3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x1ff8  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_PhysicalName()
0x1ffd  stloc.1
0x1ffe  ldloc.0
0x1fff  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PhysicalName()
0x2004  brtrue.s loc_200D
0x2006  ldsfld   string [mscorlib]System.String::Empty
0x200b  br.s     loc_2013
0x200d  ldloc.0
0x200e  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PhysicalName()
0x2013  stloc.2
0x2014  ldloc.0
0x2015  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryField()
0x201a  brtrue.s loc_2023
0x201c  ldsfld   string [mscorlib]System.String::Empty
0x2021  br.s     loc_202E
0x2023  ldloc.0
0x2024  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryField()
0x2029  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_PhysicalName()
0x202e  stloc.3
0x202f  ldloc.0
0x2030  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x2035  stloc.s  4
0x2037  ldloc.0
0x2038  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsActivity()
0x203d  brfalse  loc_20C8
0x2042  ldarg.0
0x2043  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BulkDeleteOperation::_organizationId
0x2048  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x204d  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2052  ldstr    aActivitypointe// "activitypointer"
0x2057  ldc.i4.1
0x2058  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x205d  stloc.s  5
0x205f  ldloc.s  5
0x2061  brfalse.s loc_20C8
0x2063  ldloc.s  5
0x2065  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PhysicalName()
0x206a  brtrue.s loc_2073
0x206c  ldsfld   string [mscorlib]System.String::Empty
0x2071  br.s     loc_207A
0x2073  ldloc.s  5
0x2075  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PhysicalName()
0x207a  stloc.2
0x207b  ldloc.s  5
0x207d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x2082  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_PlatformName()
0x2087  brtrue.s loc_2090
0x2089  ldsfld   string [mscorlib]System.String::Empty
0x208e  br.s     loc_209C
0x2090  ldloc.s  5
0x2092  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x2097  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_PlatformName()
0x209c  stloc.1
0x209d  ldloc.s  5
0x209f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryField()
0x20a4  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_PhysicalName()
0x20a9  brtrue.s loc_20B2
0x20ab  ldsfld   string [mscorlib]System.String::Empty
0x20b0  br.s     loc_20BE
0x20b2  ldloc.s  5
0x20b4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryField()
0x20b9  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_PhysicalName()
0x20be  stloc.3
0x20bf  ldloc.s  5
0x20c1  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x20c6  stloc.s  4
0x20c8  ldarg.0
0x20c9  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BulkDeleteOperation::_organizationId
0x20ce  ldc.i4.s 0x15
0x20d0  ldstr    aErrorInDeleteR_0// "Error in Delete. recordID {0}"
0x20d5  ldc.i4.1
0x20d6  newarr   [mscorlib]System.Object
0x20db  dup
0x20dc  ldc.i4.0
0x20dd  ldarg.2
0x20de  box      [mscorlib]System.Guid
0x20e3  stelem.ref
0x20e4  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x20e9  ldarg.0
0x20ea  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteDataAccess Microsoft.Crm.Asynchronous.BulkDeleteOperation::_bulkDeleteDataAccess
0x20ef  ldarg.1
0x20f0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_EventId()
0x20f5  callvirt instance void Microsoft.Crm.Asynchronous.BulkDeleteDataAccess::UpdateFailureCount(valuetype [mscorlib]System.Guid asyncOperationId)
0x20fa  ldarg.0
0x20fb  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteDataAccess Microsoft.Crm.Asynchronous.BulkDeleteOperation::_bulkDeleteDataAccess
0x2100  ldarg.1
0x2101  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_EventId()
0x2106  ldarg.s  6
0x2108  ldarg.s  5
0x210a  ldarg.s  4
0x210c  ldarg.2
0x210d  ldloc.s  4
0x210f  ldloc.2
0x2110  ldloc.1
0x2111  ldloc.3
0x2112  callvirt instance void Microsoft.Crm.Asynchronous.BulkDeleteDataAccess::LogDeletionFailure(valuetype [mscorlib]System.Guid asyncOperationId, int32 crmErrorCode, string errorDescription, int32 orderedQueryIndex, valuetype [mscorlib]System.Guid regardingObjectId, int32 objectTypeCode, string entityPhysicalName, string primaryKeyPhysicalName, string primaryfieldPhysicalName)
0x2117  leave.s  loc_2141
0x2119  stloc.s  6
0x211b  ldloc.s  6
0x211d  ldarg.1
0x211e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x2123  ldc.i4.s 0x15
0x2125  ldstr    aCreatingABulkD// "Creating a bulk delete failure row insi"...
0x212a  ldc.i4.1
0x212b  newarr   [mscorlib]System.Object
0x2130  dup
0x2131  ldc.i4.0
0x2132  ldloc.s  6
0x2134  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x2139  stelem.ref
0x213a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x213f  leave.s  loc_2141
0x2141  ret
```
