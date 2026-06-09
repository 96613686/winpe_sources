# Microsoft.Crm.Service.ObjectModel.IncidentService::PerformCascadeUpdate

- ea: `0x1e90`
- end: `0x1f25`
- name: `Microsoft.Crm.Service.ObjectModel.IncidentService::PerformCascadeUpdate`
- size: `149`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1740`
- `0x1980`

## callees

- `0x1cc0`
- `0x1d10`
- `0x1da0`
- `0x1e90`

## pseudocode

```c

```

## disassembly

```asm
0x1e90  ldarg.s  5
0x1e92  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1e97  stloc.0
0x1e98  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0x1e9d  ldloc.0
0x1e9e  ldarg.s  5
0x1ea0  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x1ea5  stloc.1
0x1ea6  ldarg.3
0x1ea7  ldc.i4.1
0x1ea8  beq.s    loc_1EAE
0x1eaa  ldarg.3
0x1eab  ldc.i4.2
0x1eac  bne.un.s loc_1F24
0x1eae  ldarg.0
0x1eaf  ldarg.1
0x1eb0  ldarg.s  5
0x1eb2  call     instance bool Microsoft.Crm.Service.ObjectModel.IncidentService::IsParentCase(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1eb7  brfalse.s loc_1F24
0x1eb9  ldloc.1
0x1eba  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_CascadeStatusUpdate()
0x1ebf  brfalse.s loc_1ED9
0x1ec1  ldarg.0
0x1ec2  ldarg.1
0x1ec3  ldarg.s  5
0x1ec5  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Service.ObjectModel.IncidentService::RetrieveActiveChildRecords(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1eca  stloc.2
0x1ecb  ldarg.0
0x1ecc  ldloc.2
0x1ecd  ldarg.2
0x1ece  ldarg.3
0x1ecf  ldarg.s  4
0x1ed1  ldarg.s  5
0x1ed3  call     instance void Microsoft.Crm.Service.ObjectModel.IncidentService::SetStateForChildRecords(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection childIncidents, class [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.IncidentResolution incidentResolution, int32 newState, int32 newStatusCode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1ed8  ret
0x1ed9  ldloc.1
0x1eda  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_RestrictStatusUpdate()
0x1edf  brfalse.s loc_1F24
0x1ee1  ldarg.0
0x1ee2  ldarg.1
0x1ee3  ldarg.s  5
0x1ee5  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Service.ObjectModel.IncidentService::RetrieveActiveChildRecords(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1eea  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x1eef  ldc.i4.0
0x1ef0  ble.s    loc_1F24
0x1ef2  ldarg.3
0x1ef3  ldc.i4.2
0x1ef4  bne.un.s loc_1F0B
0x1ef6  ldc.i4   0x8003F451
0x1efb  call     string [Microsoft.Crm.Constants]Microsoft.Crm.ErrorCodes::GetErrorMessage(int32)
0x1f00  ldc.i4   0x8003F451
0x1f05  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x1f0a  throw
0x1f0b  ldarg.3
0x1f0c  ldc.i4.1
0x1f0d  bne.un.s loc_1F24
0x1f0f  ldc.i4   0x8003F452
0x1f14  call     string [Microsoft.Crm.Constants]Microsoft.Crm.ErrorCodes::GetErrorMessage(int32)
0x1f19  ldc.i4   0x8003F452
0x1f1e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x1f23  throw
0x1f24  ret
```
