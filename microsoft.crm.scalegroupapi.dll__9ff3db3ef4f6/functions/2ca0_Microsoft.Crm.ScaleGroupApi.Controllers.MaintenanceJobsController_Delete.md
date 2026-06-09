# Microsoft.Crm.ScaleGroupApi.Controllers.MaintenanceJobsController::Delete

- ea: `0x2ca0`
- end: `0x2cc0`
- name: `Microsoft.Crm.ScaleGroupApi.Controllers.MaintenanceJobsController::Delete`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x2ca0  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationMaintenanceJobs::.ctor()
0x2ca5  ldarg.1
0x2ca6  call     class [Microsoft.Crm.Core]Microsoft.Crm.IScaleGroupInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.ScaleGroupInfoProvider::get_Instance()
0x2cab  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IScaleGroupInfoProvider::GetScaleGroupId()
0x2cb0  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDataCenterInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DataCenterInfoProvider::get_Instance()
0x2cb5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IDataCenterInfoProvider::GetDatacenterId()
0x2cba  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationMaintenanceJobs::DeleteJobs(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2cbf  ret
```
