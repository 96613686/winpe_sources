# Microsoft.Crm.CrmLive.Provisioning.DeleteOrganizationBackupExecutor::Execute

- ea: `0x14110`
- end: `0x14231`
- name: `Microsoft.Crm.CrmLive.Provisioning.DeleteOrganizationBackupExecutor::Execute`
- size: `289`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14110`
- `0x14240`
- `0x14260`
- `0x142d0`

## string_xrefs

- `0x14137`: `OrgId:{0}, backupfile:{1}, logfile:{2}, manifestfile:{3}`
- `0x141cb`: `Completed DeleteBackup. Details:{0}`

## pseudocode

```c

```

## disassembly

```asm
0x14110  ldarg.1
0x14111  ldstr    aTask// "task"
0x14116  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1411b  ldsfld   string [mscorlib]System.String::Empty
0x14120  stloc.0
0x14121  ldarg.1
0x14122  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x14127  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_ItemData()
0x1412c  call     T0x2B000073
0x14131  stloc.1
0x14132  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x14137  ldstr    aOrgid0Backupfi// "OrgId:{0}, backupfile:{1}, logfile:{2},"...
0x1413c  ldc.i4.4
0x1413d  newarr   [mscorlib]System.Object
0x14142  dup
0x14143  ldc.i4.0
0x14144  ldarg.1
0x14145  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x1414a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x1414f  box      [mscorlib]System.Guid
0x14154  stelem.ref
0x14155  dup
0x14156  ldc.i4.1
0x14157  ldloc.1
0x14158  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmOrganizationBackupData::get_BackupPathOnShare()
0x1415d  stelem.ref
0x1415e  dup
0x1415f  ldc.i4.2
0x14160  ldloc.1
0x14161  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmOrganizationBackupData::get_LogPathOnShare()
0x14166  stelem.ref
0x14167  dup
0x14168  ldc.i4.3
0x14169  ldloc.1
0x1416a  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmOrganizationBackupData::get_ManifestPathOnShare()
0x1416f  stelem.ref
0x14170  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x14175  stloc.0
0x14176  ldarg.1
0x14177  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x1417c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x14181  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x14186  ldstr    aStartingDeleti// "Starting deletion. Details:{0}"
0x1418b  ldc.i4.1
0x1418c  newarr   [mscorlib]System.Object
0x14191  dup
0x14192  ldc.i4.0
0x14193  ldloc.0
0x14194  stelem.ref
0x14195  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1419a  ldc.i4.1
0x1419b  call     void Microsoft.Crm.CrmLive.Provisioning.DeleteOrganizationBackupExecutor::AuditDeleteOperation(valuetype [mscorlib]System.Guid organizationId, string auditDetails, bool isSuccees)
0x141a0  ldloc.1
0x141a1  callvirt instance bool [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmOrganizationBackupData::get_CleanupAllBackups()
0x141a6  brfalse.s loc_141C0
0x141a8  ldarg.1
0x141a9  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x141ae  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x141b3  ldloc.1
0x141b4  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmOrganizationBackupData::get_BackupPathOnShare()
0x141b9  call     void Microsoft.Crm.CrmLive.Provisioning.DeleteOrganizationBackupExecutor::TryCleanupBackupsForDeletedOrganization(valuetype [mscorlib]System.Guid orgId, string backupPath)
0x141be  br.s     loc_141C6
0x141c0  ldloc.1
0x141c1  call     void Microsoft.Crm.CrmLive.Provisioning.DeleteOrganizationBackupExecutor::DeleteBackup(class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmOrganizationBackupData backupData)
0x141c6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x141cb  ldstr    aCompletedDelet// "Completed DeleteBackup. Details:{0}"
0x141d0  ldc.i4.1
0x141d1  newarr   [mscorlib]System.Object
0x141d6  dup
0x141d7  ldc.i4.0
0x141d8  ldloc.0
0x141d9  stelem.ref
0x141da  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x141df  stloc.0
0x141e0  ldarg.1
0x141e1  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x141e6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x141eb  ldloc.0
0x141ec  ldc.i4.1
0x141ed  call     void Microsoft.Crm.CrmLive.Provisioning.DeleteOrganizationBackupExecutor::AuditDeleteOperation(valuetype [mscorlib]System.Guid organizationId, string auditDetails, bool isSuccees)
0x141f2  ldc.i4.4
0x141f3  ldloc.0
0x141f4  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus, string)
0x141f9  stloc.2
0x141fa  leave.s  loc_1422F
0x141fc  stloc.3
0x141fd  ldarg.1
0x141fe  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x14203  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x14208  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1420d  ldstr    aFailedDeletion// "Failed deletion. Details:{0}"
0x14212  ldc.i4.1
0x14213  newarr   [mscorlib]System.Object
0x14218  dup
0x14219  ldc.i4.0
0x1421a  ldloc.0
0x1421b  stelem.ref
0x1421c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x14221  ldc.i4.1
0x14222  call     void Microsoft.Crm.CrmLive.Provisioning.DeleteOrganizationBackupExecutor::AuditDeleteOperation(valuetype [mscorlib]System.Guid organizationId, string auditDetails, bool isSuccees)
0x14227  ldloc.0
0x14228  ldloc.3
0x14229  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, class [mscorlib]System.Exception)
0x1422e  throw
0x1422f  ldloc.2
0x14230  ret
```
