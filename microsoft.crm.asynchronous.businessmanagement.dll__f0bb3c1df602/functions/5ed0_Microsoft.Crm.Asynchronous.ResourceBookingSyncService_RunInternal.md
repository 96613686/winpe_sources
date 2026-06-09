# Microsoft.Crm.Asynchronous.ResourceBookingSyncService::RunInternal

- ea: `0x5ed0`
- end: `0x61e8`
- name: `Microsoft.Crm.Asynchronous.ResourceBookingSyncService::RunInternal`
- size: `792`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x5da0`

## callees

- `0x5ed0`
- `0x61f0`
- `0x8a90`
- `0x8ab0`
- `0x13d40`
- `0x13d60`
- `0x13d70`
- `0x13d80`
- `0x13da0`
- `0x13f30`
- `0x14790`
- `0x14840`
- `0x14960`
- `0x14cb0`
- `0x14f00`
- `0x15250`
- `0x152c0`
- `0x15730`
- `0x15750`
- `0x15770`
- `0x15790`
- `0x157b0`
- `0x157d0`
- `0x15800`
- `0x16370`
- `0x163a0`
- `0x163f0`

## string_xrefs

- `0x5ed6`: `LoadBookableResourceCache`
- `0x5eec`: `LoadBookableResourceCache`
- `0x5f1e`: `LoadBookableResourceCache`
- `0x5edb`: `retrieve and cache bookable resources`
- `0x60a1`: `remove deleted resource bookings`
- `0x60ac`: `ProcessSyncDelete`
- `0x611a`: `remove changed user resource bookings`
- `0x6125`: `ProcessSyncChangedUserDelete`

## pseudocode

```c

