# Microsoft.Crm.CrmLive.Provisioning.OrganizationUpgradeExecutor::ApplyOrganizationUpdates

- ea: `0x25c70`
- end: `0x25cfe`
- name: `Microsoft.Crm.CrmLive.Provisioning.OrganizationUpgradeExecutor::ApplyOrganizationUpdates`
- size: `142`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x25770`

## callees

- `0x1c240`
- `0x1c3b0`
- `0x25c70`

## string_xrefs

- `0x25c98`: `Configuring and publishing reports for {0} to {1}`
- `0x25cd1`: `Retrying database updates after exception occured: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x25c70  ldarg.0
0x25c71  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationUpgradeInfo::get_OrganizationId()
0x25c76  stloc.0
0x25c77  ldarg.0
0x25c78  callvirt instance valuetype [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationUpgradeContext [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationUpgradeInfo::get_Context()
0x25c7d  ldc.i4.1
0x25c7e  bne.un.s loc_25CBE
0x25c80  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmOrganizationService::.ctor()
0x25c85  ldloc.0
0x25c86  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmOrganizationService::Retrieve(valuetype [mscorlib]System.Guid)
0x25c8b  dup
0x25c8c  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_UniqueName()
0x25c91  stloc.1
0x25c92  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_SrsUrl()
0x25c97  stloc.2
0x25c98  ldstr    aConfiguringAnd// "Configuring and publishing reports for "...
0x25c9d  ldc.i4.2
0x25c9e  newarr   [mscorlib]System.Object
0x25ca3  dup
0x25ca4  ldc.i4.0
0x25ca5  ldloc.1
0x25ca6  stelem.ref
0x25ca7  dup
0x25ca8  ldc.i4.1
0x25ca9  ldloc.2
0x25caa  stelem.ref
0x25cab  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string, object[])
0x25cb0  call     class Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::NewService()
0x25cb5  ldloc.2
0x25cb6  ldloc.0
0x25cb7  ldloc.1
0x25cb8  ldc.i4.0
0x25cb9  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess::RestoreReportsFromDB(string reportServer, valuetype [mscorlib]System.Guid organizationId, string uniqueName, bool throwOnError)
0x25cbe  ldloc.0
0x25cbf  ldc.i4.2
0x25cc0  ldc.i4.0
0x25cc1  newobj   instance void [Microsoft.Crm.Tools.Admin.DMSnapinLib]Microsoft.Crm.Tools.Admin.OrganizationDBUpdateInstaller::.ctor(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Tools.Admin.DMSnapinLib]Microsoft.Crm.Tools.Admin.DMSnapinLib.Organization.OrgDbUpdateSource, valuetype [Microsoft.Crm.Tools.Admin.DMSnapinLib]Microsoft.Crm.Tools.Admin.DMSnapinLib.Organization.OrgDbUpdateMode)
0x25cc6  stloc.3
0x25cc7  ldloc.3
0x25cc8  callvirt instance void [Microsoft.Crm.Tools.Admin.DMSnapinLib]Microsoft.Crm.Tools.Admin.OrganizationOperation::Execute()
0x25ccd  leave.s  loc_25CFD
0x25ccf  stloc.s  4
0x25cd1  ldstr    aRetryingDataba// "Retrying database updates after excepti"...
0x25cd6  ldc.i4.1
0x25cd7  newarr   [mscorlib]System.Object
0x25cdc  dup
0x25cdd  ldc.i4.0
0x25cde  ldloc.s  4
0x25ce0  callvirt instance string [mscorlib]System.Object::ToString()
0x25ce5  stelem.ref
0x25ce6  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string, object[])
0x25ceb  ldloc.3
0x25cec  callvirt instance void [Microsoft.Crm.Tools.Admin.DMSnapinLib]Microsoft.Crm.Tools.Admin.OrganizationOperation::Execute()
0x25cf1  leave.s  loc_25CFD
0x25cf3  ldloc.3
0x25cf4  brfalse.s loc_25CFC
0x25cf6  ldloc.3
0x25cf7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x25cfc  endfinally
0x25cfd  ret
```
