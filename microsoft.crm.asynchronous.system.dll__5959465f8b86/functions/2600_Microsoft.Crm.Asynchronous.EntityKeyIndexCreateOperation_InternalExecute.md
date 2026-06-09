# Microsoft.Crm.Asynchronous.EntityKeyIndexCreateOperation::InternalExecute

- ea: `0x2600`
- end: `0x2779`
- name: `Microsoft.Crm.Asynchronous.EntityKeyIndexCreateOperation::InternalExecute`
- size: `377`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x2600`
- `0x2780`
- `0x28c0`
- `0x29c0`

## string_xrefs

- `0x2657`: `Operation type must be 'EntityKeyIndexCreate'`

## pseudocode

```c

```

## disassembly

```asm
0x2600  ldarg.1
0x2601  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_Data()
0x2606  brtrue.s loc_264D
0x2608  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x260d  ldstr    aDataEntitykeyi// "Data(entityKeyId) is null for EntityKey"...
0x2612  ldc.i4.1
0x2613  newarr   [mscorlib]System.Object
0x2618  dup
0x2619  ldc.i4.0
0x261a  ldarg.1
0x261b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_EventId()
0x2620  box      [mscorlib]System.Guid
0x2625  stelem.ref
0x2626  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x262b  stloc.1
0x262c  ldnull
0x262d  ldarg.1
0x262e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x2633  ldc.i4.s 0x15
0x2635  ldloc.1
0x2636  ldc.i4.0
0x2637  newarr   [mscorlib]System.Object
0x263c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2641  ldloc.1
0x2642  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentNullException::.ctor(string)
0x2647  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncFailedResult::.ctor(class [mscorlib]System.Exception)
0x264c  ret
0x264d  ldarg.1
0x264e  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OperationType()
0x2653  ldc.i4.s 0x3F
0x2655  ceq
0x2657  ldstr    aOperationTypeM_8// "Operation type must be 'EntityKeyIndexC"...
0x265c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x2661  ldarg.0
0x2662  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0x2667  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x266c  stloc.0
0x266d  ldloc.0
0x266e  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::GetInstallConnectionTimeout()
0x2673  ldc.i4.0
0x2674  ldc.i4.0
0x2675  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, int32, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x267a  ldloc.0
0x267b  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection, valuetype [mscorlib]System.Guid)
0x2680  stloc.2
0x2681  ldloc.2
0x2682  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x2687  castclass [Microsoft.Crm.Core]Microsoft.Crm.SqlExecutionContext
0x268c  ldc.i4.0
0x268d  ldc.i4.0
0x268e  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::ActiveSolutionId
0x2693  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SqlExecutionContext::OnBeginRequest(bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.SolutionOperationContext, valuetype [mscorlib]System.Guid)
0x2698  ldarg.0
0x2699  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x269e  dup
0x269f  ldstr    aEntitykeyindex// "EntityKeyIndexStatus"
0x26a4  ldc.i4.1
0x26a5  box      [mscorlib]System.Int32
0x26aa  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x26af  ldarg.1
0x26b0  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_Data()
0x26b5  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x26ba  ldloc.2
0x26bb  call     instance void Microsoft.Crm.Asynchronous.EntityKeyIndexCreateOperation::UpdateEntityKey(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> columnValues, valuetype [mscorlib]System.Guid entityKeyId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x26c0  ldarg.0
0x26c1  ldarg.1
0x26c2  ldloc.2
0x26c3  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.EntityKeyIndexCreateOperation::CreateEntityKeyIndex(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent asyncEvent, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x26c8  stloc.3
0x26c9  ldarg.0
0x26ca  ldloc.3
0x26cb  ldarg.1
0x26cc  ldloc.2
0x26cd  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerResult Microsoft.Crm.Asynchronous.EntityKeyIndexCreateOperation::HasJobBeenAbortedOrPaused(valuetype [mscorlib]System.Guid indexId, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent asyncEvent, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x26d2  ldloc.2
0x26d3  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnEndRequest()
0x26d8  stloc.s  4
0x26da  leave    loc_2776
0x26df  stloc.s  5
0x26e1  ldarg.0
0x26e2  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x26e7  dup
0x26e8  ldstr    aEntitykeyindex// "EntityKeyIndexStatus"
0x26ed  ldc.i4.3
0x26ee  box      [mscorlib]System.Int32
0x26f3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x26f8  ldarg.1
0x26f9  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_Data()
0x26fe  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x2703  ldloc.2
0x2704  call     instance void Microsoft.Crm.Asynchronous.EntityKeyIndexCreateOperation::UpdateEntityKey(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> columnValues, valuetype [mscorlib]System.Guid entityKeyId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x2709  ldloc.2
0x270a  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnErrorRequest()
0x270f  ldloc.s  5
0x2711  isinst   [System.Data]System.Data.SqlClient.SqlException
0x2716  stloc.s  6
0x2718  ldloc.s  6
0x271a  brfalse.s loc_2751
0x271c  ldloc.s  6
0x271e  callvirt instance int32 [mscorlib]System.Runtime.InteropServices.ExternalException::get_ErrorCode()
0x2723  ldloc.s  6
0x2725  callvirt instance class [System.Data]System.Data.SqlClient.SqlErrorCollection [System.Data]System.Data.SqlClient.SqlException::get_Errors()
0x272a  ldloc.s  6
0x272c  callvirt instance class [System.Data]System.Data.SqlClient.SqlErrorCollection [System.Data]System.Data.SqlClient.SqlException::get_Errors()
0x2731  callvirt instance int32 [System.Data]System.Data.SqlClient.SqlErrorCollection::get_Count()
0x2736  ldc.i4.1
0x2737  sub
0x2738  callvirt instance class [System.Data]System.Data.SqlClient.SqlError [System.Data]System.Data.SqlClient.SqlErrorCollection::get_Item(int32)
0x273d  callvirt instance string [System.Data]System.Data.SqlClient.SqlError::get_Message()
0x2742  ldc.i4.0
0x2743  newarr   [mscorlib]System.Object
0x2748  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncFailedResult::.ctor(int32, string, object[])
0x274d  stloc.s  4
0x274f  leave.s  loc_2776
0x2751  ldc.i4   0x8004023B
0x2756  ldloc.s  5
0x2758  callvirt instance string [mscorlib]System.Exception::get_Message()
0x275d  ldc.i4.0
0x275e  newarr   [mscorlib]System.Object
0x2763  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncFailedResult::.ctor(int32, string, object[])
0x2768  stloc.s  4
0x276a  leave.s  loc_2776
0x276c  ldloc.2
0x276d  brfalse.s loc_2775
0x276f  ldloc.2
0x2770  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2775  endfinally
0x2776  ldloc.s  4
0x2778  ret
```
