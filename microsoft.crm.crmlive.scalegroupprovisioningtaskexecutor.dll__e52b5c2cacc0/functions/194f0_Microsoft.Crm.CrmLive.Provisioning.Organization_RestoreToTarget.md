# Microsoft.Crm.CrmLive.Provisioning.Organization::RestoreToTarget

- ea: `0x194f0`
- end: `0x198b8`
- name: `Microsoft.Crm.CrmLive.Provisioning.Organization::RestoreToTarget`
- size: `968`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x191e0`
- `0x19280`

## callees

- `0x194f0`
- `0x19ed0`
- `0x1a030`
- `0x1a0a0`
- `0x1a190`
- `0x1a270`
- `0x1a370`
- `0x1baa0`
- `0x1be30`
- `0x1be50`
- `0x1c080`
- `0x1c240`
- `0x1c3b0`

## string_xrefs

- `0x195a9`: `Restore -- Register new availability group and servers in config`
- `0x19708`: `Restore -- Update DNS information`
- `0x197ac`: `Restore -- Delete the organization maintenance jobs from the old scale group `
- `0x197c8`: `Restore -- Create the organization maintenance jobs to the new scale group `
- `0x1983f`: `Restore -- Remove missing users from ConfigDB`
- `0x19882`: `Restore -- Marking LastTaskStatus=OrganizationTaskStatus.Completed`

## pseudocode

```c