```

## disassembly

```asm
0x5ed0  ldarg.0
0x5ed1  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x5ed6  ldstr    aLoadbookablere// "LoadBookableResourceCache"
0x5edb  ldstr    aRetrieveAndCac// "retrieve and cache bookable resources"
0x5ee0  callvirt instance class Timer Metrics::AddTimer(string name, string description)
0x5ee5  pop
0x5ee6  ldarg.0
0x5ee7  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x5eec  ldstr    aLoadbookablere// "LoadBookableResourceCache"
0x5ef1  ldc.i4.1
0x5ef2  callvirt instance void Metrics::StartTimer(string name, bool trace)
0x5ef7  ldarg.0
0x5ef8  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.ResourceBookingSyncService::get_SystemService()
0x5efd  ldarg.0
0x5efe  ldfld    class ConfigurationSettings Microsoft.Crm.Asynchronous.ResourceBookingSyncService::Settings
0x5f03  callvirt instance int32 ConfigurationSettings::get_FetchXmlPageSize()
0x5f08  newobj   instance void BookableResourceQuery::.ctor(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService service, int32 maxPageSize)
0x5f0d  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ResourceBookingSyncService::get_OrganizationId()
0x5f12  newobj   instance void BookableResourceCache::.ctor(class BookableResourceQuery bookableResourceQuery, valuetype [mscorlib]System.Guid organizationId)
0x5f17  stloc.0
0x5f18  ldarg.0
0x5f19  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x5f1e  ldstr    aLoadbookablere// "LoadBookableResourceCache"
0x5f23  ldc.i4.1
0x5f24  callvirt instance void Metrics::StopTimer(string name, bool trace)
0x5f29  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class SyncStep>::.ctor()
0x5f2e  dup
0x5f2f  ldarg.0
0x5f30  ldftn    instance void Microsoft.Crm.Asynchronous.ResourceBookingSyncService::<RunInternal>b__3_0(class SyncConfig c)
0x5f36  newobj   instance void class [mscorlib]System.Action`1<class SyncConfig>::.ctor(object, native int)
0x5f3b  newobj   instance void SyncConfig::.ctor()
0x5f40  dup
0x5f41  ldstr    aSynchronizeRes// "synchronize resource bookings"
0x5f46  callvirt instance void SyncConfig::set_Description(string value)
0x5f4b  dup
0x5f4c  ldstr    aProcesssync// "ProcessSync"
0x5f51  callvirt instance void SyncConfig::set_Name(string value)
0x5f56  dup
0x5f57  ldloc.0
0x5f58  callvirt instance void SyncConfig::set_BookableResourceCache(class BookableResourceCache value)
0x5f5d  dup
0x5f5e  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ResourceBookingSyncService::get_OrganizationId()
0x5f63  ldloc.0
0x5f64  ldarg.0
0x5f65  ldfld    class ConfigurationSettings Microsoft.Crm.Asynchronous.ResourceBookingSyncService::Settings
0x5f6a  callvirt instance valuetype [mscorlib]System.DateTime ConfigurationSettings::get_LowerBoundDateTime()
0x5f6f  ldarg.0
0x5f70  ldfld    class ConfigurationSettings Microsoft.Crm.Asynchronous.ResourceBookingSyncService::Settings
0x5f75  callvirt instance int32 ConfigurationSettings::get_FetchXmlPageSize()
0x5f7a  newobj   instance void ResourceBookingsQuerySQL::.ctor(valuetype [mscorlib]System.Guid organizationId, class BookableResourceCache bookableResourceCache, valuetype [mscorlib]System.DateTime lowerBoundDateTime, int32 maxPageSize)
0x5f7f  callvirt instance void SyncConfig::set_Query(class IEntityQuery value)
0x5f84  dup
0x5f85  ldc.i4.1
0x5f86  callvirt instance void SyncConfig::set_UpdateUserStatus(bool value)
0x5f8b  dup
0x5f8c  ldc.i4.1
0x5f8d  callvirt instance void SyncConfig::set_IgnoreRetries(bool value)
0x5f92  newobj   instance void SyncStep::.ctor(class [mscorlib]System.Action`1<class SyncConfig> action, class SyncConfig config)
0x5f97  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class SyncStep>::Add(var<u1>)
0x5f9c  dup
0x5f9d  ldarg.0
0x5f9e  ldftn    instance void Microsoft.Crm.Asynchronous.ResourceBookingSyncService::<RunInternal>b__3_1(class SyncConfig c)
0x5fa4  newobj   instance void class [mscorlib]System.Action`1<class SyncConfig>::.ctor(object, native int)
0x5fa9  newobj   instance void SyncConfig::.ctor()
0x5fae  dup
0x5faf  ldstr    aRetryFailedRes// "retry failed resource bookings"
0x5fb4  callvirt instance void SyncConfig::set_Description(string value)
0x5fb9  dup
0x5fba  ldstr    aProcesssyncfor// "ProcessSyncForRetry"
0x5fbf  callvirt instance void SyncConfig::set_Name(string value)
0x5fc4  dup
0x5fc5  ldloc.0
0x5fc6  callvirt instance void SyncConfig::set_BookableResourceCache(class BookableResourceCache value)
0x5fcb  dup
0x5fcc  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ResourceBookingSyncService::get_OrganizationId()
0x5fd1  ldloc.0
0x5fd2  ldarg.0
0x5fd3  ldfld    class ConfigurationSettings Microsoft.Crm.Asynchronous.ResourceBookingSyncService::Settings
0x5fd8  callvirt instance valuetype [mscorlib]System.DateTime ConfigurationSettings::get_StartDateTime()
0x5fdd  ldarg.0
0x5fde  ldfld    class ConfigurationSettings Microsoft.Crm.Asynchronous.ResourceBookingSyncService::Settings
0x5fe3  callvirt instance int32 ConfigurationSettings::get_MaxRetryCount()
0x5fe8  ldarg.0
0x5fe9  ldfld    class ConfigurationSettings Microsoft.Crm.Asynchronous.ResourceBookingSyncService::Settings
0x5fee  callvirt instance int32 ConfigurationSettings::get_FetchXmlPageSize()
0x5ff3  newobj   instance void ResourceBookingsForRetryQuerySQL::.ctor(valuetype [mscorlib]System.Guid organizationId, class BookableResourceCache bookableResourceCache, valuetype [mscorlib]System.DateTime modifiedBeforeDateTime, int32 maxRetryCount, int32 maxPageSize)
0x5ff8  callvirt instance void SyncConfig::set_Query(class IEntityQuery value)
0x5ffd  dup
0x5ffe  ldc.i4.0
0x5fff  callvirt instance void SyncConfig::set_UpdateUserStatus(bool value)
0x6004  dup
0x6005  ldc.i4.0
0x6006  callvirt instance void SyncConfig::set_IgnoreRetries(bool value)
0x600b  newobj   instance void SyncStep::.ctor(class [mscorlib]System.Action`1<class SyncConfig> action, class SyncConfig config)
0x6010  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class SyncStep>::Add(var<u1>)
0x6015  dup
0x6016  ldarg.0
0x6017  ldftn    instance void Microsoft.Crm.Asynchronous.ResourceBookingSyncService::<RunInternal>b__3_2(class SyncConfig c)
0x601d  newobj   instance void class [mscorlib]System.Action`1<class SyncConfig>::.ctor(object, native int)
0x6022  newobj   instance void SyncConfig::.ctor()
0x6027  dup
0x6028  ldstr    aSynchronizePen// "synchronize pending resource bookings"
0x602d  callvirt instance void SyncConfig::set_Description(string value)
0x6032  dup
0x6033  ldstr    aProcesspending// "ProcessPendingSync"
0x6038  callvirt instance void SyncConfig::set_Name(string value)
0x603d  dup
0x603e  ldloc.0
0x603f  callvirt instance void SyncConfig::set_BookableResourceCache(class BookableResourceCache value)
0x6044  dup
0x6045  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ResourceBookingSyncService::get_OrganizationId()
0x604a  ldloc.0
0x604b  ldarg.0
0x604c  ldfld    class ConfigurationSettings Microsoft.Crm.Asynchronous.ResourceBookingSyncService::Settings
0x6051  callvirt instance valuetype [mscorlib]System.DateTime ConfigurationSettings::get_UpperBoundDateTime()
0x6056  ldarg.0
0x6057  ldfld    class ConfigurationSettings Microsoft.Crm.Asynchronous.ResourceBookingSyncService::Settings
0x605c  callvirt instance int32 ConfigurationSettings::get_MaxRetryCount()
0x6061  ldarg.0
0x6062  ldfld    class ConfigurationSettings Microsoft.Crm.Asynchronous.ResourceBookingSyncService::Settings
0x6067  callvirt instance int32 ConfigurationSettings::get_FetchXmlPageSize()
0x606c  newobj   instance void ResourceBookingsPendingIdMappingQuerySQL::.ctor(valuetype [mscorlib]System.Guid organizationId, class BookableResourceCache bookableResourceCache, valuetype [mscorlib]System.DateTime upperDateBound, int32 maxRetryCount, int32 maxPageSize)
0x6071  callvirt instance void SyncConfig::set_Query(class IEntityQuery value)
0x6076  dup
0x6077  ldc.i4.0
0x6078  callvirt instance void SyncConfig::set_UpdateUserStatus(bool value)
0x607d  dup
0x607e  ldc.i4.1
0x607f  callvirt instance void SyncConfig::set_IgnoreRetries(bool value)
0x6084  newobj   instance void SyncStep::.ctor(class [mscorlib]System.Action`1<class SyncConfig> action, class SyncConfig config)
0x6089  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class SyncStep>::Add(var<u1>)
0x608e  dup
0x608f  ldarg.0
0x6090  ldftn    instance void Microsoft.Crm.Asynchronous.ResourceBookingSyncService::<RunInternal>b__3_3(class SyncConfig c)
0x6096  newobj   instance void class [mscorlib]System.Action`1<class SyncConfig>::.ctor(object, native int)
0x609b  newobj   instance void SyncConfig::.ctor()
0x60a0  dup
0x60a1  ldstr    aRemoveDeletedR// "remove deleted resource bookings"
0x60a6  callvirt instance void SyncConfig::set_Description(string value)
0x60ab  dup
0x60ac  ldstr    aProcesssyncdel// "ProcessSyncDelete"
0x60b1  callvirt instance void SyncConfig::set_Name(string value)
0x60b6  dup
0x60b7  ldloc.0
0x60b8  callvirt instance void SyncConfig::set_BookableResourceCache(class BookableResourceCache value)
0x60bd  dup
0x60be  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ResourceBookingSyncService::get_OrganizationId()
0x60c3  ldloc.0
0x60c4  ldarg.0
0x60c5  ldfld    class ConfigurationSettings Microsoft.Crm.Asynchronous.ResourceBookingSyncService::Settings
0x60ca  callvirt instance valuetype [mscorlib]System.DateTime ConfigurationSettings::get_StartDateTime()
0x60cf  ldarg.0
0x60d0  ldfld    class ConfigurationSettings Microsoft.Crm.Asynchronous.ResourceBookingSyncService::Settings
0x60d5  callvirt instance int32 ConfigurationSettings::get_MaxRetryCount()
0x60da  ldarg.0
0x60db  ldfld    class ConfigurationSettings Microsoft.Crm.Asynchronous.ResourceBookingSyncService::Settings
0x60e0  callvirt instance int32 ConfigurationSettings::get_FetchXmlPageSize()
0x60e5  newobj   instance void ResourceBookingsToDeleteForRetryQuerySQL::.ctor(valuetype [mscorlib]System.Guid organizationId, class BookableResourceCache bookableResourceCache, valuetype [mscorlib]System.DateTime modifiedBeforeDateTime, int32 maxRetryCount, int32 maxPageSize)
0x60ea  callvirt instance void SyncConfig::set_Query(class IEntityQuery value)
0x60ef  dup
0x60f0  ldc.i4.0
0x60f1  callvirt instance void SyncConfig::set_UpdateUserStatus(bool value)
0x60f6  dup
0x60f7  ldc.i4.0
0x60f8  callvirt instance void SyncConfig::set_IgnoreRetries(bool value)
0x60fd  newobj   instance void SyncStep::.ctor(class [mscorlib]System.Action`1<class SyncConfig> action, class SyncConfig config)
0x6102  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class SyncStep>::Add(var<u1>)
0x6107  dup
0x6108  ldarg.0
0x6109  ldftn    instance void Microsoft.Crm.Asynchronous.ResourceBookingSyncService::<RunInternal>b__3_4(class SyncConfig c)
0x610f  newobj   instance void class [mscorlib]System.Action`1<class SyncConfig>::.ctor(object, native int)
0x6114  newobj   instance void SyncConfig::.ctor()
0x6119  dup
0x611a  ldstr    aRemoveChangedU// "remove changed user resource bookings"
0x611f  callvirt instance void SyncConfig::set_Description(string value)
0x6124  dup
0x6125  ldstr    aProcesssynccha// "ProcessSyncChangedUserDelete"
0x612a  callvirt instance void SyncConfig::set_Name(string value)
0x612f  dup
0x6130  ldloc.0
0x6131  callvirt instance void SyncConfig::set_BookableResourceCache(class BookableResourceCache value)
0x6136  dup
0x6137  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ResourceBookingSyncService::get_OrganizationId()
0x613c  ldarg.0
0x613d  ldfld    class ConfigurationSettings Microsoft.Crm.Asynchronous.ResourceBookingSyncService::Settings
0x6142  callvirt instance int32 ConfigurationSettings::get_FetchXmlPageSize()
0x6147  newobj   instance void ResourceBookingsWithChangedUserToDeleteQuerySQL::.ctor(valuetype [mscorlib]System.Guid organizationId, int32 maxPageSize)
0x614c  callvirt instance void SyncConfig::set_Query(class IEntityQuery value)
0x6151  dup
0x6152  ldc.i4.0
0x6153  callvirt instance void SyncConfig::set_UpdateUserStatus(bool value)
0x6158  dup
0x6159  ldc.i4.1
0x615a  callvirt instance void SyncConfig::set_IgnoreRetries(bool value)
0x615f  newobj   instance void SyncStep::.ctor(class [mscorlib]System.Action`1<class SyncConfig> action, class SyncConfig config)
0x6164  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class SyncStep>::Add(var<u1>)
0x6169  dup
0x616a  ldarg.0
0x616b  ldftn    instance void Microsoft.Crm.Asynchronous.ResourceBookingSyncService::<RunInternal>b__3_5(class SyncConfig c)
0x6171  newobj   instance void class [mscorlib]System.Action`1<class SyncConfig>::.ctor(object, native int)
0x6176  newobj   instance void SyncConfig::.ctor()
0x617b  dup
0x617c  ldstr    aCleanupIdMappi// "cleanup Id mapping table"
0x6181  callvirt instance void SyncConfig::set_Description(string value)
0x6186  dup
0x6187  ldstr    aProcesscleanup// "ProcessCleanupPastIdMapping"
0x618c  callvirt instance void SyncConfig::set_Name(string value)
0x6191  dup
0x6192  ldnull
0x6193  callvirt instance void SyncConfig::set_BookableResourceCache(class BookableResourceCache value)
0x6198  dup
0x6199  ldnull
0x619a  callvirt instance void SyncConfig::set_Query(class IEntityQuery value)
0x619f  dup
0x61a0  ldc.i4.0
0x61a1  callvirt instance void SyncConfig::set_UpdateUserStatus(bool value)
0x61a6  dup
0x61a7  ldc.i4.0
0x61a8  callvirt instance void SyncConfig::set_IgnoreRetries(bool value)
0x61ad  newobj   instance void SyncStep::.ctor(class [mscorlib]System.Action`1<class SyncConfig> action, class SyncConfig config)
0x61b2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class SyncStep>::Add(var<u1>)
0x61b7  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class SyncStep>::GetEnumerator()
0x61bc  stloc.1
0x61bd  br.s     loc_61CE
0x61bf  ldloca.s 1
0x61c1  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class SyncStep>::get_Current()
0x61c6  stloc.2
0x61c7  ldarg.0
0x61c8  ldloc.2
0x61c9  call     instance void Microsoft.Crm.Asynchronous.ResourceBookingSyncService::RunStep(class SyncStep step)
0x61ce  ldloca.s 1
0x61d0  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class SyncStep>::MoveNext()
0x61d5  brtrue.s loc_61BF
0x61d7  leave.s  loc_61E7
0x61d9  ldloca.s 1
0x61db  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class SyncStep>
0x61e1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x61e6  endfinally
0x61e7  ret
```
