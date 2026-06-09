# Microsoft.Crm.Asynchronous.ImportOperationImport::AsyncOperationAlreadyExists

- ea: `0xcdc0`
- end: `0xcf2f`
- name: `Microsoft.Crm.Asynchronous.ImportOperationImport::AsyncOperationAlreadyExists`
- size: `367`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xc8e0`

## callees

- `0xcdc0`

## pseudocode

```c

```

## disassembly

```asm
0xcdc0  ldarg.2
0xcdc1  call     string [Microsoft.Crm.Asynchronous.HandlerUtility]Microsoft.Crm.Asynchronous.DataCompressionHelper::CompressData(string)
0xcdc6  stloc.0
0xcdc7  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor()
0xcdcc  stloc.1
0xcdcd  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor()
0xcdd2  stloc.2
0xcdd3  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor()
0xcdd8  stloc.3
0xcdd9  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor()
0xcdde  stloc.s  4
0xcde0  ldloc.1
0xcde1  ldstr    aRegardingobjec_2// "regardingobjectid"
0xcde6  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_AttributeName(string)
0xcdeb  ldloc.1
0xcdec  ldc.i4.0
0xcded  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_Operator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0xcdf2  ldloc.1
0xcdf3  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<object> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::get_Values()
0xcdf8  ldarg.1
0xcdf9  box      [mscorlib]System.Guid
0xcdfe  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<object>::Add(var<u1>)
0xce03  ldloc.2
0xce04  ldstr    aOperationtype// "operationtype"
0xce09  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_AttributeName(string)
0xce0e  ldloc.2
0xce0f  ldc.i4.0
0xce10  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_Operator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0xce15  ldloc.2
0xce16  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<object> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::get_Values()
0xce1b  ldc.i4.s 0x11
0xce1d  box      [mscorlib]System.Int32
0xce22  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<object>::Add(var<u1>)
0xce27  ldloc.s  4
0xce29  ldstr    aData_0// "data"
0xce2e  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_AttributeName(string)
0xce33  ldloc.s  4
0xce35  ldc.i4.0
0xce36  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_Operator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0xce3b  ldloc.s  4
0xce3d  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<object> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::get_Values()
0xce42  ldloc.0
0xce43  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<object>::Add(var<u1>)
0xce48  ldloc.3
0xce49  ldstr    aRequestid// "requestid"
0xce4e  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_AttributeName(string)
0xce53  ldloc.3
0xce54  ldc.i4.0
0xce55  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_Operator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0xce5a  ldloc.3
0xce5b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<object> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::get_Values()
0xce60  ldarg.0
0xce61  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.ImportOperation::_asyncEvent
0xce66  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_RegardingObject()
0xce6b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmReference::get_Value()
0xce70  box      [mscorlib]System.Guid
0xce75  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<object>::Add(var<u1>)
0xce7a  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::.ctor()
0xce7f  stloc.s  5
0xce81  ldloc.s  5
0xce83  ldc.i4.0
0xce84  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::set_FilterOperator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator)
0xce89  ldloc.s  5
0xce8b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0xce90  ldc.i4.4
0xce91  newarr   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression
0xce96  dup
0xce97  ldc.i4.0
0xce98  ldloc.1
0xce99  stelem.ref
0xce9a  dup
0xce9b  ldc.i4.1
0xce9c  ldloc.2
0xce9d  stelem.ref
0xce9e  dup
0xce9f  ldc.i4.2
0xcea0  ldloc.s  4
0xcea2  stelem.ref
0xcea3  dup
0xcea4  ldc.i4.3
0xcea5  ldloc.3
0xcea6  stelem.ref
0xcea7  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::AddRange(var<u1>[])
0xceac  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor()
0xceb1  stloc.s  6
0xceb3  ldloc.s  6
0xceb5  ldstr    aAsyncoperation_0// "asyncoperation"
0xceba  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_EntityName(string)
0xcebf  ldloc.s  6
0xcec1  ldc.i4.3
0xcec2  newarr   [mscorlib]System.String
0xcec7  dup
0xcec8  ldc.i4.0
0xcec9  ldstr    aAsyncoperation_1// "asyncoperationid"
0xcece  stelem.ref
0xcecf  dup
0xced0  ldc.i4.1
0xced1  ldstr    aStatecode// "statecode"
0xced6  stelem.ref
0xced7  dup
0xced8  ldc.i4.2
0xced9  ldstr    aStatuscode// "statuscode"
0xcede  stelem.ref
0xcedf  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(string[])
0xcee4  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_ColumnSet(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet)
0xcee9  ldloc.s  6
0xceeb  ldloc.s  5
0xceed  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_Criteria(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression)
0xcef2  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleRequest::.ctor()
0xcef7  stloc.s  7
0xcef9  ldloc.s  7
0xcefb  ldloc.s  6
0xcefd  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleRequest::set_Query(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryBase)
0xcf02  ldarg.0
0xcf03  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.ImportOperation::_crmService
0xcf08  ldloc.s  7
0xcf0a  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0xcf0f  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleResponse
0xcf14  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleResponse::get_EntityCollection()
0xcf19  stloc.s  8
0xcf1b  ldloc.s  8
0xcf1d  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0xcf22  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Count()
0xcf27  ldc.i4.0
0xcf28  ble.s    loc_CF2D
0xcf2a  ldloc.s  8
0xcf2c  ret
0xcf2d  ldnull
0xcf2e  ret
```
