# Microsoft.Crm.DeletionService::RunDeletionTasks

- ea: `0x370`
- end: `0x5b4`
- name: `Microsoft.Crm.DeletionService::RunDeletionTasks`
- size: `580`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0xa95c0`

## callees

- `0x2e0`
- `0x370`
- `0x5c0`
- `0x5f0`
- `0xa00`
- `0xec0`
- `0xaf40`
- `0xaf50`
- `0x802a0`
- `0xa9510`
- `0xa9560`

## string_xrefs

- `0x378`: `DeletionService: Inside DeletionService.RunDeletionTasks`
- `0x398`: `DeletionService: Inside DeletionService.RunDeletionTasks`
- `0x393`: `RunDeletionTasks`
- `0x4d8`: `MaxDegreeOfParallelismForDeletionService`
- `0x55e`: `DeletionService: In-parallel Deletion Service encountered an internal error`
- `0x59b`: `DeletionService: Deletion Service encountered an internal error`

## pseudocode

```c

```

## disassembly

```asm
0x370  ldarg.0
0x371  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x376  ldc.i4.s 0x14
0x378  ldstr    aDeletionservic// "DeletionService: Inside DeletionService"...
0x37d  ldc.i4.0
0x37e  newarr   [mscorlib]System.Object
0x383  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x388  call     class Microsoft.Crm.Platform.DeletionServiceEventSource Microsoft.Crm.Platform.DeletionServiceEventSource::get_Instance()
0x38d  ldarg.0
0x38e  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x393  ldstr    aRundeletiontas// "RunDeletionTasks"
0x398  ldstr    aDeletionservic// "DeletionService: Inside DeletionService"...
0x39d  ldc.i4.0
0x39e  ldc.i4.0
0x39f  ldsfld   bool Microsoft.Crm.DeletionService::AllowVerboseLogging
0x3a4  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceDBConnectionTimeoutInSeconds
0x3a9  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceExecutionTimeoutInMinutes
0x3ae  ldsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0x3b3  ldc.i4.0
0x3b4  ldsfld   string [mscorlib]System.String::Empty
0x3b9  callvirt instance void Microsoft.Crm.Platform.DeletionServiceEventSource::DeletionServiceInformation(valuetype [mscorlib]System.Guid organizationId, string moduleName, string message, int32 recordsDeleted, int32 durationInSecs, bool verbose, int32 deletionServiceDBConnectionTimeoutInSeconds, int32 deletionServiceExecutionTimeoutInMinutes, int32 top_numOfRecordsToBeDeleted, bool completedAllDeletes, string sqlText)
0x3be  ldarg.0
0x3bf  ldarg.2
0x3c0  call     instance void Microsoft.Crm.DeletionService::CleanUpExpiredSubscriptions(class Microsoft.Crm.IDeletionServiceProvider deletionServiceProvider)
0x3c5  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Threading.Tasks.Task>::.ctor()
0x3ca  dup
0x3cb  ldarg.0
0x3cc  ldftn    instance void Microsoft.Crm.DeletionService::DeleteAll(class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.TableEntity> tables)
0x3d2  newobj   instance void SyncDeleteAllDelegate::.ctor(object object, native int method)
0x3d7  ldarg.1
0x3d8  call     class [mscorlib]System.Threading.Tasks.Task Microsoft.Crm.DeletionService::ExecuteDeletionTaskInParallel(class SyncDeleteAllDelegate syncMethod, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.TableEntity> tableEntities)
0x3dd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Threading.Tasks.Task>::Add(var<u1>)
0x3e2  dup
0x3e3  ldarg.0
0x3e4  ldftn    instance void Microsoft.Crm.DeletionService::CleanUpPOA()
0x3ea  newobj   instance void SyncDeletionDelegate::.ctor(object object, native int method)
0x3ef  call     class [mscorlib]System.Threading.Tasks.Task Microsoft.Crm.DeletionService::ExecuteDeletionTaskInParallel(class SyncDeletionDelegate syncMethod)
0x3f4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Threading.Tasks.Task>::Add(var<u1>)
0x3f9  dup
0x3fa  ldarg.0
0x3fb  ldftn    instance void Microsoft.Crm.DeletionService::CleanUpOrphanedAttachments()
0x401  newobj   instance void SyncDeletionDelegate::.ctor(object object, native int method)
0x406  call     class [mscorlib]System.Threading.Tasks.Task Microsoft.Crm.DeletionService::ExecuteDeletionTaskInParallel(class SyncDeletionDelegate syncMethod)
0x40b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Threading.Tasks.Task>::Add(var<u1>)
0x410  dup
0x411  ldarg.0
0x412  ldftn    instance void Microsoft.Crm.DeletionService::CleanUpMetadataSyncTrackingDeletedObjects()
0x418  newobj   instance void SyncDeletionDelegate::.ctor(object object, native int method)
0x41d  call     class [mscorlib]System.Threading.Tasks.Task Microsoft.Crm.DeletionService::ExecuteDeletionTaskInParallel(class SyncDeletionDelegate syncMethod)
0x422  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Threading.Tasks.Task>::Add(var<u1>)
0x427  dup
0x428  ldarg.0
0x429  ldftn    instance void Microsoft.Crm.DeletionService::CleanUpPostRegarding()
0x42f  newobj   instance void SyncDeletionDelegate::.ctor(object object, native int method)
0x434  call     class [mscorlib]System.Threading.Tasks.Task Microsoft.Crm.DeletionService::ExecuteDeletionTaskInParallel(class SyncDeletionDelegate syncMethod)
0x439  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Threading.Tasks.Task>::Add(var<u1>)
0x43e  dup
0x43f  ldarg.0
0x440  ldftn    instance void Microsoft.Crm.DeletionService::CleanUpTraceRegarding()
0x446  newobj   instance void SyncDeletionDelegate::.ctor(object object, native int method)
0x44b  call     class [mscorlib]System.Threading.Tasks.Task Microsoft.Crm.DeletionService::ExecuteDeletionTaskInParallel(class SyncDeletionDelegate syncMethod)
0x450  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Threading.Tasks.Task>::Add(var<u1>)
0x455  dup
0x456  ldarg.0
0x457  ldftn    instance void Microsoft.Crm.DeletionService::ShrinkMailboxStatisticsTable()
0x45d  newobj   instance void SyncDeletionDelegate::.ctor(object object, native int method)
0x462  call     class [mscorlib]System.Threading.Tasks.Task Microsoft.Crm.DeletionService::ExecuteDeletionTaskInParallel(class SyncDeletionDelegate syncMethod)
0x467  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Threading.Tasks.Task>::Add(var<u1>)
0x46c  dup
0x46d  ldarg.0
0x46e  ldftn    instance void Microsoft.Crm.DeletionService::CleanUpOfficeDocumentRecords()
0x474  newobj   instance void SyncDeletionDelegate::.ctor(object object, native int method)
0x479  call     class [mscorlib]System.Threading.Tasks.Task Microsoft.Crm.DeletionService::ExecuteDeletionTaskInParallel(class SyncDeletionDelegate syncMethod)
0x47e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Threading.Tasks.Task>::Add(var<u1>)
0x483  dup
0x484  ldarg.0
0x485  ldftn    instance void Microsoft.Crm.DeletionService::CleanUpMetadataTimestampTable()
0x48b  newobj   instance void SyncDeletionDelegate::.ctor(object object, native int method)
0x490  call     class [mscorlib]System.Threading.Tasks.Task Microsoft.Crm.DeletionService::ExecuteDeletionTaskInParallel(class SyncDeletionDelegate syncMethod)
0x495  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Threading.Tasks.Task>::Add(var<u1>)
0x49a  stloc.0
0x49b  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x4a0  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x4a5  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_SSSReliability()
0x4aa  ldarg.0
0x4ab  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x4b0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x4b5  call     bool Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail featureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4ba  brfalse.s loc_4D3
0x4bc  ldloc.0
0x4bd  ldarg.0
0x4be  ldftn    instance void Microsoft.Crm.DeletionService::ShrinkTraceLogTable()
0x4c4  newobj   instance void SyncDeletionDelegate::.ctor(object object, native int method)
0x4c9  call     class [mscorlib]System.Threading.Tasks.Task Microsoft.Crm.DeletionService::ExecuteDeletionTaskInParallel(class SyncDeletionDelegate syncMethod)
0x4ce  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Threading.Tasks.Task>::Add(var<u1>)
0x4d3  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x4d8  ldstr    aMaxdegreeofpar// "MaxDegreeOfParallelismForDeletionServic"...
0x4dd  ldloc.0
0x4de  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Threading.Tasks.Task>::get_Count()
0x4e3  callvirt T0x2B000001
0x4e8  stloc.1
0x4e9  ldloc.1
0x4ea  ldc.i4.1
0x4eb  bge.s    loc_4EF
0x4ed  ldc.i4.1
0x4ee  stloc.1
0x4ef  ldloc.1
0x4f0  ldloc.1
0x4f1  newobj   instance void [System]System.Threading.Semaphore::.ctor(int32, int32)
0x4f6  stsfld   class [System]System.Threading.Semaphore Microsoft.Crm.DeletionService::poolTask
0x4fb  ldloc.0
0x4fc  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Threading.Tasks.Task>::GetEnumerator()
0x501  stloc.2
0x502  br.s     loc_51B
0x504  ldloca.s 2
0x506  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [mscorlib]System.Threading.Tasks.Task>::get_Current()
0x50b  ldsfld   class [System]System.Threading.Semaphore Microsoft.Crm.DeletionService::poolTask
0x510  callvirt instance bool [mscorlib]System.Threading.WaitHandle::WaitOne()
0x515  pop
0x516  callvirt instance void [mscorlib]System.Threading.Tasks.Task::Start()
0x51b  ldloca.s 2
0x51d  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [mscorlib]System.Threading.Tasks.Task>::MoveNext()
0x522  brtrue.s loc_504
0x524  leave.s  loc_534
0x526  ldloca.s 2
0x528  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [mscorlib]System.Threading.Tasks.Task>
0x52e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x533  endfinally
0x534  nop
0x535  ldloc.0
0x536  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Threading.Tasks.Task>::ToArray()
0x53b  call     void [mscorlib]System.Threading.Tasks.Task::WaitAll(class [mscorlib]System.Threading.Tasks.Task[])
0x540  leave.s  loc_58A
0x542  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [mscorlib]System.Exception> [mscorlib]System.AggregateException::get_InnerExceptions()
0x547  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [mscorlib]System.Exception>::GetEnumerator()
0x54c  stloc.3
0x54d  br.s     loc_574
0x54f  ldloc.3
0x550  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [mscorlib]System.Exception>::get_Current()
0x555  stloc.s  4
0x557  ldarg.0
0x558  ldc.i4   0xC0004007
0x55d  conv.u8
0x55e  ldstr    aDeletionservic_0// "DeletionService: In-parallel Deletion S"...
0x563  ldloc.s  4
0x565  callvirt instance string [mscorlib]System.Object::ToString()
0x56a  ldsfld   string [mscorlib]System.String::Empty
0x56f  call     instance void Microsoft.Crm.DeletionService::LogCrmTraceAndEventLog(int64 logId, string crmTraceMessage, string errorMessage, string sqlText)
0x574  ldloc.3
0x575  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x57a  brtrue.s loc_54F
0x57c  leave.s  loc_588
0x57e  ldloc.3
0x57f  brfalse.s loc_587
0x581  ldloc.3
0x582  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x587  endfinally
0x588  leave.s  loc_58A
0x58a  ldarg.0
0x58b  call     instance void Microsoft.Crm.DeletionService::CleanUpSubscriptionTrackingDeletedObjects()
0x590  leave.s  loc_5B3
0x592  stloc.s  5
0x594  ldarg.0
0x595  ldc.i4   0xC0004007
0x59a  conv.u8
0x59b  ldstr    aDeletionservic_1// "DeletionService: Deletion Service encou"...
0x5a0  ldloc.s  5
0x5a2  callvirt instance string [mscorlib]System.Object::ToString()
0x5a7  ldsfld   string [mscorlib]System.String::Empty
0x5ac  call     instance void Microsoft.Crm.DeletionService::LogCrmTraceAndEventLog(int64 logId, string crmTraceMessage, string errorMessage, string sqlText)
0x5b1  rethrow
0x5b3  ret
```
