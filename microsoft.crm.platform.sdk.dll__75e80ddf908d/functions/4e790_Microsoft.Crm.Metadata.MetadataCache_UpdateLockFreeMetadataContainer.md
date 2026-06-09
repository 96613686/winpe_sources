# Microsoft.Crm.Metadata.MetadataCache::UpdateLockFreeMetadataContainer

- ea: `0x4e790`
- end: `0x4e833`
- name: `Microsoft.Crm.Metadata.MetadataCache::UpdateLockFreeMetadataContainer`
- size: `163`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x4e710`

## callees

- `0x4b560`
- `0x4b580`
- `0x4e790`
- `0x4e840`
- `0x4e890`
- `0x51730`
- `0x593e0`
- `0x5d600`
- `0x797f0`

## string_xrefs

- `0x4e7ad`: `UpdateLockFreeMetadataContainer called on non-LockFreeContainer!`
- `0x4e7ff`: `Failed to update LockFreeMetadataCache! Exception: `

## pseudocode

```c

```

## disassembly

```asm
0x4e790  ldstr    aContainerusedt// "ContainerUsedToFlush"
0x4e795  ldstr    aLockfreemetada// "LockFreeMetadataContainer"
0x4e79a  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x4e79f  ldarg.1
0x4e7a0  call     class Microsoft.Crm.Metadata.LockFreeMetadataContainer Microsoft.Crm.Metadata.MetadataCache::GetLockFreeBaseContainer(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext organizationContext)
0x4e7a5  stloc.0
0x4e7a6  ldloc.0
0x4e7a7  brtrue.s loc_4E7CA
0x4e7a9  ldnull
0x4e7aa  ldarg.0
0x4e7ab  ldc.i4.s 0x19
0x4e7ad  ldstr    aUpdatelockfree// "UpdateLockFreeMetadataContainer called "...
0x4e7b2  ldc.i4.0
0x4e7b3  newarr   [mscorlib]System.Object
0x4e7b8  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4e7bd  ldsfld   class Microsoft.Crm.Metadata.MetadataCacheStorage Microsoft.Crm.Metadata.MetadataCacheStorage::StaticInstance
0x4e7c2  ldarg.0
0x4e7c3  callvirt instance void Microsoft.Crm.Metadata.MetadataCacheStorage::FlushNoNotification(valuetype [mscorlib]System.Guid organizationId)
0x4e7c8  leave.s  loc_4E832
0x4e7ca  ldloc.0
0x4e7cb  callvirt instance class Microsoft.Crm.Metadata.IMetadataContainer Microsoft.Crm.Metadata.DynamicMetadataContainer::Clone()
0x4e7d0  stloc.1
0x4e7d1  ldarg.1
0x4e7d2  newobj   instance void Microsoft.Crm.Metadata.RefreshableMetadataCacheLoader::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext organizationContext)
0x4e7d7  ldloc.1
0x4e7d8  ldc.i4   0x5C90F
0x4e7dd  ldnull
0x4e7de  callvirt instance class Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::BuildMetadataCacheFromMetadataContainer(class Microsoft.Crm.Metadata.IMetadataContainer container, valuetype Microsoft.Crm.Metadata.LoadMasks masks, class [Microsoft.Crm.Core]Microsoft.Crm.CounterList counter)
0x4e7e3  stloc.2
0x4e7e4  ldarg.0
0x4e7e5  ldarg.2
0x4e7e6  ldloc.2
0x4e7e7  call     void Microsoft.Crm.Metadata.MetadataCache::UpdateMetadataContainer(valuetype [mscorlib]System.Guid organizationId, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext sqlExecutionContext, class Microsoft.Crm.Metadata.DynamicMetadataCache cache)
0x4e7ec  ldsfld   class Microsoft.Crm.Metadata.MetadataCacheStorage Microsoft.Crm.Metadata.MetadataCacheStorage::StaticInstance
0x4e7f1  ldarg.0
0x4e7f2  ldloc.2
0x4e7f3  callvirt instance void Microsoft.Crm.Metadata.MetadataCacheStorage::AddEntry(valuetype [mscorlib]System.Guid organizationId, class Microsoft.Crm.Metadata.DynamicMetadataCache metadataCache)
0x4e7f8  leave.s  loc_4E832
0x4e7fa  stloc.3
0x4e7fb  ldloc.3
0x4e7fc  ldarg.0
0x4e7fd  ldc.i4.s 0x19
0x4e7ff  ldstr    aFailedToUpdate// "Failed to update LockFreeMetadataCache!"...
0x4e804  ldloc.3
0x4e805  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x4e80a  call     string [mscorlib]System.String::Concat(string, string)
0x4e80f  ldc.i4.0
0x4e810  newarr   [mscorlib]System.Object
0x4e815  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4e81a  ldc.i4.0
0x4e81b  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x4e820  call     void Microsoft.Crm.Caching.CacheConfiguration::set_CachedIsLockFreeMetadataCacheEnabled(valuetype [mscorlib]System.Nullable`1<bool> value)
0x4e825  ldsfld   class Microsoft.Crm.Metadata.MetadataCacheStorage Microsoft.Crm.Metadata.MetadataCacheStorage::StaticInstance
0x4e82a  ldarg.0
0x4e82b  callvirt instance void Microsoft.Crm.Metadata.MetadataCacheStorage::FlushNoNotification(valuetype [mscorlib]System.Guid organizationId)
0x4e830  leave.s  loc_4E832
0x4e832  ret
```
