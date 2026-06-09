# Microsoft.Crm.Asynchronous.BulkDeleteOperation::<ChildJobsHaveNotBeenCreated>b__34_0

- ea: `0x2b30`
- end: `0x2c1b`
- name: `Microsoft.Crm.Asynchronous.BulkDeleteOperation::<ChildJobsHaveNotBeenCreated>b__34_0`
- size: `235`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x2b30`

## pseudocode

```c

```

## disassembly

```asm
0x2b30  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor()
0x2b35  stloc.0
0x2b36  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor()
0x2b3b  stloc.1
0x2b3c  ldloc.0
0x2b3d  ldstr    aOperationtype// "operationtype"
0x2b42  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_AttributeName(string)
0x2b47  ldloc.0
0x2b48  ldc.i4.0
0x2b49  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_Operator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0x2b4e  ldloc.0
0x2b4f  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<object> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::get_Values()
0x2b54  ldc.i4.s 0x17
0x2b56  box      [mscorlib]System.Int32
0x2b5b  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<object>::Add(var<u1>)
0x2b60  ldloc.1
0x2b61  ldstr    aRequestid// "requestid"
0x2b66  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_AttributeName(string)
0x2b6b  ldloc.1
0x2b6c  ldc.i4.0
0x2b6d  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_Operator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0x2b72  ldloc.1
0x2b73  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<object> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::get_Values()
0x2b78  ldarg.0
0x2b79  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.BulkDeleteOperation::_asyncEvent
0x2b7e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_EventId()
0x2b83  box      [mscorlib]System.Guid
0x2b88  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<object>::Add(var<u1>)
0x2b8d  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::.ctor()
0x2b92  stloc.2
0x2b93  ldloc.2
0x2b94  ldc.i4.0
0x2b95  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::set_FilterOperator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator)
0x2b9a  ldloc.2
0x2b9b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0x2ba0  ldc.i4.2
0x2ba1  newarr   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression
0x2ba6  dup
0x2ba7  ldc.i4.0
0x2ba8  ldloc.0
0x2ba9  stelem.ref
0x2baa  dup
0x2bab  ldc.i4.1
0x2bac  ldloc.1
0x2bad  stelem.ref
0x2bae  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::AddRange(var<u1>[])
0x2bb3  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor()
0x2bb8  stloc.3
0x2bb9  ldloc.3
0x2bba  ldstr    aAsyncoperation_0// "asyncoperation"
0x2bbf  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_EntityName(string)
0x2bc4  ldloc.3
0x2bc5  ldc.i4.1
0x2bc6  newarr   [mscorlib]System.String
0x2bcb  dup
0x2bcc  ldc.i4.0
0x2bcd  ldstr    aAsyncoperation_1// "asyncoperationid"
0x2bd2  stelem.ref
0x2bd3  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(string[])
0x2bd8  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_ColumnSet(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet)
0x2bdd  ldloc.3
0x2bde  ldloc.2
0x2bdf  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_Criteria(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression)
0x2be4  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleRequest::.ctor()
0x2be9  stloc.s  4
0x2beb  ldloc.s  4
0x2bed  ldloc.3
0x2bee  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleRequest::set_Query(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryBase)
0x2bf3  ldarg.0
0x2bf4  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.BulkDeleteOperation::_crmService
0x2bf9  ldloc.s  4
0x2bfb  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x2c00  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleResponse
0x2c05  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleResponse::get_EntityCollection()
0x2c0a  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x2c0f  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Count()
0x2c14  ldc.i4.0
0x2c15  ble.s    loc_2C19
0x2c17  ldc.i4.0
0x2c18  ret
0x2c19  ldc.i4.1
0x2c1a  ret
```