```

## disassembly

```asm
0x194f0  ldarg.1
0x194f1  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationService::.ctor(class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.AdminContext)
0x194f6  stloc.0
0x194f7  call     class Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::NewService()
0x194fc  stloc.1
0x194fd  ldstr    aAdminApiRestor// "Admin.Api.Restore(data.name={0}, backup"...
0x19502  ldc.i4.3
0x19503  newarr   [mscorlib]System.Object
0x19508  dup
0x19509  ldc.i4.0
0x1950a  ldarg.2
0x1950b  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_New()
0x19510  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.AdminApiData::get_Name()
0x19515  stelem.ref
0x19516  dup
0x19517  ldc.i4.1
0x19518  ldarg.3
0x19519  stelem.ref
0x1951a  dup
0x1951b  ldc.i4.2
0x1951c  ldarg.s  4
0x1951e  stelem.ref
0x1951f  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.AdminApiTrace::.ctor(string, object[])
0x19524  stloc.2
0x19525  ldloc.2
0x19526  ldstr    aRestoreDb0// "Restore -- db={0}"
0x1952b  ldc.i4.1
0x1952c  newarr   [mscorlib]System.Object
0x19531  dup
0x19532  ldc.i4.0
0x19533  ldarg.2
0x19534  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_New()
0x19539  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData::get_DBName()
0x1953e  stelem.ref
0x1953f  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTraceContext::Comment(string, object[])
0x19544  ldloc.0
0x19545  ldarg.2
0x19546  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_New()
0x1954b  ldarg.s  6
0x1954d  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationService::VerifyOrAssignNewServers(class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData, valuetype [mscorlib]System.Guid)
0x19552  ldloc.2
0x19553  ldstr    aRestoreDetermi// "Restore -- Determining StorageGroupId f"...
0x19558  ldc.i4.1
0x19559  newarr   [mscorlib]System.Object
0x1955e  dup
0x1955f  ldc.i4.0
0x19560  ldarg.2
0x19561  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_New()
0x19566  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData::get_PrimaryServer()
0x1956b  stelem.ref
0x1956c  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTraceContext::Comment(string, object[])
0x19571  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmServerService::.ctor()
0x19576  ldarg.2
0x19577  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_New()
0x1957c  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData::get_PrimaryServer()
0x19581  ldarg.s  6
0x19583  call     instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmServerService::Retrieve(string, valuetype [mscorlib]System.Guid)
0x19588  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData::get_StorageGroupId()
0x1958d  stloc.3
0x1958e  ldloc.2
0x1958f  ldstr    aRetrievedStora// "Retrieved StorageGroupId: {0}"
0x19594  ldc.i4.1
0x19595  newarr   [mscorlib]System.Object
0x1959a  dup
0x1959b  ldc.i4.0
0x1959c  ldloc.3
0x1959d  box      [mscorlib]System.Guid
0x195a2  stelem.ref
0x195a3  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTraceContext::Comment(string, object[])
0x195a8  ldloc.2
0x195a9  ldstr    aRestoreRegiste// "Restore -- Register new availability gr"...
0x195ae  ldc.i4.0
0x195af  newarr   [mscorlib]System.Object
0x195b4  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTraceContext::Comment(string, object[])
0x195b9  ldarg.2
0x195ba  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_OrganizationId()
0x195bf  ldarg.2
0x195c0  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_New()
0x195c5  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData::get_AvailabilityGroupName()
0x195ca  ldarg.2
0x195cb  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_New()
0x195d0  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData::get_PrimaryServer()
0x195d5  ldarg.2
0x195d6  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_New()
0x195db  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData::get_SecondaryServer()
0x195e0  ldarg.2
0x195e1  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ScaleGroupData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_NewScaleGroup()
0x195e6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ScaleGroupData::get_Id()
0x195eb  ldloc.3
0x195ec  ldarg.2
0x195ed  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ScaleGroupData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_NewScaleGroup()
0x195f2  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ScaleGroupData::get_ReportServer()
0x195f7  ldarg.2
0x195f8  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_New()
0x195fd  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData::get_DBName()
0x19602  ldarg.s  6
0x19604  call     void Microsoft.Crm.CrmLive.Provisioning.Organization::RegisterMappingInConfigDB(valuetype [mscorlib]System.Guid organizationId, string availabilityGroupName, string primarySqlServer, string secondarySqlServer, valuetype [mscorlib]System.Guid scaleGroupId, valuetype [mscorlib]System.Guid storageGroupId, string reportServerUrl, string dbName, valuetype [mscorlib]System.Guid datacenterId)
0x19609  ldarg.2
0x1960a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_OrganizationId()
0x1960f  ldarg.2
0x19610  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_New()
0x19615  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData::get_PrimaryServer()
0x1961a  ldloc.2
0x1961b  call     void Microsoft.Crm.CrmLive.Provisioning.Organization::CreateCustomerManagedKey(valuetype [mscorlib]System.Guid organizationId, string server, class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.AdminApiTrace trace)
0x19620  ldloc.2
0x19621  ldstr    aRestoreRestore// "Restore -- Restore primary backup={0}, "...
0x19626  ldc.i4.5
0x19627  newarr   [mscorlib]System.Object
0x1962c  dup
0x1962d  ldc.i4.0
0x1962e  ldarg.3
0x1962f  stelem.ref
0x19630  dup
0x19631  ldc.i4.1
0x19632  ldarg.s  4
0x19634  stelem.ref
0x19635  dup
0x19636  ldc.i4.2
0x19637  ldarg.2
0x19638  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_New()
0x1963d  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData::get_AvailabilityGroupName()
0x19642  stelem.ref
0x19643  dup
0x19644  ldc.i4.3
0x19645  ldarg.2
0x19646  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_New()
0x1964b  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData::get_PrimaryServer()
0x19650  stelem.ref
0x19651  dup
0x19652  ldc.i4.4
0x19653  ldarg.2
0x19654  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_New()
0x19659  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData::get_DBName()
0x1965e  stelem.ref
0x1965f  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTraceContext::Comment(string, object[])
0x19664  ldarg.2
0x19665  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_OrganizationId()
0x1966a  ldstr    aOrganization// "Organization"
0x1966f  ldstr    aAttachrestored// "AttachRestoreDb"
0x19674  call     void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.PerformanceAuditHistoryService::CreateStartEntry(valuetype [mscorlib]System.Guid, string, string)
0x19679  ldarg.2
0x1967a  callvirt instance bool [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_IsDatabasePrepared()
0x1967f  brfalse.s loc_196A8
0x19681  ldloc.1
0x19682  ldarg.2
0x19683  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_OrganizationId()
0x19688  ldarg.s  4
0x1968a  ldarg.2
0x1968b  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_New()
0x19690  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData::get_PrimaryServer()
0x19695  ldarg.2
0x19696  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_New()
0x1969b  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData::get_DBName()
0x196a0  ldc.i4.0
0x196a1  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess::RestoreLog(valuetype [mscorlib]System.Guid organizationId, string logFileName, string primaryServer, string dbName, bool isNoRecovery)
0x196a6  br.s     loc_196CD
0x196a8  ldloc.1
0x196a9  ldarg.2
0x196aa  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_OrganizationId()
0x196af  ldarg.3
0x196b0  ldarg.s  4
0x196b2  ldarg.2
0x196b3  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_New()
0x196b8  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData::get_PrimaryServer()
0x196bd  ldarg.2
0x196be  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_New()
0x196c3  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData::get_DBName()
0x196c8  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess::RestorePrimary(valuetype [mscorlib]System.Guid organizationId, string backupFileName, string logFileName, string primaryServer, string dbName)
0x196cd  ldarg.2
0x196ce  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_OrganizationId()
0x196d3  ldstr    aOrganization// "Organization"
0x196d8  ldstr    aAttachrestored// "AttachRestoreDb"
0x196dd  call     void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.PerformanceAuditHistoryService::CreateEndEntry(valuetype [mscorlib]System.Guid, string, string)
0x196e2  ldarg.2
0x196e3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_OrganizationId()
0x196e8  call     void Microsoft.Crm.CrmLive.Provisioning.Organization::SetOrgVersionInConfigDB(valuetype [mscorlib]System.Guid organizationId)
0x196ed  ldarg.2
0x196ee  callvirt instance bool [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_MakeUnique()
0x196f3  brfalse.s loc_19707
0x196f5  ldloc.1
0x196f6  ldarg.2
0x196f7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_OrganizationId()
0x196fc  ldarg.2
0x196fd  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_UniqueName()
0x19702  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess::MakeRestoredOrganizationUnique(valuetype [mscorlib]System.Guid organizationId, string organizationFriendlyName)
0x19707  ldloc.2
0x19708  ldstr    aRestoreUpdateD// "Restore -- Update DNS information"
0x1970d  ldc.i4.0
0x1970e  newarr   [mscorlib]System.Object
0x19713  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTraceContext::Comment(string, object[])
0x19718  call     class [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.PlatformClient [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.PlatformClient::ConnectLivePlatformService()
0x1971d  stloc.s  4
0x1971f  newobj   instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.DomainManagementRefreshOrgDomainsRequest::.ctor()
0x19724  stloc.s  5
0x19726  ldloc.s  5
0x19728  ldarg.2
0x19729  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_OrganizationId()
0x1972e  callvirt instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.DomainManagementRefreshOrgDomainsRequest::set_OrganizationId(valuetype [mscorlib]System.Guid)
0x19733  ldloc.s  4
0x19735  callvirt instance class [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.LivePlatformService [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.PlatformClient::get_LivePlatformService()
0x1973a  ldloc.s  5
0x1973c  callvirt instance class [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ServiceResponseMessage [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.LivePlatformService::Execute(class [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ServiceRequestMessage)
0x19741  pop
0x19742  leave.s  loc_19750
0x19744  ldloc.s  4
0x19746  brfalse.s loc_1974F
0x19748  ldloc.s  4
0x1974a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1974f  endfinally
0x19750  ldloc.2
0x19751  ldstr    aRestoreAddTheO// "Restore -- Add the organization to the "...
0x19756  ldc.i4.0
0x19757  newarr   [mscorlib]System.Object
0x1975c  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTraceContext::Comment(string, object[])
0x19761  ldarg.2
0x19762  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ScaleGroupData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_NewScaleGroup()
0x19767  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ScaleGroupData::get_Id()
0x1976c  ldarg.2
0x1976d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_OrganizationId()
0x19772  call     void [Microsoft.Crm.Core]Microsoft.Crm.StatisticsDatabase.StatisticsAdministrator::AddOrganizationToStatisticsDatabase(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x19777  leave.s  loc_1978E
0x19779  callvirt instance string [mscorlib]System.Exception::get_Message()
0x1977e  ldstr    aCannotInsertDu// "Cannot insert duplicate key"
0x19783  callvirt instance bool [mscorlib]System.String::Contains(string)
0x19788  brtrue.s loc_1978C
0x1978a  rethrow
0x1978c  leave.s  loc_1978E
0x1978e  ldarg.2
0x1978f  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ScaleGroupData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_NewScaleGroup()
0x19794  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ScaleGroupData::get_Id()
0x19799  ldarg.2
0x1979a  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ScaleGroupData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_OldScaleGroup()
0x1979f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ScaleGroupData::get_Id()
0x197a4  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x197a9  brfalse.s loc_197C7
0x197ab  ldloc.2
0x197ac  ldstr    aRestoreDeleteT// "Restore -- Delete the organization main"...
0x197b1  ldc.i4.0
0x197b2  newarr   [mscorlib]System.Object
0x197b7  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTraceContext::Comment(string, object[])
0x197bc  ldarg.2
0x197bd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_OrganizationId()
0x197c2  call     void Microsoft.Crm.CrmLive.Provisioning.Organization::TryDeleteOrganizationMaintenanceJobs(valuetype [mscorlib]System.Guid organizationId)
0x197c7  ldloc.2
0x197c8  ldstr    aRestoreCreateT// "Restore -- Create the organization main"...
0x197cd  ldc.i4.0
0x197ce  newarr   [mscorlib]System.Object
0x197d3  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTraceContext::Comment(string, object[])
0x197d8  call     class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.IOrganizationMaintenanceJobs [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationMaintenanceJobs::NewService()
0x197dd  ldarg.2
0x197de  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_OrganizationId()
0x197e3  ldarg.2
0x197e4  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ScaleGroupData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_NewScaleGroup()
0x197e9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ScaleGroupData::get_Id()
0x197ee  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.IOrganizationMaintenanceJobs::CreateJobs(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x197f3  ldarg.0
0x197f4  ldarg.2
0x197f5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_OrganizationId()
0x197fa  ldarg.2
0x197fb  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ScaleGroupData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_NewScaleGroup()
0x19800  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ScaleGroupData::get_Id()
0x19805  call     instance void Microsoft.Crm.CrmLive.Provisioning.Organization::CreateMaintenanceJobsInRemoteDatacenter(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid scalegroupId)
0x1980a  ldarg.s  5
0x1980c  brfalse.s loc_1982C
0x1980e  ldloc.1
0x1980f  ldarg.2
0x19810  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ScaleGroupData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_NewScaleGroup()
0x19815  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ScaleGroupData::get_ReportServer()
0x1981a  ldarg.2
0x1981b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_OrganizationId()
0x19820  ldarg.2
0x19821  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_UniqueName()
0x19826  ldc.i4.0
0x19827  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess::RestoreReportsFromDB(string reportServer, valuetype [mscorlib]System.Guid organizationId, string uniqueName, bool throwOnError)
0x1982c  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationMetadataProvider::get_Instance()
0x19831  ldarg.2
0x19832  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_OrganizationId()
0x19837  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider::IsOsdpOrganization(valuetype [mscorlib]System.Guid)
0x1983c  brtrue.s loc_1985A
0x1983e  ldloc.2
0x1983f  ldstr    aRestoreRemoveM// "Restore -- Remove missing users from Co"...
0x19844  ldc.i4.0
0x19845  newarr   [mscorlib]System.Object
0x1984a  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTraceContext::Comment(string, object[])
0x1984f  ldarg.2
0x19850  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_OrganizationId()
0x19855  call     void Microsoft.Crm.CrmLive.Provisioning.Organization::SyncOrganizationUsers(valuetype [mscorlib]System.Guid organizationId)
0x1985a  ldarg.2
0x1985b  callvirt instance valuetype [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveContext [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_Context()
0x19860  ldc.i4.1
0x19861  beq.s    loc_19881
0x19863  ldarg.2
0x19864  callvirt instance valuetype [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveContext [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_Context()
0x19869  brtrue.s loc_19873
0x1986b  ldarg.2
0x1986c  callvirt instance bool [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_MoveSG()
0x19871  brtrue.s loc_19881
0x19873  ldarg.0
0x19874  ldarg.2
0x19875  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_OrganizationId()
  ... truncated ...
```
