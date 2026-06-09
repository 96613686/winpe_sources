# Microsoft.Crm.UserScenarioRole.UserScenarioRoleManager::GetRoleIdFromRoleTemplateId

- ea: `0x41e50`
- end: `0x41ec7`
- name: `Microsoft.Crm.UserScenarioRole.UserScenarioRoleManager::GetRoleIdFromRoleTemplateId`
- size: `119`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x41a80`
- `0x41f30`

## string_xrefs

- `0x41e8b`: `roletemplateid`

## pseudocode

```c

```

## disassembly

```asm
0x41e50  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x41e55  pop
0x41e56  ldstr    aRole// "role"
0x41e5b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor(string)
0x41e60  stloc.0
0x41e61  ldloc.0
0x41e62  ldc.i4.1
0x41e63  newarr   [mscorlib]System.String
0x41e68  dup
0x41e69  ldc.i4.0
0x41e6a  ldstr    aRoleid// "roleid"
0x41e6f  stelem.ref
0x41e70  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(string[])
0x41e75  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_ColumnSet(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet)
0x41e7a  ldloc.0
0x41e7b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::.ctor()
0x41e80  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_Criteria(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression)
0x41e85  ldloc.0
0x41e86  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x41e8b  ldstr    aRoletemplateid// "roletemplateid"
0x41e90  ldc.i4.0
0x41e91  ldc.i4.1
0x41e92  newarr   [mscorlib]System.Object
0x41e97  dup
0x41e98  ldc.i4.0
0x41e99  ldarg.1
0x41e9a  box      [mscorlib]System.Guid
0x41e9f  stelem.ref
0x41ea0  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object[])
0x41ea5  ldarg.2
0x41ea6  ldloc.0
0x41ea7  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::RetrieveMultiple(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryBase)
0x41eac  ldc.i4.0
0x41ead  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Item(int32)
0x41eb2  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x41eb7  ldstr    aRoleid// "roleid"
0x41ebc  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x41ec1  unbox.any [mscorlib]System.Guid
0x41ec6  ret
```
