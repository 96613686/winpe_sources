# Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreDatabaseExecutor::ExecuteTaskForXdbOrg

- ea: `0x16170`
- end: `0x165e2`
- name: `Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreDatabaseExecutor::ExecuteTaskForXdbOrg`
- size: `1138`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x15fa0`

## callees

- `0x15eb0`
- `0x15ec0`
- `0x15ed0`
- `0x15ee0`
- `0x15ef0`
- `0x15f00`
- `0x15f10`
- `0x15f20`
- `0x15f30`
- `0x15f40`
- `0x15f50`
- `0x160f0`
- `0x16170`
- `0x165f0`
- `0x16650`
- `0x183c0`
- `0x18400`
- `0x18410`
- `0x18420`
- `0x18430`
- `0x18440`

## string_xrefs

- `0x16175`: `SpartanTaskCancellationTimeInSeconds`
- `0x163eb`: `Task failed with Exception`
- `0x161cd`: `TaskCanceledExceptionMaxRetryCount`
- `0x1621e`: `SpartanTaskRetryDurationInSeconds`
- `0x16393`: `Task is in progress. Will retry to check the status`
- `0x16485`: `continuous copy created for the restored database. Database Name : {0}, Logical Server {1} , Azure Region : {2}`
- `0x164bf`: `Database continuous copy creation is in progress, will check the status later. operationId {0}`
- `0x164ef`: ` Database continuous copy creation failed. operationID {0} `
- `0x16598`: `Restore task for organization {0} failed`
- `0x165bd`: `Restore organization database task failed`

## pseudocode

```c

