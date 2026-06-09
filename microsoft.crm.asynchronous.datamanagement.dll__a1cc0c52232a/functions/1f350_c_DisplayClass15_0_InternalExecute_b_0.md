# <>c__DisplayClass15_0::<InternalExecute>b__0

- ea: `0x1f350`
- end: `0x1fa6c`
- name: `<>c__DisplayClass15_0::<InternalExecute>b__0`
- size: `1820`
- prototype: ``
- caller_count: `0`
- callee_count: `24`
- tags: `file_ops, authz_impersonation, loader_planting`

## callees

- `0xf00`
- `0x1000`
- `0x10d0`
- `0x11b0`
- `0x1270`
- `0x1540`
- `0x1590`
- `0x16e0`
- `0x1710`
- `0x1780`
- `0x17b0`
- `0x17f0`
- `0x1880`
- `0x18d0`
- `0x1ba0`
- `0x1db0`
- `0x23d0`
- `0x2660`
- `0x2760`
- `0x2930`
- `0x2a90`
- `0x2ab0`
- `0x3a30`
- `0x1f350`

## string_xrefs

- `0x1f483`: `Insufficient privilege to perform this operation`
- `0x1f35f`: `Operation type must be 'BulkDelete'`
- `0x1f3e2`: `BulkDeleteDependent_`
- `0x1f410`: `BulkDeleteIndependent_`
- `0x1f9a9`: `Error in Bulk Delete handler | {0}`

## pseudocode

```c

```

## disassembly

