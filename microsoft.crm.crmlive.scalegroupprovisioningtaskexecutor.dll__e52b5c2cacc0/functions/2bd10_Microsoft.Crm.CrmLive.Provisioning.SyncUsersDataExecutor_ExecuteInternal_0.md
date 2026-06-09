# Microsoft.Crm.CrmLive.Provisioning.SyncUsersDataExecutor::ExecuteInternal_0

- ea: `0x2bd10`
- end: `0x2c6b3`
- name: `Microsoft.Crm.CrmLive.Provisioning.SyncUsersDataExecutor::ExecuteInternal_0`
- size: `2467`
- prototype: ``
- caller_count: `3`
- callee_count: `39`
- tags: `broker_com_uri`

## callers

- `0x2bc50`
- `0x2bcb0`
- `0x2bd00`

## callees

- `0xfdb0`
- `0xfdd0`
- `0xfdf0`
- `0xfe10`
- `0xfe70`
- `0xfe80`
- `0xfed0`
- `0x10130`
- `0x105d0`
- `0x10980`
- `0x2b990`
- `0x2b9b0`
- `0x2b9d0`
- `0x2b9f0`
- `0x2ba10`
- `0x2ba60`
- `0x2ba80`
- `0x2ba90`
- `0x2bbf0`
- `0x2bd10`
- `0x2c6c0`
- `0x2c760`
- `0x2c790`
- `0x2c830`
- `0x2c9f0`
- `0x2cb70`
- `0x2cbc0`
- `0x2cc40`
- `0x2cc90`
- `0x2cce0`
- `0x2ce60`
- `0x2cf50`
- `0x2d180`
- `0x2d190`
- `0x2ecd0`
- `0x2edb0`
- `0x2ee40`
- `0x33820`
- `0x33890`

## string_xrefs

- `0x2c0ad`: `Added ObjectId {0} to usersToCreateAuthRecords list. Puid:{1}`
- `0x2c126`: `Completed execution for ObjectId {0}. RequiresPublication:{1}`

## pseudocode

```c

```

## disassembly

