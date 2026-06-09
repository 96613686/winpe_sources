# Microsoft.Crm.Asynchronous.ImportOperation::IsPreviousOperationSuccessful

- ea: `0xae20`
- end: `0xaf6e`
- name: `Microsoft.Crm.Asynchronous.ImportOperation::IsPreviousOperationSuccessful`
- size: `334`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0xab30`

## callees

- `0xae20`

## string_xrefs

- `0xaef7`: `createdon`

## pseudocode

```c

```

## disassembly

```asm
0xae20  ldarg.2
0xae21  ldc.i4.4
0xae22  bne.un.s loc_AE28
0xae24  ldc.i4.3
0xae25  stloc.0
0xae26  br.s     loc_AE32
0xae28  ldarg.2
0xae29  ldc.i4.5
0xae2a  bne.un.s loc_AE30
0xae2c  ldc.i4.4
0xae2d  stloc.0
0xae2e  br.s     loc_AE32
0xae30  ldc.i4.1
0xae31  ret
0xae32  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor()
0xae37  stloc.1
0xae38  ldloc.1
0xae39  ldstr    aRegardingobjec_2// "regardingobjectid"
0xae3e  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_AttributeName(string)
0xae43  ldloc.1
0xae44  ldc.i4.0
0xae45  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_Operator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0xae4a  ldloc.1
0xae4b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<object> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::get_Values()
0xae50  ldarg.1
0xae51  box      [mscorlib]System.Guid
0xae56  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<object>::Add(var<u1>)
0xae5b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor()
0xae60  stloc.2
0xae61  ldloc.2
0xae62  ldstr    aOperationtype// "operationtype"
0xae67  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_AttributeName(string)
0xae6c  ldloc.2
0xae6d  ldc.i4.0
0xae6e  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_Operator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0xae73  ldloc.2
0xae74  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<object> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::get_Values()
0xae79  ldloc.0
0xae7a  box      [mscorlib]System.Int32
0xae7f  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<object>::Add(var<u1>)
0xae84  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::.ctor()
0xae89  stloc.3
0xae8a  ldloc.3
0xae8b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0xae90  ldc.i4.2
0xae91  newarr   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression
0xae96  dup
0xae97  ldc.i4.0
0xae98  ldloc.1
0xae99  stelem.ref
0xae9a  dup
0xae9b  ldc.i4.1
0xae9c  ldloc.2
0xae9d  stelem.ref
0xae9e  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::AddRange(var<u1>[])
0xaea3  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor()
0xaea8  stloc.s  4
0xaeaa  ldloc.s  4
0xaeac  ldstr    aAsyncoperation_0// "asyncoperation"
0xaeb1  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_EntityName(string)
0xaeb6  ldloc.s  4
0xaeb8  ldc.i4.1
0xaeb9  newarr   [mscorlib]System.String
0xaebe  dup
0xaebf  ldc.i4.0
0xaec0  ldstr    aStatuscode// "statuscode"
0xaec5  stelem.ref
0xaec6  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(string[])
0xaecb  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_ColumnSet(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet)
0xaed0  ldloc.s  4
0xaed2  ldloc.3
0xaed3  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_Criteria(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression)
0xaed8  ldc.i4.1
0xaed9  newarr   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.OrderExpression
0xaede  stloc.s  5
0xaee0  ldloc.s  5
0xaee2  ldc.i4.0
0xaee3  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.OrderExpression::.ctor()
0xaee8  stelem.ref
0xaee9  ldloc.s  5
0xaeeb  ldc.i4.0
0xaeec  ldelem.ref
0xaeed  ldc.i4.1
0xaeee  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.OrderExpression::set_OrderType(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.OrderType)
0xaef3  ldloc.s  5
0xaef5  ldc.i4.0
0xaef6  ldelem.ref
0xaef7  ldstr    aCreatedon// "createdon"
0xaefc  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.OrderExpression::set_AttributeName(string)
0xaf01  ldloc.s  4
0xaf03  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.OrderExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Orders()
0xaf08  ldloc.s  5
0xaf0a  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.OrderExpression>::AddRange(var<u1>[])
0xaf0f  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleRequest::.ctor()
0xaf14  stloc.s  6
0xaf16  ldloc.s  6
0xaf18  ldloc.s  4
0xaf1a  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleRequest::set_Query(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryBase)
0xaf1f  ldarg.0
0xaf20  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.ImportOperation::_crmService
0xaf25  ldloc.s  6
0xaf27  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0xaf2c  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleResponse
0xaf31  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleResponse::get_EntityCollection()
0xaf36  stloc.s  7
0xaf38  ldloc.s  7
0xaf3a  brfalse.s loc_AF6C
0xaf3c  ldloc.s  7
0xaf3e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0xaf43  brfalse.s loc_AF6C
0xaf45  ldloc.s  7
0xaf47  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0xaf4c  ldc.i4.0
0xaf4d  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Item(!!T0)
0xaf52  ldstr    aStatuscode// "statuscode"
0xaf57  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0xaf5c  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0xaf61  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0xaf66  ldc.i4.s 0x1E
0xaf68  bne.un.s loc_AF6C
0xaf6a  ldc.i4.1
0xaf6b  ret
0xaf6c  ldc.i4.0
0xaf6d  ret
```
