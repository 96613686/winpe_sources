# Microsoft.Crm.ScaleGroupApi.Controllers.SecurityRoleController::GetSecurityRoles

- ea: `0x3320`
- end: `0x3546`
- name: `Microsoft.Crm.ScaleGroupApi.Controllers.SecurityRoleController::GetSecurityRoles`
- size: `550`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0xe80`
- `0xeb0`
- `0x14b0`
- `0x14d0`
- `0x14f0`
- `0x1510`
- `0x1530`
- `0x1550`
- `0x1560`
- `0x3320`

## string_xrefs

- `0x345b`: `roletemplateid`
- `0x3469`: `roletemplateid`
- `0x347a`: `roletemplateid`

## pseudocode

```c

```

## disassembly

```asm
0x3320  ldarg.1
0x3321  ldstr    aOrganizationid// "organizationId"
0x3326  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x332b  ldarg.1
0x332c  call     class Microsoft.Crm.ScaleGroupApi.OrganizationSdkProvider Microsoft.Crm.ScaleGroupApi.OrganizationSdkProvider::CreateInstance(valuetype [mscorlib]System.Guid orgId)
0x3331  stloc.0
0x3332  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor()
0x3337  dup
0x3338  ldstr    aRole// "role"
0x333d  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_EntityName(string)
0x3342  dup
0x3343  ldc.i4.1
0x3344  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(bool)
0x3349  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_ColumnSet(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet)
0x334e  stloc.1
0x334f  ldstr    aRole// "role"
0x3354  ldstr    aBusinessunit// "businessunit"
0x3359  ldstr    aBusinessunitid// "businessunitid"
0x335e  ldstr    aBusinessunitid// "businessunitid"
0x3363  ldc.i4.0
0x3364  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity::.ctor(string, string, string, string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.JoinOperator)
0x3369  stloc.2
0x336a  ldloc.1
0x336b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_LinkEntities()
0x3370  ldloc.2
0x3371  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity>::Add(var<u1>)
0x3376  ldloc.1
0x3377  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_LinkEntities()
0x337c  ldc.i4.0
0x337d  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity>::get_Item(!!T0)
0x3382  ldstr    aBu// "bu"
0x3387  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity::set_EntityAlias(string)
0x338c  ldloc.1
0x338d  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_LinkEntities()
0x3392  ldc.i4.0
0x3393  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity>::get_Item(!!T0)
0x3398  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity::get_Columns()
0x339d  ldc.i4.1
0x339e  newarr   [mscorlib]System.String
0x33a3  dup
0x33a4  ldc.i4.0
0x33a5  ldstr    aParentbusiness// "parentbusinessunitid"
0x33aa  stelem.ref
0x33ab  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumns(string[])
0x33b0  ldloc.0
0x33b1  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.ScaleGroupApi.OrganizationSdkProvider::get_Sdk()
0x33b6  ldloc.1
0x33b7  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::RetrieveMultiple(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryBase)
0x33bc  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ScaleGroupApi.Models.SGSecurityRole>::.ctor()
0x33c1  stloc.3
0x33c2  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x33c7  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::GetEnumerator()
0x33cc  stloc.s  4
0x33ce  br       loc_3515
0x33d3  ldloc.s  4
0x33d5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Current()
0x33da  stloc.s  5
0x33dc  ldloc.s  5
0x33de  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x33e3  ldstr    aBusinessunitid// "businessunitid"
0x33e8  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x33ed  brfalse.s loc_33FD
0x33ef  ldloc.s  5
0x33f1  ldstr    aBusinessunitid// "businessunitid"
0x33f6  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x33fb  brtrue.s loc_3400
0x33fd  ldnull
0x33fe  br.s     loc_3411
0x3400  ldloc.s  5
0x3402  ldstr    aBusinessunitid// "businessunitid"
0x3407  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x340c  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x3411  stloc.s  6
0x3413  ldloc.s  5
0x3415  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x341a  ldstr    aBuParentbusine// "bu.parentbusinessunitid"
0x341f  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x3424  brfalse.s loc_3434
0x3426  ldloc.s  5
0x3428  ldstr    aBuParentbusine// "bu.parentbusinessunitid"
0x342d  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x3432  brtrue.s loc_3437
0x3434  ldnull
0x3435  br.s     loc_3452
0x3437  ldloc.s  5
0x3439  ldstr    aBuParentbusine// "bu.parentbusinessunitid"
0x343e  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x3443  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AliasedValue
0x3448  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AliasedValue::get_Value()
0x344d  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x3452  stloc.s  7
0x3454  ldloc.s  5
0x3456  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x345b  ldstr    aRoletemplateid// "roletemplateid"
0x3460  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x3465  brfalse.s loc_3475
0x3467  ldloc.s  5
0x3469  ldstr    aRoletemplateid// "roletemplateid"
0x346e  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x3473  brtrue.s loc_3478
0x3475  ldnull
0x3476  br.s     loc_3489
0x3478  ldloc.s  5
0x347a  ldstr    aRoletemplateid// "roletemplateid"
0x347f  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x3484  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x3489  stloc.s  8
0x348b  ldloc.3
0x348c  newobj   instance void Microsoft.Crm.ScaleGroupApi.Models.SGSecurityRole::.ctor()
0x3491  dup
0x3492  ldloc.s  5
0x3494  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x3499  callvirt instance void Microsoft.Crm.ScaleGroupApi.Models.SGSecurityRole::set_SecurityRoleId(valuetype [mscorlib]System.Guid value)
0x349e  dup
0x349f  ldloc.s  5
0x34a1  ldstr    aName// "name"
0x34a6  callvirt T0x2B000014
0x34ab  callvirt instance void Microsoft.Crm.ScaleGroupApi.Models.SGSecurityRole::set_SecurityRoleName(string value)
0x34b0  dup
0x34b1  ldloc.s  8
0x34b3  brtrue.s loc_34BC
0x34b5  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x34ba  br.s     loc_34C3
0x34bc  ldloc.s  8
0x34be  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x34c3  callvirt instance void Microsoft.Crm.ScaleGroupApi.Models.SGSecurityRole::set_RoleTemplateId(valuetype [mscorlib]System.Guid value)
0x34c8  dup
0x34c9  ldloc.s  6
0x34cb  brtrue.s loc_34D4
0x34cd  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x34d2  br.s     loc_34DB
0x34d4  ldloc.s  6
0x34d6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x34db  callvirt instance void Microsoft.Crm.ScaleGroupApi.Models.SGSecurityRole::set_BusinessUnitId(valuetype [mscorlib]System.Guid value)
0x34e0  dup
0x34e1  ldloc.s  6
0x34e3  brtrue.s loc_34EC
0x34e5  ldsfld   string [mscorlib]System.String::Empty
0x34ea  br.s     loc_34F3
0x34ec  ldloc.s  6
0x34ee  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Name()
0x34f3  callvirt instance void Microsoft.Crm.ScaleGroupApi.Models.SGSecurityRole::set_BusinessUnitName(string value)
0x34f8  dup
0x34f9  ldloc.s  7
0x34fb  brtrue.s loc_3504
0x34fd  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3502  br.s     loc_350B
0x3504  ldloc.s  7
0x3506  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x350b  callvirt instance void Microsoft.Crm.ScaleGroupApi.Models.SGSecurityRole::set_ParentBusinessUnitId(valuetype [mscorlib]System.Guid value)
0x3510  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ScaleGroupApi.Models.SGSecurityRole>::Add(var<u1>)
0x3515  ldloc.s  4
0x3517  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x351c  brtrue   loc_33D3
0x3521  leave.s  loc_352F
0x3523  ldloc.s  4
0x3525  brfalse.s loc_352E
0x3527  ldloc.s  4
0x3529  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x352e  endfinally
0x352f  ldloc.3
0x3530  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ScaleGroupApi.Models.SGSecurityRole>::ToArray()
0x3535  stloc.s  9
0x3537  leave.s  loc_3543
0x3539  ldloc.0
0x353a  brfalse.s loc_3542
0x353c  ldloc.0
0x353d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3542  endfinally
0x3543  ldloc.s  9
0x3545  ret
```
