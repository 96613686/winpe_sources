# Microsoft.Crm.Asynchronous.ImportOperationImport::AllJobsSubmittedTillNowHaveCompleted

- ea: `0xd610`
- end: `0xd7c2`
- name: `Microsoft.Crm.Asynchronous.ImportOperationImport::AllJobsSubmittedTillNowHaveCompleted`
- size: `434`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xd7f0`

## callees

- `0xd610`

## pseudocode

```c

```

## disassembly

```asm
0xd610  ldarg.0
0xd611  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Asynchronous.ImportOperationImport::_failedJobs
0xd616  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Clear()
0xd61b  ldarg.2
0xd61c  ldc.i4.1
0xd61d  add
0xd61e  newarr   [mscorlib]System.String
0xd623  stloc.0
0xd624  ldc.i4.0
0xd625  stloc.s  8
0xd627  br.s     loc_D644
0xd629  ldloc.0
0xd62a  ldloc.s  8
0xd62c  ldloca.s 8
0xd62e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xd633  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xd638  call     string [Microsoft.Crm.Asynchronous.HandlerUtility]Microsoft.Crm.Asynchronous.DataCompressionHelper::CompressData(string)
0xd63d  stelem.ref
0xd63e  ldloc.s  8
0xd640  ldc.i4.1
0xd641  add
0xd642  stloc.s  8
0xd644  ldloc.s  8
0xd646  ldarg.2
0xd647  ble.s    loc_D629
0xd649  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor()
0xd64e  stloc.1
0xd64f  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor()
0xd654  stloc.2
0xd655  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor()
0xd65a  stloc.3
0xd65b  ldloc.1
0xd65c  ldstr    aStatecode// "statecode"
0xd661  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_AttributeName(string)
0xd666  ldloc.1
0xd667  ldc.i4.1
0xd668  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_Operator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0xd66d  ldloc.1
0xd66e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<object> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::get_Values()
0xd673  ldc.i4.3
0xd674  box      [mscorlib]System.Int32
0xd679  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<object>::Add(var<u1>)
0xd67e  ldloc.2
0xd67f  ldstr    aRequestid// "requestid"
0xd684  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_AttributeName(string)
0xd689  ldloc.2
0xd68a  ldc.i4.0
0xd68b  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_Operator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0xd690  ldloc.2
0xd691  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<object> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::get_Values()
0xd696  ldarg.1
0xd697  box      [mscorlib]System.Guid
0xd69c  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<object>::Add(var<u1>)
0xd6a1  ldloc.3
0xd6a2  ldstr    aData_0// "data"
0xd6a7  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_AttributeName(string)
0xd6ac  ldloc.3
0xd6ad  ldc.i4.8
0xd6ae  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_Operator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0xd6b3  ldloc.3
0xd6b4  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<object> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::get_Values()
0xd6b9  ldloc.0
0xd6ba  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<object>::AddRange(var<u1>[])
0xd6bf  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::.ctor()
0xd6c4  stloc.s  4
0xd6c6  ldloc.s  4
0xd6c8  ldc.i4.0
0xd6c9  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::set_FilterOperator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator)
0xd6ce  ldloc.s  4
0xd6d0  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0xd6d5  ldc.i4.3
0xd6d6  newarr   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression
0xd6db  dup
0xd6dc  ldc.i4.0
0xd6dd  ldloc.1
0xd6de  stelem.ref
0xd6df  dup
0xd6e0  ldc.i4.1
0xd6e1  ldloc.2
0xd6e2  stelem.ref
0xd6e3  dup
0xd6e4  ldc.i4.2
0xd6e5  ldloc.3
0xd6e6  stelem.ref
0xd6e7  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::AddRange(var<u1>[])
0xd6ec  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor()
0xd6f1  stloc.s  5
0xd6f3  ldloc.s  5
0xd6f5  ldstr    aAsyncoperation_0// "asyncoperation"
0xd6fa  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_EntityName(string)
0xd6ff  ldloc.s  5
0xd701  ldc.i4.2
0xd702  newarr   [mscorlib]System.String
0xd707  dup
0xd708  ldc.i4.0
0xd709  ldstr    aAsyncoperation_1// "asyncoperationid"
0xd70e  stelem.ref
0xd70f  dup
0xd710  ldc.i4.1
0xd711  ldstr    aStatuscode// "statuscode"
0xd716  stelem.ref
0xd717  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(string[])
0xd71c  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_ColumnSet(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet)
0xd721  ldloc.s  5
0xd723  ldloc.s  4
0xd725  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_Criteria(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression)
0xd72a  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleRequest::.ctor()
0xd72f  stloc.s  6
0xd731  ldloc.s  6
0xd733  ldloc.s  5
0xd735  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleRequest::set_Query(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryBase)
0xd73a  ldarg.0
0xd73b  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.ImportOperation::_crmService
0xd740  ldloc.s  6
0xd742  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0xd747  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleResponse
0xd74c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleResponse::get_EntityCollection()
0xd751  stloc.s  7
0xd753  ldloc.s  7
0xd755  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0xd75a  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::GetEnumerator()
0xd75f  stloc.s  9
0xd761  br.s     loc_D798
0xd763  ldloc.s  9
0xd765  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Current()
0xd76a  stloc.s  0xA
0xd76c  ldloc.s  0xA
0xd76e  ldstr    aStatuscode// "statuscode"
0xd773  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0xd778  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0xd77d  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0xd782  ldc.i4.s 0x1F
0xd784  bne.un.s loc_D798
0xd786  ldarg.0
0xd787  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Asynchronous.ImportOperationImport::_failedJobs
0xd78c  ldloc.s  0xA
0xd78e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0xd793  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0xd798  ldloc.s  9
0xd79a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xd79f  brtrue.s loc_D763
0xd7a1  leave.s  loc_D7AF
0xd7a3  ldloc.s  9
0xd7a5  brfalse.s loc_D7AE
0xd7a7  ldloc.s  9
0xd7a9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd7ae  endfinally
0xd7af  ldloc.s  7
0xd7b1  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0xd7b6  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Count()
0xd7bb  ldc.i4.0
0xd7bc  ble.s    loc_D7C0
0xd7be  ldc.i4.0
0xd7bf  ret
0xd7c0  ldc.i4.1
0xd7c1  ret
```
