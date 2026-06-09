# Microsoft.Crm.Metadata.MetadataCache::Flush_2

- ea: `0x4e580`
- end: `0x4e6ca`
- name: `Microsoft.Crm.Metadata.MetadataCache::Flush_2`
- size: `330`
- prototype: ``
- caller_count: `9`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x4e350`
- `0x4e430`
- `0x4e460`
- `0x4e470`
- `0x4e480`
- `0x4e490`
- `0x4e4a0`
- `0x4eb60`
- `0x4f120`

## callees

- `0x1e620`
- `0x1e8e0`
- `0x4cb30`
- `0x4cc30`
- `0x4cff0`
- `0x4e4d0`
- `0x4e510`
- `0x4e580`
- `0x4e6d0`
- `0x4e8d0`
- `0x4e910`

## string_xrefs

- `0x4e682`: `MetadataCache`
- `0x4e687`: `MetadataCache`
- `0x4e5fa`: `Flushing metadata cache for organization {0} - with fireNotification as {1}`
- `0x4e621`: `Metadata_BEGIN_Microsoft.Crm.Metadata.MetadataCache.Flush`
- `0x4e6b4`: `Metadata_END_Microsoft.Crm.Metadata.MetadataCache.Flush`

## pseudocode

```c

```

## disassembly

```asm
0x4e580  ldarg.0
0x4e581  brtrue.s loc_4E58A
0x4e583  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4e588  br.s     loc_4E590
0x4e58a  ldarg.0
0x4e58b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x4e590  stloc.0
0x4e591  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInClientContext()
0x4e596  brfalse.s loc_4E5AD
0x4e598  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInHosterContext()
0x4e59d  brtrue.s loc_4E5AD
0x4e59f  call     bool Microsoft.Crm.Metadata.MetadataCache::get_UseOutlookFlushMode()
0x4e5a4  brfalse.s loc_4E5AD
0x4e5a6  ldloc.0
0x4e5a7  call     void Microsoft.Crm.Metadata.MetadataCache::ClientFlush(valuetype [mscorlib]System.Guid organizationId)
0x4e5ac  ret
0x4e5ad  ldc.i4.0
0x4e5ae  stloc.1
0x4e5af  ldarg.0
0x4e5b0  ldc.i4.0
0x4e5b1  call     var<u1> class [Microsoft.Crm]Microsoft.Crm.StaticPerThreadCacheManager`1<class Microsoft.Crm.Metadata.PerThreadMetadataCacheManager>::TryGetOrCreateInstance(!!T0, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4e5b6  stloc.2
0x4e5b7  ldloc.2
0x4e5b8  brfalse.s loc_4E5D0
0x4e5ba  ldarg.3
0x4e5bb  brfalse.s loc_4E5C7
0x4e5bd  ldloc.2
0x4e5be  ldarg.0
0x4e5bf  ldarg.2
0x4e5c0  callvirt instance void Microsoft.Crm.Metadata.PerThreadMetadataCacheManager::Flush(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context, bool forceRemoveCache)
0x4e5c5  br.s     loc_4E5D0
0x4e5c7  ldloc.2
0x4e5c8  ldc.i4.0
0x4e5c9  ldarg.0
0x4e5ca  callvirt instance bool Microsoft.Crm.Metadata.PerThreadMetadataCacheManager::FlushPerThreadCacheAndMarkStandardCacheForRemovalIfRequired(bool allOrgs, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4e5cf  stloc.1
0x4e5d0  ldloc.1
0x4e5d1  brfalse.s loc_4E5F7
0x4e5d3  ldloc.2
0x4e5d4  callvirt instance class Microsoft.Crm.Metadata.MetadataCacheDictionaryEntry Microsoft.Crm.Metadata.PerThreadMetadataCacheManager::get_InternalCache()
0x4e5d9  brfalse.s loc_4E5E9
0x4e5db  call     class Microsoft.Crm.Metadata.LabelCache Microsoft.Crm.Metadata.LabelCache::Instance()
0x4e5e0  ldarg.0
0x4e5e1  ldarg.1
0x4e5e2  ldc.i4.0
0x4e5e3  callvirt instance void Microsoft.Crm.Metadata.LabelCache::Flush(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context, [opt] bool fireNotification, [opt] bool forceRemoveCache)
0x4e5e8  ret
0x4e5e9  call     class Microsoft.Crm.Metadata.LabelCache Microsoft.Crm.Metadata.LabelCache::Instance()
0x4e5ee  ldarg.0
0x4e5ef  ldarg.1
0x4e5f0  ldc.i4.1
0x4e5f1  callvirt instance void Microsoft.Crm.Metadata.LabelCache::Flush(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context, [opt] bool fireNotification, [opt] bool forceRemoveCache)
0x4e5f6  ret
0x4e5f7  ldloc.0
0x4e5f8  ldc.i4.s 0x19
0x4e5fa  ldstr    aFlushingMetada// "Flushing metadata cache for organizatio"...
0x4e5ff  ldc.i4.2
0x4e600  newarr   [mscorlib]System.Object
0x4e605  dup
0x4e606  ldc.i4.0
0x4e607  ldloc.0
0x4e608  box      [mscorlib]System.Guid
0x4e60d  stelem.ref
0x4e60e  dup
0x4e60f  ldc.i4.1
0x4e610  ldarg.1
0x4e611  box      [mscorlib]System.Boolean
0x4e616  stelem.ref
0x4e617  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4e61c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4e621  ldstr    aMetadataBeginM// "Metadata_BEGIN_Microsoft.Crm.Metadata.M"...
0x4e626  ldc.i4.0
0x4e627  newarr   [mscorlib]System.Object
0x4e62c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4e631  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x4e636  ldloc.0
0x4e637  ldarg.0
0x4e638  ldarg.2
0x4e639  call     bool Microsoft.Crm.Metadata.MetadataCache::FlushInternal(valuetype [mscorlib]System.Guid organizationId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context, [opt] bool forceRemoveCache)
0x4e63e  stloc.3
0x4e63f  ldstr    aNotificationte// "NotificationTestHookEnabled"
0x4e644  ldc.i4.0
0x4e645  box      [mscorlib]System.Int32
0x4e64a  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x4e64f  unbox.any [mscorlib]System.Int32
0x4e654  ldc.i4.1
0x4e655  bne.un.s loc_4E65D
0x4e657  ldarg.0
0x4e658  call     void Microsoft.Crm.Metadata.MetadataCache::PostFlushNotification(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4e65d  ldarg.1
0x4e65e  brfalse.s loc_4E6A2
0x4e660  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInClientContext()
0x4e665  brtrue.s loc_4E6A2
0x4e667  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInCrmInternalToolContext()
0x4e66c  brtrue.s loc_4E6A2
0x4e66e  call     string [Microsoft.Crm]Microsoft.Crm.CacheItemRemoveNotificationDataHelper::get_LocalServerId()
0x4e673  call     string [Microsoft.Crm.Core]Microsoft.Crm.RegControl::GetProcessName()
0x4e678  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x4e67d  callvirt instance string [mscorlib]System.AppDomain::get_FriendlyName()
0x4e682  ldstr    aMetadatacache// "MetadataCache"
0x4e687  ldstr    aMetadatacache// "MetadataCache"
0x4e68c  newobj   instance void [Microsoft.Crm]Microsoft.Crm.CacheItemRemoveNotificationData::.ctor(string, string, string, string, string)
0x4e691  stloc.s  4
0x4e693  ldc.i4.s 0x23
0x4e695  ldloc.s  4
0x4e697  callvirt instance string [Microsoft.Crm]Microsoft.Crm.CacheItemRemoveNotificationData::DataAsString()
0x4e69c  ldarg.0
0x4e69d  call     void Microsoft.Crm.Metadata.MetadataCache::FireEvent(valuetype [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType eventType, string eventData, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4e6a2  call     class Microsoft.Crm.Metadata.LabelCache Microsoft.Crm.Metadata.LabelCache::Instance()
0x4e6a7  ldarg.0
0x4e6a8  ldarg.1
0x4e6a9  ldloc.3
0x4e6aa  callvirt instance void Microsoft.Crm.Metadata.LabelCache::Flush(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context, [opt] bool fireNotification, [opt] bool forceRemoveCache)
0x4e6af  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4e6b4  ldstr    aMetadataEndMic// "Metadata_END_Microsoft.Crm.Metadata.Met"...
0x4e6b9  ldc.i4.0
0x4e6ba  newarr   [mscorlib]System.Object
0x4e6bf  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4e6c4  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x4e6c9  ret
```
