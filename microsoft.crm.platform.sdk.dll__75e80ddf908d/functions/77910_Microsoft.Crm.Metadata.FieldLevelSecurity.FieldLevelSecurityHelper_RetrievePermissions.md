# Microsoft.Crm.Metadata.FieldLevelSecurity.FieldLevelSecurityHelper::RetrievePermissions

- ea: `0x77910`
- end: `0x779bb`
- name: `Microsoft.Crm.Metadata.FieldLevelSecurity.FieldLevelSecurityHelper::RetrievePermissions`
- size: `171`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0xad690`

## callees

- `0x12d20`

## string_xrefs

- `0x77910`: `principalobjectattributeaccess`
- `0x7792c`: `readaccess`
- `0x77934`: `updateaccess`

## pseudocode

```c

```

## disassembly

```asm
0x77910  ldstr    aPrincipalobjec_0// "principalobjectattributeaccess"
0x77915  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor(string)
0x7791a  stloc.0
0x7791b  ldloc.0
0x7791c  ldc.i4.3
0x7791d  newarr   [mscorlib]System.String
0x77922  dup
0x77923  ldc.i4.0
0x77924  ldstr    aAttributeid_1// "attributeid"
0x77929  stelem.ref
0x7792a  dup
0x7792b  ldc.i4.1
0x7792c  ldstr    aReadaccess// "readaccess"
0x77931  stelem.ref
0x77932  dup
0x77933  ldc.i4.2
0x77934  ldstr    aUpdateaccess// "updateaccess"
0x77939  stelem.ref
0x7793a  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(string[])
0x7793f  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_ColumnSet(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet)
0x77944  ldloc.0
0x77945  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x7794a  ldc.i4.0
0x7794b  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::set_FilterOperator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator)
0x77950  ldloc.0
0x77951  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x77956  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0x7795b  ldstr    aObjecttypecode_0// "objecttypecode"
0x77960  ldc.i4.0
0x77961  ldarg.2
0x77962  callvirt instance int32 Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x77967  box      [mscorlib]System.Int32
0x7796c  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x77971  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::Add(var<u1>)
0x77976  ldloc.0
0x77977  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x7797c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0x77981  ldstr    aObjectid// "objectid"
0x77986  ldc.i4.0
0x77987  ldarg.0
0x77988  box      [mscorlib]System.Guid
0x7798d  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x77992  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::Add(var<u1>)
0x77997  ldloc.0
0x77998  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x7799d  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0x779a2  ldstr    aPrincipalid// "principalid"
0x779a7  ldc.i4.s 0x4A
0x779a9  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0x779ae  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::Add(var<u1>)
0x779b3  ldarg.1
0x779b4  ldloc.0
0x779b5  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::RetrieveMultiple(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryBase)
0x779ba  ret
```
