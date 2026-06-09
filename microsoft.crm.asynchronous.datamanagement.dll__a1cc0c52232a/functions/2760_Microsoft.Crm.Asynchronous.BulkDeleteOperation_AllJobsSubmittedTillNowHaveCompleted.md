# Microsoft.Crm.Asynchronous.BulkDeleteOperation::AllJobsSubmittedTillNowHaveCompleted

- ea: `0x2760`
- end: `0x2926`
- name: `Microsoft.Crm.Asynchronous.BulkDeleteOperation::AllJobsSubmittedTillNowHaveCompleted`
- size: `454`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x2660`
- `0x1f350`

## callees

- `0x2760`

## pseudocode

```c

```

## disassembly

```asm
0x2760  ldarg.0
0x2761  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Asynchronous.BulkDeleteOperation::_pausedJobs
0x2766  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Clear()
0x276b  ldarg.0
0x276c  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Asynchronous.BulkDeleteOperation::_failedJobs
0x2771  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Clear()
0x2776  ldarg.0
0x2777  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Asynchronous.BulkDeleteOperation::_cancelledJobs
0x277c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Clear()
0x2781  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor()
0x2786  stloc.0
0x2787  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor()
0x278c  stloc.1
0x278d  ldloc.0
0x278e  ldstr    aRequestid// "requestid"
0x2793  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_AttributeName(string)
0x2798  ldloc.0
0x2799  ldc.i4.0
0x279a  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_Operator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0x279f  ldloc.0
0x27a0  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<object> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::get_Values()
0x27a5  ldarg.0
0x27a6  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.BulkDeleteOperation::_asyncEvent
0x27ab  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_EventId()
0x27b0  box      [mscorlib]System.Guid
0x27b5  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<object>::Add(var<u1>)
0x27ba  ldloc.1
0x27bb  ldstr    aOperationtype// "operationtype"
0x27c0  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_AttributeName(string)
0x27c5  ldloc.1
0x27c6  ldc.i4.0
0x27c7  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_Operator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0x27cc  ldloc.1
0x27cd  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<object> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::get_Values()
0x27d2  ldc.i4.s 0x17
0x27d4  box      [mscorlib]System.Int32
0x27d9  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<object>::Add(var<u1>)
0x27de  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::.ctor()
0x27e3  stloc.2
0x27e4  ldloc.2
0x27e5  ldc.i4.0
0x27e6  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::set_FilterOperator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator)
0x27eb  ldloc.2
0x27ec  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0x27f1  ldc.i4.2
0x27f2  newarr   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression
0x27f7  dup
0x27f8  ldc.i4.0
0x27f9  ldloc.0
0x27fa  stelem.ref
0x27fb  dup
0x27fc  ldc.i4.1
0x27fd  ldloc.1
0x27fe  stelem.ref
0x27ff  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::AddRange(var<u1>[])
0x2804  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor()
0x2809  stloc.3
0x280a  ldloc.3
0x280b  ldstr    aAsyncoperation_0// "asyncoperation"
0x2810  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_EntityName(string)
0x2815  ldloc.3
0x2816  ldc.i4.3
0x2817  newarr   [mscorlib]System.String
0x281c  dup
0x281d  ldc.i4.0
0x281e  ldstr    aAsyncoperation_1// "asyncoperationid"
0x2823  stelem.ref
0x2824  dup
0x2825  ldc.i4.1
0x2826  ldstr    aStatecode// "statecode"
0x282b  stelem.ref
0x282c  dup
0x282d  ldc.i4.2
0x282e  ldstr    aStatuscode// "statuscode"
0x2833  stelem.ref
0x2834  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(string[])
0x2839  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_ColumnSet(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet)
0x283e  ldloc.3
0x283f  ldloc.2
0x2840  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_Criteria(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression)
0x2845  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleRequest::.ctor()
0x284a  stloc.s  4
0x284c  ldloc.s  4
0x284e  ldloc.3
0x284f  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleRequest::set_Query(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryBase)
0x2854  ldarg.0
0x2855  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.BulkDeleteOperation::_crmService
0x285a  ldloc.s  4
0x285c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x2861  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleResponse
0x2866  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleResponse::get_EntityCollection()
0x286b  ldc.i4.0
0x286c  stloc.s  5
0x286e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x2873  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::GetEnumerator()
0x2878  stloc.s  6
0x287a  br       loc_2903
0x287f  ldloc.s  6
0x2881  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Current()
0x2886  dup
0x2887  ldstr    aStatuscode// "statuscode"
0x288c  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x2891  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0x2896  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0x289b  stloc.s  7
0x289d  dup
0x289e  ldstr    aStatecode// "statecode"
0x28a3  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x28a8  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0x28ad  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0x28b2  stloc.s  8
0x28b4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x28b9  stloc.s  9
0x28bb  ldloc.s  8
0x28bd  ldc.i4.3
0x28be  bne.un.s loc_28EA
0x28c0  ldloc.s  7
0x28c2  ldc.i4.s 0x20
0x28c4  bne.un.s loc_28D5
0x28c6  ldarg.0
0x28c7  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Asynchronous.BulkDeleteOperation::_cancelledJobs
0x28cc  ldloc.s  9
0x28ce  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x28d3  br.s     loc_2903
0x28d5  ldloc.s  7
0x28d7  ldc.i4.s 0x1F
0x28d9  bne.un.s loc_2903
0x28db  ldarg.0
0x28dc  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Asynchronous.BulkDeleteOperation::_failedJobs
0x28e1  ldloc.s  9
0x28e3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x28e8  br.s     loc_2903
0x28ea  ldloc.s  5
0x28ec  ldc.i4.1
0x28ed  add
0x28ee  stloc.s  5
0x28f0  ldloc.s  7
0x28f2  ldc.i4.s 0xA
0x28f4  bne.un.s loc_2903
0x28f6  ldarg.0
0x28f7  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Asynchronous.BulkDeleteOperation::_pausedJobs
0x28fc  ldloc.s  9
0x28fe  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x2903  ldloc.s  6
0x2905  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x290a  brtrue   loc_287F
0x290f  leave.s  loc_291D
0x2911  ldloc.s  6
0x2913  brfalse.s loc_291C
0x2915  ldloc.s  6
0x2917  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x291c  endfinally
0x291d  ldloc.s  5
0x291f  ldc.i4.0
0x2920  ble.s    loc_2924
0x2922  ldc.i4.0
0x2923  ret
0x2924  ldc.i4.1
0x2925  ret
```