```

## disassembly

```asm
0x16170  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x16175  ldstr    aSpartantaskcan// "SpartanTaskCancellationTimeInSeconds"
0x1617a  ldc.i4.0
0x1617b  callvirt T0x2B000069
0x16180  stloc.s  0xA
0x16182  ldloca.s 0xA
0x16184  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x16189  brtrue.s loc_16197
0x1618b  ldloca.s 0xB
0x1618d  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x16193  ldloc.s  0xB
0x16195  br.s     loc_161A9
0x16197  ldloca.s 0xA
0x16199  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::GetValueOrDefault()
0x1619e  ldc.i4   0x3E8
0x161a3  mul
0x161a4  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x161a9  stloc.s  9
0x161ab  ldloca.s 9
0x161ad  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x161b2  brtrue.s loc_161BB
0x161b4  ldc.i4   0x7530
0x161b9  br.s     loc_161C2
0x161bb  ldloca.s 9
0x161bd  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::GetValueOrDefault()
0x161c2  newobj   instance void [mscorlib]System.Threading.CancellationTokenSource::.ctor(int32)
0x161c7  stloc.0
0x161c8  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x161cd  ldstr    aTaskcanceledex// "TaskCanceledExceptionMaxRetryCount"
0x161d2  ldc.i4.0
0x161d3  callvirt T0x2B000069
0x161d8  stloc.s  9
0x161da  ldloca.s 9
0x161dc  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x161e1  brtrue.s loc_161EA
0x161e3  ldc.i4   0x12C
0x161e8  br.s     loc_161F1
0x161ea  ldloca.s 9
0x161ec  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::GetValueOrDefault()
0x161f1  stloc.1
0x161f2  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x161f7  ldstr    aSpartanexcepti// "SpartanExceptionMaxRetryCount"
0x161fc  ldc.i4.0
0x161fd  callvirt T0x2B000069
0x16202  stloc.s  9
0x16204  ldloca.s 9
0x16206  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x1620b  brtrue.s loc_16211
0x1620d  ldc.i4.s 0x32
0x1620f  br.s     loc_16218
0x16211  ldloca.s 9
0x16213  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::GetValueOrDefault()
0x16218  stloc.2
0x16219  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x1621e  ldstr    aSpartantaskret// "SpartanTaskRetryDurationInSeconds"
0x16223  ldc.i4.0
0x16224  callvirt T0x2B000069
0x16229  stloc.s  9
0x1622b  ldloca.s 9
0x1622d  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x16232  brtrue.s loc_1623B
0x16234  ldc.i4   0x12C
0x16239  br.s     loc_16242
0x1623b  ldloca.s 9
0x1623d  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::GetValueOrDefault()
0x16242  stloc.3
0x16243  call     class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueManager [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueManager::NewManager()
0x16248  stloc.s  4
0x1624a  call     T0x2B000081
0x1624f  stloc.s  5
0x16251  ldnull
0x16252  stloc.s  6
0x16254  ldnull
0x16255  stloc.s  7
0x16257  ldnull
0x16258  stloc.s  8
0x1625a  ldarg.1
0x1625b  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x16260  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_ItemRuntimeData()
0x16265  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1626a  brfalse.s loc_162B9
0x1626c  newobj   instance void Microsoft.Crm.CrmLive.Provisioning.XdbRestoreRuntimeData::.ctor()
0x16271  dup
0x16272  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x16277  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.XdbRestoreRuntimeData::set_RestoreOperationId(valuetype [mscorlib]System.Guid value)
0x1627c  dup
0x1627d  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x16282  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.XdbRestoreRuntimeData::set_ContinuousCopyOperationId(valuetype [mscorlib]System.Guid value)
0x16287  dup
0x16288  ldc.i4.0
0x16289  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.XdbRestoreRuntimeData::set_SpartanRetryCount(int32 value)
0x1628e  dup
0x1628f  ldc.i4.0
0x16290  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.XdbRestoreRuntimeData::set_TaskCancelledRetryCount(int32 value)
0x16295  dup
0x16296  ldc.i4.0
0x16297  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.XdbRestoreRuntimeData::set_DatabaseRestoreComplete(bool value)
0x1629c  stloc.s  8
0x1629e  ldloc.s  4
0x162a0  ldarg.1
0x162a1  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x162a6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_QueueItemId()
0x162ab  ldloc.s  8
0x162ad  call     T0x2B000082
0x162b2  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueManager::UpdateQueueItemRuntimeData(valuetype [mscorlib]System.Guid, string)
0x162b7  br.s     loc_162CB
0x162b9  ldarg.1
0x162ba  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x162bf  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_ItemRuntimeData()
0x162c4  call     T0x2B000083
0x162c9  stloc.s  8
0x162cb  ldloc.s  8
0x162cd  callvirt instance bool Microsoft.Crm.CrmLive.Provisioning.XdbRestoreRuntimeData::get_DatabaseRestoreComplete()
0x162d2  brtrue   loc_16571
0x162d7  ldloc.s  5
0x162d9  ldarg.2
0x162da  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreInfo::get_OrganizationId()
0x162df  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.IOrganization::CreateCustomerManagedKeyForXdb(valuetype [mscorlib]System.Guid organizationId)
0x162e4  ldloc.s  5
0x162e6  ldloc.s  8
0x162e8  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.XdbRestoreRuntimeData::get_RestoreOperationId()
0x162ed  stloc.s  0xC
0x162ef  ldloca.s 0xC
0x162f1  constrained. [mscorlib]System.Guid
0x162f7  callvirt instance string [mscorlib]System.Object::ToString()
0x162fc  ldarg.2
0x162fd  ldloc.0
0x162fe  callvirt instance valuetype [mscorlib]System.Threading.CancellationToken [mscorlib]System.Threading.CancellationTokenSource::get_Token()
0x16303  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanPrimaryDatabaseIdentifier> Microsoft.Crm.CrmLive.Provisioning.IOrganization::RestoreXdbDatabase(string operationId, class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreInfo restoreInfo, valuetype [mscorlib]System.Threading.CancellationToken token)
0x16308  ldc.i4.0
0x16309  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanPrimaryDatabaseIdentifier>::ConfigureAwait(!!T0)
0x1630e  stloc.s  0xD
0x16310  ldloca.s 0xD
0x16312  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanPrimaryDatabaseIdentifier>::GetAwaiter()
0x16317  stloc.s  0xE
0x16319  ldloca.s 0xE
0x1631b  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanPrimaryDatabaseIdentifier>::GetResult()
0x16320  stloc.s  6
0x16322  ldarg.1
0x16323  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x16328  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x1632d  ldc.i4.s 0x42
0x1632f  ldstr    aOrganizationDa_0// "Organization database restored. Databas"...
0x16334  ldloc.s  6
0x16336  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier::get_DatabaseName()
0x1633b  ldloc.s  6
0x1633d  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier::get_LogicalServer()
0x16342  ldloc.s  6
0x16344  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier::get_AzureRegion()
0x16349  call     string [mscorlib]System.String::Format(string, object, object, object)
0x1634e  ldc.i4.0
0x1634f  newarr   [mscorlib]System.Object
0x16354  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x16359  leave    loc_1640D
0x1635e  pop
0x1635f  ldarg.1
0x16360  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x16365  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x1636a  ldc.i4.s 0x42
0x1636c  ldstr    aRestoreIsStill// "restore is still in progress, will chec"...
0x16371  ldarg.2
0x16372  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreInfo::get_DatabaseName()
0x16377  ldloc.s  8
0x16379  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.XdbRestoreRuntimeData::get_RestoreOperationId()
0x1637e  box      [mscorlib]System.Guid
0x16383  call     string [mscorlib]System.String::Format(string, object, object)
0x16388  ldc.i4.0
0x16389  newarr   [mscorlib]System.Object
0x1638e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x16393  ldstr    aTaskIsInProgre// "Task is in progress. Will retry to chec"...
0x16398  ldarg.1
0x16399  ldloc.s  4
0x1639b  ldloc.s  8
0x1639d  ldloc.1
0x1639e  ldloc.s  8
0x163a0  callvirt instance int32 Microsoft.Crm.CrmLive.Provisioning.XdbRestoreRuntimeData::get_SpartanRetryCount()
0x163a5  add
0x163a6  ldloc.3
0x163a7  call     class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreDatabaseExecutor::TaskCancelledBuildRetry(string message, class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask task, class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueManager queueManager, class Microsoft.Crm.CrmLive.Provisioning.XdbRestoreRuntimeData runtimeData, int32 maxRetryCount, int32 taskRetryDuration)
0x163ac  stloc.s  0xF
0x163ae  leave    loc_165DF
0x163b3  stloc.s  0x10
0x163b5  ldloc.s  0x10
0x163b7  ldarg.1
0x163b8  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x163bd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x163c2  ldc.i4.s 0x42
0x163c4  ldstr    aRestoreDatabas// " restore database failed, retrying agai"...
0x163c9  ldarg.2
0x163ca  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreInfo::get_DatabaseName()
0x163cf  ldloc.s  8
0x163d1  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.XdbRestoreRuntimeData::get_RestoreOperationId()
0x163d6  box      [mscorlib]System.Guid
0x163db  call     string [mscorlib]System.String::Format(string, object, object)
0x163e0  ldc.i4.0
0x163e1  newarr   [mscorlib]System.Object
0x163e6  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x163eb  ldstr    aTaskFailedWith// "Task failed with Exception"
0x163f0  ldloc.s  0x10
0x163f2  ldarg.1
0x163f3  ldloc.s  4
0x163f5  ldloc.s  8
0x163f7  ldloc.2
0x163f8  ldloc.s  8
0x163fa  callvirt instance int32 Microsoft.Crm.CrmLive.Provisioning.XdbRestoreRuntimeData::get_TaskCancelledRetryCount()
0x163ff  add
0x16400  ldloc.3
0x16401  call     class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreDatabaseExecutor::TaskFailedBuildRetry(string message, class [mscorlib]System.Exception ex, class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask task, class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueManager queueManager, class Microsoft.Crm.CrmLive.Provisioning.XdbRestoreRuntimeData runtimeData, int32 maxRetryCount, int32 taskRetryDuration)
0x16406  stloc.s  0xF
0x16408  leave    loc_165DF
0x1640d  nop
0x1640e  ldc.i4   0x1388
0x16413  newobj   instance void [mscorlib]System.Threading.CancellationTokenSource::.ctor(int32)
0x16418  stloc.s  0x11
0x1641a  ldloc.s  5
0x1641c  ldloc.s  8
0x1641e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.XdbRestoreRuntimeData::get_ContinuousCopyOperationId()
0x16423  stloc.s  0xC
0x16425  ldloca.s 0xC
0x16427  constrained. [mscorlib]System.Guid
0x1642d  callvirt instance string [mscorlib]System.Object::ToString()
0x16432  ldloc.s  6
0x16434  ldarg.2
0x16435  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreInfo::get_OrganizationId()
0x1643a  ldarg.2
0x1643b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreInfo::get_NewScaleGroupId()
0x16440  ldloc.s  0x11
0x16442  callvirt instance valuetype [mscorlib]System.Threading.CancellationToken [mscorlib]System.Threading.CancellationTokenSource::get_Token()
0x16447  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanSecondaryDatabaseIdentifier> Microsoft.Crm.CrmLive.Provisioning.IOrganization::CreateContinuousCopy(string operationId, class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanPrimaryDatabaseIdentifier primaryDatabase, valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid scalegroupId, valuetype [mscorlib]System.Threading.CancellationToken token)
0x1644c  ldc.i4.0
0x1644d  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanSecondaryDatabaseIdentifier>::ConfigureAwait(!!T0)
0x16452  stloc.s  0x12
0x16454  ldloca.s 0x12
0x16456  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanSecondaryDatabaseIdentifier>::GetAwaiter()
0x1645b  stloc.s  0x13
0x1645d  ldloca.s 0x13
0x1645f  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanSecondaryDatabaseIdentifier>::GetResult()
0x16464  stloc.s  7
0x16466  leave.s  loc_16474
0x16468  ldloc.s  0x11
0x1646a  brfalse.s loc_16473
0x1646c  ldloc.s  0x11
0x1646e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x16473  endfinally
0x16474  ldloc.s  7
0x16476  brfalse.s loc_164AF
0x16478  ldarg.1
0x16479  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x1647e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x16483  ldc.i4.s 0x42
0x16485  ldstr    aContinuousCopy// "continuous copy created for the restore"...
0x1648a  ldloc.s  7
0x1648c  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier::get_DatabaseName()
0x16491  ldloc.s  7
0x16493  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier::get_LogicalServer()
0x16498  ldloc.s  7
0x1649a  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier::get_AzureRegion()
0x1649f  call     string [mscorlib]System.String::Format(string, object, object, object)
0x164a4  ldc.i4.0
0x164a5  newarr   [mscorlib]System.Object
0x164aa  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x164af  leave.s  loc_16512
0x164b1  pop
0x164b2  ldarg.1
0x164b3  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x164b8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x164bd  ldc.i4.s 0x42
0x164bf  ldstr    aDatabaseContin// "Database continuous copy creation is in"...
0x164c4  ldloc.s  8
0x164c6  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.XdbRestoreRuntimeData::get_ContinuousCopyOperationId()
0x164cb  box      [mscorlib]System.Guid
0x164d0  call     string [mscorlib]System.String::Format(string, object)
0x164d5  ldc.i4.0
0x164d6  newarr   [mscorlib]System.Object
0x164db  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x164e0  leave.s  loc_16512
0x164e2  ldarg.1
0x164e3  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x164e8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x164ed  ldc.i4.s 0x42
0x164ef  ldstr    aDatabaseContin_0// " Database continuous copy creation fail"...
0x164f4  ldloc.s  8
0x164f6  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.XdbRestoreRuntimeData::get_ContinuousCopyOperationId()
0x164fb  box      [mscorlib]System.Guid
0x16500  call     string [mscorlib]System.String::Format(string, object)
0x16505  ldc.i4.0
0x16506  newarr   [mscorlib]System.Object
0x1650b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x16510  leave.s  loc_16512
0x16512  ldloc.s  5
0x16514  ldarg.2
0x16515  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreInfo::get_OrganizationId()
0x1651a  ldarg.1
0x1651b  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x16520  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_ScaleGroupId()
0x16525  ldloc.s  6
0x16527  ldloc.s  7
0x16529  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.IOrganization::UpdateOrganizationNewDatabases(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid scalegroupId, class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanPrimaryDatabaseIdentifier primaryDb, class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanSecondaryDatabaseIdentifier secondaryDb)
0x1652e  ldloc.s  5
0x16530  ldarg.2
  ... truncated ...
```
