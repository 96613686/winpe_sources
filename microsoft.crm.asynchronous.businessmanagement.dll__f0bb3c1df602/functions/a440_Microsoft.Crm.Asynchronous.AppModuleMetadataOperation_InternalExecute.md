# Microsoft.Crm.Asynchronous.AppModuleMetadataOperation::InternalExecute

- ea: `0xa440`
- end: `0xa700`
- name: `Microsoft.Crm.Asynchronous.AppModuleMetadataOperation::InternalExecute`
- size: `704`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0xa440`
- `0xa700`
- `0xa740`

## string_xrefs

- `0xa4cf`: `Attempting to populate AMM table for App {0}`
- `0xa630`: `Retrying AMM update, count: {0} for App {1} : {2}`
- `0xa6b3`: `Exiting after retrying AMM update {0} times for App {1} : {2}`

## pseudocode

```c

```

## disassembly

```asm
0xa440  ldarg.1
0xa441  ldnull
0xa442  cgt.un
0xa444  ldstr    aAsyncOperation// "Async operation is null: AppModuleMetad"...
0xa449  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0xa44e  ldarg.1
0xa44f  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OperationType()
0xa454  ldc.i4.s 0x48
0xa456  ceq
0xa458  ldstr    aOperationTypeM_6// "Operation type must be 'AppModuleMetada"...
0xa45d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0xa462  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleTelemetryEvents [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleTelemetryEvents::get_Instance()
0xa467  ldarg.1
0xa468  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xa46d  ldstr    aAppmoduleasync// "AppModuleAsyncJob"
0xa472  ldarg.1
0xa473  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_PrimaryEntityId()
0xa478  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xa47d  stloc.3
0xa47e  ldloca.s 3
0xa480  ldarg.1
0xa481  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_CreatedOn()
0xa486  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::Subtract(valuetype [mscorlib]System.DateTime)
0xa48b  stloc.s  4
0xa48d  ldloca.s 4
0xa48f  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0xa494  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleTelemetryEvents::AppModuleOfflineAsyncJob(valuetype [mscorlib]System.Guid, string, valuetype [mscorlib]System.Guid, float64)
0xa499  newobj   instance void [System]System.Diagnostics.Stopwatch::.ctor()
0xa49e  stloc.0
0xa49f  ldloc.0
0xa4a0  callvirt instance void [System]System.Diagnostics.Stopwatch::Start()
0xa4a5  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppModuleMetadataOperationLogService::.ctor()
0xa4aa  stloc.1
0xa4ab  ldloca.s 2
0xa4ad  ldarg.1
0xa4ae  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_Data()
0xa4b3  call     instance void [mscorlib]System.Guid::.ctor(string)
0xa4b8  ldarg.1
0xa4b9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xa4be  ldc.i4.0
0xa4bf  ldc.i4.0
0xa4c0  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0xa4c5  stloc.s  5
0xa4c7  ldarg.1
0xa4c8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xa4cd  ldc.i4.s 0x47
0xa4cf  ldstr    aAttemptingToPo// "Attempting to populate AMM table for Ap"...
0xa4d4  ldc.i4.1
0xa4d5  newarr   [mscorlib]System.Object
0xa4da  dup
0xa4db  ldc.i4.0
0xa4dc  ldarg.1
0xa4dd  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_Data()
0xa4e2  stelem.ref
0xa4e3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xa4e8  ldloc.s  5
0xa4ea  ldc.i4.0
0xa4eb  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnBeginRequest(bool)
0xa4f0  ldloc.1
0xa4f1  ldloc.2
0xa4f2  ldloc.s  5
0xa4f4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppModuleMetadataOperationLogService::Retrieve(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xa4f9  ldloc.1
0xa4fa  ldloc.2
0xa4fb  ldarg.1
0xa4fc  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_RetryCount()
0xa501  ldloc.s  5
0xa503  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppModuleMetadataOperationLogService::UpdateLogToActiveState(valuetype [mscorlib]System.Guid, int32, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xa508  ldstr    aAppmoduleid// "appmoduleid"
0xa50d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xa512  unbox.any [mscorlib]System.Guid
0xa517  stloc.s  6
0xa519  ldloc.s  5
0xa51b  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xa520  stloc.s  7
0xa522  ldloc.s  6
0xa524  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xa529  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xa52e  brfalse.s loc_A53F
0xa530  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.MetadataService.Utility.AppModuleMetadataUpdater::.ctor()
0xa535  ldloc.s  5
0xa537  call     instance class [Microsoft.Crm.ObjectModel]Microsoft.Crm.MetadataService.Utility.GlobalInfo [Microsoft.Crm.ObjectModel]Microsoft.Crm.MetadataService.Utility.AppModuleMetadataUpdater::PopulateGlobalCache(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xa53c  pop
0xa53d  br.s     loc_A54E
0xa53f  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.MetadataService.Utility.AppModuleMetadataUpdater::.ctor()
0xa544  ldloc.s  6
0xa546  ldloc.s  5
0xa548  call     instance class [Microsoft.Crm.ObjectModel]Microsoft.Crm.MetadataService.Utility.AppInfo [Microsoft.Crm.ObjectModel]Microsoft.Crm.MetadataService.Utility.AppModuleMetadataUpdater::PopulateAppModuleCache(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xa54d  pop
0xa54e  leave.s  loc_A55C
0xa550  ldloc.s  7
0xa552  brfalse.s loc_A55B
0xa554  ldloc.s  7
0xa556  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa55b  endfinally
0xa55c  ldarg.0
0xa55d  ldloc.1
0xa55e  ldloc.2
0xa55f  ldloc.s  5
0xa561  call     instance void Microsoft.Crm.Asynchronous.AppModuleMetadataOperation::DeleteOperationLog(class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppModuleMetadataOperationLogService appModuleMetadataOperationLogService, valuetype [mscorlib]System.Guid appModuleMetadataOperationLogId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xa566  ldarg.1
0xa567  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xa56c  ldc.i4.s 0x47
0xa56e  ldstr    aPopulatingAmmT// "Populating AMM table for App {0} was su"...
0xa573  ldc.i4.1
0xa574  newarr   [mscorlib]System.Object
0xa579  dup
0xa57a  ldc.i4.0
0xa57b  ldarg.1
0xa57c  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_Data()
0xa581  stelem.ref
0xa582  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xa587  ldloc.s  5
0xa589  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnEndRequest()
0xa58e  ldloc.0
0xa58f  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0xa594  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleTelemetryEvents [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleTelemetryEvents::get_Instance()
0xa599  ldarg.1
0xa59a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xa59f  ldstr    aAppmoduleasync// "AppModuleAsyncJob"
0xa5a4  ldarg.1
0xa5a5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_PrimaryEntityId()
0xa5aa  ldloc.0
0xa5ab  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0xa5b0  conv.r8
0xa5b1  ldc.r8   1000.0
0xa5ba  div
0xa5bb  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleTelemetryEvents::AppModuleOfflineAPI(valuetype [mscorlib]System.Guid, string, valuetype [mscorlib]System.Guid, float64)
0xa5c0  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSucceededResult::.ctor()
0xa5c5  stloc.s  8
0xa5c7  leave    loc_A6FD
0xa5cc  stloc.s  9
0xa5ce  ldloc.s  9
0xa5d0  ldarg.1
0xa5d1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xa5d6  ldc.i4.s 0x47
0xa5d8  ldstr    aErrorPupulatin// "Error pupulating AMM table for App {0} "...
0xa5dd  ldc.i4.2
0xa5de  newarr   [mscorlib]System.Object
0xa5e3  dup
0xa5e4  ldc.i4.0
0xa5e5  ldarg.1
0xa5e6  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_Data()
0xa5eb  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xa5f0  brtrue.s loc_A5FA
0xa5f2  ldarg.1
0xa5f3  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_Data()
0xa5f8  br.s     loc_A5FF
0xa5fa  ldstr    aNotFound// "Not Found"
0xa5ff  stelem.ref
0xa600  dup
0xa601  ldc.i4.1
0xa602  ldloc.s  9
0xa604  callvirt instance string [mscorlib]System.Exception::get_Message()
0xa609  stelem.ref
0xa60a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xa60f  ldarg.1
0xa610  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_RetryCount()
0xa615  ldc.i4.3
0xa616  bge      loc_A69F
0xa61b  ldarg.0
0xa61c  ldloc.1
0xa61d  ldloc.2
0xa61e  ldarg.1
0xa61f  ldloc.s  5
0xa621  call     instance void Microsoft.Crm.Asynchronous.AppModuleMetadataOperation::UpdateOperationLog(class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppModuleMetadataOperationLogService appModuleMetadataOperationLogService, valuetype [mscorlib]System.Guid appModuleMetadataOperationLogId, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent asyncEvent, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xa626  ldloc.s  9
0xa628  ldarg.1
0xa629  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xa62e  ldc.i4.s 0x47
0xa630  ldstr    aRetryingAmmUpd// "Retrying AMM update, count: {0} for App"...
0xa635  ldc.i4.3
0xa636  newarr   [mscorlib]System.Object
0xa63b  dup
0xa63c  ldc.i4.0
0xa63d  ldarg.1
0xa63e  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_RetryCount()
0xa643  box      [mscorlib]System.Int32
0xa648  stelem.ref
0xa649  dup
0xa64a  ldc.i4.1
0xa64b  ldarg.1
0xa64c  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_Data()
0xa651  stelem.ref
0xa652  dup
0xa653  ldc.i4.2
0xa654  ldloc.s  9
0xa656  callvirt instance string [mscorlib]System.Exception::get_Message()
0xa65b  stelem.ref
0xa65c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xa661  ldloc.s  5
0xa663  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnErrorRequest()
0xa668  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xa66d  stloc.3
0xa66e  ldloca.s 3
0xa670  ldc.r8   5.0
0xa679  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMinutes(float64)
0xa67e  stloc.s  0xA
0xa680  ldc.i4.1
0xa681  ldloc.s  9
0xa683  callvirt instance int32 [mscorlib]System.Exception::get_HResult()
0xa688  ldloc.s  9
0xa68a  callvirt instance string [mscorlib]System.Exception::get_Message()
0xa68f  newobj   instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.ErrorAction::.ctor(valuetype [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.ErrorActionType, int32, string)
0xa694  ldloc.s  0xA
0xa696  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncRetryResultWithPostponeUntil::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.ErrorAction, valuetype [mscorlib]System.DateTime)
0xa69b  stloc.s  8
0xa69d  leave.s  loc_A6FD
0xa69f  ldarg.0
0xa6a0  ldloc.1
0xa6a1  ldloc.2
0xa6a2  ldloc.s  5
0xa6a4  call     instance void Microsoft.Crm.Asynchronous.AppModuleMetadataOperation::DeleteOperationLog(class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppModuleMetadataOperationLogService appModuleMetadataOperationLogService, valuetype [mscorlib]System.Guid appModuleMetadataOperationLogId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xa6a9  ldloc.s  9
0xa6ab  ldarg.1
0xa6ac  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xa6b1  ldc.i4.s 0x47
0xa6b3  ldstr    aExitingAfterRe// "Exiting after retrying AMM update {0} t"...
0xa6b8  ldc.i4.3
0xa6b9  newarr   [mscorlib]System.Object
0xa6be  dup
0xa6bf  ldc.i4.0
0xa6c0  ldc.i4.3
0xa6c1  box      [mscorlib]System.Int32
0xa6c6  stelem.ref
0xa6c7  dup
0xa6c8  ldc.i4.1
0xa6c9  ldarg.1
0xa6ca  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_Data()
0xa6cf  stelem.ref
0xa6d0  dup
0xa6d1  ldc.i4.2
0xa6d2  ldloc.s  9
0xa6d4  callvirt instance string [mscorlib]System.Exception::get_Message()
0xa6d9  stelem.ref
0xa6da  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xa6df  ldloc.s  5
0xa6e1  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnErrorRequest()
0xa6e6  ldloc.s  9
0xa6e8  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncFailedResult::.ctor(class [mscorlib]System.Exception)
0xa6ed  stloc.s  8
0xa6ef  leave.s  loc_A6FD
0xa6f1  ldloc.s  5
0xa6f3  brfalse.s loc_A6FC
0xa6f5  ldloc.s  5
0xa6f7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa6fc  endfinally
0xa6fd  ldloc.s  8
0xa6ff  ret
```
