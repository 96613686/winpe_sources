# Microsoft.Crm.CrmLive.Provisioning.Organization::PostRestoreOperations

- ea: `0x19c90`
- end: `0x19e70`
- name: `Microsoft.Crm.CrmLive.Provisioning.Organization::PostRestoreOperations`
- size: `480`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x19c90`
- `0x19ee0`
- `0x1a030`
- `0x1a0a0`
- `0x1a370`
- `0x1c080`
- `0x1c240`
- `0x1c3b0`

## string_xrefs

- `0x19ce8`: `Restore -- Update DNS information`
- `0x19df6`: `Restore -- Remove missing users from ConfigDB`
- `0x19e2d`: `Restore -- Marking LastTaskStatus=OrganizationTaskStatus.Completed`
- `0x19d73`: `Restore -- Create the organization maintenance jobs to the new scale group`

## pseudocode

```c

```

## disassembly

```asm
0x19c90  ldarg.1
0x19c91  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationService::.ctor(class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.AdminContext)
0x19c96  stloc.0
0x19c97  call     class Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::NewService()
0x19c9c  stloc.1
0x19c9d  ldloc.0
0x19c9e  ldarg.2
0x19c9f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreInfo::get_OrganizationId()
0x19ca4  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationService::RetrieveDBInfo(valuetype [mscorlib]System.Guid)
0x19ca9  stloc.2
0x19caa  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmScaleGroupService::.ctor()
0x19caf  ldloc.2
0x19cb0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData::get_ScaleGroupId()
0x19cb5  call     instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ScaleGroupData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmScaleGroupService::Retrieve(valuetype [mscorlib]System.Guid)
0x19cba  stloc.3
0x19cbb  ldarg.2
0x19cbc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreInfo::get_OrganizationId()
0x19cc1  call     void Microsoft.Crm.CrmLive.Provisioning.Organization::SetOrgVersionInConfigDB(valuetype [mscorlib]System.Guid organizationId)
0x19cc6  ldarg.2
0x19cc7  callvirt instance bool [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreInfo::get_MakeUnique()
0x19ccc  brfalse.s loc_19CE0
0x19cce  ldloc.1
0x19ccf  ldarg.2
0x19cd0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreInfo::get_OrganizationId()
0x19cd5  ldarg.2
0x19cd6  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreInfo::get_OrganizationUniqueName()
0x19cdb  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess::MakeRestoredOrganizationUnique(valuetype [mscorlib]System.Guid organizationId, string organizationFriendlyName)
0x19ce0  ldarg.2
0x19ce1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreInfo::get_OrganizationId()
0x19ce6  ldc.i4.s 0x42
0x19ce8  ldstr    aRestoreUpdateD// "Restore -- Update DNS information"
0x19ced  ldc.i4.0
0x19cee  newarr   [mscorlib]System.Object
0x19cf3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x19cf8  call     class [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.PlatformClient [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.PlatformClient::ConnectLivePlatformService()
0x19cfd  stloc.s  4
0x19cff  newobj   instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.DomainManagementRefreshOrgDomainsRequest::.ctor()
0x19d04  stloc.s  5
0x19d06  ldloc.s  5
0x19d08  ldarg.2
0x19d09  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreInfo::get_OrganizationId()
0x19d0e  callvirt instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.DomainManagementRefreshOrgDomainsRequest::set_OrganizationId(valuetype [mscorlib]System.Guid)
0x19d13  ldloc.s  4
0x19d15  callvirt instance class [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.LivePlatformService [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.PlatformClient::get_LivePlatformService()
0x19d1a  ldloc.s  5
0x19d1c  callvirt instance class [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ServiceResponseMessage [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.LivePlatformService::Execute(class [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ServiceRequestMessage)
0x19d21  pop
0x19d22  leave.s  loc_19D30
0x19d24  ldloc.s  4
0x19d26  brfalse.s loc_19D2F
0x19d28  ldloc.s  4
0x19d2a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x19d2f  endfinally
0x19d30  ldarg.2
0x19d31  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreInfo::get_OrganizationId()
0x19d36  ldc.i4.s 0x42
0x19d38  ldstr    aRestoreAddTheO// "Restore -- Add the organization to the "...
0x19d3d  ldc.i4.0
0x19d3e  newarr   [mscorlib]System.Object
0x19d43  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x19d48  ldloc.3
0x19d49  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ScaleGroupData::get_Id()
0x19d4e  ldarg.2
0x19d4f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreInfo::get_OrganizationId()
0x19d54  call     void [Microsoft.Crm.Core]Microsoft.Crm.StatisticsDatabase.StatisticsAdministrator::AddOrganizationToStatisticsDatabase(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x19d59  leave.s  loc_19D6B
0x19d5b  callvirt instance int32 [System.Data]System.Data.SqlClient.SqlException::get_Number()
0x19d60  ldc.i4   0xA29
0x19d65  beq.s    loc_19D69
0x19d67  rethrow
0x19d69  leave.s  loc_19D6B
0x19d6b  ldarg.2
0x19d6c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreInfo::get_OrganizationId()
0x19d71  ldc.i4.s 0x42
0x19d73  ldstr    aRestoreCreateT_0// "Restore -- Create the organization main"...
0x19d78  ldc.i4.0
0x19d79  newarr   [mscorlib]System.Object
0x19d7e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x19d83  call     class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.IOrganizationMaintenanceJobs [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationMaintenanceJobs::NewService()
0x19d88  ldarg.2
0x19d89  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreInfo::get_OrganizationId()
0x19d8e  ldloc.3
0x19d8f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ScaleGroupData::get_Id()
0x19d94  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.IOrganizationMaintenanceJobs::CreateJobs(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x19d99  ldarg.0
0x19d9a  ldarg.2
0x19d9b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreInfo::get_OrganizationId()
0x19da0  ldloc.3
0x19da1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ScaleGroupData::get_Id()
0x19da6  call     instance void Microsoft.Crm.CrmLive.Provisioning.Organization::CreateMaintenanceJobsInRemoteDatacenter(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid scalegroupId)
0x19dab  ldarg.2
0x19dac  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreInfo::get_OrganizationId()
0x19db1  ldc.i4.s 0x42
0x19db3  ldstr    aRestoreRestore_1// "Restore -- Restore reports from databas"...
0x19db8  ldc.i4.0
0x19db9  newarr   [mscorlib]System.Object
0x19dbe  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x19dc3  ldloc.1
0x19dc4  ldloc.3
0x19dc5  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ScaleGroupData::get_ReportServer()
0x19dca  ldarg.2
0x19dcb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreInfo::get_OrganizationId()
0x19dd0  ldarg.2
0x19dd1  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreInfo::get_OrganizationUniqueName()
0x19dd6  ldc.i4.1
0x19dd7  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess::RestoreReportsFromDB(string reportServer, valuetype [mscorlib]System.Guid organizationId, string uniqueName, bool throwOnError)
0x19ddc  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationMetadataProvider::get_Instance()
0x19de1  ldarg.2
0x19de2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreInfo::get_OrganizationId()
0x19de7  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider::IsOsdpOrganization(valuetype [mscorlib]System.Guid)
0x19dec  brtrue.s loc_19E11
0x19dee  ldarg.2
0x19def  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreInfo::get_OrganizationId()
0x19df4  ldc.i4.s 0x42
0x19df6  ldstr    aRestoreRemoveM// "Restore -- Remove missing users from Co"...
0x19dfb  ldc.i4.0
0x19dfc  newarr   [mscorlib]System.Object
0x19e01  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x19e06  ldarg.2
0x19e07  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreInfo::get_OrganizationId()
0x19e0c  call     void Microsoft.Crm.CrmLive.Provisioning.Organization::SyncOrganizationUsers(valuetype [mscorlib]System.Guid organizationId)
0x19e11  ldarg.0
0x19e12  ldarg.2
0x19e13  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreInfo::get_OrganizationId()
0x19e18  ldloc.1
0x19e19  ldnull
0x19e1a  ldarg.2
0x19e1b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreInfo::get_SourceOrganizationId()
0x19e20  call     instance void Microsoft.Crm.CrmLive.Provisioning.Organization::PublishRestoreEvent(valuetype [mscorlib]System.Guid organizationId, class Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess orgAccess, class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.AdminApiTrace trace, valuetype [mscorlib]System.Guid srcOrganizationId)
0x19e25  ldarg.2
0x19e26  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreInfo::get_OrganizationId()
0x19e2b  ldc.i4.s 0x42
0x19e2d  ldstr    aRestoreMarking// "Restore -- Marking LastTaskStatus=Organ"...
0x19e32  ldc.i4.0
0x19e33  newarr   [mscorlib]System.Object
0x19e38  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x19e3d  ldloc.0
0x19e3e  ldarg.2
0x19e3f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreInfo::get_OrganizationId()
0x19e44  ldc.i4.0
0x19e45  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationService::SetLastTaskStatus(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationTaskStatus)
0x19e4a  leave.s  loc_19E6F
0x19e4c  stloc.s  6
0x19e4e  ldloc.s  6
0x19e50  ldarg.2
0x19e51  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreInfo::get_OrganizationId()
0x19e56  ldc.i4.s 0x42
0x19e58  ldstr    aException0// "Exception : {0}"
0x19e5d  ldc.i4.1
0x19e5e  newarr   [mscorlib]System.Object
0x19e63  dup
0x19e64  ldc.i4.0
0x19e65  ldloc.s  6
0x19e67  stelem.ref
0x19e68  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x19e6d  rethrow
0x19e6f  ret
```
