# Microsoft.Crm.Data.DemoUserManager::RenameAndDisableDemoUsersInternal

- ea: `0x4ba20`
- end: `0x4bb36`
- name: `Microsoft.Crm.Data.DemoUserManager::RenameAndDisableDemoUsersInternal`
- size: `278`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x4ba00`
- `0x4ba10`

## callees

- `0x4ba20`
- `0x4bb90`
- `0x4bbe0`
- `0x4bc30`
- `0x4bc50`

## string_xrefs

- `0x4ba3f`: `crmdemo.dynamics.com`

## pseudocode

```c

```

## disassembly

```asm
0x4ba20  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor()
0x4ba25  stloc.0
0x4ba26  ldloc.0
0x4ba27  ldstr    aDomainname_0// "domainname"
0x4ba2c  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_AttributeName(string)
0x4ba31  ldloc.0
0x4ba32  ldc.i4.s 0x38
0x4ba34  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_Operator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0x4ba39  ldloc.0
0x4ba3a  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<object> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::get_Values()
0x4ba3f  ldstr    aCrmdemoDynamic// "crmdemo.dynamics.com"
0x4ba44  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<object>::Add(var<u1>)
0x4ba49  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::.ctor()
0x4ba4e  stloc.1
0x4ba4f  ldloc.1
0x4ba50  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0x4ba55  ldloc.0
0x4ba56  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::Add(var<u1>)
0x4ba5b  ldstr    aSystemuser// "systemuser"
0x4ba60  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor(string)
0x4ba65  stloc.2
0x4ba66  ldloc.2
0x4ba67  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_ColumnSet()
0x4ba6c  ldc.i4.4
0x4ba6d  newarr   [mscorlib]System.String
0x4ba72  dup
0x4ba73  ldc.i4.0
0x4ba74  ldstr    aFirstname// "firstname"
0x4ba79  stelem.ref
0x4ba7a  dup
0x4ba7b  ldc.i4.1
0x4ba7c  ldstr    aLastname// "lastname"
0x4ba81  stelem.ref
0x4ba82  dup
0x4ba83  ldc.i4.2
0x4ba84  ldstr    aDomainname_0// "domainname"
0x4ba89  stelem.ref
0x4ba8a  dup
0x4ba8b  ldc.i4.3
0x4ba8c  ldstr    aIsdisabled// "isdisabled"
0x4ba91  stelem.ref
0x4ba92  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumns(string[])
0x4ba97  ldloc.2
0x4ba98  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x4ba9d  ldloc.1
0x4ba9e  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddFilter(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression)
0x4baa3  ldarg.1
0x4baa4  ldloc.2
0x4baa5  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::RetrieveMultiple(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryBase)
0x4baaa  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x4baaf  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::GetEnumerator()
0x4bab4  stloc.3
0x4bab5  br.s     loc_4BB21
0x4bab7  ldloc.3
0x4bab8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Current()
0x4babd  stloc.s  4
0x4babf  ldarg.2
0x4bac0  brfalse.s loc_4BAEC
0x4bac2  ldloc.s  4
0x4bac4  ldstr    aFirstname// "firstname"
0x4bac9  ldstr    asc_7AF58// "---"
0x4bace  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x4bad3  ldloc.s  4
0x4bad5  ldstr    aLastname// "lastname"
0x4bada  ldstr    asc_7AF58// "---"
0x4badf  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x4bae4  ldarg.1
0x4bae5  ldloc.s  4
0x4bae7  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Update(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0x4baec  newobj   instance void Microsoft.Crm.Data.SetStateRequest::.ctor()
0x4baf1  dup
0x4baf2  ldloc.s  4
0x4baf4  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::ToEntityReference()
0x4baf9  callvirt instance void Microsoft.Crm.Data.SetStateRequest::set_EntityMoniker(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference value)
0x4bafe  dup
0x4baff  ldc.i4.1
0x4bb00  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0x4bb05  callvirt instance void Microsoft.Crm.Data.SetStateRequest::set_State(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue value)
0x4bb0a  dup
0x4bb0b  ldc.i4.m1
0x4bb0c  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0x4bb11  callvirt instance void Microsoft.Crm.Data.SetStateRequest::set_Status(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue value)
0x4bb16  stloc.s  5
0x4bb18  ldarg.1
0x4bb19  ldloc.s  5
0x4bb1b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x4bb20  pop
0x4bb21  ldloc.3
0x4bb22  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4bb27  brtrue.s loc_4BAB7
0x4bb29  leave.s  loc_4BB35
0x4bb2b  ldloc.3
0x4bb2c  brfalse.s loc_4BB34
0x4bb2e  ldloc.3
0x4bb2f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4bb34  endfinally
0x4bb35  ret
```
