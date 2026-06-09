# Microsoft.Crm.Asynchronous.BulkDeleteOperation::CancelAllChildJobs

- ea: `0x23d0`
- end: `0x2657`
- name: `Microsoft.Crm.Asynchronous.BulkDeleteOperation::CancelAllChildJobs`
- size: `647`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1db0`
- `0x2660`
- `0x1f350`

## callees

- `0x23d0`

## string_xrefs

- `0x24f5`: `Retrieve of BulkDeleteChild Job Failed with exception | {0}`
- `0x2522`: `Retrieve of BulkDeleteChild Job Failed with exception | {0}`
- `0x25f3`: `Cancelling of Bulk Delete Child Job Failed with exception | {0}`
- `0x2620`: `Cancelling of Bulk Delete Child Job Failed with exception | {0}`

## pseudocode

```c

```

## disassembly

```asm
0x23d0  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor()
0x23d5  stloc.0
0x23d6  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor()
0x23db  stloc.1
0x23dc  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor()
0x23e1  stloc.2
0x23e2  ldnull
0x23e3  stloc.3
0x23e4  ldloc.0
0x23e5  ldstr    aOperationtype// "operationtype"
0x23ea  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_AttributeName(string)
0x23ef  ldloc.0
0x23f0  ldc.i4.0
0x23f1  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_Operator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0x23f6  ldloc.0
0x23f7  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<object> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::get_Values()
0x23fc  ldc.i4.s 0x17
0x23fe  box      [mscorlib]System.Int32
0x2403  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<object>::Add(var<u1>)
0x2408  ldloc.1
0x2409  ldstr    aStatecode// "statecode"
0x240e  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_AttributeName(string)
0x2413  ldloc.1
0x2414  ldc.i4.1
0x2415  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_Operator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0x241a  ldloc.1
0x241b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<object> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::get_Values()
0x2420  ldc.i4.3
0x2421  box      [mscorlib]System.Int32
0x2426  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<object>::Add(var<u1>)
0x242b  ldloc.2
0x242c  ldstr    aRequestid// "requestid"
0x2431  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_AttributeName(string)
0x2436  ldloc.2
0x2437  ldc.i4.0
0x2438  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_Operator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0x243d  ldloc.2
0x243e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<object> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::get_Values()
0x2443  ldarg.0
0x2444  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.BulkDeleteOperation::_asyncEvent
0x2449  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_EventId()
0x244e  box      [mscorlib]System.Guid
0x2453  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<object>::Add(var<u1>)
0x2458  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::.ctor()
0x245d  stloc.s  4
0x245f  ldloc.s  4
0x2461  ldc.i4.0
0x2462  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::set_FilterOperator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator)
0x2467  ldloc.s  4
0x2469  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0x246e  ldc.i4.3
0x246f  newarr   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression
0x2474  dup
0x2475  ldc.i4.0
0x2476  ldloc.0
0x2477  stelem.ref
0x2478  dup
0x2479  ldc.i4.1
0x247a  ldloc.1
0x247b  stelem.ref
0x247c  dup
0x247d  ldc.i4.2
0x247e  ldloc.2
0x247f  stelem.ref
0x2480  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::AddRange(var<u1>[])
0x2485  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor()
0x248a  stloc.s  5
0x248c  ldloc.s  5
0x248e  ldstr    aAsyncoperation_0// "asyncoperation"
0x2493  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_EntityName(string)
0x2498  ldloc.s  5
0x249a  ldc.i4.1
0x249b  newarr   [mscorlib]System.String
0x24a0  dup
0x24a1  ldc.i4.0
0x24a2  ldstr    aAsyncoperation_1// "asyncoperationid"
0x24a7  stelem.ref
0x24a8  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(string[])
0x24ad  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_ColumnSet(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet)
0x24b2  ldloc.s  5
0x24b4  ldloc.s  4
0x24b6  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_Criteria(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression)
0x24bb  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleRequest::.ctor()
0x24c0  stloc.s  6
0x24c2  ldloc.s  6
0x24c4  ldloc.s  5
0x24c6  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleRequest::set_Query(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryBase)
0x24cb  ldnull
0x24cc  stloc.s  7
0x24ce  ldarg.0
0x24cf  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.BulkDeleteOperation::_crmService
0x24d4  ldloc.s  6
0x24d6  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x24db  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleResponse
0x24e0  stloc.s  7
0x24e2  leave.s  loc_253E
0x24e4  stloc.s  8
0x24e6  ldloc.s  8
0x24e8  ldarg.0
0x24e9  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.BulkDeleteOperation::_asyncEvent
0x24ee  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x24f3  ldc.i4.s 0x15
0x24f5  ldstr    aRetrieveOfBulk// "Retrieve of BulkDeleteChild Job Failed "...
0x24fa  ldc.i4.1
0x24fb  newarr   [mscorlib]System.Object
0x2500  dup
0x2501  ldc.i4.0
0x2502  ldloc.s  8
0x2504  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x2509  stelem.ref
0x250a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x250f  leave.s  loc_253E
0x2511  stloc.s  9
0x2513  ldloc.s  9
0x2515  ldarg.0
0x2516  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.BulkDeleteOperation::_asyncEvent
0x251b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x2520  ldc.i4.s 0x15
0x2522  ldstr    aRetrieveOfBulk// "Retrieve of BulkDeleteChild Job Failed "...
0x2527  ldc.i4.1
0x2528  newarr   [mscorlib]System.Object
0x252d  dup
0x252e  ldc.i4.0
0x252f  ldloc.s  9
0x2531  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x2536  stelem.ref
0x2537  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x253c  leave.s  loc_253E
0x253e  ldloc.s  7
0x2540  brtrue.s loc_2545
0x2542  ldnull
0x2543  br.s     loc_254C
0x2545  ldloc.s  7
0x2547  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleResponse::get_EntityCollection()
0x254c  stloc.3
0x254d  ldloc.3
0x254e  brfalse  loc_2656
0x2553  ldloc.3
0x2554  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x2559  brfalse  loc_2656
0x255e  ldloc.3
0x255f  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x2564  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Count()
0x2569  ldc.i4.0
0x256a  ble      loc_2656
0x256f  ldloc.3
0x2570  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x2575  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::GetEnumerator()
0x257a  stloc.s  0xA
0x257c  br       loc_263C
0x2581  ldloc.s  0xA
0x2583  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Current()
0x2588  stloc.s  0xB
0x258a  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor()
0x258f  stloc.s  0xC
0x2591  ldloc.s  0xC
0x2593  ldstr    aAsyncoperation_0// "asyncoperation"
0x2598  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_LogicalName(string)
0x259d  ldloc.s  0xC
0x259f  ldloc.s  0xB
0x25a1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x25a6  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Id(valuetype [mscorlib]System.Guid)
0x25ab  ldloc.s  0xC
0x25ad  ldstr    aStatecode// "statecode"
0x25b2  ldc.i4.3
0x25b3  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0x25b8  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x25bd  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.UpdateRequest::.ctor()
0x25c2  stloc.s  0xD
0x25c4  ldloc.s  0xD
0x25c6  ldloc.s  0xC
0x25c8  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.UpdateRequest::set_Target(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0x25cd  ldarg.0
0x25ce  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.BulkDeleteOperation::_crmService
0x25d3  ldloc.s  0xD
0x25d5  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x25da  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.UpdateResponse
0x25df  pop
0x25e0  leave.s  loc_263C
0x25e2  stloc.s  0xE
0x25e4  ldloc.s  0xE
0x25e6  ldarg.0
0x25e7  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.BulkDeleteOperation::_asyncEvent
0x25ec  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x25f1  ldc.i4.s 0x15
0x25f3  ldstr    aCancellingOfBu// "Cancelling of Bulk Delete Child Job Fai"...
0x25f8  ldc.i4.1
0x25f9  newarr   [mscorlib]System.Object
0x25fe  dup
0x25ff  ldc.i4.0
0x2600  ldloc.s  0xE
0x2602  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x2607  stelem.ref
0x2608  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x260d  leave.s  loc_263C
0x260f  stloc.s  0xF
0x2611  ldloc.s  0xF
0x2613  ldarg.0
0x2614  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.BulkDeleteOperation::_asyncEvent
0x2619  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x261e  ldc.i4.s 0x15
0x2620  ldstr    aCancellingOfBu// "Cancelling of Bulk Delete Child Job Fai"...
0x2625  ldc.i4.1
0x2626  newarr   [mscorlib]System.Object
0x262b  dup
0x262c  ldc.i4.0
0x262d  ldloc.s  0xF
0x262f  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x2634  stelem.ref
0x2635  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x263a  leave.s  loc_263C
0x263c  ldloc.s  0xA
0x263e  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2643  brtrue   loc_2581
0x2648  leave.s  loc_2656
0x264a  ldloc.s  0xA
0x264c  brfalse.s loc_2655
0x264e  ldloc.s  0xA
0x2650  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2655  endfinally
0x2656  ret
```