```asm
0x2bd10  newobj   instance void <>c__DisplayClass7_0::.ctor()
0x2bd15  stloc.0
0x2bd16  ldloc.0
0x2bd17  ldarg.0
0x2bd18  stfld    class Microsoft.Crm.CrmLive.Provisioning.SyncUsersDataExecutor <>c__DisplayClass7_0::<>4__this
0x2bd1d  ldloc.0
0x2bd1e  ldarg.1
0x2bd1f  stfld    class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask <>c__DisplayClass7_0::task
0x2bd24  ldloc.0
0x2bd25  ldfld    class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask <>c__DisplayClass7_0::task
0x2bd2a  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x2bd2f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x2bd34  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationType [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmOrganizationService::GetOrganizationType(valuetype [mscorlib]System.Guid)
0x2bd39  ldc.i4.s 9
0x2bd3b  bne.un.s loc_2BD48
0x2bd3d  ldstr    aSyncuserdataQu// "SyncUserData queue items are invalid on"...
0x2bd42  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x2bd47  throw
0x2bd48  nop
0x2bd49  newobj   instance void <>c__DisplayClass7_1::.ctor()
0x2bd4e  stloc.1
0x2bd4f  ldloc.1
0x2bd50  ldloc.0
0x2bd51  stfld    class <>c__DisplayClass7_0 <>c__DisplayClass7_1::CS$<>8__locals1
0x2bd56  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.CrmLive.Provisioning.SkippedUsers>::.ctor()
0x2bd5b  stloc.2
0x2bd5c  ldloc.1
0x2bd5d  ldfld    class <>c__DisplayClass7_0 <>c__DisplayClass7_1::CS$<>8__locals1
0x2bd62  ldfld    class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask <>c__DisplayClass7_0::task
0x2bd67  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x2bd6c  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_ItemData()
0x2bd71  call     T0x2B0000CD
0x2bd76  stloc.3
0x2bd77  call     T0x2B000036
0x2bd7c  ldloc.1
0x2bd7d  ldfld    class <>c__DisplayClass7_0 <>c__DisplayClass7_1::CS$<>8__locals1
0x2bd82  ldfld    class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask <>c__DisplayClass7_0::task
0x2bd87  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x2bd8c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x2bd91  ldarg.3
0x2bd92  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProviderFactory::GetProvider(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.DataProviderType)
0x2bd97  stloc.s  4
0x2bd99  ldloc.3
0x2bd9a  callvirt instance bool [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.UserProvisioningBatchInfo::get_IgnoreLicenseChecks()
0x2bd9f  brfalse.s loc_2BDC3
0x2bda1  call     T0x2B000036
0x2bda6  ldloc.1
0x2bda7  ldfld    class <>c__DisplayClass7_0 <>c__DisplayClass7_1::CS$<>8__locals1
0x2bdac  ldfld    class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask <>c__DisplayClass7_0::task
0x2bdb1  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x2bdb6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x2bdbb  ldc.i4.2
0x2bdbc  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProviderFactory::GetProvider(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.DataProviderType)
0x2bdc1  stloc.s  4
0x2bdc3  ldloc.3
0x2bdc4  call     class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.DirectoryObjectUser> Microsoft.Crm.CrmLive.Provisioning.SyncUsersDataExecutor::GenerateUserList(class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.UserProvisioningBatchInfo data)
0x2bdc9  stloc.s  5
0x2bdcb  ldc.i4.1
0x2bdcc  stloc.s  6
0x2bdce  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::.ctor()
0x2bdd3  stloc.s  7
0x2bdd5  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::.ctor()
0x2bdda  stloc.s  8
0x2bddc  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<class Microsoft.Crm.CrmLive.Provisioning.SyncUserDto, class Microsoft.Crm.CrmLive.Provisioning.SyncUserResult>>::.ctor()
0x2bde1  stloc.s  9
0x2bde3  ldarg.0
0x2bde4  ldloc.1
0x2bde5  ldfld    class <>c__DisplayClass7_0 <>c__DisplayClass7_1::CS$<>8__locals1
0x2bdea  ldftn    instance bool <>c__DisplayClass7_0::<ExecuteInternal>b__0()
0x2bdf0  newobj   instance void class [mscorlib]System.Func`1<bool>::.ctor(object, native int)
0x2bdf5  newobj   instance void class [mscorlib]System.Lazy`1<bool>::.ctor(class [mscorlib]System.Func`1<var<u1>>)
0x2bdfa  call     instance void Microsoft.Crm.CrmLive.Provisioning.SyncUsersDataExecutor::set_OrganizationDeleted(class [mscorlib]System.Lazy`1<bool> value)
0x2bdff  ldloc.1
0x2be00  ldfld    class <>c__DisplayClass7_0 <>c__DisplayClass7_1::CS$<>8__locals1
0x2be05  ldfld    class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask <>c__DisplayClass7_0::task
0x2be0a  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x2be0f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x2be14  call     class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.OrganizationLifecycleData Microsoft.Crm.CrmLive.Provisioning.SyncUsersDataExecutor::GetLifecycleData(valuetype [mscorlib]System.Guid organizationId)
0x2be19  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.OrganizationLifecycleStatus [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.OrganizationLifecycleData::get_OrganizationLifecycleState()
0x2be1e  ldc.i4.s 0xA
0x2be20  ceq
0x2be22  stloc.s  0xA
0x2be24  ldarg.0
0x2be25  ldc.i4.0
0x2be26  stfld    valuetype Microsoft.Crm.CrmLive.Provisioning.SyncUserOutcome Microsoft.Crm.CrmLive.Provisioning.SyncUsersDataExecutor::_jitSyncUserOutcome
0x2be2b  ldloca.s 0xB
0x2be2d  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0x2be33  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2be38  stloc.s  0xC
0x2be3a  ldloc.1
0x2be3b  ldfld    class <>c__DisplayClass7_0 <>c__DisplayClass7_1::CS$<>8__locals1
0x2be40  ldfld    class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask <>c__DisplayClass7_0::task
0x2be45  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x2be4a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x2be4f  call     valuetype [mscorlib]System.DateTime Microsoft.Crm.CrmLive.Provisioning.SyncUsersDataExecutor::GetOrganizationCreatedOn(valuetype [mscorlib]System.Guid organizationId)
0x2be54  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::.ctor(var<u1>)
0x2be59  stloc.s  0xB
0x2be5b  ldloc.1
0x2be5c  ldfld    class <>c__DisplayClass7_0 <>c__DisplayClass7_1::CS$<>8__locals1
0x2be61  ldfld    class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask <>c__DisplayClass7_0::task
0x2be66  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x2be6b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x2be70  call     valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.CrmLive.Provisioning.SyncUsersDataExecutor::GetOrganizationContextId(valuetype [mscorlib]System.Guid organizationId)
0x2be75  stloc.s  0xD
0x2be77  ldloca.s 0xD
0x2be79  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x2be7e  brtrue.s loc_2BE87
0x2be80  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2be85  br.s     loc_2BE8E
0x2be87  ldloca.s 0xD
0x2be89  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::GetValueOrDefault()
0x2be8e  stloc.s  0xC
0x2be90  leave.s  loc_2BEE7
0x2be92  stloc.s  0xE
0x2be94  call     class Microsoft.Crm.CrmLive.Provisioning.ProvisioningUserEventSource Microsoft.Crm.CrmLive.Provisioning.ProvisioningUserEventSource::get_Instance()
0x2be99  ldloc.1
0x2be9a  ldfld    class <>c__DisplayClass7_0 <>c__DisplayClass7_1::CS$<>8__locals1
0x2be9f  ldfld    class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask <>c__DisplayClass7_0::task
0x2bea4  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x2bea9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_QueueItemId()
0x2beae  ldloc.1
0x2beaf  ldfld    class <>c__DisplayClass7_0 <>c__DisplayClass7_1::CS$<>8__locals1
0x2beb4  ldfld    class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask <>c__DisplayClass7_0::task
0x2beb9  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x2bebe  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x2bec3  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2bec8  ldloc.s  0xE
0x2beca  callvirt instance string [mscorlib]System.Object::ToString()
0x2becf  ldarg.0
0x2bed0  ldflda   valuetype Microsoft.Crm.CrmLive.Provisioning.UserProvisioningRequestSource Microsoft.Crm.CrmLive.Provisioning.SyncUsersDataExecutor::_provisioningRequestSource
0x2bed5  constrained. Microsoft.Crm.CrmLive.Provisioning.UserProvisioningRequestSource
0x2bedb  callvirt instance string [mscorlib]System.Object::ToString()
0x2bee0  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisioningUserEventSource::UserProvisioningTelemetryError(valuetype [mscorlib]System.Guid queueItemId, valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid userObjectId, string errorDetails, string provisioningRequestSource)
0x2bee5  leave.s  loc_2BEE7
0x2bee7  ldloc.s  5
0x2bee9  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.DirectoryObjectUser>::GetEnumerator()
0x2beee  stloc.s  0xF
0x2bef0  br       loc_2C300
0x2bef5  ldloc.s  0xF
0x2bef7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.DirectoryObjectUser>::get_Current()
0x2befc  stloc.s  0x10
0x2befe  ldnull
0x2beff  stloc.s  0x11
0x2bf01  ldloc.1
0x2bf02  ldfld    class <>c__DisplayClass7_0 <>c__DisplayClass7_1::CS$<>8__locals1
0x2bf07  ldfld    class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask <>c__DisplayClass7_0::task
0x2bf0c  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x2bf11  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_QueueItemId()
0x2bf16  ldloc.1
0x2bf17  ldfld    class <>c__DisplayClass7_0 <>c__DisplayClass7_1::CS$<>8__locals1
0x2bf1c  ldfld    class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask <>c__DisplayClass7_0::task
0x2bf21  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x2bf26  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x2bf2b  ldarg.0
0x2bf2c  ldfld    valuetype Microsoft.Crm.CrmLive.Provisioning.UserProvisioningRequestSource Microsoft.Crm.CrmLive.Provisioning.SyncUsersDataExecutor::_provisioningRequestSource
0x2bf31  call     bool Microsoft.Crm.CrmLive.Provisioning.SyncUsersDataExecutor::IsOrganizationDeprovisioned(valuetype [mscorlib]System.Guid queueItemId, valuetype [mscorlib]System.Guid organizationId, valuetype Microsoft.Crm.CrmLive.Provisioning.UserProvisioningRequestSource provisioningRequestSource)
0x2bf36  brfalse.s loc_2BF4A
0x2bf38  ldc.i4.4
0x2bf39  ldstr    aOrganizationIs_0// "Organization is deprovisioned."
0x2bf3e  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus, string)
0x2bf43  stloc.s  0x13
0x2bf45  leave    loc_2C6B0
0x2bf4a  ldloc.1
0x2bf4b  ldfld    class <>c__DisplayClass7_0 <>c__DisplayClass7_1::CS$<>8__locals1
0x2bf50  ldfld    class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask <>c__DisplayClass7_0::task
0x2bf55  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x2bf5a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_QueueItemId()
0x2bf5f  ldloc.s  4
0x2bf61  ldloc.1
0x2bf62  ldfld    class <>c__DisplayClass7_0 <>c__DisplayClass7_1::CS$<>8__locals1
0x2bf67  ldfld    class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask <>c__DisplayClass7_0::task
0x2bf6c  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x2bf71  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x2bf76  ldloc.s  0x10
0x2bf78  ldloc.s  0xA
0x2bf7a  ldarg.0
0x2bf7b  ldfld    valuetype Microsoft.Crm.CrmLive.Provisioning.UserProvisioningRequestSource Microsoft.Crm.CrmLive.Provisioning.SyncUsersDataExecutor::_provisioningRequestSource
0x2bf80  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.CrmLive.Provisioning.SyncUsersDataExecutor::RetrieveObject(valuetype [mscorlib]System.Guid queueItemId, class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider directoryProvider, valuetype [mscorlib]System.Guid organizationId, class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.DirectoryObjectUser user, bool isSubscriptionMapping, valuetype Microsoft.Crm.CrmLive.Provisioning.UserProvisioningRequestSource provisioningRequestSource)
0x2bf85  stloc.s  0x12
0x2bf87  ldloc.1
0x2bf88  ldfld    class <>c__DisplayClass7_0 <>c__DisplayClass7_1::CS$<>8__locals1
0x2bf8d  ldfld    class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask <>c__DisplayClass7_0::task
0x2bf92  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x2bf97  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x2bf9c  ldloc.s  0x12
0x2bf9e  ldloc.s  4
0x2bfa0  ldloc.3
0x2bfa1  callvirt instance bool [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.UserProvisioningBatchInfo::get_IgnoreLicenseChecks()
0x2bfa6  call     class Microsoft.Crm.CrmLive.Provisioning.SyncUserDto Microsoft.Crm.CrmLive.Provisioning.SyncUserAction::GetSyncUserDetails(valuetype [mscorlib]System.Guid organizationId, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag record, class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider directoryProvider, bool ignoreLicenseCheckes)
0x2bfab  stloc.s  0x11
0x2bfad  ldloc.1
0x2bfae  ldfld    class <>c__DisplayClass7_0 <>c__DisplayClass7_1::CS$<>8__locals1
0x2bfb3  ldfld    class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask <>c__DisplayClass7_0::task
0x2bfb8  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x2bfbd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x2bfc2  ldloc.s  0x10
0x2bfc4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.DirectoryObjectUser::get_ObjectId()
0x2bfc9  ldloc.s  0x12
0x2bfcb  newobj   instance void Microsoft.Crm.CrmLive.Provisioning.UserManagementFactoryOverrideContext::.ctor(valuetype [mscorlib]System.Guid orgId, valuetype [mscorlib]System.Guid objectId, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag objectData)
0x2bfd0  stloc.s  0x14
0x2bfd2  ldloc.1
0x2bfd3  ldfld    class <>c__DisplayClass7_0 <>c__DisplayClass7_1::CS$<>8__locals1
0x2bfd8  ldfld    class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask <>c__DisplayClass7_0::task
0x2bfdd  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x2bfe2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x2bfe7  call     bool [Microsoft.Crm.Online.DirectoryData]Microsoft.Crm.Online.DirectoryData.LicenseUtilities::IsTrial(valuetype [mscorlib]System.Guid)
0x2bfec  stloc.s  0x15
0x2bfee  newobj   instance void Microsoft.Crm.CrmLive.Provisioning.SyncUserAction::.ctor()
0x2bff3  ldloc.1
0x2bff4  ldfld    class <>c__DisplayClass7_0 <>c__DisplayClass7_1::CS$<>8__locals1
0x2bff9  ldfld    class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask <>c__DisplayClass7_0::task
0x2bffe  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x2c003  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x2c008  ldloc.s  0x12
0x2c00a  ldloc.s  0x10
0x2c00c  ldloc.s  4
0x2c00e  ldloc.s  0x15
0x2c010  ldc.i4.0
0x2c011  callvirt instance class Microsoft.Crm.CrmLive.Provisioning.SyncUserResult Microsoft.Crm.CrmLive.Provisioning.SyncUserAction::SyncUser(valuetype [mscorlib]System.Guid organizationId, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag record, class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.DirectoryObjectUser user, class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider provider, bool ignoreLicenseChecks, [opt] bool isTrial)
0x2c016  stloc.s  0x16
0x2c018  ldloc.s  0x16
0x2c01a  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.SyncUserResult::get_SkippedUserSyncDetail()
0x2c01f  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x2c024  brtrue.s loc_2C04B
0x2c026  ldloc.2
0x2c027  newobj   instance void Microsoft.Crm.CrmLive.Provisioning.SkippedUsers::.ctor()
0x2c02c  dup
0x2c02d  ldloc.s  0x10
0x2c02f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.DirectoryObjectUser::get_ObjectId()
0x2c034  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.SkippedUsers::set_UserOjectId(valuetype [mscorlib]System.Guid value)
0x2c039  dup
0x2c03a  ldloc.s  0x16
0x2c03c  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.SyncUserResult::get_SkippedUserSyncDetail()
0x2c041  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.SkippedUsers::set_SkipUserSyncDetail(string value)
0x2c046  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.CrmLive.Provisioning.SkippedUsers>::Add(var<u1>)
0x2c04b  ldloc.s  0x16
0x2c04d  callvirt instance class Microsoft.Crm.CrmLive.Provisioning.SyncUserAuthInfo Microsoft.Crm.CrmLive.Provisioning.SyncUserResult::get_SyncUserAuthInformation()
0x2c052  brfalse  loc_2C102
0x2c057  ldarg.3
0x2c058  ldc.i4.2
0x2c059  bne.un.s loc_2C07C
0x2c05b  ldloc.s  0x10
0x2c05d  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.DirectoryObjectUser::get_Puid()
0x2c062  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2c067  brtrue.s loc_2C07C
0x2c069  ldloc.s  0x16
0x2c06b  callvirt instance class Microsoft.Crm.CrmLive.Provisioning.SyncUserAuthInfo Microsoft.Crm.CrmLive.Provisioning.SyncUserResult::get_SyncUserAuthInformation()
0x2c070  ldloc.s  0x10
0x2c072  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.DirectoryObjectUser::get_Puid()
0x2c077  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.SyncUserAuthInfo::set_UserPuid(string value)
0x2c07c  ldloc.s  0x16
0x2c07e  callvirt instance class Microsoft.Crm.CrmLive.Provisioning.SyncUserAuthInfo Microsoft.Crm.CrmLive.Provisioning.SyncUserResult::get_SyncUserAuthInformation()
0x2c083  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.SyncUserAuthInfo::get_UserPuid()
0x2c088  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2c08d  brtrue   loc_2C1BD
0x2c092  ldloc.s  9
0x2c094  ldloc.s  0x11
0x2c096  ldloc.s  0x16
0x2c098  call     T0x2B0000CE
0x2c09d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<class Microsoft.Crm.CrmLive.Provisioning.SyncUserDto, class Microsoft.Crm.CrmLive.Provisioning.SyncUserResult>>::Add(var<u1>)
0x2c0a2  ldarg.0
0x2c0a3  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.CrmLive.Provisioning.SyncUsersDataExecutor::_taskLog
0x2c0a8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2c0ad  ldstr    aAddedObjectid0// "Added ObjectId {0} to usersToCreateAuth"...
0x2c0b2  ldc.i4.2
0x2c0b3  newarr   [mscorlib]System.Object
0x2c0b8  dup
0x2c0b9  ldc.i4.0
0x2c0ba  ldloc.s  0x10
0x2c0bc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.DirectoryObjectUser::get_ObjectId()
0x2c0c1  box      [mscorlib]System.Guid
0x2c0c6  stelem.ref
0x2c0c7  dup
0x2c0c8  ldc.i4.1
0x2c0c9  ldloc.s  0x16
0x2c0cb  callvirt instance class Microsoft.Crm.CrmLive.Provisioning.SyncUserAuthInfo Microsoft.Crm.CrmLive.Provisioning.SyncUserResult::get_SyncUserAuthInformation()
0x2c0d0  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.SyncUserAuthInfo::get_UserPuid()
0x2c0d5  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x2c0da  brfalse.s loc_2C0E5
0x2c0dc  ldloc.s  0x10
0x2c0de  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.DirectoryObjectUser::get_Puid()
0x2c0e3  br.s     loc_2C0F1
0x2c0e5  ldloc.s  0x16
0x2c0e7  callvirt instance class Microsoft.Crm.CrmLive.Provisioning.SyncUserAuthInfo Microsoft.Crm.CrmLive.Provisioning.SyncUserResult::get_SyncUserAuthInformation()
0x2c0ec  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.SyncUserAuthInfo::get_UserPuid()
0x2c0f1  stelem.ref
0x2c0f2  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2c0f7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x2c0fc  pop
0x2c0fd  br       loc_2C1BD
0x2c102  ldloc.3
0x2c103  ldloc.s  0x10
0x2c105  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.DirectoryObjectUser::get_ObjectId()
0x2c10a  ldloc.s  0x16
0x2c10c  callvirt instance bool Microsoft.Crm.CrmLive.Provisioning.SyncUserResult::get_RequiresPublication()
0x2c111  newobj   instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.DirectoryObjectUser::.ctor(valuetype [mscorlib]System.Guid, bool)
0x2c116  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.UserProvisioningBatchInfo::AddToCompleted(class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.DirectoryObjectUser)
0x2c11b  ldarg.0
0x2c11c  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.CrmLive.Provisioning.SyncUsersDataExecutor::_taskLog
0x2c121  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
  ... truncated ...
```
