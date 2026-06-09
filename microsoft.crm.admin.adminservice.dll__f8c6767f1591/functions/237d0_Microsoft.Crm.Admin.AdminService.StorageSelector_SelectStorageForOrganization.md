# Microsoft.Crm.Admin.AdminService.StorageSelector::SelectStorageForOrganization

- ea: `0x237d0`
- end: `0x239b1`
- name: `Microsoft.Crm.Admin.AdminService.StorageSelector::SelectStorageForOrganization`
- size: `481`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `service_task, broker_com_uri`

## callers

- `0x15f90`

## callees

- `0x179e0`
- `0x17b70`
- `0x17cf0`
- `0x17fb0`
- `0x18380`
- `0x21dd0`
- `0x233e0`
- `0x233f0`
- `0x23400`
- `0x23420`
- `0x23430`
- `0x23730`
- `0x23790`
- `0x237d0`
- `0x239c0`
- `0x23b70`
- `0x23b90`
- `0x23bb0`
- `0x23bc0`

## string_xrefs

- `0x237d1`: `organizationCreateInfo`
- `0x237e1`: `organizationCreateInfo.ScaleGroupId`

## pseudocode

```c

```

## disassembly

```asm
0x237d0  ldarg.2
0x237d1  ldstr    aOrganizationcr// "organizationCreateInfo"
0x237d6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x237db  ldarg.2
0x237dc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfo::get_ScaleGroupId()
0x237e1  ldstr    aOrganizationcr_0// "organizationCreateInfo.ScaleGroupId"
0x237e6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x237eb  ldarg.1
0x237ec  ldstr    aDatacenterid// "datacenterId"
0x237f1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x237f6  newobj   instance void Microsoft.Crm.Admin.AdminService.OrganizationStorageInfo::.ctor()
0x237fb  stloc.0
0x237fc  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x23801  ldc.i4.s 9
0x23803  ldstr    aSelectingStora// "Selecting Storage for organization {0} "...
0x23808  ldc.i4.2
0x23809  newarr   [mscorlib]System.Object
0x2380e  dup
0x2380f  ldc.i4.0
0x23810  ldarg.2
0x23811  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfo::get_OrganizationName()
0x23816  stelem.ref
0x23817  dup
0x23818  ldc.i4.1
0x23819  ldarg.1
0x2381a  box      [mscorlib]System.Guid
0x2381f  stelem.ref
0x23820  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x23825  ldarg.2
0x23826  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfo::get_ScaleGroupId()
0x2382b  stloc.1
0x2382c  ldarg.2
0x2382d  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfo::get_PreferredAvailabilityGroupName()
0x23832  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x23837  brtrue.s loc_238A0
0x23839  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x2383e  ldc.i4.s 0xA
0x23840  ldstr    aUsingSpecified// "Using specified PreferredAvailabilityGr"...
0x23845  ldc.i4.1
0x23846  newarr   [mscorlib]System.Object
0x2384b  dup
0x2384c  ldc.i4.0
0x2384d  ldarg.2
0x2384e  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfo::get_PreferredAvailabilityGroupName()
0x23853  stelem.ref
0x23854  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x23859  newobj   instance void Microsoft.Crm.Admin.AdminService.CrmAvailabilityGroupService::.ctor()
0x2385e  dup
0x2385f  ldarg.2
0x23860  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfo::get_PreferredAvailabilityGroupName()
0x23865  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.CrmAvailabilityGroupService::GetIdFromName(string availabilityGroupName)
0x2386a  callvirt instance class Microsoft.Crm.Admin.AdminService.AvailabilityGroupData Microsoft.Crm.Admin.AdminService.CrmAvailabilityGroupService::Retrieve(valuetype [mscorlib]System.Guid availabilityGroupId)
0x2386f  stloc.3
0x23870  ldloc.3
0x23871  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.AvailabilityGroupData::get_DatacenterId()
0x23876  ldarg.1
0x23877  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2387c  ldstr    aPreferredavail// "PreferredAvailabilityGroup is not in th"...
0x23881  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x23886  ldloc.0
0x23887  ldarg.2
0x23888  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfo::get_PreferredAvailabilityGroupName()
0x2388d  callvirt instance void Microsoft.Crm.Admin.AdminService.OrganizationStorageInfo::set_AvailabilityGroup(string value)
0x23892  ldloc.0
0x23893  ldloc.3
0x23894  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.AvailabilityGroupData::get_StorageGroupId()
0x23899  callvirt instance void Microsoft.Crm.Admin.AdminService.OrganizationStorageInfo::set_StorageGroupId(valuetype [mscorlib]System.Guid value)
0x2389e  ldloc.0
0x2389f  ret
0x238a0  ldarg.0
0x238a1  ldarg.1
0x238a2  ldarg.2
0x238a3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfo::get_ScaleGroupId()
0x238a8  call     instance class Microsoft.Crm.Admin.AdminService.StorageGroupInfo Microsoft.Crm.Admin.AdminService.StorageSelector::PickStorageGroup(valuetype [mscorlib]System.Guid datacenterId, valuetype [mscorlib]System.Guid scaleGroupId)
0x238ad  stloc.2
0x238ae  ldloc.2
0x238af  brtrue   loc_23954
0x238b4  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x238b9  ldc.i4.s 0xA
0x238bb  ldstr    aStoragegroupNo// "StorageGroup not found. Using Scalegrou"...
0x238c0  ldc.i4.1
0x238c1  newarr   [mscorlib]System.Object
0x238c6  dup
0x238c7  ldc.i4.0
0x238c8  ldloca.s 1
0x238ca  constrained. [mscorlib]System.Guid
0x238d0  callvirt instance string [mscorlib]System.Object::ToString()
0x238d5  stelem.ref
0x238d6  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x238db  ldloc.0
0x238dc  ldarg.0
0x238dd  ldarg.1
0x238de  ldloc.1
0x238df  call     instance string Microsoft.Crm.Admin.AdminService.StorageSelector::SelectAvailabilityGroupFromScaleGroup(valuetype [mscorlib]System.Guid datacenterId, valuetype [mscorlib]System.Guid scaleGroupId)
0x238e4  callvirt instance void Microsoft.Crm.Admin.AdminService.OrganizationStorageInfo::set_AvailabilityGroup(string value)
0x238e9  ldloc.0
0x238ea  callvirt instance string Microsoft.Crm.Admin.AdminService.OrganizationStorageInfo::get_AvailabilityGroup()
0x238ef  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x238f4  brfalse.s loc_23952
0x238f6  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x238fb  ldc.i4.s 0xA
0x238fd  ldstr    aAvailabilitygr_8// "AvailabilityGroup not found for ScaleGr"...
0x23902  ldc.i4.1
0x23903  newarr   [mscorlib]System.Object
0x23908  dup
0x23909  ldc.i4.0
0x2390a  ldloca.s 1
0x2390c  constrained. [mscorlib]System.Guid
0x23912  callvirt instance string [mscorlib]System.Object::ToString()
0x23917  stelem.ref
0x23918  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2391d  ldarg.0
0x2391e  ldarg.1
0x2391f  ldloc.1
0x23920  call     instance class Microsoft.Crm.Admin.AdminService.ServerData Microsoft.Crm.Admin.AdminService.StorageSelector::GetSqlServerFromScaleGroup(valuetype [mscorlib]System.Guid datacenterId, valuetype [mscorlib]System.Guid scaleGroupId)
0x23925  stloc.s  4
0x23927  ldloc.s  4
0x23929  ldstr    aUnableToFindSq// "Unable to find SQL server for ScaleGrou"...
0x2392e  ldloca.s 1
0x23930  constrained. [mscorlib]System.Guid
0x23936  callvirt instance string [mscorlib]System.Object::ToString()
0x2393b  call     string [mscorlib]System.String::Concat(string, string)
0x23940  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x23945  ldloc.0
0x23946  ldloc.s  4
0x23948  callvirt instance string Microsoft.Crm.Admin.AdminService.ServerData::get_Name()
0x2394d  callvirt instance void Microsoft.Crm.Admin.AdminService.OrganizationStorageInfo::set_SqlServerName(string value)
0x23952  ldloc.0
0x23953  ret
0x23954  ldloc.0
0x23955  ldloc.2
0x23956  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.StorageGroupInfo::get_Id()
0x2395b  callvirt instance void Microsoft.Crm.Admin.AdminService.OrganizationStorageInfo::set_StorageGroupId(valuetype [mscorlib]System.Guid value)
0x23960  ldloc.0
0x23961  ldarg.0
0x23962  ldarg.1
0x23963  ldloc.2
0x23964  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.StorageGroupInfo::get_Id()
0x23969  call     instance string Microsoft.Crm.Admin.AdminService.StorageSelector::SelectAvailabilityGroupFromStorageGroup(valuetype [mscorlib]System.Guid datacenterId, valuetype [mscorlib]System.Guid storageGroupId)
0x2396e  callvirt instance void Microsoft.Crm.Admin.AdminService.OrganizationStorageInfo::set_AvailabilityGroup(string value)
0x23973  ldloc.0
0x23974  callvirt instance string Microsoft.Crm.Admin.AdminService.OrganizationStorageInfo::get_AvailabilityGroup()
0x23979  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2397e  brfalse.s loc_239AF
0x23980  ldloc.2
0x23981  callvirt instance bool Microsoft.Crm.Admin.AdminService.StorageGroupInfo::get_IsMirroringEnabled()
0x23986  ldc.i4.0
0x23987  ceq
0x23989  ldstr    aMirroringIsEna// "Mirroring is enabled for the storage gr"...
0x2398e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x23993  ldarg.0
0x23994  ldarg.1
0x23995  ldloc.2
0x23996  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.StorageGroupInfo::get_Id()
0x2399b  call     instance class Microsoft.Crm.Admin.AdminService.ServerData Microsoft.Crm.Admin.AdminService.StorageSelector::GetSqlServerFromStorageGroup(valuetype [mscorlib]System.Guid datacenterId, valuetype [mscorlib]System.Guid storageGroupId)
0x239a0  stloc.s  5
0x239a2  ldloc.0
0x239a3  ldloc.s  5
0x239a5  callvirt instance string Microsoft.Crm.Admin.AdminService.ServerData::get_Name()
0x239aa  callvirt instance void Microsoft.Crm.Admin.AdminService.OrganizationStorageInfo::set_SqlServerName(string value)
0x239af  ldloc.0
0x239b0  ret
```
