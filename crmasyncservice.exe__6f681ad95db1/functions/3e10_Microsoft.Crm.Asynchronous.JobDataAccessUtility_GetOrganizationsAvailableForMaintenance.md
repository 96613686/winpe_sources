# Microsoft.Crm.Asynchronous.JobDataAccessUtility::GetOrganizationsAvailableForMaintenance

- ea: `0x3e10`
- end: `0x3ee6`
- name: `Microsoft.Crm.Asynchronous.JobDataAccessUtility::GetOrganizationsAvailableForMaintenance`
- size: `214`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x2210`
- `0x3d60`
- `0x46f0`

## callees

- `0x3e10`
- `0x4340`

## string_xrefs

- `0x3eaf`: `[DBUPDATES][PRE-SELECT] Found {0} enabled orgs in SG {1} in DC {2}.`

## pseudocode

```c

```

## disassembly

```asm
0x3e10  ldc.i4.0
0x3e11  stloc.0
0x3e12  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x3e17  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x3e1c  ldc.i4.2
0x3e1d  bne.un.s loc_3E29
0x3e1f  ldarg.0
0x3e20  call     bool [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmScaleGroupService::IsXdbScaleGroup(valuetype [mscorlib]System.Guid)
0x3e25  ldc.i4.0
0x3e26  ceq
0x3e28  stloc.0
0x3e29  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmOrganizationService::.ctor()
0x3e2e  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationFilter::.ctor()
0x3e33  stloc.1
0x3e34  ldloc.1
0x3e35  ldarg.0
0x3e36  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationFilter::set_ScaleGroupId(valuetype [mscorlib]System.Guid)
0x3e3b  ldloc.1
0x3e3c  ldc.i4.1
0x3e3d  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState>::.ctor(var<u1>)
0x3e42  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationFilter::set_State(valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState>)
0x3e47  ldloc.1
0x3e48  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDataCenterInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DataCenterInfoProvider::get_Instance()
0x3e4d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IDataCenterInfoProvider::GetDatacenterId()
0x3e52  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationFilter::set_DatacenterId(valuetype [mscorlib]System.Guid)
0x3e57  ldc.i4.3
0x3e58  newarr   [mscorlib]System.String
0x3e5d  dup
0x3e5e  ldc.i4.0
0x3e5f  ldstr    aId// "Id"
0x3e64  stelem.ref
0x3e65  dup
0x3e66  ldc.i4.1
0x3e67  ldstr    aScalegroupid// "ScaleGroupId"
0x3e6c  stelem.ref
0x3e6d  dup
0x3e6e  ldc.i4.2
0x3e6f  ldstr    aSqlservername// "SqlServerName"
0x3e74  stelem.ref
0x3e75  ldloc.1
0x3e76  ldloc.0
0x3e77  ldc.i4.0
0x3e78  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData[] [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmOrganizationService::RetrieveMultiple(string[], class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationFilter, bool, bool)
0x3e7d  stloc.2
0x3e7e  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x3e83  stloc.3
0x3e84  ldloc.3
0x3e85  ldloc.2
0x3e86  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData, valuetype [mscorlib]System.Guid> <>c::<>9__0_0
0x3e8b  dup
0x3e8c  brtrue.s loc_3EA5
0x3e8e  pop
0x3e8f  ldsfld   class <>c <>c::<>9
0x3e94  ldftn    instance valuetype [mscorlib]System.Guid <>c::<GetOrganizationsAvailableForMaintenance>b__0_0(class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData org)
0x3e9a  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData, valuetype [mscorlib]System.Guid>::.ctor(object, native int)
0x3e9f  dup
0x3ea0  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData, valuetype [mscorlib]System.Guid> <>c::<>9__0_0
0x3ea5  call     T0x2B00000B
0x3eaa  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x3eaf  ldstr    aDbupdatesPreSe// "[DBUPDATES][PRE-SELECT] Found {0} enabl"...
0x3eb4  ldc.i4.3
0x3eb5  newarr   [mscorlib]System.Object
0x3eba  dup
0x3ebb  ldc.i4.0
0x3ebc  ldloc.3
0x3ebd  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x3ec2  box      [mscorlib]System.Int32
0x3ec7  stelem.ref
0x3ec8  dup
0x3ec9  ldc.i4.1
0x3eca  ldarg.0
0x3ecb  box      [mscorlib]System.Guid
0x3ed0  stelem.ref
0x3ed1  dup
0x3ed2  ldc.i4.2
0x3ed3  ldloc.1
0x3ed4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationFilter::get_DatacenterId()
0x3ed9  box      [mscorlib]System.Guid
0x3ede  stelem.ref
0x3edf  call     void Microsoft.Crm.Asynchronous.JobManager::LogDBUpdateScheduledTelemetry(string messageFormat, object[] args)
0x3ee4  ldloc.3
0x3ee5  ret
```
