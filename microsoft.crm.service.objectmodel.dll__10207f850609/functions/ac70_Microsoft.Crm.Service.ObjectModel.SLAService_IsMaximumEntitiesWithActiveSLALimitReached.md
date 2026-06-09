# Microsoft.Crm.Service.ObjectModel.SLAService::IsMaximumEntitiesWithActiveSLALimitReached

- ea: `0xac70`
- end: `0xacc4`
- name: `Microsoft.Crm.Service.ObjectModel.SLAService::IsMaximumEntitiesWithActiveSLALimitReached`
- size: `84`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x9fc0`
- `0xa700`

## callees

- `0xac70`
- `0xace0`
- `0xaea0`

## pseudocode

```c

```

## disassembly

```asm
0xac70  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0xac75  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::GetSku()
0xac7a  ldc.i4.2
0xac7b  bne.un.s loc_ACC2
0xac7d  ldarg.2
0xac7e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xac83  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0xac88  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsSLAFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xac8d  brfalse.s loc_ACC2
0xac8f  ldarg.1
0xac90  ldc.i4.0
0xac91  ble.s    loc_ACC2
0xac93  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0xac98  ldarg.2
0xac99  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xac9e  ldarg.2
0xac9f  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0xaca4  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_MaximumEntitiesWithActiveSLA()
0xaca9  stloc.0
0xacaa  ldarg.2
0xacab  call     int32 Microsoft.Crm.Service.ObjectModel.SLAService::GetEntityCountWithActiveSLA(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xacb0  ldloc.0
0xacb1  bne.un.s loc_ACC0
0xacb3  ldarg.0
0xacb4  ldarg.1
0xacb5  ldc.i4.1
0xacb6  ldarg.2
0xacb7  call     instance bool Microsoft.Crm.Service.ObjectModel.SLAService::IsActiveSLAExistOnTargetEntity(int32 objectTypeCode, bool includeIncident, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xacbc  ldc.i4.0
0xacbd  ceq
0xacbf  ret
0xacc0  ldc.i4.0
0xacc1  ret
0xacc2  ldc.i4.0
0xacc3  ret
```
