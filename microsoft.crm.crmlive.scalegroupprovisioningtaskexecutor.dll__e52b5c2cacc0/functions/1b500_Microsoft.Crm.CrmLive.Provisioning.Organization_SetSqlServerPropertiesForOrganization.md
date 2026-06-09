# Microsoft.Crm.CrmLive.Provisioning.Organization::SetSqlServerPropertiesForOrganization

- ea: `0x1b500`
- end: `0x1b5e3`
- name: `Microsoft.Crm.CrmLive.Provisioning.Organization::SetSqlServerPropertiesForOrganization`
- size: `227`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1b240`

## callees

- `0x91b0`
- `0x1b150`
- `0x1b500`
- `0x240d0`
- `0x24170`

## string_xrefs

- `0x1b529`: `SqlServer not provided in OrganizationCreateInfo.  Using default: {0}`
- `0x1b561`: `SqlServer specified directly in OrganizationCreateInfo: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x1b500  ldarg.2
0x1b501  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfoLocal::get_PreferredAvailabilityGroupName()
0x1b506  stloc.0
0x1b507  ldloc.0
0x1b508  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1b50d  brfalse.s loc_1B58C
0x1b50f  ldarg.2
0x1b510  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfoLocal::get_SqlServerName()
0x1b515  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1b51a  brfalse.s loc_1B554
0x1b51c  ldarg.1
0x1b51d  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x1b522  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x1b527  ldc.i4.s 0xA
0x1b529  ldstr    aSqlserverNotPr// "SqlServer not provided in OrganizationC"...
0x1b52e  ldc.i4.1
0x1b52f  newarr   [mscorlib]System.Object
0x1b534  dup
0x1b535  ldc.i4.0
0x1b536  ldarg.0
0x1b537  call     instance string Microsoft.Crm.CrmLive.Provisioning.Organization::get_SqlServerName()
0x1b53c  stelem.ref
0x1b53d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1b542  ldarg.1
0x1b543  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x1b548  ldarg.0
0x1b549  call     instance string Microsoft.Crm.CrmLive.Provisioning.Organization::get_SqlServerName()
0x1b54e  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_SqlServerName(string)
0x1b553  ret
0x1b554  ldarg.1
0x1b555  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x1b55a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x1b55f  ldc.i4.s 0xA
0x1b561  ldstr    aSqlserverSpeci// "SqlServer specified directly in Organiz"...
0x1b566  ldc.i4.1
0x1b567  newarr   [mscorlib]System.Object
0x1b56c  dup
0x1b56d  ldc.i4.0
0x1b56e  ldarg.2
0x1b56f  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfoLocal::get_SqlServerName()
0x1b574  stelem.ref
0x1b575  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1b57a  ldarg.1
0x1b57b  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x1b580  ldarg.2
0x1b581  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfoLocal::get_SqlServerName()
0x1b586  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_SqlServerName(string)
0x1b58b  ret
0x1b58c  ldarg.1
0x1b58d  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x1b592  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x1b597  ldc.i4.s 0xA
0x1b599  ldstr    aSelectedAvaila// "Selected AvailabilityGroup: {0}"
0x1b59e  ldc.i4.1
0x1b59f  newarr   [mscorlib]System.Object
0x1b5a4  dup
0x1b5a5  ldc.i4.0
0x1b5a6  ldloc.0
0x1b5a7  stelem.ref
0x1b5a8  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1b5ad  ldarg.1
0x1b5ae  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x1b5b3  ldloc.0
0x1b5b4  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_AvailabilityGroupName(string)
0x1b5b9  ldloc.0
0x1b5ba  call     class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.ReplicaStatus [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.ReplicaStatus::GetReplicaStatus(string)
0x1b5bf  stloc.1
0x1b5c0  ldarg.1
0x1b5c1  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x1b5c6  ldloc.1
0x1b5c7  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.ReplicaStatus::get_PrimaryReplica()
0x1b5cc  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_SqlServerName(string)
0x1b5d1  ldarg.1
0x1b5d2  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x1b5d7  ldloc.1
0x1b5d8  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.ReplicaStatus::get_SyncReplica()
0x1b5dd  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_MirroredSqlServerName(string)
0x1b5e2  ret
```
