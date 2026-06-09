# Microsoft.Crm.Asynchronous.ImportOperation::InternalExecute

- ea: `0xab30`
- end: `0xada5`
- name: `Microsoft.Crm.Asynchronous.ImportOperation::InternalExecute`
- size: `629`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0xab30`
- `0xadc0`
- `0xadf0`
- `0xae20`
- `0xaf70`
- `0xafb0`
- `0xb0e0`
- `0xb9d0`
- `0xba40`

## string_xrefs

- `0xac43`: `An operation on which this operation depends did not complete successfully.`
- `0xad01`: `Exception happened during execution of import = {0} | Details: {1}`

## pseudocode

```c

```

## disassembly

```asm
0xab30  ldarg.1
0xab31  ldnull
0xab32  cgt.un
0xab34  ldstr    aAsyncEventCann// "Async Event cannot be null"
0xab39  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0xab3e  ldarg.1
0xab3f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_RegardingObject()
0xab44  ldstr    aRegardingobjec_1// "regardingObject"
0xab49  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xab4e  ldarg.0
0xab4f  ldarg.1
0xab50  stfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.ImportOperation::_asyncEvent
0xab55  ldarg.0
0xab56  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.ImportOperation::_asyncEvent
0xab5b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_RegardingObject()
0xab60  stloc.0
0xab61  ldarg.0
0xab62  call     instance void Microsoft.Crm.Asynchronous.ImportOperation::InitializeServices()
0xab67  ldarg.0
0xab68  ldarg.0
0xab69  call     instance int32 Microsoft.Crm.Asynchronous.ImportOperation::GetUserLanguage()
0xab6e  stfld    int32 Microsoft.Crm.Asynchronous.ImportOperation::_languageCode
0xab73  ldarg.0
0xab74  ldarg.0
0xab75  call     instance class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Asynchronous.ImportOperation::GetUserLocale()
0xab7a  stfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Asynchronous.ImportOperation::_userCultureInfo
0xab7f  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveRequest::.ctor()
0xab84  stloc.1
0xab85  ldloc.1
0xab86  ldc.i4.2
0xab87  newarr   [mscorlib]System.String
0xab8c  dup
0xab8d  ldc.i4.0
0xab8e  ldstr    aBusinessunitid// "businessunitid"
0xab93  stelem.ref
0xab94  dup
0xab95  ldc.i4.1
0xab96  ldstr    aOrganizationid// "organizationid"
0xab9b  stelem.ref
0xab9c  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(string[])
0xaba1  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveRequest::set_ColumnSet(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet)
0xaba6  ldloc.1
0xaba7  ldstr    aSystemuser// "systemuser"
0xabac  ldarg.0
0xabad  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.ImportOperation::_asyncEvent
0xabb2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_OwnerId()
0xabb7  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0xabbc  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveRequest::set_Target(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference)
0xabc1  ldarg.0
0xabc2  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.ImportOperation::_crmService
0xabc7  ldloc.1
0xabc8  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0xabcd  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveResponse
0xabd2  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveResponse::get_Entity()
0xabd7  stloc.2
0xabd8  ldarg.0
0xabd9  ldloc.2
0xabda  ldstr    aBusinessunitid// "businessunitid"
0xabdf  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0xabe4  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0xabe9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0xabee  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserBusinessUnitId
0xabf3  ldarg.0
0xabf4  ldarg.0
0xabf5  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.ImportOperation::_asyncEvent
0xabfa  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_OwnerId()
0xabff  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserId
0xac04  ldloc.0
0xac05  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmReference::get_Value()
0xac0a  stloc.3
0xac0b  ldnull
0xac0c  stloc.s  4
0xac0e  ldarg.0
0xac0f  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.ImportOperation::_asyncEvent
0xac14  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OperationType()
0xac19  ldc.i4.4
0xac1a  beq.s    loc_AC2A
0xac1c  ldarg.0
0xac1d  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.ImportOperation::_asyncEvent
0xac22  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OperationType()
0xac27  ldc.i4.5
0xac28  bne.un.s loc_AC57
0xac2a  ldarg.0
0xac2b  ldloc.3
0xac2c  ldarg.0
0xac2d  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.ImportOperation::_asyncEvent
0xac32  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OperationType()
0xac37  call     instance bool Microsoft.Crm.Asynchronous.ImportOperation::IsPreviousOperationSuccessful(valuetype [mscorlib]System.Guid importId, int32 operationType)
0xac3c  brtrue.s loc_AC57
0xac3e  ldc.i4   0x80048464
0xac43  ldstr    aAnOperationOnW// "An operation on which this operation de"...
0xac48  ldc.i4.0
0xac49  newarr   [mscorlib]System.Object
0xac4e  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncFailedResult::.ctor(int32, string, object[])
0xac53  stloc.s  4
0xac55  br.s     loc_AC76
0xac57  ldarg.0
0xac58  ldarg.0
0xac59  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.ImportOperation::_asyncEvent
0xac5e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xac63  ldloc.3
0xac64  ldarg.0
0xac65  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.ImportOperation::_asyncEvent
0xac6a  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OperationType()
0xac6f  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerResult Microsoft.Crm.Asynchronous.ImportOperation::ExecuteImportOperation(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid objectId, int32 operationType)
0xac74  stloc.s  4
0xac76  ldloc.s  4
0xac78  isinst   [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncFailedResult
0xac7d  brtrue.s loc_AC88
0xac7f  ldloc.s  4
0xac81  isinst   [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncCanceledResult
0xac86  brfalse.s loc_ACBE
0xac88  ldarg.0
0xac89  ldloc.3
0xac8a  ldc.i4.5
0xac8b  ldc.i4.1
0xac8c  call     instance void Microsoft.Crm.Asynchronous.ImportOperation::SetImportStatus(valuetype [mscorlib]System.Guid importId, int32 importStatus, bool cleanupImportFilesContent)
0xac91  ldarg.1
0xac92  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OperationType()
0xac97  ldc.i4.3
0xac98  beq.s    loc_ACA3
0xac9a  ldarg.1
0xac9b  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OperationType()
0xaca0  ldc.i4.4
0xaca1  bne.un.s loc_ACB5
0xaca3  ldarg.0
0xaca4  ldarg.0
0xaca5  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.ImportOperation::_asyncEvent
0xacaa  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OperationType()
0xacaf  ldloc.3
0xacb0  call     instance void Microsoft.Crm.Asynchronous.ImportOperation::CancelDependentJobs(int32 currentOperationType, valuetype [mscorlib]System.Guid importId)
0xacb5  ldarg.0
0xacb6  ldloc.3
0xacb7  call     instance void Microsoft.Crm.Asynchronous.ImportOperation::DropParsedTablesForImport(valuetype [mscorlib]System.Guid importId)
0xacbc  br.s     loc_ACEB
0xacbe  ldloc.s  4
0xacc0  isinst   [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSucceededResult
0xacc5  brfalse.s loc_ACEB
0xacc7  ldarg.0
0xacc8  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.ImportOperation::_asyncEvent
0xaccd  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OperationType()
0xacd2  ldc.i4.5
0xacd3  beq.s    loc_ACE4
0xacd5  ldarg.0
0xacd6  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.ImportOperation::_asyncEvent
0xacdb  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OperationType()
0xace0  ldc.i4.s 0x26
0xace2  bne.un.s loc_ACEB
0xace4  ldarg.0
0xace5  ldloc.3
0xace6  call     instance void Microsoft.Crm.Asynchronous.ImportOperation::DropParsedTablesForImport(valuetype [mscorlib]System.Guid importId)
0xaceb  leave    loc_AD9F
0xacf0  stloc.s  5
0xacf2  ldloc.s  5
0xacf4  ldarg.0
0xacf5  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.ImportOperation::_asyncEvent
0xacfa  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xacff  ldc.i4.s 0x18
0xad01  ldstr    aExceptionHappe// "Exception happened during execution of "...
0xad06  ldc.i4.2
0xad07  newarr   [mscorlib]System.Object
0xad0c  dup
0xad0d  ldc.i4.0
0xad0e  ldloc.3
0xad0f  box      [mscorlib]System.Guid
0xad14  stelem.ref
0xad15  dup
0xad16  ldc.i4.1
0xad17  ldloc.s  5
0xad19  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0xad1e  stelem.ref
0xad1f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xad24  ldc.i4.0
0xad25  stloc.s  6
0xad27  ldloc.s  5
0xad29  isinst   class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>
0xad2e  stloc.s  7
0xad30  ldloc.s  7
0xad32  brfalse.s loc_AD42
0xad34  ldloc.s  7
0xad36  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0xad3b  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::get_ErrorCode()
0xad40  stloc.s  6
0xad42  ldloc.s  6
0xad44  ldc.i4   0x8004A001
0xad49  beq.s    loc_AD54
0xad4b  ldloc.s  5
0xad4d  isinst   [Microsoft.Crm.Core]Microsoft.Crm.CrmSqlGovernorRequestDeniedException
0xad52  brfalse.s loc_AD56
0xad54  rethrow
0xad56  ldarg.0
0xad57  ldloc.3
0xad58  ldc.i4.5
0xad59  ldc.i4.1
0xad5a  call     instance void Microsoft.Crm.Asynchronous.ImportOperation::SetImportStatus(valuetype [mscorlib]System.Guid importId, int32 importStatus, bool cleanupImportFilesContent)
0xad5f  ldarg.0
0xad60  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.ImportOperation::_asyncEvent
0xad65  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OperationType()
0xad6a  ldc.i4.3
0xad6b  beq.s    loc_AD7B
0xad6d  ldarg.0
0xad6e  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.ImportOperation::_asyncEvent
0xad73  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OperationType()
0xad78  ldc.i4.4
0xad79  bne.un.s loc_AD8D
0xad7b  ldarg.0
0xad7c  ldarg.0
0xad7d  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.ImportOperation::_asyncEvent
0xad82  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OperationType()
0xad87  ldloc.3
0xad88  call     instance void Microsoft.Crm.Asynchronous.ImportOperation::CancelDependentJobs(int32 currentOperationType, valuetype [mscorlib]System.Guid importId)
0xad8d  ldarg.0
0xad8e  ldloc.3
0xad8f  call     instance void Microsoft.Crm.Asynchronous.ImportOperation::DropParsedTablesForImport(valuetype [mscorlib]System.Guid importId)
0xad94  ldloc.s  5
0xad96  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncFailedResult::.ctor(class [mscorlib]System.Exception)
0xad9b  stloc.s  8
0xad9d  leave.s  loc_ADA2
0xad9f  ldloc.s  4
0xada1  ret
0xada2  ldloc.s  8
0xada4  ret
```
