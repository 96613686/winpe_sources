# Microsoft.Crm.Application.Controls.SystemCustomization.GrantPrincipalsGridDataProvider::DeletePOAAForPrincipal

- ea: `0xc0740`
- end: `0xc0830`
- name: `Microsoft.Crm.Application.Controls.SystemCustomization.GrantPrincipalsGridDataProvider::DeletePOAAForPrincipal`
- size: `240`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0xc05d0`

## callees

- `0xc0740`

## string_xrefs

- `0xc0740`: `principalobjectattributeaccess`
- `0xc07fc`: `principalobjectattributeaccess`
- `0xc0750`: `principalobjectattributeaccessid`
- `0xc0802`: `principalobjectattributeaccessid`

## pseudocode

```c

```

## disassembly

```asm
0xc0740  ldstr    aPrincipalobjec// "principalobjectattributeaccess"
0xc0745  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::.ctor(string)
0xc074a  dup
0xc074b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0xc0750  ldstr    aPrincipalobjec_0// "principalobjectattributeaccessid"
0xc0755  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0xc075a  dup
0xc075b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0xc0760  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::get_Conditions()
0xc0765  ldstr    aObjectid// "objectid"
0xc076a  ldc.i4.0
0xc076b  ldarg.s  4
0xc076d  box      [mscorlib]System.Guid
0xc0772  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0xc0777  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xc077c  pop
0xc077d  dup
0xc077e  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0xc0783  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::get_Conditions()
0xc0788  ldstr    aPrincipalid// "principalid"
0xc078d  ldc.i4.0
0xc078e  ldarg.2
0xc078f  box      [mscorlib]System.Guid
0xc0794  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0xc0799  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xc079e  pop
0xc079f  dup
0xc07a0  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0xc07a5  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::get_Conditions()
0xc07aa  ldstr    aObjecttypecode// "objecttypecode"
0xc07af  ldc.i4.0
0xc07b0  ldarg.3
0xc07b1  box      [mscorlib]System.Int32
0xc07b6  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0xc07bb  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xc07c0  pop
0xc07c1  dup
0xc07c2  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0xc07c7  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::get_Conditions()
0xc07cc  ldstr    aPrincipalidtyp// "principalidtype"
0xc07d1  ldc.i4.0
0xc07d2  ldarg.1
0xc07d3  box      [mscorlib]System.Int32
0xc07d8  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0xc07dd  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xc07e2  pop
0xc07e3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xc07e8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xc07ed  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::GetEnumerator()
0xc07f2  stloc.0
0xc07f3  br.s     loc_C081B
0xc07f5  ldloc.0
0xc07f6  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Current()
0xc07fb  stloc.1
0xc07fc  ldstr    aPrincipalobjec// "principalobjectattributeaccess"
0xc0801  ldloc.1
0xc0802  ldstr    aPrincipalobjec_0// "principalobjectattributeaccessid"
0xc0807  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xc080c  unbox.any [mscorlib]System.Guid
0xc0811  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xc0816  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Delete(string, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xc081b  ldloc.0
0xc081c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xc0821  brtrue.s loc_C07F5
0xc0823  leave.s  loc_C082F
0xc0825  ldloc.0
0xc0826  brfalse.s loc_C082E
0xc0828  ldloc.0
0xc0829  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc082e  endfinally
0xc082f  ret
```
