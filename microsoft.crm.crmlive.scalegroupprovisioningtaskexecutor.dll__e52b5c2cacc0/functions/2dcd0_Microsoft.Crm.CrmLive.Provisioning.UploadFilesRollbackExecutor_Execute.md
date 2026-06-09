# Microsoft.Crm.CrmLive.Provisioning.UploadFilesRollbackExecutor::Execute

- ea: `0x2dcd0`
- end: `0x2dd78`
- name: `Microsoft.Crm.CrmLive.Provisioning.UploadFilesRollbackExecutor::Execute`
- size: `168`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1360`
- `0x1370`
- `0x13d0`
- `0x1450`
- `0xdce0`
- `0xde80`
- `0x2dcd0`
- `0x2dd80`

## string_xrefs

- `0x2dd49`: `An exception was thrown while trying to rollback Uploaded files.`

## pseudocode

```c

```

## disassembly

```asm
0x2dcd0  newobj   instance void [System]System.Diagnostics.Stopwatch::.ctor()
0x2dcd5  stloc.0
0x2dcd6  ldarg.1
0x2dcd7  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x2dcdc  stloc.1
0x2dcdd  ldnull
0x2dcde  stloc.2
0x2dcdf  ldloc.0
0x2dce0  callvirt instance void [System]System.Diagnostics.Stopwatch::Start()
0x2dce5  ldloc.1
0x2dce6  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_ItemData()
0x2dceb  call     class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationBackupToAzureRollbackInfo [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationBackupToAzureRollbackInfo::Deserialize(string)
0x2dcf0  stloc.2
0x2dcf1  call     class Microsoft.Crm.CrmLive.Telemetry.UploadFilesRollbackEventSource Microsoft.Crm.CrmLive.Telemetry.UploadFilesRollbackEventSource::get_Instance()
0x2dcf6  ldloc.2
0x2dcf7  ldloc.1
0x2dcf8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_QueueItemId()
0x2dcfd  callvirt instance void Microsoft.Crm.CrmLive.Telemetry.UploadFilesRollbackEventSource::UploadFilesRollbackStart(class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationBackupToAzureRollbackInfo azureRollbackInfo, valuetype [mscorlib]System.Guid queueItemId)
0x2dd02  ldloc.2
0x2dd03  call     void Microsoft.Crm.CrmLive.Provisioning.BackupRestoreExecutorUtility::ValidateUploadFileRollbackExecutorItemData(class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationBackupToAzureRollbackInfo itemData)
0x2dd08  ldloc.2
0x2dd09  callvirt instance string[] [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationBackupToAzureRollbackInfo::get_BlobNames()
0x2dd0e  ldloc.2
0x2dd0f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationBackupToAzureRollbackInfo::get_RestorePointId()
0x2dd14  call     class [Microsoft.Crm.Azure]Microsoft.Crm.Azure.Models.AzureAccountSettings Microsoft.Crm.CrmLive.Provisioning.BackupRestoreExecutorUtility::GetAzureAccountSettings(valuetype [mscorlib]System.Guid restorePointId)
0x2dd19  call     void Microsoft.Crm.CrmLive.Provisioning.UploadFilesRollbackExecutor::CleanBlobsFromAzure(class [mscorlib]System.Collections.Generic.IEnumerable`1<string> blobNames, class [Microsoft.Crm.Azure]Microsoft.Crm.Azure.Models.AzureAccountSettings azureSettings)
0x2dd1e  ldc.i4.4
0x2dd1f  ldstr    aSuccess_0// "Success"
0x2dd24  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus, string)
0x2dd29  stloc.3
0x2dd2a  leave.s  loc_2DD76
0x2dd2c  stloc.s  4
0x2dd2e  call     class Microsoft.Crm.CrmLive.Telemetry.UploadFilesRollbackEventSource Microsoft.Crm.CrmLive.Telemetry.UploadFilesRollbackEventSource::get_Instance()
0x2dd33  ldloc.2
0x2dd34  ldloc.1
0x2dd35  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_QueueItemId()
0x2dd3a  ldloc.0
0x2dd3b  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0x2dd40  ldloc.s  4
0x2dd42  callvirt instance void Microsoft.Crm.CrmLive.Telemetry.UploadFilesRollbackEventSource::UploadFilesRollbackError(class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationBackupToAzureRollbackInfo azureRollbackInfo, valuetype [mscorlib]System.Guid queueItemId, int64 duration, class [mscorlib]System.Exception exception)
0x2dd47  ldc.i4.s 0xB
0x2dd49  ldstr    aAnExceptionWas_3// "An exception was thrown while trying to"...
0x2dd4e  ldloc.s  4
0x2dd50  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus, string, class [mscorlib]System.Exception)
0x2dd55  stloc.3
0x2dd56  leave.s  loc_2DD76
0x2dd58  ldloc.0
0x2dd59  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x2dd5e  call     class Microsoft.Crm.CrmLive.Telemetry.UploadFilesRollbackEventSource Microsoft.Crm.CrmLive.Telemetry.UploadFilesRollbackEventSource::get_Instance()
0x2dd63  ldloc.2
0x2dd64  ldloc.1
0x2dd65  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_QueueItemId()
0x2dd6a  ldloc.0
0x2dd6b  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0x2dd70  callvirt instance void Microsoft.Crm.CrmLive.Telemetry.UploadFilesRollbackEventSource::UploadFilesRollbackFinish(class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationBackupToAzureRollbackInfo azureRollbackInfo, valuetype [mscorlib]System.Guid queueItemId, int64 duration)
0x2dd75  endfinally
0x2dd76  ldloc.3
0x2dd77  ret
```
