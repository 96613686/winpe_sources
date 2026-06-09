# Microsoft.Crm.Asynchronous.ResourceBookingSyncService::IsResourceBookingSyncEnabled

- ea: `0x88e0`
- end: `0x894c`
- name: `Microsoft.Crm.Asynchronous.ResourceBookingSyncService::IsResourceBookingSyncEnabled`
- size: `108`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x5da0`

## callees

- `0x88e0`
- `0x8ab0`
- `0x16390`
- `0x163e0`

## pseudocode

```c

```

## disassembly

```asm
0x88e0  ldc.i4.0
0x88e1  stloc.0
0x88e2  ldarg.0
0x88e3  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x88e8  ldstr    aMethodisresour// "MethodIsResourceBookingSyncEnabled"
0x88ed  callvirt instance void Metrics::StartTimer(string name)
0x88f2  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x88f7  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x88fc  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_ResourceBookingExchangeSync()
0x8901  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::get_Name()
0x8906  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ResourceBookingSyncService::get_OrganizationId()
0x890b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x8910  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8915  stloc.0
0x8916  ldloc.0
0x8917  brfalse.s loc_893A
0x8919  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ResourceBookingSyncService::get_OrganizationId()
0x891e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x8923  stloc.1
0x8924  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0x8929  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ResourceBookingSyncService::get_OrganizationId()
0x892e  ldloc.1
0x892f  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x8934  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_IsResourceBookingExchangeSyncEnabled()
0x8939  stloc.0
0x893a  ldarg.0
0x893b  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x8940  ldstr    aMethodisresour// "MethodIsResourceBookingSyncEnabled"
0x8945  callvirt instance void Metrics::StopTimer(string name)
0x894a  ldloc.0
0x894b  ret
```
