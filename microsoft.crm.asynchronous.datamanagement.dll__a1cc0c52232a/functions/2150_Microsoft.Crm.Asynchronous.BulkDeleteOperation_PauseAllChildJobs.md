# Microsoft.Crm.Asynchronous.BulkDeleteOperation::PauseAllChildJobs

- ea: `0x2150`
- end: `0x23cc`
- name: `Microsoft.Crm.Asynchronous.BulkDeleteOperation::PauseAllChildJobs`
- size: `636`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1ba0`
- `0x1db0`
- `0x2660`

## callees

- `0x2150`

## string_xrefs

- `0x2368`: `Pausing of BulkDeleteChild Job Failed with exception | {0}`
- `0x2395`: `Pausing of BulkDeleteChild Job Failed with exception | {0}`

## pseudocode

```c

```

## disassembly

```asm
0x2150  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor()
0x2155  stloc.0
0x2156  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor()
0x215b  stloc.1
0x215c  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor()
0x2161  stloc.2
0x2162  ldloc.0
0x2163  ldstr    aOperationtype// "operationtype"
0x2168  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_AttributeName(string)
0x216d  ldloc.0
0x216e  ldc.i4.0
0x216f  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_Operator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0x2174  ldloc.0
0x2175  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<object> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::get_Values()
0x217a  ldc.i4.s 0x17
0x217c  box      [mscorlib]System.Int32
0x2181  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<object>::Add(var<u1>)
0x2186  ldloc.1
0x2187  ldstr    aStatecode// "statecode"
0x218c  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_AttributeName(string)
0x2191  ldloc.1
0x2192  ldc.i4.1
0x2193  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_Operator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0x2198  ldloc.1
0x2199  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<object> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::get_Values()
0x219e  ldc.i4.3
0x219f  box      [mscorlib]System.Int32
0x21a4  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<object>::Add(var<u1>)
0x21a9  ldloc.2
0x21aa  ldstr    aRequestid// "requestid"
0x21af  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_AttributeName(string)
0x21b4  ldloc.2
0x21b5  ldc.i4.0
0x21b6  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_Operator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0x21bb  ldloc.2
0x21bc  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<object> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::get_Values()
0x21c1  ldarg.0
0x21c2  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.BulkDeleteOperation::_asyncEvent
0x21c7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_EventId()
0x21cc  box      [mscorlib]System.Guid
0x21d1  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<object>::Add(var<u1>)
0x21d6  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::.ctor()
0x21db  stloc.3
0x21dc  ldloc.3
0x21dd  ldc.i4.0
0x21de  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::set_FilterOperator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator)
0x21e3  ldloc.3
0x21e4  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0x21e9  ldc.i4.3
0x21ea  newarr   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression
0x21ef  dup
0x21f0  ldc.i4.0
0x21f1  ldloc.0
0x21f2  stelem.ref
0x21f3  dup
0x21f4  ldc.i4.1
0x21f5  ldloc.1
0x21f6  stelem.ref
0x21f7  dup
0x21f8  ldc.i4.2
0x21f9  ldloc.2
0x21fa  stelem.ref
0x21fb  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::AddRange(var<u1>[])
0x2200  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor()
0x2205  stloc.s  4
0x2207  ldloc.s  4
0x2209  ldstr    aAsyncoperation_0// "asyncoperation"
0x220e  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_EntityName(string)
0x2213  ldloc.s  4
0x2215  ldc.i4.3
0x2216  newarr   [mscorlib]System.String
0x221b  dup
0x221c  ldc.i4.0
0x221d  ldstr    aAsyncoperation_1// "asyncoperationid"
0x2222  stelem.ref
0x2223  dup
0x2224  ldc.i4.1
0x2225  ldstr    aStatecode// "statecode"
0x222a  stelem.ref
0x222b  dup
0x222c  ldc.i4.2
0x222d  ldstr    aStatuscode// "statuscode"
0x2232  stelem.ref
0x2233  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(string[])
0x2238  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_ColumnSet(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet)
0x223d  ldloc.s  4
0x223f  ldloc.3
0x2240  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_Criteria(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression)
0x2245  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleRequest::.ctor()
0x224a  stloc.s  5
0x224c  ldloc.s  5
0x224e  ldloc.s  4
0x2250  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleRequest::set_Query(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryBase)
0x2255  ldarg.0
0x2256  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.BulkDeleteOperation::_crmService
0x225b  ldloc.s  5
0x225d  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x2262  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleResponse
0x2267  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleResponse::get_EntityCollection()
0x226c  stloc.s  6
0x226e  ldloc.s  6
0x2270  brfalse  loc_23CB
0x2275  ldloc.s  6
0x2277  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x227c  brfalse  loc_23CB
0x2281  ldloc.s  6
0x2283  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x2288  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Count()
0x228d  ldc.i4.0
0x228e  ble      loc_23CB
0x2293  ldloc.s  6
0x2295  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x229a  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::GetEnumerator()
0x229f  stloc.s  7
0x22a1  br       loc_23B1
0x22a6  ldloc.s  7
0x22a8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Current()
0x22ad  stloc.s  8
0x22af  ldloc.s  8
0x22b1  ldstr    aStatuscode// "statuscode"
0x22b6  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x22bb  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0x22c0  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0x22c5  stloc.s  9
0x22c7  ldloc.s  8
0x22c9  ldstr    aStatecode// "statecode"
0x22ce  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x22d3  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0x22d8  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0x22dd  ldc.i4.1
0x22de  beq.s    loc_2355
0x22e0  ldloc.s  9
0x22e2  ldc.i4.s 0x15
0x22e4  beq.s    loc_2355
0x22e6  ldloc.s  9
0x22e8  ldc.i4.s 0x16
0x22ea  beq.s    loc_2355
0x22ec  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor()
0x22f1  stloc.s  0xA
0x22f3  ldloc.s  0xA
0x22f5  ldstr    aAsyncoperation_0// "asyncoperation"
0x22fa  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_LogicalName(string)
0x22ff  ldloc.s  0xA
0x2301  ldloc.s  8
0x2303  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x2308  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Id(valuetype [mscorlib]System.Guid)
0x230d  ldloc.s  0xA
0x230f  ldstr    aStatecode// "statecode"
0x2314  ldc.i4.1
0x2315  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0x231a  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x231f  ldloc.s  0xA
0x2321  ldstr    aStatuscode// "statuscode"
0x2326  ldc.i4.s 0xA
0x2328  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0x232d  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x2332  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.UpdateRequest::.ctor()
0x2337  stloc.s  0xB
0x2339  ldloc.s  0xB
0x233b  ldloc.s  0xA
0x233d  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.UpdateRequest::set_Target(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0x2342  ldarg.0
0x2343  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.BulkDeleteOperation::_crmService
0x2348  ldloc.s  0xB
0x234a  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x234f  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.UpdateResponse
0x2354  pop
0x2355  leave.s  loc_23B1
0x2357  stloc.s  0xC
0x2359  ldloc.s  0xC
0x235b  ldarg.0
0x235c  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.BulkDeleteOperation::_asyncEvent
0x2361  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x2366  ldc.i4.s 0x15
0x2368  ldstr    aPausingOfBulkd// "Pausing of BulkDeleteChild Job Failed w"...
0x236d  ldc.i4.1
0x236e  newarr   [mscorlib]System.Object
0x2373  dup
0x2374  ldc.i4.0
0x2375  ldloc.s  0xC
0x2377  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x237c  stelem.ref
0x237d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2382  leave.s  loc_23B1
0x2384  stloc.s  0xD
0x2386  ldloc.s  0xD
0x2388  ldarg.0
0x2389  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.BulkDeleteOperation::_asyncEvent
0x238e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x2393  ldc.i4.s 0x15
0x2395  ldstr    aPausingOfBulkd// "Pausing of BulkDeleteChild Job Failed w"...
0x239a  ldc.i4.1
0x239b  newarr   [mscorlib]System.Object
0x23a0  dup
0x23a1  ldc.i4.0
0x23a2  ldloc.s  0xD
0x23a4  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x23a9  stelem.ref
0x23aa  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x23af  leave.s  loc_23B1
0x23b1  ldloc.s  7
0x23b3  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x23b8  brtrue   loc_22A6
0x23bd  leave.s  loc_23CB
0x23bf  ldloc.s  7
0x23c1  brfalse.s loc_23CA
0x23c3  ldloc.s  7
0x23c5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x23ca  endfinally
0x23cb  ret
```
