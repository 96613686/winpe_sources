# Microsoft.Crm.CrmLive.Provisioning.ScaleGroupOrgMaintenanceJobExecutor::OnMonitorUpdateStatus

- ea: `0x28fd0`
- end: `0x29141`
- name: `Microsoft.Crm.CrmLive.Provisioning.ScaleGroupOrgMaintenanceJobExecutor::OnMonitorUpdateStatus`
- size: `369`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x28f60`

## callees

- `0x28e70`
- `0x28e90`
- `0x28eb0`
- `0x28ed0`
- `0x28ee0`
- `0x28ef0`
- `0x28f40`
- `0x28f50`
- `0x28fd0`
- `0x29340`
- `0x29390`
- `0x294b0`
- `0x29520`

## string_xrefs

- `0x29057`: `{0} out of {1} processed, waiting for operation {2} to complete. Current retry count is {3}`
- `0x29109`: `Failed Updates exceeds threshold`

## pseudocode

```c

```

## disassembly

```asm
0x28fd0  ldstr    aPollingStatusO// "Polling status of operation {0}"
0x28fd5  ldc.i4.1
0x28fd6  newarr   [mscorlib]System.Object
0x28fdb  dup
0x28fdc  ldc.i4.0
0x28fdd  ldarg.0
0x28fde  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.ScaleGroupOrgMaintenanceJobExecutor::get_OperationName()
0x28fe3  stelem.ref
0x28fe4  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string, object[])
0x28fe9  call     class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.IOrganizationMaintenanceJobs [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationMaintenanceJobs::NewService()
0x28fee  ldarg.0
0x28fef  call     instance string Microsoft.Crm.CrmLive.Provisioning.ScaleGroupOrgMaintenanceJobExecutor::get_ScaleGroupName()
0x28ff4  ldarg.0
0x28ff5  callvirt instance int32 Microsoft.Crm.CrmLive.Provisioning.ScaleGroupOrgMaintenanceJobExecutor::get_OperationType()
0x28ffa  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationMaintenanceJobStatusSummaryData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.IOrganizationMaintenanceJobs::RetrieveOrganizationMaintenanceJobStatusSummary(string, int32)
0x28fff  stloc.0
0x29000  ldarg.0
0x29001  call     instance class Microsoft.Crm.CrmLive.Provisioning.ScaleGroupMaintenanceJobRuntimeData Microsoft.Crm.CrmLive.Provisioning.ScaleGroupOrgMaintenanceJobExecutor::get_RuntimeData()
0x29006  ldloc.0
0x29007  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ScaleGroupMaintenanceJobRuntimeData::set_Summary(class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationMaintenanceJobStatusSummaryData value)
0x2900c  ldarg.0
0x2900d  ldfld    class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueManager Microsoft.Crm.CrmLive.Provisioning.ScaleGroupOrgMaintenanceJobExecutor::_queueManager
0x29012  ldarg.0
0x29013  call     instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem Microsoft.Crm.CrmLive.Provisioning.ScaleGroupOrgMaintenanceJobExecutor::get_QueueItem()
0x29018  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_QueueItemId()
0x2901d  ldarg.0
0x2901e  call     instance class Microsoft.Crm.CrmLive.Provisioning.ScaleGroupMaintenanceJobRuntimeData Microsoft.Crm.CrmLive.Provisioning.ScaleGroupOrgMaintenanceJobExecutor::get_RuntimeData()
0x29023  call     T0x2B0000C0
0x29028  ldnull
0x29029  ldnull
0x2902a  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueManager::UpdateQueueItem(valuetype [mscorlib]System.Guid, string, object, string)
0x2902f  ldloc.0
0x29030  callvirt instance int32 [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationMaintenanceJobStatusSummaryData::get_CompletedOrganizationCount()
0x29035  ldloc.0
0x29036  callvirt instance int32 [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationMaintenanceJobStatusSummaryData::get_TotalNumberOfOrgs()
0x2903b  beq.s    loc_290A6
0x2903d  ldarg.0
0x2903e  ldloc.0
0x2903f  ldloca.s 1
0x29041  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0x29047  ldloc.1
0x29048  ldloca.s 1
0x2904a  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0x29050  ldloc.1
0x29051  ldc.i4.2
0x29052  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ScaleGroupOrgMaintenanceJobExecutor::RefreshUpdateHistory(class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationMaintenanceJobStatusSummaryData summary, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> startTime, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> endTime, valuetype [Microsoft.Crm.Constants]Microsoft.Crm.OperationTaskStatus status)
0x29057  ldstr    a0OutOf1Process// "{0} out of {1} processed, waiting for o"...
0x2905c  ldc.i4.4
0x2905d  newarr   [mscorlib]System.Object
0x29062  dup
0x29063  ldc.i4.0
0x29064  ldloc.0
0x29065  callvirt instance int32 [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationMaintenanceJobStatusSummaryData::get_CompletedOrganizationCount()
0x2906a  box      [mscorlib]System.Int32
0x2906f  stelem.ref
0x29070  dup
0x29071  ldc.i4.1
0x29072  ldloc.0
0x29073  callvirt instance int32 [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationMaintenanceJobStatusSummaryData::get_TotalNumberOfOrgs()
0x29078  box      [mscorlib]System.Int32
0x2907d  stelem.ref
0x2907e  dup
0x2907f  ldc.i4.2
0x29080  ldarg.0
0x29081  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.ScaleGroupOrgMaintenanceJobExecutor::get_OperationName()
0x29086  stelem.ref
0x29087  dup
0x29088  ldc.i4.3
0x29089  ldarg.0
0x2908a  call     instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem Microsoft.Crm.CrmLive.Provisioning.ScaleGroupOrgMaintenanceJobExecutor::get_QueueItem()
0x2908f  callvirt instance int32 [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_RetryCount()
0x29094  box      [mscorlib]System.Int32
0x29099  stelem.ref
0x2909a  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string, object[])
0x2909f  ldarg.0
0x290a0  call     instance class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult Microsoft.Crm.CrmLive.Provisioning.ScaleGroupOrgMaintenanceJobExecutor::Retry()
0x290a5  ret
0x290a6  ldarg.0
0x290a7  call     instance class Microsoft.Crm.CrmLive.Provisioning.ScaleGroupMaintenanceJobRuntimeData Microsoft.Crm.CrmLive.Provisioning.ScaleGroupOrgMaintenanceJobExecutor::get_RuntimeData()
0x290ac  callvirt instance bool Microsoft.Crm.CrmLive.Provisioning.ScaleGroupMaintenanceJobRuntimeData::get_RetryOrgUpdates()
0x290b1  brfalse.s loc_290C9
0x290b3  ldloc.0
0x290b4  callvirt instance int32 [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationMaintenanceJobStatusSummaryData::get_FailedOrganizationCount()
0x290b9  ldc.i4.0
0x290ba  ble.s    loc_290C9
0x290bc  ldarg.0
0x290bd  call     instance void Microsoft.Crm.CrmLive.Provisioning.ScaleGroupOrgMaintenanceJobExecutor::RetryOrgUpdates()
0x290c2  ldarg.0
0x290c3  call     instance class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult Microsoft.Crm.CrmLive.Provisioning.ScaleGroupOrgMaintenanceJobExecutor::Retry()
0x290c8  ret
0x290c9  ldloc.0
0x290ca  callvirt instance int32 [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationMaintenanceJobStatusSummaryData::get_FailedOrganizationCount()
0x290cf  ldarg.0
0x290d0  call     instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.ScaleGroupUpdateData Microsoft.Crm.CrmLive.Provisioning.ScaleGroupOrgMaintenanceJobExecutor::get_OperationData()
0x290d5  callvirt instance int32 [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.ScaleGroupUpdateData::get_FailureThreshold()
0x290da  ldloc.0
0x290db  callvirt instance int32 [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationMaintenanceJobStatusSummaryData::get_TotalNumberOfOrgs()
0x290e0  mul
0x290e1  ldc.i4.s 0x64
0x290e3  div
0x290e4  ble.s    loc_29114
0x290e6  ldarg.0
0x290e7  ldloc.0
0x290e8  ldloca.s 1
0x290ea  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0x290f0  ldloc.1
0x290f1  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x290f6  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::.ctor(var<u1>)
0x290fb  ldc.i4.3
0x290fc  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ScaleGroupOrgMaintenanceJobExecutor::RefreshUpdateHistory(class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationMaintenanceJobStatusSummaryData summary, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> startTime, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> endTime, valuetype [Microsoft.Crm.Constants]Microsoft.Crm.OperationTaskStatus status)
0x29101  ldarg.0
0x29102  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ScaleGroupOrgMaintenanceJobExecutor::CleanUpAfterUpdate()
0x29107  ldc.i4.s 0xB
0x29109  ldstr    aFailedUpdatesE// "Failed Updates exceeds threshold"
0x2910e  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus, string)
0x29113  ret
0x29114  ldarg.0
0x29115  ldloc.0
0x29116  ldloca.s 1
0x29118  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0x2911e  ldloc.1
0x2911f  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x29124  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::.ctor(var<u1>)
0x29129  ldc.i4.4
0x2912a  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ScaleGroupOrgMaintenanceJobExecutor::RefreshUpdateHistory(class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationMaintenanceJobStatusSummaryData summary, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> startTime, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> endTime, valuetype [Microsoft.Crm.Constants]Microsoft.Crm.OperationTaskStatus status)
0x2912f  ldarg.0
0x29130  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ScaleGroupOrgMaintenanceJobExecutor::CleanUpAfterUpdate()
0x29135  ldc.i4.4
0x29136  ldstr    aSuccess// "success"
0x2913b  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus, string)
0x29140  ret
```
