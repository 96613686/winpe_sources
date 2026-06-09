# Microsoft.Crm.CrmLive.Provisioning.DropXdbDatabaseExecutor::Execute

- ea: `0x13850`
- end: `0x13bd8`
- name: `Microsoft.Crm.CrmLive.Provisioning.DropXdbDatabaseExecutor::Execute`
- size: `904`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x13790`
- `0x137d0`
- `0x137e0`
- `0x13800`
- `0x13820`
- `0x13830`
- `0x13850`
- `0x13be0`
- `0x13ca0`

## string_xrefs

- `0x1385b`: `SpartanTaskCancellationTimeInSeconds`
- `0x13966`: `No databases to drop for the the organization {0}, Operation completed`
- `0x13a07`: `DeleteDatabase_`
- `0x13b37`: ` Exception encountered while trying to delete database, retrying again. Database {0}, operationID {1} `
- `0x13b5a`: `Task failed with Exception`
- `0x13b8f`: ` Organization database has been deleted. DatabaseName : {0}, OperationId {1}`

## pseudocode

```c

```

## disassembly

```asm
0x13850  call     T0x2B00001A
0x13855  stloc.0
0x13856  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x1385b  ldstr    aSpartantaskcan// "SpartanTaskCancellationTimeInSeconds"
0x13860  ldc.i4.0
0x13861  callvirt T0x2B000069
0x13866  stloc.s  7
0x13868  ldloca.s 7
0x1386a  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x1386f  brtrue.s loc_1387D
0x13871  ldloca.s 8
0x13873  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x13879  ldloc.s  8
0x1387b  br.s     loc_1388F
0x1387d  ldloca.s 7
0x1387f  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::GetValueOrDefault()
0x13884  ldc.i4   0x3E8
0x13889  mul
0x1388a  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x1388f  stloc.s  6
0x13891  ldloca.s 6
0x13893  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x13898  brtrue.s loc_138A1
0x1389a  ldc.i4   0x7530
0x1389f  br.s     loc_138A8
0x138a1  ldloca.s 6
0x138a3  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::GetValueOrDefault()
0x138a8  newobj   instance void [mscorlib]System.Threading.CancellationTokenSource::.ctor(int32)
0x138ad  call     instance valuetype [mscorlib]System.Threading.CancellationToken [mscorlib]System.Threading.CancellationTokenSource::get_Token()
0x138b2  stloc.1
0x138b3  call     class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueManager [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueManager::NewManager()
0x138b8  stloc.2
0x138b9  ldc.i4.1
0x138ba  stloc.3
0x138bb  ldarg.1
0x138bc  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x138c1  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_ItemData()
0x138c6  brfalse.s loc_138DE
0x138c8  ldarg.1
0x138c9  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x138ce  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_ItemData()
0x138d3  call     T0x2B00006A
0x138d8  callvirt instance bool Microsoft.Crm.CrmLive.Provisioning.DropXdbDatabaseInfo::get_DropSoftDeletedDatabasesOnly()
0x138dd  stloc.3
0x138de  ldarg.1
0x138df  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x138e4  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_ItemRuntimeData()
0x138e9  brtrue.s loc_13928
0x138eb  newobj   instance void Microsoft.Crm.CrmLive.Provisioning.DropXdbDatabaseRuntimeData::.ctor()
0x138f0  stloc.s  4
0x138f2  ldloc.s  4
0x138f4  ldsfld   string [mscorlib]System.String::Empty
0x138f9  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.DropXdbDatabaseRuntimeData::set_OperationId(string value)
0x138fe  ldloc.s  4
0x13900  ldc.i4.0
0x13901  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.DropXdbDatabaseRuntimeData::set_TaskCancelledRetryCount(int32 value)
0x13906  ldloc.s  4
0x13908  ldc.i4.0
0x13909  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.DropXdbDatabaseRuntimeData::set_SpartanRetryCount(int32 value)
0x1390e  ldloc.2
0x1390f  ldarg.1
0x13910  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x13915  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_QueueItemId()
0x1391a  ldloc.s  4
0x1391c  call     T0x2B00006B
0x13921  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueManager::UpdateQueueItemRuntimeData(valuetype [mscorlib]System.Guid, string)
0x13926  br.s     loc_1393A
0x13928  ldarg.1
0x13929  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x1392e  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_ItemRuntimeData()
0x13933  call     T0x2B00006C
0x13938  stloc.s  4
0x1393a  ldloc.0
0x1393b  ldarg.1
0x1393c  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x13941  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x13946  ldc.i4.0
0x13947  ldc.i4.0
0x13948  ldloc.3
0x13949  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x1394e  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationDatabaseLocation> [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.IOrganizationDatabaseLocationService::RetrieveOrganizationCurrentDatabaseDetails(valuetype [mscorlib]System.Guid, bool, bool, valuetype [mscorlib]System.Nullable`1<bool>)
0x13953  stloc.s  5
0x13955  ldloc.s  5
0x13957  brtrue.s loc_13997
0x13959  ldarg.1
0x1395a  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x1395f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x13964  ldc.i4.s 0x44
0x13966  ldstr    aNoDatabasesToD// "No databases to drop for the the organi"...
0x1396b  ldarg.1
0x1396c  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x13971  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x13976  box      [mscorlib]System.Guid
0x1397b  call     string [mscorlib]System.String::Format(string, object)
0x13980  ldc.i4.0
0x13981  newarr   [mscorlib]System.Object
0x13986  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1398b  ldc.i4.4
0x1398c  ldstr    aNoDatabasesToD_0// "No databases to drop"
0x13991  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus, string)
0x13996  ret
0x13997  ldloc.s  5
0x13999  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationDatabaseLocation>::GetEnumerator()
0x1399e  stloc.s  9
0x139a0  br       loc_13BB2
0x139a5  ldloca.s 9
0x139a7  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationDatabaseLocation>::get_Current()
0x139ac  stloc.s  0xA
0x139ae  ldloc.s  0xA
0x139b0  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationDatabaseLocation::get_DatabaseName()
0x139b5  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x139ba  brtrue.s loc_139D8
0x139bc  ldloc.s  0xA
0x139be  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationDatabaseLocation::get_LogicalServer()
0x139c3  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x139c8  brtrue.s loc_139D8
0x139ca  ldloc.s  0xA
0x139cc  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationDatabaseLocation::get_Region()
0x139d1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x139d6  brfalse.s loc_13A05
0x139d8  ldarg.1
0x139d9  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x139de  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x139e3  ldc.i4.s 0x44
0x139e5  ldstr    aSkipDropdataba// "skip DropDatabase as the database / log"...
0x139ea  ldc.i4.0
0x139eb  newarr   [mscorlib]System.Object
0x139f0  call     string [mscorlib]System.String::Format(string, object[])
0x139f5  ldc.i4.0
0x139f6  newarr   [mscorlib]System.Object
0x139fb  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x13a00  br       loc_13BB2
0x13a05  ldloc.s  4
0x13a07  ldstr    aDeletedatabase// "DeleteDatabase_"
0x13a0c  ldloc.s  0xA
0x13a0e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationDatabaseLocation::get_Id()
0x13a13  box      [mscorlib]System.Guid
0x13a18  call     string [mscorlib]System.String::Concat(object, object)
0x13a1d  dup
0x13a1e  stloc.s  0xD
0x13a20  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.DropXdbDatabaseRuntimeData::set_OperationId(string value)
0x13a25  ldloc.s  0xD
0x13a27  stloc.s  0xB
0x13a29  ldloc.s  4
0x13a2b  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.DropXdbDatabaseRuntimeData::get_OperationId()
0x13a30  ldloc.s  0xB
0x13a32  ldc.i4.5
0x13a33  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x13a38  brtrue.s loc_13A6B
0x13a3a  ldloc.s  4
0x13a3c  ldloc.s  0xB
0x13a3e  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.DropXdbDatabaseRuntimeData::set_OperationId(string value)
0x13a43  ldloc.s  4
0x13a45  ldc.i4.0
0x13a46  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.DropXdbDatabaseRuntimeData::set_TaskCancelledRetryCount(int32 value)
0x13a4b  ldloc.s  4
0x13a4d  ldc.i4.0
0x13a4e  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.DropXdbDatabaseRuntimeData::set_SpartanRetryCount(int32 value)
0x13a53  ldloc.2
0x13a54  ldarg.1
0x13a55  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x13a5a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_QueueItemId()
0x13a5f  ldloc.s  4
0x13a61  call     T0x2B00006B
0x13a66  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueManager::UpdateQueueItemRuntimeData(valuetype [mscorlib]System.Guid, string)
0x13a6b  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanPrimaryDatabaseIdentifier::.ctor()
0x13a70  dup
0x13a71  ldloc.s  0xA
0x13a73  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationDatabaseLocation::get_Region()
0x13a78  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier::set_AzureRegion(string)
0x13a7d  dup
0x13a7e  ldloc.s  0xA
0x13a80  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationDatabaseLocation::get_DatabaseName()
0x13a85  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier::set_DatabaseName(string)
0x13a8a  dup
0x13a8b  ldloc.s  0xA
0x13a8d  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationDatabaseLocation::get_LogicalServer()
0x13a92  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier::set_LogicalServer(string)
0x13a97  dup
0x13a98  ldsfld   string [mscorlib]System.String::Empty
0x13a9d  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier::set_ConnectionString(string)
0x13aa2  stloc.s  0xC
0x13aa4  call     T0x2B000019
0x13aa9  ldloc.s  4
0x13aab  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.DropXdbDatabaseRuntimeData::get_OperationId()
0x13ab0  ldloc.s  0xC
0x13ab2  ldarg.1
0x13ab3  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x13ab8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x13abd  ldloc.1
0x13abe  callvirt instance class [mscorlib]System.Threading.Tasks.Task [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.ISpartanService::DropDatabaseAsync(string, class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Threading.CancellationToken)
0x13ac3  ldc.i4.0
0x13ac4  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable [mscorlib]System.Threading.Tasks.Task::ConfigureAwait(bool)
0x13ac9  stloc.s  0xE
0x13acb  ldloca.s 0xE
0x13acd  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable::GetAwaiter()
0x13ad2  stloc.s  0xF
0x13ad4  ldloca.s 0xF
0x13ad6  call     instance void [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::GetResult()
0x13adb  leave    loc_13B6E
0x13ae0  pop
0x13ae1  ldarg.1
0x13ae2  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x13ae7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x13aec  ldc.i4.s 0x44
0x13aee  ldstr    aDatabaseDeleti// "database deletion is still in progress "...
0x13af3  ldloc.s  0xC
0x13af5  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier::get_DatabaseName()
0x13afa  ldloc.s  4
0x13afc  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.DropXdbDatabaseRuntimeData::get_OperationId()
0x13b01  call     string [mscorlib]System.String::Format(string, object, object)
0x13b06  ldc.i4.0
0x13b07  newarr   [mscorlib]System.Object
0x13b0c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x13b11  ldstr    aDropDatabaseIs// "Drop database is still in progress, wil"...
0x13b16  ldarg.1
0x13b17  ldloc.2
0x13b18  ldloc.s  4
0x13b1a  call     class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult Microsoft.Crm.CrmLive.Provisioning.DropXdbDatabaseExecutor::TaskCancelledBuildRetry(string message, class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask task, class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueManager queueManager, class Microsoft.Crm.CrmLive.Provisioning.DropXdbDatabaseRuntimeData runtimeData)
0x13b1f  stloc.s  0x10
0x13b21  leave    loc_13BD5
0x13b26  stloc.s  0x11
0x13b28  ldloc.s  0x11
0x13b2a  ldarg.1
0x13b2b  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x13b30  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x13b35  ldc.i4.s 0x44
0x13b37  ldstr    aExceptionEncou// " Exception encountered while trying to "...
0x13b3c  ldloc.s  0xC
0x13b3e  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier::get_DatabaseName()
0x13b43  ldloc.s  4
0x13b45  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.DropXdbDatabaseRuntimeData::get_OperationId()
0x13b4a  call     string [mscorlib]System.String::Format(string, object, object)
0x13b4f  ldc.i4.0
0x13b50  newarr   [mscorlib]System.Object
0x13b55  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x13b5a  ldstr    aTaskFailedWith// "Task failed with Exception"
0x13b5f  ldloc.s  0x11
0x13b61  ldarg.1
0x13b62  ldloc.2
0x13b63  ldloc.s  4
0x13b65  call     class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult Microsoft.Crm.CrmLive.Provisioning.DropXdbDatabaseExecutor::TaskFailedBuildRetry(string message, class [mscorlib]System.Exception ex, class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask task, class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueManager queueManager, class Microsoft.Crm.CrmLive.Provisioning.DropXdbDatabaseRuntimeData runtimeData)
0x13b6a  stloc.s  0x10
0x13b6c  leave.s  loc_13BD5
0x13b6e  ldloc.0
0x13b6f  ldloc.s  0xA
0x13b71  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationDatabaseLocation::get_OrganizationId()
0x13b76  ldloc.s  0xA
0x13b78  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationDatabaseLocation::get_Id()
0x13b7d  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.IOrganizationDatabaseLocationService::DeleteOrgDatabaseById(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x13b82  ldarg.1
0x13b83  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x13b88  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x13b8d  ldc.i4.s 0x44
0x13b8f  ldstr    aOrganizationDa// " Organization database has been deleted"...
0x13b94  ldloc.s  0xA
0x13b96  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationDatabaseLocation::get_DatabaseName()
0x13b9b  ldloc.s  4
0x13b9d  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.DropXdbDatabaseRuntimeData::get_OperationId()
0x13ba2  call     string [mscorlib]System.String::Format(string, object, object)
0x13ba7  ldc.i4.0
0x13ba8  newarr   [mscorlib]System.Object
0x13bad  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x13bb2  ldloca.s 9
0x13bb4  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationDatabaseLocation>::MoveNext()
0x13bb9  brtrue   loc_139A5
0x13bbe  leave.s  loc_13BCE
0x13bc0  ldloca.s 9
0x13bc2  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationDatabaseLocation>
0x13bc8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x13bcd  endfinally
0x13bce  ldc.i4.4
0x13bcf  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus)
0x13bd4  ret
0x13bd5  ldloc.s  0x10
0x13bd7  ret
```
