# Microsoft.Crm.CrmLive.Provisioning.OrganizationUpgradeExecutor::ExecuteInternal

- ea: `0x25770`
- end: `0x25b5d`
- name: `Microsoft.Crm.CrmLive.Provisioning.OrganizationUpgradeExecutor::ExecuteInternal`
- size: `1005`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x32f60`

## callees

- `0x18ff0`
- `0x1ae10`
- `0x1ba60`
- `0x1bb50`
- `0x25620`
- `0x25770`
- `0x25b60`
- `0x25c70`
- `0x25d00`
- `0x25d60`
- `0x25e80`
- `0x25eb0`
- `0x25f60`
- `0x25f70`
- `0x25fd0`
- `0x2f0f0`

## string_xrefs

- `0x25a24`: `CrmScaleGroupProvisioningService`
- `0x257f1`: `Exception during CalculateOrganizationUpgradeOrUpdateRequirement`
- `0x25897`: `PreUpgradeException attempting to retrieve database usage before upgrade operation`
- `0x2595e`: `Comparing new DataMB and IndexMB usage for org {0}`
- `0x259e1`: `Exception during post upgrade processing`
- `0x25b22`: `Upgrade organization: create SetupOrgDBMirroring queue item.`

## pseudocode

```c

```

## disassembly

```asm
0x25770  ldarg.0
0x25771  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x25776  call     instance void Microsoft.Crm.CrmLive.Provisioning.OrganizationUpgradeExecutor::set_WorkThread(class [mscorlib]System.Threading.Thread value)
0x2577b  ldarg.1
0x2577c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationUpgradeInfo::get_OrganizationId()
0x25781  stloc.0
0x25782  ldloc.0
0x25783  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x25788  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2578d  ldstr    aCannotUpgradeA// "Cannot upgrade an organization with emp"...
0x25792  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x25797  ldloc.0
0x25798  call     void Microsoft.Crm.CrmLive.Provisioning.TracingListener::SetOrganizationId(valuetype [mscorlib]System.Guid organizationId)
0x2579d  ldarg.1
0x2579e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationUpgradeInfo::get_OrganizationId()
0x257a3  ldstr    aOrganization// "Organization"
0x257a8  ldstr    aUpgrade// "Upgrade"
0x257ad  call     void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.PerformanceAuditHistoryService::CreateStartEntry(valuetype [mscorlib]System.Guid, string, string)
0x257b2  ldloc.0
0x257b3  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState Microsoft.Crm.CrmLive.Provisioning.OrganizationUpgradeExecutor::GetOrganizationState(valuetype [mscorlib]System.Guid orgId)
0x257b8  stloc.1
0x257b9  ldarg.1
0x257ba  callvirt instance int32 [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationUpgradeInfo::get_FinalState()
0x257bf  ldc.i4.m1
0x257c0  beq.s    loc_257C9
0x257c2  ldarg.1
0x257c3  callvirt instance int32 [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationUpgradeInfo::get_FinalState()
0x257c8  stloc.1
0x257c9  ldsfld   string [mscorlib]System.String::Empty
0x257ce  stloc.2
0x257cf  ldnull
0x257d0  stloc.3
0x257d1  ldnull
0x257d2  stloc.s  4
0x257d4  ldc.i4.0
0x257d5  stloc.s  5
0x257d7  ldloc.0
0x257d8  call     void Microsoft.Crm.CrmLive.Provisioning.Organization::UpdateActiveDirectoryGroupsForOnebox(valuetype [mscorlib]System.Guid organizationId)
0x257dd  ldarg.0
0x257de  ldloc.0
0x257df  ldc.i4.4
0x257e0  call     instance void Microsoft.Crm.CrmLive.Provisioning.OrganizationUpgradeExecutor::SetOrganizationState(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState state)
0x257e5  ldloc.0
0x257e6  call     valuetype Microsoft.Crm.CrmLive.Provisioning.OrganizationUpgradeOrUpdateRequirement Microsoft.Crm.CrmLive.Provisioning.Organization::CalculateOrganizationUpgradeOrUpdateRequirement(valuetype [mscorlib]System.Guid organizationId)
0x257eb  stloc.s  6
0x257ed  leave.s  loc_257FE
0x257ef  stloc.s  7
0x257f1  ldstr    aExceptionDurin// "Exception during CalculateOrganizationU"...
0x257f6  ldloc.s  7
0x257f8  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.PreUpgradeException::.ctor(string, class [mscorlib]System.Exception)
0x257fd  throw
0x257fe  ldloc.s  6
0x25800  brtrue.s loc_25827
0x25802  ldarg.0
0x25803  ldstr    aSkippingUpgrad// "Skipping upgrade of Organization {0} si"...
0x25808  ldc.i4.1
0x25809  newarr   [mscorlib]System.Object
0x2580e  dup
0x2580f  ldc.i4.0
0x25810  ldloc.0
0x25811  box      [mscorlib]System.Guid
0x25816  stelem.ref
0x25817  call     instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.TaskExecutorBase::TraceInfo(string, object[])
0x2581c  ldstr    aSkippingUpgrad_0// "Skipping upgrade since it is up to date"...
0x25821  stloc.2
0x25822  br       loc_259EE
0x25827  ldloc.s  6
0x25829  ldc.i4.3
0x2582a  bne.un.s loc_25837
0x2582c  ldstr    aOperationIsNot// "Operation is not supported because curr"...
0x25831  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.PreUpgradeException::.ctor(string)
0x25836  throw
0x25837  ldarg.1
0x25838  callvirt instance valuetype [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationUpgradeContext [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationUpgradeInfo::get_Context()
0x2583d  ldc.i4.1
0x2583e  beq.s    loc_25861
0x25840  ldarg.0
0x25841  ldstr    aBackingUpPreUp// "Backing up pre-upgraded Organization {0"...
0x25846  ldc.i4.1
0x25847  newarr   [mscorlib]System.Object
0x2584c  dup
0x2584d  ldc.i4.0
0x2584e  ldloc.0
0x2584f  box      [mscorlib]System.Guid
0x25854  stelem.ref
0x25855  call     instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.TaskExecutorBase::TraceInfo(string, object[])
0x2585a  ldloc.0
0x2585b  call     class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationBackupData Microsoft.Crm.CrmLive.Provisioning.OrganizationUpgradeExecutor::BackupOrganization(valuetype [mscorlib]System.Guid orgId)
0x25860  stloc.3
0x25861  ldnull
0x25862  stloc.s  8
0x25864  ldnull
0x25865  stloc.s  9
0x25867  ldarg.0
0x25868  ldstr    aRecordingExist// "Recording existing DataMB and IndexMB u"...
0x2586d  ldc.i4.1
0x2586e  newarr   [mscorlib]System.Object
0x25873  dup
0x25874  ldc.i4.0
0x25875  ldloc.0
0x25876  box      [mscorlib]System.Guid
0x2587b  stelem.ref
0x2587c  call     instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.TaskExecutorBase::TraceInfo(string, object[])
0x25881  ldloc.0
0x25882  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationDatabaseUtility::.ctor(valuetype [mscorlib]System.Guid)
0x25887  stloc.s  8
0x25889  ldloc.s  8
0x2588b  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationStorageData [Microsoft.Crm.Core]Microsoft.Crm.OrganizationDatabaseUtility::DefineDBSize()
0x25890  stloc.s  9
0x25892  leave.s  loc_258A9
0x25894  ldloc.0
0x25895  ldc.i4.s 0xA
0x25897  ldstr    aPreupgradeexce// "PreUpgradeException attempting to retri"...
0x2589c  ldc.i4.0
0x2589d  newarr   [mscorlib]System.Object
0x258a2  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x258a7  leave.s  loc_258A9
0x258a9  ldloc.s  6
0x258ab  ldc.i4.2
0x258ac  bne.un.s loc_258B7
0x258ae  ldarg.0
0x258af  ldarg.1
0x258b0  call     instance void Microsoft.Crm.CrmLive.Provisioning.OrganizationUpgradeExecutor::PerformOrganizationUpgrade(class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationUpgradeInfo upgradeInfo)
0x258b5  br.s     loc_25903
0x258b7  ldloc.s  6
0x258b9  ldc.i4.1
0x258ba  bne.un.s loc_258C4
0x258bc  ldarg.1
0x258bd  call     void Microsoft.Crm.CrmLive.Provisioning.OrganizationUpgradeExecutor::ApplyOrganizationUpdates(class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationUpgradeInfo upgradeInfo)
0x258c2  br.s     loc_25903
0x258c4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x258c9  ldstr    aUnhandledValue// "Unhandled value for {0}.{1}"
0x258ce  ldc.i4.2
0x258cf  newarr   [mscorlib]System.Object
0x258d4  dup
0x258d5  ldc.i4.0
0x258d6  ldloc.s  6
0x258d8  box      Microsoft.Crm.CrmLive.Provisioning.OrganizationUpgradeOrUpdateRequirement
0x258dd  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x258e2  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x258e7  stelem.ref
0x258e8  dup
0x258e9  ldc.i4.1
0x258ea  ldloca.s 6
0x258ec  constrained. Microsoft.Crm.CrmLive.Provisioning.OrganizationUpgradeOrUpdateRequirement
0x258f2  callvirt instance string [mscorlib]System.Object::ToString()
0x258f7  stelem.ref
0x258f8  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x258fd  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.DBUpdateException::.ctor(string)
0x25902  throw
0x25903  nop
0x25904  ldarg.1
0x25905  callvirt instance bool [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationUpgradeInfo::get_IsCduPrevalidation()
0x2590a  brtrue.s loc_2592A
0x2590c  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x25911  stloc.s  0xA
0x25913  ldloc.0
0x25914  ldloc.s  0xA
0x25916  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Provisioning.CommerceUpdateTagQueueItemCreator::Create(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService)
0x2591b  pop
0x2591c  leave.s  loc_2592A
0x2591e  ldloc.s  0xA
0x25920  brfalse.s loc_25929
0x25922  ldloc.s  0xA
0x25924  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x25929  endfinally
0x2592a  ldarg.1
0x2592b  callvirt instance valuetype [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationUpgradeContext [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationUpgradeInfo::get_Context()
0x25930  ldc.i4.1
0x25931  beq.s    loc_25955
0x25933  ldarg.0
0x25934  ldstr    aBackingUpUpgra// "Backing up upgraded Organization {0} da"...
0x25939  ldc.i4.1
0x2593a  newarr   [mscorlib]System.Object
0x2593f  dup
0x25940  ldc.i4.0
0x25941  ldloc.0
0x25942  box      [mscorlib]System.Guid
0x25947  stelem.ref
0x25948  call     instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.TaskExecutorBase::TraceInfo(string, object[])
0x2594d  ldloc.0
0x2594e  call     class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationBackupData Microsoft.Crm.CrmLive.Provisioning.OrganizationUpgradeExecutor::BackupOrganization(valuetype [mscorlib]System.Guid orgId)
0x25953  stloc.s  4
0x25955  ldloc.s  8
0x25957  brfalse.s loc_259D3
0x25959  ldloc.s  9
0x2595b  brfalse.s loc_259D3
0x2595d  ldarg.0
0x2595e  ldstr    aComparingNewDa// "Comparing new DataMB and IndexMB usage "...
0x25963  ldc.i4.1
0x25964  newarr   [mscorlib]System.Object
0x25969  dup
0x2596a  ldc.i4.0
0x2596b  ldloc.0
0x2596c  box      [mscorlib]System.Guid
0x25971  stelem.ref
0x25972  call     instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.TaskExecutorBase::TraceInfo(string, object[])
0x25977  ldloc.s  8
0x25979  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationStorageData [Microsoft.Crm.Core]Microsoft.Crm.OrganizationDatabaseUtility::DefineDBSize()
0x2597e  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.OrganizationStorageData::get_TotalDataSize()
0x25983  ldloc.s  9
0x25985  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.OrganizationStorageData::get_TotalDataSize()
0x2598a  sub
0x2598b  stloc.s  0xB
0x2598d  ldloc.s  0xB
0x2598f  ldc.i4.0
0x25990  ble.s    loc_259D3
0x25992  ldarg.0
0x25993  ldstr    aAdding0MbFreeS// "Adding {0} MB free storage to org {1}"
0x25998  ldc.i4.2
0x25999  newarr   [mscorlib]System.Object
0x2599e  dup
0x2599f  ldc.i4.0
0x259a0  ldloc.s  0xB
0x259a2  box      [mscorlib]System.Int32
0x259a7  stelem.ref
0x259a8  dup
0x259a9  ldc.i4.1
0x259aa  ldloc.0
0x259ab  box      [mscorlib]System.Guid
0x259b0  stelem.ref
0x259b1  call     instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.TaskExecutorBase::TraceInfo(string, object[])
0x259b6  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmOrganizationService::.ctor()
0x259bb  ldloc.0
0x259bc  ldloc.s  0xB
0x259be  ldarg.1
0x259bf  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationUpgradeInfo::get_SourceScaleGroupId()
0x259c4  call     class [Microsoft.Crm.Core]Microsoft.Crm.IScaleGroupInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.ScaleGroupInfoProvider::get_Instance()
0x259c9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IScaleGroupInfoProvider::GetScaleGroupId()
0x259ce  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmOrganizationService::AddFreeStorageDueToUpgrade(valuetype [mscorlib]System.Guid, int32, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x259d3  ldloc.3
0x259d4  ldloc.s  4
0x259d6  ldc.i4.1
0x259d7  call     string Microsoft.Crm.CrmLive.Provisioning.OrganizationUpgradeExecutor::RetrieveDetailsMessage(class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationBackupData originalBackupData, class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationBackupData upgradedBackupData, bool successfulUpgrade)
0x259dc  stloc.2
0x259dd  leave.s  loc_259EE
0x259df  stloc.s  0xC
0x259e1  ldstr    aExceptionDurin_0// "Exception during post upgrade processin"...
0x259e6  ldloc.s  0xC
0x259e8  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.PostUpgradeException::.ctor(string, class [mscorlib]System.Exception)
0x259ed  throw
0x259ee  ldloc.0
0x259ef  ldstr    aOrganization// "Organization"
0x259f4  ldstr    aUpgrade// "Upgrade"
0x259f9  call     void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.PerformanceAuditHistoryService::CreateEndEntry(valuetype [mscorlib]System.Guid, string, string)
0x259fe  ldc.i4.4
0x259ff  ldloc.2
0x25a00  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus, string)
0x25a05  stloc.s  0xD
0x25a07  leave    loc_25B5A
0x25a0c  stloc.s  0xE
0x25a0e  ldc.i4.1
0x25a0f  stloc.s  5
0x25a11  ldloc.3
0x25a12  ldloc.s  4
0x25a14  ldc.i4.0
0x25a15  call     string Microsoft.Crm.CrmLive.Provisioning.OrganizationUpgradeExecutor::RetrieveDetailsMessage(class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationBackupData originalBackupData, class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationBackupData upgradedBackupData, bool successfulUpgrade)
0x25a1a  stloc.2
0x25a1b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::.ctor()
0x25a20  stloc.s  0xF
0x25a22  ldloc.s  0xF
0x25a24  ldstr    aCrmscalegroupp// "CrmScaleGroupProvisioningService"
0x25a29  ldc.i4.1
0x25a2a  ldc.i4   0xC000460C
0x25a2f  conv.u8
0x25a30  ldc.i4.3
0x25a31  newarr   [mscorlib]System.Object
0x25a36  dup
0x25a37  ldc.i4.0
0x25a38  ldloc.0
0x25a39  box      [mscorlib]System.Guid
0x25a3e  stelem.ref
0x25a3f  dup
0x25a40  ldc.i4.1
0x25a41  ldloc.2
0x25a42  stelem.ref
0x25a43  dup
0x25a44  ldc.i4.2
0x25a45  ldloc.s  0xE
0x25a47  stelem.ref
0x25a48  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::WriteEntry(string, valuetype [System]System.Diagnostics.EventLogEntryType, int64, object[])
0x25a4d  leave.s  loc_25A5B
0x25a4f  ldloc.s  0xF
0x25a51  brfalse.s loc_25A5A
0x25a53  ldloc.s  0xF
0x25a55  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x25a5a  endfinally
0x25a5b  nop
0x25a5c  ldloc.0
0x25a5d  ldstr    aFull// "FULL"
0x25a62  call     void Microsoft.Crm.CrmLive.Provisioning.OrganizationUpgradeExecutor::SetDatabaseRecoveryMode(valuetype [mscorlib]System.Guid orgId, string recoveryMode)
0x25a67  leave.s  loc_25A78
0x25a69  pop
0x25a6a  ldloc.2
0x25a6b  ldstr    aFailureInSetti// "\nFailure in setting the recovery mode "...
0x25a70  call     string [mscorlib]System.String::Concat(string, string)
0x25a75  stloc.2
0x25a76  leave.s  loc_25A78
0x25a78  nop
0x25a79  ldarg.1
  ... truncated ...
```
