# Microsoft.Crm.Asynchronous.ImportOperation::RetrieveNotCompletedImportFiles

- ea: `0xb8d0`
- end: `0xb9cb`
- name: `Microsoft.Crm.Asynchronous.ImportOperation::RetrieveNotCompletedImportFiles`
- size: `251`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0xb850`

## pseudocode

```c

```

## disassembly

```asm
0xb8d0  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor()
0xb8d5  stloc.0
0xb8d6  ldloc.0
0xb8d7  ldstr    aImportid_1// "importid"
0xb8dc  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_AttributeName(string)
0xb8e1  ldloc.0
0xb8e2  ldc.i4.0
0xb8e3  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_Operator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0xb8e8  ldloc.0
0xb8e9  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<object> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::get_Values()
0xb8ee  ldarg.1
0xb8ef  box      [mscorlib]System.Guid
0xb8f4  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<object>::Add(var<u1>)
0xb8f9  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor()
0xb8fe  stloc.1
0xb8ff  ldloc.1
0xb900  ldstr    aStatuscode// "statuscode"
0xb905  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_AttributeName(string)
0xb90a  ldloc.1
0xb90b  ldc.i4.1
0xb90c  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_Operator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0xb911  ldloc.1
0xb912  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<object> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::get_Values()
0xb917  ldc.i4.4
0xb918  box      [mscorlib]System.Int32
0xb91d  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<object>::Add(var<u1>)
0xb922  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor()
0xb927  stloc.2
0xb928  ldloc.2
0xb929  ldstr    aProcesscode// "processcode"
0xb92e  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_AttributeName(string)
0xb933  ldloc.2
0xb934  ldc.i4.0
0xb935  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_Operator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0xb93a  ldloc.2
0xb93b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<object> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::get_Values()
0xb940  ldc.i4.1
0xb941  box      [mscorlib]System.Int32
0xb946  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<object>::Add(var<u1>)
0xb94b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::.ctor()
0xb950  stloc.3
0xb951  ldloc.3
0xb952  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0xb957  ldc.i4.3
0xb958  newarr   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression
0xb95d  dup
0xb95e  ldc.i4.0
0xb95f  ldloc.0
0xb960  stelem.ref
0xb961  dup
0xb962  ldc.i4.1
0xb963  ldloc.1
0xb964  stelem.ref
0xb965  dup
0xb966  ldc.i4.2
0xb967  ldloc.2
0xb968  stelem.ref
0xb969  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::AddRange(var<u1>[])
0xb96e  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor()
0xb973  stloc.s  4
0xb975  ldloc.s  4
0xb977  ldstr    aImportfile// "importfile"
0xb97c  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_EntityName(string)
0xb981  ldloc.s  4
0xb983  ldc.i4.1
0xb984  newarr   [mscorlib]System.String
0xb989  dup
0xb98a  ldc.i4.0
0xb98b  ldstr    aImportfileid_2// "importfileid"
0xb990  stelem.ref
0xb991  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(string[])
0xb996  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_ColumnSet(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet)
0xb99b  ldloc.s  4
0xb99d  ldloc.3
0xb99e  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_Criteria(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression)
0xb9a3  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleRequest::.ctor()
0xb9a8  stloc.s  5
0xb9aa  ldloc.s  5
0xb9ac  ldloc.s  4
0xb9ae  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleRequest::set_Query(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryBase)
0xb9b3  ldarg.0
0xb9b4  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.ImportOperation::_crmService
0xb9b9  ldloc.s  5
0xb9bb  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0xb9c0  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleResponse
0xb9c5  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleResponse::get_EntityCollection()
0xb9ca  ret
```
