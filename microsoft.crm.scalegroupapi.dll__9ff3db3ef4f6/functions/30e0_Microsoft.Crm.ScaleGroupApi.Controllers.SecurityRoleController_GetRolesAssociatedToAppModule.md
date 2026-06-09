# Microsoft.Crm.ScaleGroupApi.Controllers.SecurityRoleController::GetRolesAssociatedToAppModule

- ea: `0x30e0`
- end: `0x331a`
- name: `Microsoft.Crm.ScaleGroupApi.Controllers.SecurityRoleController::GetRolesAssociatedToAppModule`
- size: `570`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0xe80`
- `0xeb0`
- `0x14b0`
- `0x14d0`
- `0x14f0`
- `0x1510`
- `0x1530`
- `0x1560`
- `0x30e0`

## pseudocode

```c

```

## disassembly

```asm
0x30e0  ldarg.1
0x30e1  box      [mscorlib]System.Guid
0x30e6  ldstr    aOrganizationid_0// "OrganizationId"
0x30eb  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x30f0  ldarg.2
0x30f1  ldstr    aAppmoduleuniqu// "appModuleUniqueName"
0x30f6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x30fb  ldarg.1
0x30fc  call     class Microsoft.Crm.ScaleGroupApi.OrganizationSdkProvider Microsoft.Crm.ScaleGroupApi.OrganizationSdkProvider::CreateInstance(valuetype [mscorlib]System.Guid orgId)
0x3101  stloc.0
0x3102  ldstr    aAppmodule// "appmodule"
0x3107  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor(string)
0x310c  stloc.1
0x310d  ldloc.1
0x310e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x3113  ldstr    aUniquename// "uniquename"
0x3118  ldc.i4.0
0x3119  ldc.i4.1
0x311a  newarr   [mscorlib]System.Object
0x311f  dup
0x3120  ldc.i4.0
0x3121  ldarg.2
0x3122  stelem.ref
0x3123  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object[])
0x3128  ldloc.1
0x3129  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_ColumnSet()
0x312e  ldc.i4.2
0x312f  newarr   [mscorlib]System.String
0x3134  dup
0x3135  ldc.i4.0
0x3136  ldstr    aAppmoduleid// "appmoduleid"
0x313b  stelem.ref
0x313c  dup
0x313d  ldc.i4.1
0x313e  ldstr    aSolutionid// "solutionid"
0x3143  stelem.ref
0x3144  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumns(string[])
0x3149  ldloc.0
0x314a  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.ScaleGroupApi.OrganizationSdkProvider::get_Sdk()
0x314f  ldloc.1
0x3150  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::RetrieveMultiple(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryBase)
0x3155  stloc.2
0x3156  ldloc.2
0x3157  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x315c  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Count()
0x3161  ldc.i4.1
0x3162  ble.s    loc_316F
0x3164  ldstr    aMultipleAppmod// "Multiple appmodules with same unique na"...
0x3169  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x316e  throw
0x316f  ldloc.2
0x3170  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x3175  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Count()
0x317a  ldc.i4.1
0x317b  bge.s    loc_3188
0x317d  ldstr    aNoAppmoduleWit// "No appmodule with given unique name is "...
0x3182  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x3187  throw
0x3188  ldloc.2
0x3189  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x318e  ldc.i4.0
0x318f  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Item(!!T0)
0x3194  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x3199  ldstr    aSolutionid// "solutionid"
0x319e  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x31a3  unbox.any [mscorlib]System.Guid
0x31a8  pop
0x31a9  ldloc.2
0x31aa  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x31af  ldc.i4.0
0x31b0  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Item(!!T0)
0x31b5  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x31ba  ldstr    aAppmoduleid// "appmoduleid"
0x31bf  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x31c4  unbox.any [mscorlib]System.Guid
0x31c9  stloc.3
0x31ca  ldstr    aAppmoduleroles// "appmoduleroles"
0x31cf  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor(string)
0x31d4  stloc.s  4
0x31d6  ldloc.s  4
0x31d8  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x31dd  ldstr    aAppmoduleid// "appmoduleid"
0x31e2  ldc.i4.0
0x31e3  ldc.i4.1
0x31e4  newarr   [mscorlib]System.Object
0x31e9  dup
0x31ea  ldc.i4.0
0x31eb  ldloc.3
0x31ec  box      [mscorlib]System.Guid
0x31f1  stelem.ref
0x31f2  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object[])
0x31f7  ldstr    aAppmoduleroles// "appmoduleroles"
0x31fc  ldstr    aRole// "role"
0x3201  ldstr    aRoleid// "roleid"
0x3206  ldstr    aRoleid// "roleid"
0x320b  ldc.i4.0
0x320c  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity::.ctor(string, string, string, string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.JoinOperator)
0x3211  stloc.s  5
0x3213  ldloc.s  4
0x3215  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_LinkEntities()
0x321a  ldloc.s  5
0x321c  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity>::Add(var<u1>)
0x3221  ldloc.s  4
0x3223  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_LinkEntities()
0x3228  ldc.i4.0
0x3229  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity>::get_Item(!!T0)
0x322e  ldstr    aRo// "ro"
0x3233  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity::set_EntityAlias(string)
0x3238  ldloc.s  4
0x323a  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_LinkEntities()
0x323f  ldc.i4.0
0x3240  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity>::get_Item(!!T0)
0x3245  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity::get_Columns()
0x324a  ldc.i4.2
0x324b  newarr   [mscorlib]System.String
0x3250  dup
0x3251  ldc.i4.0
0x3252  ldstr    aRoleid// "roleid"
0x3257  stelem.ref
0x3258  dup
0x3259  ldc.i4.1
0x325a  ldstr    aName// "name"
0x325f  stelem.ref
0x3260  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumns(string[])
0x3265  ldloc.0
0x3266  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.ScaleGroupApi.OrganizationSdkProvider::get_Sdk()
0x326b  ldloc.s  4
0x326d  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::RetrieveMultiple(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryBase)
0x3272  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ScaleGroupApi.Models.SGSecurityRole>::.ctor()
0x3277  stloc.s  6
0x3279  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x327e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::GetEnumerator()
0x3283  stloc.s  7
0x3285  br.s     loc_32FB
0x3287  ldloc.s  7
0x3289  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Current()
0x328e  stloc.s  8
0x3290  ldloc.s  6
0x3292  newobj   instance void Microsoft.Crm.ScaleGroupApi.Models.SGSecurityRole::.ctor()
0x3297  dup
0x3298  ldloc.s  8
0x329a  ldstr    aRoRoleid// "ro.roleid"
0x329f  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x32a4  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AliasedValue
0x32a9  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AliasedValue::get_Value()
0x32ae  unbox.any [mscorlib]System.Guid
0x32b3  callvirt instance void Microsoft.Crm.ScaleGroupApi.Models.SGSecurityRole::set_SecurityRoleId(valuetype [mscorlib]System.Guid value)
0x32b8  dup
0x32b9  ldloc.s  8
0x32bb  ldstr    aRoName// "ro.name"
0x32c0  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x32c5  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AliasedValue
0x32ca  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AliasedValue::get_Value()
0x32cf  castclass [mscorlib]System.String
0x32d4  callvirt instance void Microsoft.Crm.ScaleGroupApi.Models.SGSecurityRole::set_SecurityRoleName(string value)
0x32d9  dup
0x32da  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x32df  callvirt instance void Microsoft.Crm.ScaleGroupApi.Models.SGSecurityRole::set_BusinessUnitId(valuetype [mscorlib]System.Guid value)
0x32e4  dup
0x32e5  ldnull
0x32e6  callvirt instance void Microsoft.Crm.ScaleGroupApi.Models.SGSecurityRole::set_BusinessUnitName(string value)
0x32eb  dup
0x32ec  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x32f1  callvirt instance void Microsoft.Crm.ScaleGroupApi.Models.SGSecurityRole::set_ParentBusinessUnitId(valuetype [mscorlib]System.Guid value)
0x32f6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ScaleGroupApi.Models.SGSecurityRole>::Add(var<u1>)
0x32fb  ldloc.s  7
0x32fd  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x3302  brtrue.s loc_3287
0x3304  leave.s  loc_3312
0x3306  ldloc.s  7
0x3308  brfalse.s loc_3311
0x330a  ldloc.s  7
0x330c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3311  endfinally
0x3312  ldloc.s  6
0x3314  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ScaleGroupApi.Models.SGSecurityRole>::ToArray()
0x3319  ret
```
