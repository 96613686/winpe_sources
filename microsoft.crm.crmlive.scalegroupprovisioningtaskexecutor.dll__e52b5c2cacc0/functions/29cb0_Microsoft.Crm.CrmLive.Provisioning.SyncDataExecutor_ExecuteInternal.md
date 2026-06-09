# Microsoft.Crm.CrmLive.Provisioning.SyncDataExecutor::ExecuteInternal

- ea: `0x29cb0`
- end: `0x2a0a4`
- name: `Microsoft.Crm.CrmLive.Provisioning.SyncDataExecutor::ExecuteInternal`
- size: `1012`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `service_task, broker_com_uri`

## callers

- `0x29c60`

## callees

- `0x1110`
- `0x1120`
- `0x1220`
- `0xf420`
- `0xf4f0`
- `0xf510`
- `0x18280`
- `0x29cb0`
- `0x2a0b0`
- `0x2a150`
- `0x2a640`
- `0x2a740`
- `0x2a7e0`
- `0x2a820`
- `0x2a8a0`
- `0x2a8d0`
- `0x2aad0`
- `0x2ae90`
- `0x2b240`
- `0x2b340`
- `0x2b690`

## string_xrefs

- `0x29dcd`: `Waiting for child items to complete`
- `0x2a013`: `Waiting for child items to complete`
- `0x29ebd`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\TaskExecutor\SyncDataExecutor.cs`
- `0x29f15`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\TaskExecutor\SyncDataExecutor.cs`

## pseudocode

```c

```

## disassembly