```asm
0x1f350  ldarg.0
0x1f351  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent <>c__DisplayClass15_0::asyncEvent
0x1f356  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OperationType()
0x1f35b  ldc.i4.s 0xD
0x1f35d  ceq
0x1f35f  ldstr    aOperationTypeM_9// "Operation type must be 'BulkDelete'"
0x1f364  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x1f369  ldnull
0x1f36a  stloc.0
0x1f36b  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSucceededResult::.ctor()
0x1f370  stloc.1
0x1f371  ldarg.0
0x1f372  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteOperation <>c__DisplayClass15_0::<>4__this
0x1f377  ldc.i4.1
0x1f378  stfld    int32 Microsoft.Crm.Asynchronous.BulkDeleteOperation::_threadCount
0x1f37d  ldarg.0
0x1f37e  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteOperation <>c__DisplayClass15_0::<>4__this
0x1f383  ldarg.0
0x1f384  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent <>c__DisplayClass15_0::asyncEvent
0x1f389  stfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.BulkDeleteOperation::_asyncEvent
0x1f38e  ldarg.0
0x1f38f  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteOperation <>c__DisplayClass15_0::<>4__this
0x1f394  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x1f399  stfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Asynchronous.BulkDeleteOperation::_pausedJobs
0x1f39e  ldarg.0
0x1f39f  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteOperation <>c__DisplayClass15_0::<>4__this
0x1f3a4  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x1f3a9  stfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Asynchronous.BulkDeleteOperation::_failedJobs
0x1f3ae  ldarg.0
0x1f3af  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteOperation <>c__DisplayClass15_0::<>4__this
0x1f3b4  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x1f3b9  stfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Asynchronous.BulkDeleteOperation::_cancelledJobs
0x1f3be  ldc.i4.0
0x1f3bf  stloc.2
0x1f3c0  ldc.i4.0
0x1f3c1  stloc.3
0x1f3c2  ldc.i4.0
0x1f3c3  stloc.s  4
0x1f3c5  ldarg.0
0x1f3c6  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteOperation <>c__DisplayClass15_0::<>4__this
0x1f3cb  ldarg.0
0x1f3cc  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent <>c__DisplayClass15_0::asyncEvent
0x1f3d1  ldc.i4.0
0x1f3d2  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService [Microsoft.Crm.Asynchronous.HandlerUtility]Microsoft.Crm.Asynchronous.SdkServiceFactory::CreateInstance(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent, bool)
0x1f3d7  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.BulkDeleteOperation::_crmService
0x1f3dc  ldarg.0
0x1f3dd  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteOperation <>c__DisplayClass15_0::<>4__this
0x1f3e2  ldstr    aBulkdeletedepe// "BulkDeleteDependent_"
0x1f3e7  ldarg.0
0x1f3e8  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent <>c__DisplayClass15_0::asyncEvent
0x1f3ed  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_EventId()
0x1f3f2  stloc.s  9
0x1f3f4  ldloca.s 9
0x1f3f6  ldstr    aN// "N"
0x1f3fb  call     instance string [mscorlib]System.Guid::ToString(string)
0x1f400  call     string [mscorlib]System.String::Concat(string, string)
0x1f405  stfld    string Microsoft.Crm.Asynchronous.BulkDeleteOperation::_tempDependentTableName
0x1f40a  ldarg.0
0x1f40b  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteOperation <>c__DisplayClass15_0::<>4__this
0x1f410  ldstr    aBulkdeleteinde// "BulkDeleteIndependent_"
0x1f415  ldarg.0
0x1f416  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent <>c__DisplayClass15_0::asyncEvent
0x1f41b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_EventId()
0x1f420  stloc.s  9
0x1f422  ldloca.s 9
0x1f424  ldstr    aN// "N"
0x1f429  call     instance string [mscorlib]System.Guid::ToString(string)
0x1f42e  call     string [mscorlib]System.String::Concat(string, string)
0x1f433  stfld    string Microsoft.Crm.Asynchronous.BulkDeleteOperation::_tempIndependentTempTableName
0x1f438  ldarg.0
0x1f439  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteOperation <>c__DisplayClass15_0::<>4__this
0x1f43e  ldarg.0
0x1f43f  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent <>c__DisplayClass15_0::asyncEvent
0x1f444  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x1f449  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BulkDeleteOperation::_organizationId
0x1f44e  ldarg.0
0x1f44f  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteOperation <>c__DisplayClass15_0::<>4__this
0x1f454  ldarg.0
0x1f455  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent <>c__DisplayClass15_0::asyncEvent
0x1f45a  call     instance class [Microsoft.Crm]Microsoft.Crm.BulkDeleteData Microsoft.Crm.Asynchronous.BulkDeleteOperation::GetBulkDeleteOperationData(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent asyncEvent)
0x1f45f  stloc.0
0x1f460  ldarg.0
0x1f461  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteOperation <>c__DisplayClass15_0::<>4__this
0x1f466  ldarg.0
0x1f467  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent <>c__DisplayClass15_0::asyncEvent
0x1f46c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_OwnerId()
0x1f471  ldarg.0
0x1f472  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent <>c__DisplayClass15_0::asyncEvent
0x1f477  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x1f47c  call     instance bool Microsoft.Crm.Asynchronous.BulkDeleteOperation::UserHasBulkDeletePrivilege(valuetype [mscorlib]System.Guid userId, valuetype [mscorlib]System.Guid organizationId)
0x1f481  brtrue.s loc_1F493
0x1f483  ldstr    aInsufficientPr// "Insufficient privilege to perform this "...
0x1f488  ldc.i4   0x8004024B
0x1f48d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x1f492  throw
0x1f493  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Asynchronous.BulkDeleteOperation::Logger
0x1f498  call     var<u1> class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Crm.Asynchronous.BulkDeleteDropTableIfDeletionHadNotStartedActivity>::get_Instance()
0x1f49d  ldarg.0
0x1f49e  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteOperation <>c__DisplayClass15_0::<>4__this
0x1f4a3  ldftn    instance void Microsoft.Crm.Asynchronous.BulkDeleteOperation::<InternalExecute>b__15_1()
0x1f4a9  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x1f4ae  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryExtensions::Execute(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryActivityType, class [mscorlib]System.Action)
0x1f4b3  ldarg.0
0x1f4b4  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteOperation <>c__DisplayClass15_0::<>4__this
0x1f4b9  call     instance bool Microsoft.Crm.Asynchronous.BulkDeleteOperation::ChildJobsHaveNotBeenCreated()
0x1f4be  brfalse.s loc_1F4DB
0x1f4c0  ldarg.0
0x1f4c1  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteOperation <>c__DisplayClass15_0::<>4__this
0x1f4c6  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteDataAccess Microsoft.Crm.Asynchronous.BulkDeleteOperation::_bulkDeleteDataAccess
0x1f4cb  ldarg.0
0x1f4cc  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteOperation <>c__DisplayClass15_0::<>4__this
0x1f4d1  ldfld    string Microsoft.Crm.Asynchronous.BulkDeleteOperation::_tempIndependentTempTableName
0x1f4d6  callvirt instance void Microsoft.Crm.Asynchronous.BulkDeleteDataAccess::DeleteTempTable(string tableName)
0x1f4db  ldarg.0
0x1f4dc  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteOperation <>c__DisplayClass15_0::<>4__this
0x1f4e1  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteDataAccess Microsoft.Crm.Asynchronous.BulkDeleteOperation::_bulkDeleteDataAccess
0x1f4e6  ldarg.0
0x1f4e7  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteOperation <>c__DisplayClass15_0::<>4__this
0x1f4ec  ldfld    string Microsoft.Crm.Asynchronous.BulkDeleteOperation::_tempDependentTableName
0x1f4f1  ldloca.s 3
0x1f4f3  callvirt instance bool Microsoft.Crm.Asynchronous.BulkDeleteDataAccess::CreateTempTable(string tableName, [out] bool& tableIsPresent)
0x1f4f8  stloc.2
0x1f4f9  ldarg.0
0x1f4fa  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteOperation <>c__DisplayClass15_0::<>4__this
0x1f4ff  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteDataAccess Microsoft.Crm.Asynchronous.BulkDeleteOperation::_bulkDeleteDataAccess
0x1f504  ldarg.0
0x1f505  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteOperation <>c__DisplayClass15_0::<>4__this
0x1f50a  ldfld    string Microsoft.Crm.Asynchronous.BulkDeleteOperation::_tempIndependentTempTableName
0x1f50f  ldloca.s 4
0x1f511  callvirt instance bool Microsoft.Crm.Asynchronous.BulkDeleteDataAccess::CreateTempTable(string tableName, [out] bool& tableIsPresent)
0x1f516  ldarg.0
0x1f517  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteOperation <>c__DisplayClass15_0::<>4__this
0x1f51c  ldloc.0
0x1f51d  callvirt instance string[] [Microsoft.Crm]Microsoft.Crm.BulkDeleteData::get_QuerySet()
0x1f522  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression[] Microsoft.Crm.Asynchronous.BulkDeleteOperation::GetQueryExpressionsFromFetchXml(string[] fetchXml)
0x1f527  stloc.s  5
0x1f529  ldarg.0
0x1f52a  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteOperation <>c__DisplayClass15_0::<>4__this
0x1f52f  ldloc.s  5
0x1f531  call     instance void Microsoft.Crm.Asynchronous.BulkDeleteOperation::OrderQueryExpressionsBasedOnCascadeRestrictRelationship(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression[] querySet)
0x1f536  ldarg.0
0x1f537  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteOperation <>c__DisplayClass15_0::<>4__this
0x1f53c  call     instance string Microsoft.Crm.Asynchronous.BulkDeleteOperation::GetFetchXmlFromQuerySet()
0x1f541  stloc.s  6
0x1f543  ldarg.0
0x1f544  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteOperation <>c__DisplayClass15_0::<>4__this
0x1f549  ldarg.0
0x1f54a  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent <>c__DisplayClass15_0::asyncEvent
0x1f54f  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BulkDeleteOperation::GetBusinessUnitId(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent asyncEvent)
0x1f554  stloc.s  7
0x1f556  ldarg.0
0x1f557  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteOperation <>c__DisplayClass15_0::<>4__this
0x1f55c  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteDataAccess Microsoft.Crm.Asynchronous.BulkDeleteOperation::_bulkDeleteDataAccess
0x1f561  ldarg.0
0x1f562  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent <>c__DisplayClass15_0::asyncEvent
0x1f567  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_EventId()
0x1f56c  ldloc.s  6
0x1f56e  ldarg.0
0x1f56f  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent <>c__DisplayClass15_0::asyncEvent
0x1f574  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_OwnerId()
0x1f579  ldloc.s  7
0x1f57b  callvirt instance void Microsoft.Crm.Asynchronous.BulkDeleteDataAccess::SetOrderedQuerySetXml(valuetype [mscorlib]System.Guid asyncOperationId, string querySetXml, valuetype [mscorlib]System.Guid ownerId, valuetype [mscorlib]System.Guid businessUnitId)
0x1f580  brtrue.s loc_1F5C6
0x1f582  ldarg.0
0x1f583  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteOperation <>c__DisplayClass15_0::<>4__this
0x1f588  ldarg.0
0x1f589  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent <>c__DisplayClass15_0::asyncEvent
0x1f58e  ldarg.0
0x1f58f  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteOperation <>c__DisplayClass15_0::<>4__this
0x1f594  ldfld    string Microsoft.Crm.Asynchronous.BulkDeleteOperation::_tempIndependentTempTableName
0x1f599  ldarg.0
0x1f59a  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteOperation <>c__DisplayClass15_0::<>4__this
0x1f59f  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression> Microsoft.Crm.Asynchronous.BulkDeleteOperation::_notOrderedQueryExpList
0x1f5a4  ldc.i4.0
0x1f5a5  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerResult Microsoft.Crm.Asynchronous.BulkDeleteOperation::RetrieveRecordsAndPopulateTemporaryTable(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent asyncEvent, string tableName, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression> queryExpressionList, bool pauseChildJobs)
0x1f5aa  stloc.1
0x1f5ab  ldarg.0
0x1f5ac  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteOperation <>c__DisplayClass15_0::<>4__this
0x1f5b1  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteDataAccess Microsoft.Crm.Asynchronous.BulkDeleteOperation::_bulkDeleteDataAccess
0x1f5b6  ldarg.0
0x1f5b7  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteOperation <>c__DisplayClass15_0::<>4__this
0x1f5bc  ldfld    string Microsoft.Crm.Asynchronous.BulkDeleteOperation::_tempIndependentTempTableName
0x1f5c1  callvirt instance void Microsoft.Crm.Asynchronous.BulkDeleteDataAccess::CreateIndexOnTempTable(string tableName)
0x1f5c6  ldloc.1
0x1f5c7  isinst   [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSucceededResult
0x1f5cc  brtrue.s loc_1F5D6
0x1f5ce  ldloc.1
0x1f5cf  stloc.s  0xA
0x1f5d1  leave    loc_1FA69
0x1f5d6  ldarg.0
0x1f5d7  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteOperation <>c__DisplayClass15_0::<>4__this
0x1f5dc  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteDataAccess Microsoft.Crm.Asynchronous.BulkDeleteOperation::_bulkDeleteDataAccess
0x1f5e1  ldarg.0
0x1f5e2  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteOperation <>c__DisplayClass15_0::<>4__this
0x1f5e7  ldfld    string Microsoft.Crm.Asynchronous.BulkDeleteOperation::_tempIndependentTempTableName
0x1f5ec  callvirt instance int32 Microsoft.Crm.Asynchronous.BulkDeleteDataAccess::CountOfRows(string tableName)
0x1f5f1  stloc.s  8
0x1f5f3  ldarg.0
0x1f5f4  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteOperation <>c__DisplayClass15_0::<>4__this
0x1f5f9  ldfld    int32 Microsoft.Crm.Asynchronous.BulkDeleteOperation::_threadCount
0x1f5fe  ldloc.s  8
0x1f600  ble.s    loc_1F60E
0x1f602  ldarg.0
0x1f603  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteOperation <>c__DisplayClass15_0::<>4__this
0x1f608  ldc.i4.1
0x1f609  stfld    int32 Microsoft.Crm.Asynchronous.BulkDeleteOperation::_threadCount
0x1f60e  ldloc.s  8
0x1f610  brfalse  loc_1F735
0x1f615  ldloc.s  8
0x1f617  ldarg.0
0x1f618  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteOperation <>c__DisplayClass15_0::<>4__this
0x1f61d  ldfld    int32 Microsoft.Crm.Asynchronous.BulkDeleteOperation::_threadCount
0x1f622  div
0x1f623  stloc.s  0xB
0x1f625  ldc.i4.0
0x1f626  stloc.s  0xE
0x1f628  br       loc_1F6F8
0x1f62d  ldloc.s  0xE
0x1f62f  ldloc.s  0xB
0x1f631  mul
0x1f632  ldc.i4.1
0x1f633  add
0x1f634  stloc.s  0xC
0x1f636  ldloc.s  0xE
0x1f638  ldarg.0
0x1f639  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteOperation <>c__DisplayClass15_0::<>4__this
0x1f63e  ldfld    int32 Microsoft.Crm.Asynchronous.BulkDeleteOperation::_threadCount
0x1f643  ldc.i4.1
0x1f644  sub
0x1f645  bne.un.s loc_1F64D
0x1f647  ldloc.s  8
0x1f649  stloc.s  0xD
0x1f64b  br.s     loc_1F656
0x1f64d  ldloc.s  0xE
0x1f64f  ldc.i4.1
0x1f650  add
0x1f651  ldloc.s  0xB
0x1f653  mul
0x1f654  stloc.s  0xD
0x1f656  newobj   instance void [Microsoft.Crm]Microsoft.Crm.BulkDeleteChildData::.ctor()
0x1f65b  stloc.s  0xF
0x1f65d  ldloc.s  0xF
0x1f65f  ldloc.s  0xC
0x1f661  callvirt instance void [Microsoft.Crm]Microsoft.Crm.BulkDeleteChildData::set_StartRow(int32)
0x1f666  ldloc.s  0xF
0x1f668  ldloc.s  0xD
0x1f66a  callvirt instance void [Microsoft.Crm]Microsoft.Crm.BulkDeleteChildData::set_EndRow(int32)
0x1f66f  ldloc.s  0xF
0x1f671  ldarg.0
0x1f672  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteOperation <>c__DisplayClass15_0::<>4__this
0x1f677  ldfld    string Microsoft.Crm.Asynchronous.BulkDeleteOperation::_tempIndependentTempTableName
0x1f67c  callvirt instance void [Microsoft.Crm]Microsoft.Crm.BulkDeleteChildData::set_TempTableName(string)
0x1f681  ldarg.0
0x1f682  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteOperation <>c__DisplayClass15_0::<>4__this
0x1f687  ldloc.s  0xF
0x1f689  call     instance string Microsoft.Crm.Asynchronous.BulkDeleteOperation::SerializeAndCompressData(class [Microsoft.Crm]Microsoft.Crm.BulkDeleteChildData bulkDeleteChildData)
0x1f68e  stloc.s  0x10
0x1f690  ldarg.0
0x1f691  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteOperation <>c__DisplayClass15_0::<>4__this
0x1f696  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BulkDeleteOperation::_organizationId
0x1f69b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x1f6a0  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1f6a5  ldstr    aAsyncoperation_2// "AsyncOperation"
0x1f6aa  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string)
0x1f6af  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x1f6b4  stloc.s  0x11
0x1f6b6  ldarg.0
0x1f6b7  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteOperation <>c__DisplayClass15_0::<>4__this
0x1f6bc  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteDataAccess Microsoft.Crm.Asynchronous.BulkDeleteOperation::_bulkDeleteDataAccess
0x1f6c1  ldarg.0
0x1f6c2  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent <>c__DisplayClass15_0::asyncEvent
0x1f6c7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_EventId()
0x1f6cc  ldloc.s  0x10
0x1f6ce  ldarg.0
0x1f6cf  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent <>c__DisplayClass15_0::asyncEvent
0x1f6d4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_EventId()
0x1f6d9  ldsfld   string [mscorlib]System.String::Empty
0x1f6de  ldc.i4.s 0x17
0x1f6e0  ldarg.0
0x1f6e1  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent <>c__DisplayClass15_0::asyncEvent
0x1f6e6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_EventId()
0x1f6eb  ldloc.s  0x11
0x1f6ed  callvirt instance void Microsoft.Crm.Asynchronous.DataManagementDataAccessBase::CreateAsyncOperation(valuetype [mscorlib]System.Guid asyncOperationId, string data, valuetype [mscorlib]System.Guid regardingObjectId, string dependencyToken, int32 operationType, valuetype [mscorlib]System.Guid requestId, int32 typeCode)
0x1f6f2  ldloc.s  0xE
0x1f6f4  ldc.i4.1
0x1f6f5  add
0x1f6f6  stloc.s  0xE
0x1f6f8  ldloc.s  0xE
0x1f6fa  ldarg.0
0x1f6fb  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteOperation <>c__DisplayClass15_0::<>4__this
0x1f700  ldfld    int32 Microsoft.Crm.Asynchronous.BulkDeleteOperation::_threadCount
0x1f705  blt      loc_1F62D
0x1f70a  ldarg.0
0x1f70b  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteOperation <>c__DisplayClass15_0::<>4__this
0x1f710  call     instance bool Microsoft.Crm.Asynchronous.BulkDeleteOperation::AllJobsSubmittedTillNowHaveCompleted()
0x1f715  brtrue.s loc_1F735
0x1f717  ldarg.0
0x1f718  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteOperation <>c__DisplayClass15_0::<>4__this
0x1f71d  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Asynchronous.BulkDeleteOperation::_pausedJobs
0x1f722  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
  ... truncated ...
```
