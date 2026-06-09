# Microsoft.Crm.Asynchronous.PublishDuplicateRuleOperation::IsAsyncOperationAlreadyPresent

- ea: `0x1e420`
- end: `0x1e561`
- name: `Microsoft.Crm.Asynchronous.PublishDuplicateRuleOperation::IsAsyncOperationAlreadyPresent`
- size: `321`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1e3f0`

## callees

- `0x1e420`

## string_xrefs

- `0x1e525`: `Error in retrieving recurring system task for {0} entity.`

## pseudocode

```c

```

## disassembly

```asm
0x1e420  ldc.i4.1
0x1e421  newarr   [mscorlib]System.String
0x1e426  dup
0x1e427  ldc.i4.0
0x1e428  ldstr    aAsyncoperation_1// "asyncoperationid"
0x1e42d  stelem.ref
0x1e42e  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(string[])
0x1e433  stloc.0
0x1e434  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor()
0x1e439  stloc.1
0x1e43a  ldloc.1
0x1e43b  ldloc.0
0x1e43c  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_ColumnSet(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet)
0x1e441  ldloc.1
0x1e442  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x1e447  ldstr    aPrimaryentityt// "primaryentitytype"
0x1e44c  ldc.i4.0
0x1e44d  ldc.i4.1
0x1e44e  newarr   [mscorlib]System.Object
0x1e453  dup
0x1e454  ldc.i4.0
0x1e455  ldarg.2
0x1e456  box      [mscorlib]System.Int32
0x1e45b  stelem.ref
0x1e45c  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object[])
0x1e461  ldloc.1
0x1e462  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x1e467  ldstr    aOperationtype// "operationtype"
0x1e46c  ldc.i4.0
0x1e46d  ldc.i4.1
0x1e46e  newarr   [mscorlib]System.Object
0x1e473  dup
0x1e474  ldc.i4.0
0x1e475  ldc.i4.s 0xC
0x1e477  box      [mscorlib]System.Int32
0x1e47c  stelem.ref
0x1e47d  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object[])
0x1e482  ldloc.1
0x1e483  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x1e488  ldstr    aRecurrencepatt// "recurrencepattern"
0x1e48d  ldc.i4.s 0xD
0x1e48f  ldc.i4.0
0x1e490  newarr   [mscorlib]System.Object
0x1e495  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object[])
0x1e49a  ldloc.1
0x1e49b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x1e4a0  ldstr    aRecurrencestar// "recurrencestarttime"
0x1e4a5  ldc.i4.s 0xD
0x1e4a7  ldc.i4.0
0x1e4a8  newarr   [mscorlib]System.Object
0x1e4ad  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object[])
0x1e4b2  ldloc.1
0x1e4b3  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x1e4b8  ldstr    aStatecode// "statecode"
0x1e4bd  ldc.i4.8
0x1e4be  ldc.i4.3
0x1e4bf  newarr   [mscorlib]System.Object
0x1e4c4  dup
0x1e4c5  ldc.i4.0
0x1e4c6  ldc.i4.0
0x1e4c7  box      [mscorlib]System.Int32
0x1e4cc  stelem.ref
0x1e4cd  dup
0x1e4ce  ldc.i4.1
0x1e4cf  ldc.i4.1
0x1e4d0  box      [mscorlib]System.Int32
0x1e4d5  stelem.ref
0x1e4d6  dup
0x1e4d7  ldc.i4.2
0x1e4d8  ldc.i4.2
0x1e4d9  box      [mscorlib]System.Int32
0x1e4de  stelem.ref
0x1e4df  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object[])
0x1e4e4  ldloc.1
0x1e4e5  ldstr    aAsyncoperation_0// "asyncoperation"
0x1e4ea  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_EntityName(string)
0x1e4ef  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleRequest::.ctor()
0x1e4f4  stloc.2
0x1e4f5  ldloc.2
0x1e4f6  ldloc.1
0x1e4f7  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleRequest::set_Query(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryBase)
0x1e4fc  ldarg.3
0x1e4fd  ldloc.2
0x1e4fe  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x1e503  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleResponse
0x1e508  stloc.3
0x1e509  ldloc.3
0x1e50a  brfalse.s loc_1E521
0x1e50c  ldloc.3
0x1e50d  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleResponse::get_EntityCollection()
0x1e512  brfalse.s loc_1E521
0x1e514  ldloc.3
0x1e515  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleResponse::get_EntityCollection()
0x1e51a  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x1e51f  brtrue.s loc_1E54A
0x1e521  ldnull
0x1e522  ldarg.0
0x1e523  ldc.i4.s 0x15
0x1e525  ldstr    aErrorInRetriev_1// "Error in retrieving recurring system ta"...
0x1e52a  ldc.i4.1
0x1e52b  newarr   [mscorlib]System.Object
0x1e530  dup
0x1e531  ldc.i4.0
0x1e532  ldarg.1
0x1e533  stelem.ref
0x1e534  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1e539  ldc.i4   0x80040216
0x1e53e  ldc.i4.0
0x1e53f  newarr   [mscorlib]System.Object
0x1e544  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x1e549  throw
0x1e54a  ldloc.3
0x1e54b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleResponse::get_EntityCollection()
0x1e550  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x1e555  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Count()
0x1e55a  ldc.i4.0
0x1e55b  ble.s    loc_1E55F
0x1e55d  ldc.i4.1
0x1e55e  ret
0x1e55f  ldc.i4.0
0x1e560  ret
```
