# Microsoft.Crm.Asynchronous.UpdateKnowledgeArticleStatesOperation::InternalExecute

- ea: `0xa7b0`
- end: `0xa983`
- name: `Microsoft.Crm.Asynchronous.UpdateKnowledgeArticleStatesOperation::InternalExecute`
- size: `467`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0xa7b0`
- `0xa990`
- `0xac60`
- `0xaec0`
- `0xb140`
- `0xb160`

## string_xrefs

- `0xa7ba`: `Operation type must be 'UpdateKnowledgeArticleStates'`
- `0xa804`: `Async Handler for Update Knowledge Article States Operation encountered some errors, see log for more detail.`
- `0xa93e`: `AsyncHandler::UpdateKnowledgeArticleStatesOperation could not complete because of exception {0}`

## pseudocode

```c

```

## disassembly

```asm
0xa7b0  ldarg.1
0xa7b1  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OperationType()
0xa7b6  ldc.i4.s 0x41
0xa7b8  ceq
0xa7ba  ldstr    aOperationTypeM_7// "Operation type must be 'UpdateKnowledge"...
0xa7bf  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0xa7c4  ldarg.0
0xa7c5  ldarg.1
0xa7c6  stfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.UpdateKnowledgeArticleStatesOperation::_asyncEvent
0xa7cb  ldarg.0
0xa7cc  ldarg.1
0xa7cd  ldc.i4.0
0xa7ce  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService [Microsoft.Crm.Asynchronous.HandlerUtility]Microsoft.Crm.Asynchronous.SdkServiceFactory::CreateInstance(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent, bool)
0xa7d3  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.UpdateKnowledgeArticleStatesOperation::_sdkService
0xa7d8  ldarg.0
0xa7d9  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xa7de  stfld    valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.UpdateKnowledgeArticleStatesOperation::_now
0xa7e3  ldarg.0
0xa7e4  ldc.i4.0
0xa7e5  stfld    bool Microsoft.Crm.Asynchronous.UpdateKnowledgeArticleStatesOperation::_errorOccured
0xa7ea  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSucceededResult::.ctor()
0xa7ef  stloc.0
0xa7f0  ldarg.0
0xa7f1  call     instance void Microsoft.Crm.Asynchronous.UpdateKnowledgeArticleStatesOperation::ExpireKnowledgeArticles()
0xa7f6  ldarg.0
0xa7f7  call     instance void Microsoft.Crm.Asynchronous.UpdateKnowledgeArticleStatesOperation::PublishKnowledgeArticles()
0xa7fc  ldarg.0
0xa7fd  ldfld    bool Microsoft.Crm.Asynchronous.UpdateKnowledgeArticleStatesOperation::_errorOccured
0xa802  brfalse.s loc_A80F
0xa804  ldstr    aAsyncHandlerFo_2// "Async Handler for Update Knowledge Arti"...
0xa809  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0xa80e  throw
0xa80f  ldarg.0
0xa810  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.UpdateKnowledgeArticleStatesOperation::_config
0xa815  newobj   instance void Microsoft.Crm.Asynchronous.UpdateKnowledgeArticleStateDataAccess::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration config)
0xa81a  stloc.1
0xa81b  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MaxValue
0xa820  call     class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::FromUniversal(valuetype [mscorlib]System.DateTime)
0xa825  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_UniversalTime()
0xa82a  stloc.2
0xa82b  ldloc.1
0xa82c  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.UpdateKnowledgeArticleStatesOperation::_updateKnowledgeArticleStatesId
0xa831  ldloc.2
0xa832  ldc.i4.1
0xa833  callvirt instance void Microsoft.Crm.Asynchronous.UpdateKnowledgeArticleStateDataAccess::PostponeOrPreponeUpdateKnowledgeArticleStatesJob(valuetype [mscorlib]System.Guid jobId, valuetype [mscorlib]System.DateTime postPoneUntil, [opt] bool unconditionalUpdate)
0xa838  ldarg.0
0xa839  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime Microsoft.Crm.Asynchronous.UpdateKnowledgeArticleStatesOperation::GetNextArticleProcessingTime()
0xa83e  stloc.3
0xa83f  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xa844  stloc.s  6
0xa846  ldloca.s 6
0xa848  ldc.r8   5.0
0xa851  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMinutes(float64)
0xa856  stloc.s  4
0xa858  ldloc.3
0xa859  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_UniversalTime()
0xa85e  ldloc.s  4
0xa860  call     bool [mscorlib]System.DateTime::op_GreaterThanOrEqual(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0xa865  brtrue.s loc_A870
0xa867  ldloc.s  4
0xa869  call     class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::FromUniversal(valuetype [mscorlib]System.DateTime)
0xa86e  br.s     loc_A871
0xa870  ldloc.3
0xa871  stloc.s  5
0xa873  ldloc.s  5
0xa875  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_UniversalTime()
0xa87a  ldloc.2
0xa87b  call     bool [mscorlib]System.DateTime::op_Inequality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0xa880  brfalse.s loc_A895
0xa882  ldloc.1
0xa883  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.UpdateKnowledgeArticleStatesOperation::_updateKnowledgeArticleStatesId
0xa888  ldloc.s  5
0xa88a  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_UniversalTime()
0xa88f  ldc.i4.0
0xa890  callvirt instance void Microsoft.Crm.Asynchronous.UpdateKnowledgeArticleStateDataAccess::PostponeOrPreponeUpdateKnowledgeArticleStatesJob(valuetype [mscorlib]System.Guid jobId, valuetype [mscorlib]System.DateTime postPoneUntil, [opt] bool unconditionalUpdate)
0xa895  leave    loc_A95A
0xa89a  stloc.s  7
0xa89c  ldarg.0
0xa89d  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.UpdateKnowledgeArticleStatesOperation::_asyncEvent
0xa8a2  callvirt instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_OrganizationConfiguration()
0xa8a7  stloc.s  8
0xa8a9  ldstr    aMscrmplatform// "MSCRMPlatform"
0xa8ae  ldc.i4   0xC0004410
0xa8b3  conv.u8
0xa8b4  ldc.i4.6
0xa8b5  newarr   [mscorlib]System.String
0xa8ba  dup
0xa8bb  ldc.i4.0
0xa8bc  call     string [mscorlib]System.Environment::get_MachineName()
0xa8c1  stelem.ref
0xa8c2  dup
0xa8c3  ldc.i4.1
0xa8c4  ldarg.0
0xa8c5  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.UpdateKnowledgeArticleStatesOperation::_asyncEvent
0xa8ca  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OperationType()
0xa8cf  stloc.s  9
0xa8d1  ldloca.s 9
0xa8d3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa8d8  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xa8dd  stelem.ref
0xa8de  dup
0xa8df  ldc.i4.2
0xa8e0  ldarg.0
0xa8e1  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.UpdateKnowledgeArticleStatesOperation::_asyncEvent
0xa8e6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xa8eb  stloc.s  0xA
0xa8ed  ldloca.s 0xA
0xa8ef  constrained. [mscorlib]System.Guid
0xa8f5  callvirt instance string [mscorlib]System.Object::ToString()
0xa8fa  stelem.ref
0xa8fb  dup
0xa8fc  ldc.i4.3
0xa8fd  ldloc.s  8
0xa8ff  callvirt instance string [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationName()
0xa904  stelem.ref
0xa905  dup
0xa906  ldc.i4.4
0xa907  ldc.i4   0x80040216
0xa90c  stloc.s  9
0xa90e  ldloca.s 9
0xa910  ldstr    aX// "x"
0xa915  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa91a  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0xa91f  stelem.ref
0xa920  dup
0xa921  ldc.i4.5
0xa922  ldloc.s  7
0xa924  callvirt instance string [mscorlib]System.Exception::get_Message()
0xa929  stelem.ref
0xa92a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::WriteEventError(string, int64, string[])
0xa92f  ldloc.s  7
0xa931  ldarg.0
0xa932  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.UpdateKnowledgeArticleStatesOperation::_asyncEvent
0xa937  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xa93c  ldc.i4.s 0x15
0xa93e  ldstr    aAsynchandlerUp// "AsyncHandler::UpdateKnowledgeArticleSta"...
0xa943  ldc.i4.1
0xa944  newarr   [mscorlib]System.Object
0xa949  dup
0xa94a  ldc.i4.0
0xa94b  ldloc.s  7
0xa94d  callvirt instance string [mscorlib]System.Exception::get_Message()
0xa952  stelem.ref
0xa953  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xa958  rethrow
0xa95a  ldarg.0
0xa95b  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.UpdateKnowledgeArticleStatesOperation::_asyncEvent
0xa960  callvirt instance valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerEarlyExitRequest [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::QueryForEarlyExitRequest()
0xa965  stloc.s  0xB
0xa967  ldloc.s  0xB
0xa969  ldc.i4.1
0xa96a  beq.s    loc_A973
0xa96c  ldloc.s  0xB
0xa96e  ldc.i4.2
0xa96f  beq.s    loc_A97B
0xa971  br.s     loc_A981
0xa973  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncPausedResult::.ctor()
0xa978  stloc.0
0xa979  br.s     loc_A981
0xa97b  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncCanceledResult::.ctor()
0xa980  stloc.0
0xa981  ldloc.0
0xa982  ret
```
