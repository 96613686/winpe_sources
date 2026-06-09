# Microsoft.Crm.CrmLive.Provisioning.SetupOrgDBMirroringExecutor::Execute

- ea: `0x170b0`
- end: `0x174ea`
- name: `Microsoft.Crm.CrmLive.Provisioning.SetupOrgDBMirroringExecutor::Execute`
- size: `1082`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x170b0`
- `0x174f0`
- `0x17900`
- `0x17ad0`
- `0x17c20`
- `0x17d50`
- `0x17d70`
- `0x17e00`

## string_xrefs

- `0x171a6`: `Task execution should wait to DatabaseLogBackup job {0} to complete`
- `0x17457`: `CrmProvisioningService`
- `0x174d1`: `SetupOrgDBMirroring completed successfully`

## pseudocode

```c

```

## disassembly

```asm
0x170b0  ldarg.1
0x170b1  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x170b6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x170bb  call     bool [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmOrganizationService::IsBackedByXdb(valuetype [mscorlib]System.Guid)
0x170c0  stloc.0
0x170c1  ldloc.0
0x170c2  brtrue.s loc_170D8
0x170c4  ldarg.1
0x170c5  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x170ca  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x170cf  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationType [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmOrganizationService::GetOrganizationType(valuetype [mscorlib]System.Guid)
0x170d4  ldc.i4.s 9
0x170d6  bne.un.s loc_1710B
0x170d8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x170dd  ldstr    aSetupOrgDbMirr// "Setup Org DB Mirroring skipped. Not app"...
0x170e2  ldc.i4.1
0x170e3  newarr   [mscorlib]System.Object
0x170e8  dup
0x170e9  ldc.i4.0
0x170ea  ldloc.0
0x170eb  brtrue.s loc_170F4
0x170ed  ldstr    aTestdriveOrg// "TestDrive org"
0x170f2  br.s     loc_170F9
0x170f4  ldstr    aHostedOnAzureS// "hosted on Azure SQL DB"
0x170f9  stelem.ref
0x170fa  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x170ff  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string)
0x17104  ldc.i4.4
0x17105  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus)
0x1710a  ret
0x1710b  ldarg.1
0x1710c  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x17111  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_ItemData()
0x17116  call     class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationDBInfo [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationDBInfo::Deserialize(string)
0x1711b  stloc.1
0x1711c  ldnull
0x1711d  stloc.2
0x1711e  ldarg.0
0x1711f  ldflda   valuetype [mscorlib]System.Nullable`1<bool> Microsoft.Crm.CrmLive.Provisioning.SetupOrgDBMirroringExecutor::_canApplyCustomerManagedKey
0x17124  initobj  valuetype [mscorlib]System.Nullable`1<bool>
0x1712a  ldnull
0x1712b  stloc.3
0x1712c  ldc.i4.0
0x1712d  stloc.s  4
0x1712f  ldstr    aSetuporgdbmirr// "SetupOrgDBMirroring started. Retry coun"...
0x17134  ldc.i4.1
0x17135  newarr   [mscorlib]System.Object
0x1713a  dup
0x1713b  ldc.i4.0
0x1713c  ldarg.1
0x1713d  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x17142  callvirt instance int32 [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_RetryCount()
0x17147  box      [mscorlib]System.Int32
0x1714c  stelem.ref
0x1714d  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string, object[])
0x17152  ldarg.1
0x17153  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x17158  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x1715d  call     class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationMaintenanceJobData[] [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationMaintenanceJobs::RetrieveOrganizationMaintenanceJobs(valuetype [mscorlib]System.Guid)
0x17162  stloc.s  5
0x17164  ldc.i4.0
0x17165  stloc.s  6
0x17167  br.s     loc_171E8
0x17169  ldloc.s  5
0x1716b  ldloc.s  6
0x1716d  ldelem.ref
0x1716e  stloc.s  7
0x17170  ldloc.s  7
0x17172  callvirt instance int32 [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationMaintenanceJobData::get_OperationType()
0x17177  ldc.i4.s 0x1A
0x17179  bne.un.s loc_171E2
0x1717b  ldloc.s  7
0x1717d  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationMaintenanceJobData::get_NextRuntime()
0x17182  stloc.s  9
0x17184  ldloca.s 9
0x17186  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x1718b  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::Subtract(valuetype [mscorlib]System.DateTime)
0x17190  stloc.s  8
0x17192  ldloc.s  7
0x17194  callvirt instance int32 [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationMaintenanceJobData::get_State()
0x17199  ldc.i4.1
0x1719a  beq.s    loc_171A6
0x1719c  ldloca.s 8
0x1719e  call     instance int32 [mscorlib]System.TimeSpan::get_Minutes()
0x171a3  ldc.i4.5
0x171a4  bge.s    loc_171E2
0x171a6  ldstr    aTaskExecutionS// "Task execution should wait to DatabaseL"...
0x171ab  ldc.i4.1
0x171ac  newarr   [mscorlib]System.Object
0x171b1  dup
0x171b2  ldc.i4.0
0x171b3  ldloc.s  7
0x171b5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationMaintenanceJobData::get_Id()
0x171ba  box      [mscorlib]System.Guid
0x171bf  stelem.ref
0x171c0  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string, object[])
0x171c5  ldc.i4.s 0xC
0x171c7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x171cc  ldstr    aDatabaseLogBac// "Database Log Backup Job is actually run"...
0x171d1  ldc.i4.0
0x171d2  newarr   [mscorlib]System.Object
0x171d7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x171dc  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus, string)
0x171e1  ret
0x171e2  ldloc.s  6
0x171e4  ldc.i4.1
0x171e5  add
0x171e6  stloc.s  6
0x171e8  ldloc.s  6
0x171ea  ldloc.s  5
0x171ec  ldlen
0x171ed  conv.i4
0x171ee  blt      loc_17169
0x171f3  nop
0x171f4  ldarg.1
0x171f5  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x171fa  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_QueueItemId()
0x171ff  stloc.s  0xA
0x17201  ldarg.1
0x17202  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x17207  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x1720c  stloc.s  0xB
0x1720e  ldarg.0
0x1720f  ldloc.s  0xB
0x17211  call     instance void Microsoft.Crm.CrmLive.Provisioning.SetupOrgDBMirroringExecutor::SetDatabaseMirroringSetupInProgress(valuetype [mscorlib]System.Guid orgId)
0x17216  ldloc.1
0x17217  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationDBInfo::get_AvailabilityGroupName()
0x1721c  call     class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.ReplicaStatus [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.ReplicaStatus::GetReplicaStatus(string)
0x17221  stloc.2
0x17222  ldstr    aGetreplicastat// "GetReplicaStatus: Availability Group: {"...
0x17227  ldc.i4.5
0x17228  newarr   [mscorlib]System.Object
0x1722d  dup
0x1722e  ldc.i4.0
0x1722f  ldloc.1
0x17230  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationDBInfo::get_AvailabilityGroupName()
0x17235  stelem.ref
0x17236  dup
0x17237  ldc.i4.1
0x17238  ldloc.2
0x17239  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.ReplicaStatus::get_PrimaryReplica()
0x1723e  stelem.ref
0x1723f  dup
0x17240  ldc.i4.2
0x17241  ldloc.2
0x17242  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.ReplicaStatus::get_SyncReplica()
0x17247  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1724c  brfalse.s loc_17255
0x1724e  ldsfld   string [mscorlib]System.String::Empty
0x17253  br.s     loc_1725B
0x17255  ldloc.2
0x17256  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.ReplicaStatus::get_SyncReplica()
0x1725b  stelem.ref
0x1725c  dup
0x1725d  ldc.i4.3
0x1725e  ldloc.2
0x1725f  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.ReplicaStatus::get_AsyncReplica1()
0x17264  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x17269  brfalse.s loc_17272
0x1726b  ldsfld   string [mscorlib]System.String::Empty
0x17270  br.s     loc_17278
0x17272  ldloc.2
0x17273  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.ReplicaStatus::get_AsyncReplica1()
0x17278  stelem.ref
0x17279  dup
0x1727a  ldc.i4.4
0x1727b  ldloc.2
0x1727c  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.ReplicaStatus::get_AsyncReplica2()
0x17281  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x17286  brfalse.s loc_1728F
0x17288  ldsfld   string [mscorlib]System.String::Empty
0x1728d  br.s     loc_17295
0x1728f  ldloc.2
0x17290  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.ReplicaStatus::get_AsyncReplica2()
0x17295  stelem.ref
0x17296  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string, object[])
0x1729b  ldloc.1
0x1729c  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationDBInfo::get_AvailabilityGroupName()
0x172a1  ldloc.2
0x172a2  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.ReplicaStatus::get_PrimaryReplica()
0x172a7  ldloc.1
0x172a8  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationDBInfo::get_DatabaseName()
0x172ad  call     bool [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.SqlUtility::IsDatabaseInAvailabilityGroup(string, string, string)
0x172b2  brtrue.s loc_172D6
0x172b4  ldarg.0
0x172b5  ldloc.s  0xB
0x172b7  ldloc.1
0x172b8  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationDBInfo::get_AvailabilityGroupName()
0x172bd  ldloc.1
0x172be  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationDBInfo::get_PrimaryServer()
0x172c3  ldloc.2
0x172c4  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.ReplicaStatus::get_PrimaryReplica()
0x172c9  ldloc.1
0x172ca  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationDBInfo::get_DatabaseName()
0x172cf  ldloca.s 3
0x172d1  call     instance void Microsoft.Crm.CrmLive.Provisioning.SetupOrgDBMirroringExecutor::CreateDatabasePrimaryReplica(valuetype [mscorlib]System.Guid organizationId, string availabilityGroupName, string organizationServer, string primaryReplica, string databaseName, class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmOrganizationBackupData& crmOrganizationBackupData)
0x172d6  ldarg.0
0x172d7  ldloc.1
0x172d8  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationDBInfo::get_AvailabilityGroupName()
0x172dd  ldloc.2
0x172de  ldarg.1
0x172df  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x172e4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x172e9  call     instance void Microsoft.Crm.CrmLive.Provisioning.SetupOrgDBMirroringExecutor::UpdateCrmConfiguration(string availabilityGroupName, class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.ReplicaStatus replicaStatus, valuetype [mscorlib]System.Guid organizationId)
0x172ee  ldc.i4.1
0x172ef  stloc.s  4
0x172f1  ldarg.0
0x172f2  ldloc.s  0xA
0x172f4  ldloc.s  0xB
0x172f6  ldloc.1
0x172f7  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationDBInfo::get_AvailabilityGroupName()
0x172fc  ldloc.2
0x172fd  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.ReplicaStatus::get_PrimaryReplica()
0x17302  ldloc.2
0x17303  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.ReplicaStatus::get_SyncReplica()
0x17308  ldloc.1
0x17309  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationDBInfo::get_DatabaseName()
0x1730e  ldloca.s 3
0x17310  call     instance void Microsoft.Crm.CrmLive.Provisioning.SetupOrgDBMirroringExecutor::CreateDatabaseReplica(valuetype [mscorlib]System.Guid queueItemId, valuetype [mscorlib]System.Guid organizationId, string availabilityGroupName, string primaryReplica, string replica, string databaseName, class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmOrganizationBackupData& crmOrganizationBackupData)
0x17315  ldarg.0
0x17316  ldloc.s  0xA
0x17318  ldloc.s  0xB
0x1731a  ldloc.1
0x1731b  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationDBInfo::get_AvailabilityGroupName()
0x17320  ldloc.2
0x17321  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.ReplicaStatus::get_PrimaryReplica()
0x17326  ldloc.2
0x17327  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.ReplicaStatus::get_AsyncReplica1()
0x1732c  ldloc.1
0x1732d  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationDBInfo::get_DatabaseName()
0x17332  ldloca.s 3
0x17334  call     instance void Microsoft.Crm.CrmLive.Provisioning.SetupOrgDBMirroringExecutor::CreateDatabaseReplica(valuetype [mscorlib]System.Guid queueItemId, valuetype [mscorlib]System.Guid organizationId, string availabilityGroupName, string primaryReplica, string replica, string databaseName, class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmOrganizationBackupData& crmOrganizationBackupData)
0x17339  ldarg.0
0x1733a  ldloc.s  0xA
0x1733c  ldloc.s  0xB
0x1733e  ldloc.1
0x1733f  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationDBInfo::get_AvailabilityGroupName()
0x17344  ldloc.2
0x17345  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.ReplicaStatus::get_PrimaryReplica()
0x1734a  ldloc.2
0x1734b  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.ReplicaStatus::get_AsyncReplica2()
0x17350  ldloc.1
0x17351  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationDBInfo::get_DatabaseName()
0x17356  ldloca.s 3
0x17358  call     instance void Microsoft.Crm.CrmLive.Provisioning.SetupOrgDBMirroringExecutor::CreateDatabaseReplica(valuetype [mscorlib]System.Guid queueItemId, valuetype [mscorlib]System.Guid organizationId, string availabilityGroupName, string primaryReplica, string replica, string databaseName, class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmOrganizationBackupData& crmOrganizationBackupData)
0x1735d  ldarg.0
0x1735e  ldarg.1
0x1735f  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x17364  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x17369  ldloc.1
0x1736a  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationDBInfo::get_DatabaseName()
0x1736f  call     instance void Microsoft.Crm.CrmLive.Provisioning.SetupOrgDBMirroringExecutor::SetSqlCellLevelEncryptionOnAllReplicas(valuetype [mscorlib]System.Guid organizationId, string databaseName)
0x17374  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.SqlEncryption.TransparentDataEncryptionService::.ctor()
0x17379  ldloc.2
0x1737a  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.ReplicaStatus::get_PrimaryReplica()
0x1737f  ldarg.1
0x17380  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x17385  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x1738a  ldloc.1
0x1738b  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationDBInfo::get_DatabaseName()
0x17390  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.SqlEncryption.TransparentDataEncryptionService::EnableEncryption(string, valuetype [mscorlib]System.Guid, string)
0x17395  leave    loc_174D1
0x1739a  stloc.s  0xC
0x1739c  ldstr    aErrorSettingUp// "Error setting up mirroring: error messa"...
0x173a1  ldc.i4.2
0x173a2  newarr   [mscorlib]System.Object
0x173a7  dup
0x173a8  ldc.i4.0
0x173a9  ldloc.s  0xC
0x173ab  callvirt instance string [mscorlib]System.Exception::get_Message()
0x173b0  stelem.ref
0x173b1  dup
0x173b2  ldc.i4.1
0x173b3  ldloc.s  0xC
0x173b5  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0x173ba  stelem.ref
0x173bb  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string, object[])
0x173c0  ldloc.s  0xC
0x173c2  ldarg.1
0x173c3  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x173c8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x173cd  ldc.i4.s 0xA
0x173cf  ldstr    aErrorSettingUp_0// "Error setting up mirroring rolling back"...
0x173d4  ldc.i4.0
0x173d5  newarr   [mscorlib]System.Object
0x173da  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x173df  ldarg.0
0x173e0  ldarg.1
0x173e1  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x173e6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_QueueItemId()
0x173eb  ldarg.1
0x173ec  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x173f1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x173f6  ldloc.1
0x173f7  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationDBInfo::get_AvailabilityGroupName()
0x173fc  ldloc.2
0x173fd  ldloc.1
0x173fe  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationDBInfo::get_DatabaseName()
0x17403  ldloc.s  4
0x17405  call     instance void Microsoft.Crm.CrmLive.Provisioning.SetupOrgDBMirroringExecutor::RollbackFromFailure(valuetype [mscorlib]System.Guid queueItemId, valuetype [mscorlib]System.Guid organizationId, string availabilityGroupName, class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.ReplicaStatus status, string databaseName, bool wasConfigurationUpdated)
  ... truncated ...
```
