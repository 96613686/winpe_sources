# Microsoft.Crm.CrmLive.Provisioning.DownloadFilesRollbackExecutor::Execute

- ea: `0x14690`
- end: `0x1474c`
- name: `Microsoft.Crm.CrmLive.Provisioning.DownloadFilesRollbackExecutor::Execute`
- size: `188`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callees

- `0xdd0`
- `0xde0`
- `0xe40`
- `0xec0`
- `0xdd70`
- `0x14690`
- `0x14750`
- `0x14770`
- `0x147f0`

## string_xrefs

- `0x1471b`: `An exception was thrown while trying to rollback downloaded/joined files.`

## pseudocode

```c

```

## disassembly

```asm
0x14690  newobj   instance void [System]System.Diagnostics.Stopwatch::.ctor()
0x14695  stloc.0
0x14696  newobj   instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem::.ctor()
0x1469b  stloc.1
0x1469c  newobj   instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreFromAzureInfo::.ctor()
0x146a1  stloc.2
0x146a2  ldarg.1
0x146a3  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x146a8  stloc.1
0x146a9  ldloc.1
0x146aa  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_ItemData()
0x146af  call     class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreFromAzureInfo [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreFromAzureInfo::Deserialize(string)
0x146b4  stloc.2
0x146b5  ldloc.2
0x146b6  call     void Microsoft.Crm.CrmLive.Provisioning.BackupRestoreExecutorUtility::ValidateDownloadExecutorItemData(class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreFromAzureInfo itemData)
0x146bb  ldloc.0
0x146bc  callvirt instance void [System]System.Diagnostics.Stopwatch::Start()
0x146c1  call     class Microsoft.Crm.CrmLive.Telemetry.DownloadFilesRollbackEventSource Microsoft.Crm.CrmLive.Telemetry.DownloadFilesRollbackEventSource::get_Instance()
0x146c6  ldloc.2
0x146c7  ldloc.1
0x146c8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_QueueItemId()
0x146cd  callvirt instance void Microsoft.Crm.CrmLive.Telemetry.DownloadFilesRollbackEventSource::DownloadFilesRollbackStart(class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreFromAzureInfo azureRestoreInfo, valuetype [mscorlib]System.Guid queueItemId)
0x146d2  ldloc.2
0x146d3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreFromAzureInfo::get_RestorePointId()
0x146d8  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.RestorePointBackupInfo> Microsoft.Crm.CrmLive.Provisioning.DownloadFilesRollbackExecutor::GetBackupInfoFromRestorePoint(valuetype [mscorlib]System.Guid restorePointId)
0x146dd  call     class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.Crm.CrmLive.Provisioning.DownloadFilesRollbackExecutor::GetDirectories(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.RestorePointBackupInfo> blobInfos)
0x146e2  stloc.3
0x146e3  ldloc.2
0x146e4  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreFromAzureInfo::get_DownloadPath()
0x146e9  ldloc.3
0x146ea  call     void Microsoft.Crm.CrmLive.Provisioning.DownloadFilesRollbackExecutor::DoCleanUp(string downloadPath, class [mscorlib]System.Collections.Generic.IList`1<string> directories)
0x146ef  ldc.i4.4
0x146f0  ldstr    aSuccess_0// "Success"
0x146f5  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus, string)
0x146fa  stloc.s  4
0x146fc  leave.s  loc_14749
0x146fe  stloc.s  5
0x14700  call     class Microsoft.Crm.CrmLive.Telemetry.DownloadFilesRollbackEventSource Microsoft.Crm.CrmLive.Telemetry.DownloadFilesRollbackEventSource::get_Instance()
0x14705  ldloc.2
0x14706  ldloc.1
0x14707  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_QueueItemId()
0x1470c  ldloc.0
0x1470d  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0x14712  ldloc.s  5
0x14714  callvirt instance void Microsoft.Crm.CrmLive.Telemetry.DownloadFilesRollbackEventSource::DownloadFilesRollbackError(class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreFromAzureInfo azureRestoreInfo, valuetype [mscorlib]System.Guid queueItemId, int64 duration, class [mscorlib]System.Exception exception)
0x14719  ldc.i4.s 0xB
0x1471b  ldstr    aAnExceptionWas_0// "An exception was thrown while trying to"...
0x14720  ldloc.s  5
0x14722  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus, string, class [mscorlib]System.Exception)
0x14727  stloc.s  4
0x14729  leave.s  loc_14749
0x1472b  ldloc.0
0x1472c  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x14731  call     class Microsoft.Crm.CrmLive.Telemetry.DownloadFilesRollbackEventSource Microsoft.Crm.CrmLive.Telemetry.DownloadFilesRollbackEventSource::get_Instance()
0x14736  ldloc.2
0x14737  ldloc.1
0x14738  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_QueueItemId()
0x1473d  ldloc.0
0x1473e  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0x14743  callvirt instance void Microsoft.Crm.CrmLive.Telemetry.DownloadFilesRollbackEventSource::DownloadFilesRollbackFinish(class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreFromAzureInfo azureRestoreInfo, valuetype [mscorlib]System.Guid queueItemId, int64 duration)
0x14748  endfinally
0x14749  ldloc.s  4
0x1474b  ret
```