```asm
0x29cb0  ldarg.1
0x29cb1  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x29cb6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x29cbb  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationType [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmOrganizationService::GetOrganizationType(valuetype [mscorlib]System.Guid)
0x29cc0  ldc.i4.s 9
0x29cc2  bne.un.s loc_29CCF
0x29cc4  ldstr    aSyncdataQueueI// "SyncData queue items cannot execute on "...
0x29cc9  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x29cce  throw
0x29ccf  ldarg.1
0x29cd0  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x29cd5  stloc.0
0x29cd6  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x29cdb  stloc.1
0x29cdc  ldsfld   string [mscorlib]System.String::Empty
0x29ce1  stloc.2
0x29ce2  ldc.i4.0
0x29ce3  stloc.3
0x29ce4  ldloc.0
0x29ce5  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_ItemData()
0x29cea  call     T0x2B000035
0x29cef  stloc.s  4
0x29cf1  ldc.i4.0
0x29cf2  stloc.s  5
0x29cf4  ldloc.s  4
0x29cf6  callvirt instance bool [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.SyncDataDetails::get_IgnoreLicenseChecks()
0x29cfb  brfalse.s loc_29D00
0x29cfd  ldc.i4.2
0x29cfe  stloc.s  5
0x29d00  ldarg.0
0x29d01  call     T0x2B000036
0x29d06  ldarg.1
0x29d07  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x29d0c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x29d11  ldloc.s  5
0x29d13  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProviderFactory::GetProvider(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.DataProviderType)
0x29d18  stfld    class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider Microsoft.Crm.CrmLive.Provisioning.SyncDataExecutor::_directoryProvider
0x29d1d  ldarg.0
0x29d1e  ldarg.1
0x29d1f  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x29d24  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x29d29  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncDataExecutor::_orgId
0x29d2e  ldloc.0
0x29d2f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_DependentQueueItemId()
0x29d34  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x29d39  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x29d3e  brfalse  loc_29DFC
0x29d43  ldloc.0
0x29d44  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_ItemRuntimeData()
0x29d49  ldloca.s 3
0x29d4b  call     T0x2B0000C3
0x29d50  brfalse  loc_29DD8
0x29d55  ldloc.3
0x29d56  ldc.i4.1
0x29d57  bne.un   loc_29DFC
0x29d5c  ldloc.0
0x29d5d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_QueueItemId()
0x29d62  call     class [mscorlib]System.Tuple`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus, valuetype [mscorlib]System.Guid> Microsoft.Crm.CrmLive.Provisioning.SyncDataExecutor::GetChildItemResults(valuetype [mscorlib]System.Guid parentId)
0x29d67  stloc.s  7
0x29d69  ldloc.s  7
0x29d6b  callvirt instance var<u1> class [mscorlib]System.Tuple`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus, valuetype [mscorlib]System.Guid>::get_Item1()
0x29d70  ldc.i4.s 0xC
0x29d72  beq.s    loc_29D81
0x29d74  ldloc.s  7
0x29d76  callvirt instance var<u1> class [mscorlib]System.Tuple`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus, valuetype [mscorlib]System.Guid>::get_Item1()
0x29d7b  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus)
0x29d80  ret
0x29d81  ldloc.s  7
0x29d83  callvirt instance var<u1> class [mscorlib]System.Tuple`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus, valuetype [mscorlib]System.Guid>::get_Item2()
0x29d88  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x29d8d  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x29d92  ldstr    aWeMustWaitOnAV// "We must wait on a valid child item"
0x29d97  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x29d9c  call     class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueManager [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueManager::NewManager()
0x29da1  ldarg.1
0x29da2  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x29da7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_QueueItemId()
0x29dac  ldloca.s 3
0x29dae  constrained. Microsoft.Crm.CrmLive.Provisioning.SyncDataExecutorJoinDependentBehavior
0x29db4  callvirt instance string [mscorlib]System.Object::ToString()
0x29db9  ldloc.s  7
0x29dbb  callvirt instance var<u1> class [mscorlib]System.Tuple`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus, valuetype [mscorlib]System.Guid>::get_Item2()
0x29dc0  box      [mscorlib]System.Guid
0x29dc5  ldnull
0x29dc6  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueManager::UpdateQueueItem(valuetype [mscorlib]System.Guid, string, object, string)
0x29dcb  ldc.i4.s 0xC
0x29dcd  ldstr    aWaitingForChil_0// "Waiting for child items to complete"
0x29dd2  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus, string)
0x29dd7  ret
0x29dd8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x29ddd  ldstr    aSyncdataexecto// "SyncDataExector waited on a dependent q"...
0x29de2  ldc.i4.1
0x29de3  newarr   [mscorlib]System.Object
0x29de8  dup
0x29de9  ldc.i4.0
0x29dea  ldloc.0
0x29deb  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_ItemRuntimeData()
0x29df0  stelem.ref
0x29df1  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x29df6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x29dfb  throw
0x29dfc  ldloc.s  4
0x29dfe  call     class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.CrmLive.Provisioning.SyncDataExecutor::GetObjectsToSync(class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.SyncDataDetails details)
0x29e03  stloc.s  6
0x29e05  ldloc.s  6
0x29e07  call     T0x2B00009A
0x29e0c  brfalse  loc_29E9A
0x29e11  ldc.i4.0
0x29e12  stloc.s  8
0x29e14  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x29e19  stloc.s  9
0x29e1b  ldarg.0
0x29e1c  ldloc.0
0x29e1d  ldloc.s  6
0x29e1f  ldloc.s  4
0x29e21  callvirt instance bool [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.SyncDataDetails::get_IgnoreLicenseChecks()
0x29e26  ldloca.s 8
0x29e28  call     instance void Microsoft.Crm.CrmLive.Provisioning.SyncDataExecutor::SyncByObject(class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem item, class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid> objectsToSync, bool ignoreLicenseChecks, [out] int32& countOfObjectsSynchronized)
0x29e2d  call     class Microsoft.Crm.CrmLive.Telemetry.SyncDataEventSource Microsoft.Crm.CrmLive.Telemetry.SyncDataEventSource::get_Instance()
0x29e32  ldarg.0
0x29e33  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncDataExecutor::_orgId
0x29e38  ldloc.s  6
0x29e3a  call     T0x2B000049
0x29e3f  ldloc.s  8
0x29e41  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x29e46  ldloc.s  9
0x29e48  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x29e4d  stloc.s  0xA
0x29e4f  ldloca.s 0xA
0x29e51  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0x29e56  conv.i8
0x29e57  callvirt instance void Microsoft.Crm.CrmLive.Telemetry.SyncDataEventSource::SyncDataByObjectInfo(valuetype [mscorlib]System.Guid organizationId, int32 numObjectsToSync, int32 numObjectsSyncd, int64 elapsedMilliseconds)
0x29e5c  leave    loc_2A046
0x29e61  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.CrmOsdpInitialUserNotFoundException::get_ContextId()
0x29e66  ldarg.1
0x29e67  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncDataExecutor::CreateWaitForInitialUserQueueItem(valuetype [mscorlib]System.Guid contextId, class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask fromTask)
0x29e6c  stloc.1
0x29e6d  ldstr    aNoUserFoundFor// "No user found for this org to provision"
0x29e72  stloc.2
0x29e73  ldc.i4.0
0x29e74  stloc.3
0x29e75  leave    loc_2A046
0x29e7a  stloc.s  0xB
0x29e7c  ldstr    aErrorOccuredWh// "Error occured while syncing object"
0x29e81  ldloc.s  0xB
0x29e83  ldarg.1
0x29e84  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x29e89  callvirt instance int32 [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_RetryCount()
0x29e8e  call     class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::BuildRetry(string, class [mscorlib]System.Exception, int32)
0x29e93  stloc.s  0xC
0x29e95  leave    loc_2A0A1
0x29e9a  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationSettingsProvider::get_Instance()
0x29e9f  ldloc.0
0x29ea0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x29ea5  ldc.i4.1
0x29ea6  newarr   [mscorlib]System.String
0x29eab  dup
0x29eac  ldc.i4.0
0x29ead  ldstr    aProvisioningac// "ProvisioningActionInProgress"
0x29eb2  stelem.ref
0x29eb3  ldc.i4   0xB5
0x29eb8  ldstr    aExecuteinterna// "ExecuteInternal"
0x29ebd  ldstr    aDDbsShDccm2110_42// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x29ec2  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider::GetOrganization(valuetype [mscorlib]System.Guid, string[], int32, string, string)
0x29ec7  ldstr    aProvisioningac// "ProvisioningActionInProgress"
0x29ecc  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x29ed1  castclass [mscorlib]System.String
0x29ed6  stloc.s  0xD
0x29ed8  ldloc.s  0xD
0x29eda  brfalse.s loc_29EEE
0x29edc  ldloc.s  0xD
0x29ede  ldstr    aFalse// "false"
0x29ee3  ldc.i4.5
0x29ee4  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x29ee9  ldc.i4.0
0x29eea  ceq
0x29eec  br.s     loc_29EEF
0x29eee  ldc.i4.0
0x29eef  brfalse.s loc_29F00
0x29ef1  ldarg.0
0x29ef2  ldstr    aCanTSyncWhileO// "Can't sync while organization provision"...
0x29ef7  ldarg.1
0x29ef8  ldnull
0x29ef9  ldc.i4.0
0x29efa  call     instance class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult Microsoft.Crm.CrmLive.Provisioning.SyncDataExecutor::BuildRetryWithExponentialBackoff(string details, class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask task, class [mscorlib]System.Exception exception, bool isSubscriptionMapping)
0x29eff  ret
0x29f00  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationSettingsProvider::get_Instance()
0x29f05  ldloc.0
0x29f06  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x29f0b  ldc.i4   0xBD
0x29f10  ldstr    aExecuteinterna// "ExecuteInternal"
0x29f15  ldstr    aDDbsShDccm2110_42// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x29f1a  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider::GetOrganizationState(valuetype [mscorlib]System.Guid, int32, string, string)
0x29f1f  ldc.i4.0
0x29f20  ceq
0x29f22  stloc.s  0xE
0x29f24  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.OrganizationLifecycleService::.ctor()
0x29f29  ldloc.0
0x29f2a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x29f2f  call     instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.OrganizationLifecycleStatus [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.OrganizationLifecycleService::GetOrganizationLifecycleStatus(valuetype [mscorlib]System.Guid)
0x29f34  ldc.i4.s 0xA
0x29f36  ceq
0x29f38  stloc.s  0xF
0x29f3a  ldloc.0
0x29f3b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x29f40  call     bool Microsoft.Crm.CrmLive.Provisioning.SyncDataExecutor::IsInitialDirectoryObjectSync(valuetype [mscorlib]System.Guid organizationId)
0x29f45  stloc.s  0x10
0x29f47  ldarg.0
0x29f48  ldloc.s  0xE
0x29f4a  ldloc.s  0xF
0x29f4c  ldloc.s  0x10
0x29f4e  newobj   instance void Microsoft.Crm.CrmLive.Provisioning.SyncDataBehavior::.ctor(bool isOrgDisabled, bool isSubscriptionMapping, bool isInitialSync)
0x29f53  stfld    class Microsoft.Crm.CrmLive.Provisioning.SyncDataBehavior Microsoft.Crm.CrmLive.Provisioning.SyncDataExecutor::_syncDataBehavior
0x29f58  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x29f5d  stloc.s  0x11
0x29f5f  ldloc.s  0xF
0x29f61  brfalse.s loc_29F6A
0x29f63  ldarg.0
0x29f64  ldloc.0
0x29f65  call     instance void Microsoft.Crm.CrmLive.Provisioning.SyncDataExecutor::PrepareForSubscriptionMapping(class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem item)
0x29f6a  ldarg.0
0x29f6b  ldfld    class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider Microsoft.Crm.CrmLive.Provisioning.SyncDataExecutor::_directoryProvider
0x29f70  callvirt instance bool [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider::get_UseCloudChanges()
0x29f75  brfalse.s loc_29F8B
0x29f77  ldarg.0
0x29f78  ldloc.0
0x29f79  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x29f7e  ldloc.0
0x29f7f  ldloc.s  0xE
0x29f81  ldloc.s  0xF
0x29f83  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncDataExecutor::SyncNewObjectsAndLinksFromCloud(valuetype [mscorlib]System.Guid organizationId, class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem queueItem, bool isOrgDisabled, bool isSubscriptionMapping)
0x29f88  stloc.1
0x29f89  br.s     loc_29FAF
0x29f8b  ldarg.0
0x29f8c  ldloc.0
0x29f8d  ldloc.s  0xF
0x29f8f  ldloc.s  0x10
0x29f91  ldloc.s  0xE
0x29f93  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncDataExecutor::SyncByContextIncremental(class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem item, bool isSubscriptionMapping, bool initialSync, bool isOrgDisabled)
0x29f98  stloc.1
0x29f99  ldarg.0
0x29f9a  ldfld    class Microsoft.Crm.CrmLive.Provisioning.SyncDataBehavior Microsoft.Crm.CrmLive.Provisioning.SyncDataExecutor::_syncDataBehavior
0x29f9f  callvirt instance bool Microsoft.Crm.CrmLive.Provisioning.SyncDataBehavior::get_SyncDirectoryLinks()
0x29fa4  brfalse.s loc_29FAF
0x29fa6  ldarg.0
0x29fa7  ldloc.0
0x29fa8  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncDataExecutor::SyncByDirectoryLinkIncremental(class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem item)
0x29fad  stloc.s  0x11
0x29faf  ldarg.0
0x29fb0  ldfld    class Microsoft.Crm.CrmLive.Provisioning.SyncDataBehavior Microsoft.Crm.CrmLive.Provisioning.SyncDataExecutor::_syncDataBehavior
0x29fb5  callvirt instance bool Microsoft.Crm.CrmLive.Provisioning.SyncDataBehavior::get_UpdateDirectoryLinkWatermarkToLatestRevision()
0x29fba  brfalse.s loc_29FE8
0x29fbc  ldarg.0
0x29fbd  ldfld    class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider Microsoft.Crm.CrmLive.Provisioning.SyncDataExecutor::_directoryProvider
0x29fc2  callvirt instance bool [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider::get_UseCloudChanges()
0x29fc7  brtrue.s loc_29FE8
0x29fc9  ldloc.0
0x29fca  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x29fcf  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncDataExecutor::RetrieveOrganizationContextId(valuetype [mscorlib]System.Guid organizationId)
0x29fd4  call     int64 Microsoft.Crm.CrmLive.Provisioning.SyncDataExecutor::GetLastLinkRevisionForOrg(valuetype [mscorlib]System.Guid contextId)
0x29fd9  stloc.s  0x12
0x29fdb  ldloc.0
0x29fdc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x29fe1  ldloc.s  0x12
0x29fe3  call     void Microsoft.Crm.CrmLive.Provisioning.SyncDataExecutor::UpdateOrganizationDirectoryLinkRevision(valuetype [mscorlib]System.Guid organizationId, int64 revision)
0x29fe8  ldloc.s  0x11
0x29fea  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x29fef  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x29ff4  brfalse.s loc_2A006
0x29ff6  ldloc.1
0x29ff7  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x29ffc  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2a001  brfalse.s loc_2A006
0x2a003  ldloc.s  0x11
0x2a005  stloc.1
0x2a006  ldloc.1
0x2a007  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2a00c  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2a011  brfalse.s loc_2A01B
0x2a013  ldstr    aWaitingForChil_0// "Waiting for child items to complete"
0x2a018  stloc.2
0x2a019  ldc.i4.1
0x2a01a  stloc.3
0x2a01b  leave.s  loc_2A046
0x2a01d  stloc.s  0x13
0x2a01f  ldloc.s  0xF
0x2a021  brfalse.s loc_2A032
0x2a023  ldarg.0
0x2a024  ldfld    class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider Microsoft.Crm.CrmLive.Provisioning.SyncDataExecutor::_directoryProvider
0x2a029  callvirt instance bool [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider::get_UseCloudChanges()
0x2a02e  brtrue.s loc_2A032
0x2a030  rethrow
0x2a032  ldarg.0
0x2a033  ldstr    aIncrementalSyn// "Incremental syncing error."
0x2a038  ldarg.1
0x2a039  ldloc.s  0x13
0x2a03b  ldloc.s  0xF
0x2a03d  call     instance class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult Microsoft.Crm.CrmLive.Provisioning.SyncDataExecutor::BuildRetryWithExponentialBackoff(string details, class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask task, class [mscorlib]System.Exception exception, bool isSubscriptionMapping)
0x2a042  stloc.s  0xC
0x2a044  leave.s  loc_2A0A1
  ... truncated ...
```
