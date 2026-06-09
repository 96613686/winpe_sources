# Microsoft.Crm.CrmLive.Provisioning.UpdateLifecycleAction::Undo

- ea: `0x11f60`
- end: `0x12004`
- name: `Microsoft.Crm.CrmLive.Provisioning.UpdateLifecycleAction::Undo`
- size: `164`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x64b0`
- `0x6580`
- `0x65b0`
- `0x7020`
- `0x91b0`
- `0x11f60`

## string_xrefs

- `0x11f87`: `ProvisionUpdateLifeCycleUndo`

## pseudocode

```c

```

## disassembly

```asm
0x11f60  ldarg.0
0x11f61  ldarg.0
0x11f62  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x11f67  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x11f6c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x11f71  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::TraceUndoMethodEntry(valuetype [mscorlib]System.Guid organizationId)
0x11f76  ldarg.0
0x11f77  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x11f7c  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x11f81  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_UniqueName()
0x11f86  stloc.0
0x11f87  ldstr    aProvisionupdat_0// "ProvisionUpdateLifeCycleUndo"
0x11f8c  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.CrmLiveContext::.ctor(string)
0x11f91  stloc.2
0x11f92  ldloc.2
0x11f93  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.OrganizationLifecycleService::.ctor(class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.CrmLiveContext)
0x11f98  stloc.3
0x11f99  ldloc.3
0x11f9a  ldloc.0
0x11f9b  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.OrganizationLifecycleStatus [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.OrganizationLifecycleService::GetOrganizationLifecycleStatus(string)
0x11fa0  stloc.1
0x11fa1  leave.s  loc_11FA8
0x11fa3  pop
0x11fa4  ldc.i4.0
0x11fa5  stloc.1
0x11fa6  leave.s  loc_11FA8
0x11fa8  ldloc.1
0x11fa9  brfalse.s loc_11FCB
0x11fab  ldloc.2
0x11fac  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.CrmLiveContext::BeginTransaction()
0x11fb1  ldloc.3
0x11fb2  ldc.i4.6
0x11fb3  ldloc.1
0x11fb4  ldloc.0
0x11fb5  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.OrganizationLifecycleService::SwitchOrganizationLifecycleStatus(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.OrganizationLifecycleStatus, valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.OrganizationLifecycleStatus, string)
0x11fba  ldloc.2
0x11fbb  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.CrmLiveContext::CommitTransaction()
0x11fc0  leave.s  loc_11FD7
0x11fc2  pop
0x11fc3  ldloc.2
0x11fc4  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.CrmLiveContext::RollbackTransaction()
0x11fc9  leave.s  loc_11FD7
0x11fcb  leave.s  loc_11FD7
0x11fcd  ldloc.2
0x11fce  brfalse.s loc_11FD6
0x11fd0  ldloc.2
0x11fd1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x11fd6  endfinally
0x11fd7  ldarg.0
0x11fd8  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x11fdd  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x11fe2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x11fe7  ldc.i4.0
0x11fe8  call     void Microsoft.Crm.CrmLive.Provisioning.EnableOrganizationAction::EnableAsyncProcessing(valuetype [mscorlib]System.Guid organizationId, bool enabled)
0x11fed  ldarg.0
0x11fee  ldarg.0
0x11fef  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x11ff4  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x11ff9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x11ffe  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::TraceUndoMethodExit(valuetype [mscorlib]System.Guid organizationId)
0x12003  ret
```
