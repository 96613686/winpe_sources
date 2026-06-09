# Microsoft.Crm.CrmLive.Provisioning.ScaleGroupOrgDBUpdateExecutor::ExecuteUpdate

- ea: `0x29610`
- end: `0x296e0`
- name: `Microsoft.Crm.CrmLive.Provisioning.ScaleGroupOrgDBUpdateExecutor::ExecuteUpdate`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x28e90`
- `0x28eb0`
- `0x28ef0`
- `0x294e0`
- `0x29610`

## string_xrefs

- `0x2963c`: `Update parallelism of db updates from current default setting {0} to {1}`
- `0x296b1`: `Applying Org DB updates to orgs in scalegroup {0}`

## pseudocode

```c

```

## disassembly

```asm
0x29610  ldsfld   string [mscorlib]System.String::Empty
0x29615  stloc.0
0x29616  ldsfld   string [mscorlib]System.String::Empty
0x2961b  stloc.1
0x2961c  ldc.i4.0
0x2961d  stloc.2
0x2961e  ldstr    aSgorgs// "SGORGS"
0x29623  stloc.3
0x29624  ldarg.0
0x29625  call     instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.ScaleGroupUpdateData Microsoft.Crm.CrmLive.Provisioning.ScaleGroupOrgMaintenanceJobExecutor::get_OperationData()
0x2962a  callvirt instance int32 [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.ScaleGroupUpdateData::get_MaxConcurrentDBUpdates()
0x2962f  ldarg.0
0x29630  call     instance class Microsoft.Crm.CrmLive.Provisioning.ScaleGroupMaintenanceJobRuntimeData Microsoft.Crm.CrmLive.Provisioning.ScaleGroupOrgMaintenanceJobExecutor::get_RuntimeData()
0x29635  callvirt instance int32 Microsoft.Crm.CrmLive.Provisioning.ScaleGroupMaintenanceJobRuntimeData::get_OriginalMaxConcurrentDBUpdates()
0x2963a  ble.s    loc_296B1
0x2963c  ldstr    aUpdateParallel// "Update parallelism of db updates from c"...
0x29641  ldc.i4.2
0x29642  newarr   [mscorlib]System.Object
0x29647  dup
0x29648  ldc.i4.0
0x29649  ldarg.0
0x2964a  call     instance class Microsoft.Crm.CrmLive.Provisioning.ScaleGroupMaintenanceJobRuntimeData Microsoft.Crm.CrmLive.Provisioning.ScaleGroupOrgMaintenanceJobExecutor::get_RuntimeData()
0x2964f  callvirt instance int32 Microsoft.Crm.CrmLive.Provisioning.ScaleGroupMaintenanceJobRuntimeData::get_OriginalMaxConcurrentDBUpdates()
0x29654  box      [mscorlib]System.Int32
0x29659  stelem.ref
0x2965a  dup
0x2965b  ldc.i4.1
0x2965c  ldarg.0
0x2965d  call     instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.ScaleGroupUpdateData Microsoft.Crm.CrmLive.Provisioning.ScaleGroupOrgMaintenanceJobExecutor::get_OperationData()
0x29662  callvirt instance int32 [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.ScaleGroupUpdateData::get_MaxConcurrentDBUpdates()
0x29667  box      [mscorlib]System.Int32
0x2966c  stelem.ref
0x2966d  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string, object[])
0x29672  call     class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ICrmDeploymentService [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmDeploymentService::NewService()
0x29677  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x2967c  stloc.s  4
0x2967e  ldloc.s  4
0x29680  ldstr    aAsyncmaximumse// "AsyncMaximumServerConcurrentJobs"
0x29685  ldarg.0
0x29686  call     instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.ScaleGroupUpdateData Microsoft.Crm.CrmLive.Provisioning.ScaleGroupOrgMaintenanceJobExecutor::get_OperationData()
0x2968b  callvirt instance int32 [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.ScaleGroupUpdateData::get_MaxConcurrentDBUpdates()
0x29690  box      [mscorlib]System.Int32
0x29695  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x2969a  ldarg.0
0x2969b  call     instance string Microsoft.Crm.CrmLive.Provisioning.ScaleGroupOrgMaintenanceJobExecutor::get_ScaleGroupName()
0x296a0  ldloc.s  4
0x296a2  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ICrmDeploymentService::UpdateScaleGroupDeployment(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag)
0x296a7  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x296ac  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::Flush()
0x296b1  ldstr    aApplyingOrgDbU// "Applying Org DB updates to orgs in scal"...
0x296b6  ldc.i4.1
0x296b7  newarr   [mscorlib]System.Object
0x296bc  dup
0x296bd  ldc.i4.0
0x296be  ldarg.0
0x296bf  call     instance string Microsoft.Crm.CrmLive.Provisioning.ScaleGroupOrgMaintenanceJobExecutor::get_ScaleGroupName()
0x296c4  stelem.ref
0x296c5  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string, object[])
0x296ca  call     class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.IOrganizationMaintenanceJobs [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationMaintenanceJobs::NewService()
0x296cf  ldarg.0
0x296d0  call     instance string Microsoft.Crm.CrmLive.Provisioning.ScaleGroupOrgMaintenanceJobExecutor::get_ScaleGroupName()
0x296d5  ldloc.3
0x296d6  ldloc.0
0x296d7  ldloc.1
0x296d8  ldloc.2
0x296d9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.IOrganizationMaintenanceJobs::StartDBUpdates(string, string, string, string, bool)
0x296de  pop
0x296df  ret
```
