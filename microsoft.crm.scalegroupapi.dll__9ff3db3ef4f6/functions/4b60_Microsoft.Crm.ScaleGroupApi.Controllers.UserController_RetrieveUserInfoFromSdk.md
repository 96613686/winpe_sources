# Microsoft.Crm.ScaleGroupApi.Controllers.UserController::RetrieveUserInfoFromSdk

- ea: `0x4b60`
- end: `0x4d5e`
- name: `Microsoft.Crm.ScaleGroupApi.Controllers.UserController::RetrieveUserInfoFromSdk`
- size: `510`
- prototype: ``
- caller_count: `3`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x4990`
- `0x4a10`
- `0x4af0`

## callees

- `0xe80`
- `0xeb0`
- `0x1b00`
- `0x1b20`
- `0x1b40`
- `0x1b60`
- `0x1b80`
- `0x1ba0`
- `0x1bc0`
- `0x1be0`
- `0x1c00`
- `0x1c20`
- `0x1c40`
- `0x1e30`
- `0x1f70`
- `0x4b60`

## string_xrefs

- `0x4c53`: `roletemplateid`
- `0x4c61`: `roletemplateid`
- `0x4d16`: `issyncwithdirectory`
- `0x4d38`: `accessmode`

## pseudocode

```c

```

## disassembly

```asm
0x4b60  ldarg.1
0x4b61  call     class Microsoft.Crm.ScaleGroupApi.OrganizationSdkProvider Microsoft.Crm.ScaleGroupApi.OrganizationSdkProvider::CreateInstance(valuetype [mscorlib]System.Guid orgId)
0x4b66  stloc.0
0x4b67  ldloc.0
0x4b68  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.ScaleGroupApi.OrganizationSdkProvider::get_Sdk()
0x4b6d  ldstr    aSystemuser// "systemuser"
0x4b72  ldarg.0
0x4b73  ldc.i4.1
0x4b74  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(bool)
0x4b79  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Retrieve(string, valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet)
0x4b7e  stloc.1
0x4b7f  ldloc.1
0x4b80  brtrue.s loc_4B8A
0x4b82  ldnull
0x4b83  stloc.s  4
0x4b85  leave    loc_4D5B
0x4b8a  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor()
0x4b8f  stloc.2
0x4b90  ldloc.2
0x4b91  ldstr    aRole// "role"
0x4b96  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_EntityName(string)
0x4b9b  ldloc.2
0x4b9c  ldc.i4.1
0x4b9d  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(bool)
0x4ba2  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_ColumnSet(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet)
0x4ba7  ldloc.2
0x4ba8  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_LinkEntities()
0x4bad  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity::.ctor()
0x4bb2  dup
0x4bb3  ldstr    aRole// "role"
0x4bb8  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity::set_LinkFromEntityName(string)
0x4bbd  dup
0x4bbe  ldstr    aRoleid// "roleid"
0x4bc3  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity::set_LinkFromAttributeName(string)
0x4bc8  dup
0x4bc9  ldstr    aSystemuserrole// "systemuserroles"
0x4bce  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity::set_LinkToEntityName(string)
0x4bd3  dup
0x4bd4  ldstr    aRoleid// "roleid"
0x4bd9  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity::set_LinkToAttributeName(string)
0x4bde  dup
0x4bdf  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::.ctor()
0x4be4  dup
0x4be5  ldc.i4.0
0x4be6  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::set_FilterOperator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator)
0x4beb  dup
0x4bec  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0x4bf1  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor()
0x4bf6  dup
0x4bf7  ldstr    aSystemuserid// "systemuserid"
0x4bfc  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_AttributeName(string)
0x4c01  dup
0x4c02  ldc.i4.0
0x4c03  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_Operator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0x4c08  dup
0x4c09  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<object> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::get_Values()
0x4c0e  ldarg.0
0x4c0f  box      [mscorlib]System.Guid
0x4c14  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<object>::Add(var<u1>)
0x4c19  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::Add(var<u1>)
0x4c1e  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity::set_LinkCriteria(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression)
0x4c23  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity>::Add(var<u1>)
0x4c28  newobj   instance void Microsoft.Crm.ScaleGroupApi.Models.SGUser::.ctor()
0x4c2d  stloc.3
0x4c2e  ldloc.0
0x4c2f  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.ScaleGroupApi.OrganizationSdkProvider::get_Sdk()
0x4c34  ldloc.2
0x4c35  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::RetrieveMultiple(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryBase)
0x4c3a  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x4c3f  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::GetEnumerator()
0x4c44  stloc.s  5
0x4c46  br.s     loc_4C7A
0x4c48  ldloc.s  5
0x4c4a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Current()
0x4c4f  stloc.s  6
0x4c51  ldloc.s  6
0x4c53  ldstr    aRoletemplateid// "roletemplateid"
0x4c58  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x4c5d  brfalse.s loc_4C7A
0x4c5f  ldloc.s  6
0x4c61  ldstr    aRoletemplateid// "roletemplateid"
0x4c66  callvirt T0x2B000012
0x4c6b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x4c70  stloc.s  7
0x4c72  ldloc.3
0x4c73  ldloc.s  7
0x4c75  callvirt instance void Microsoft.Crm.ScaleGroupApi.Models.SGUser::AddRole(valuetype [mscorlib]System.Guid roleTemplateId)
0x4c7a  ldloc.s  5
0x4c7c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4c81  brtrue.s loc_4C48
0x4c83  leave.s  loc_4C91
0x4c85  ldloc.s  5
0x4c87  brfalse.s loc_4C90
0x4c89  ldloc.s  5
0x4c8b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4c90  endfinally
0x4c91  ldloc.3
0x4c92  ldarg.0
0x4c93  callvirt instance void Microsoft.Crm.ScaleGroupApi.Models.SGUser::set_CrmUserId(valuetype [mscorlib]System.Guid value)
0x4c98  ldloc.3
0x4c99  ldloc.1
0x4c9a  ldstr    aDomainname// "domainname"
0x4c9f  callvirt T0x2B000014
0x4ca4  callvirt instance void Microsoft.Crm.ScaleGroupApi.Models.SGUser::set_DomainName(string value)
0x4ca9  ldloc.3
0x4caa  ldloc.1
0x4cab  ldstr    aFullname// "fullname"
0x4cb0  callvirt T0x2B000014
0x4cb5  callvirt instance void Microsoft.Crm.ScaleGroupApi.Models.SGUser::set_FullName(string value)
0x4cba  ldloc.3
0x4cbb  ldloc.1
0x4cbc  ldstr    aCaltype// "caltype"
0x4cc1  callvirt T0x2B00002B
0x4cc6  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0x4ccb  callvirt instance void Microsoft.Crm.ScaleGroupApi.Models.SGUser::set_CalType(int32 value)
0x4cd0  ldloc.3
0x4cd1  ldloc.1
0x4cd2  ldstr    aWindowsliveid// "windowsliveid"
0x4cd7  callvirt T0x2B000014
0x4cdc  callvirt instance void Microsoft.Crm.ScaleGroupApi.Models.SGUser::set_WindowsLiveID(string value)
0x4ce1  ldloc.3
0x4ce2  ldloc.1
0x4ce3  ldstr    aInternalemaila// "internalemailaddress"
0x4ce8  callvirt T0x2B000014
0x4ced  callvirt instance void Microsoft.Crm.ScaleGroupApi.Models.SGUser::set_InternalEmailAddress(string value)
0x4cf2  ldloc.3
0x4cf3  ldloc.1
0x4cf4  ldstr    aIslicensed// "islicensed"
0x4cf9  callvirt T0x2B000020
0x4cfe  callvirt instance void Microsoft.Crm.ScaleGroupApi.Models.SGUser::set_IsLicensed(bool value)
0x4d03  ldloc.3
0x4d04  ldloc.1
0x4d05  ldstr    aIsdisabled// "isdisabled"
0x4d0a  callvirt T0x2B000020
0x4d0f  callvirt instance void Microsoft.Crm.ScaleGroupApi.Models.SGUser::set_IsDisabled(bool value)
0x4d14  ldloc.3
0x4d15  ldloc.1
0x4d16  ldstr    aIssyncwithdire// "issyncwithdirectory"
0x4d1b  callvirt T0x2B000020
0x4d20  callvirt instance void Microsoft.Crm.ScaleGroupApi.Models.SGUser::set_IsSyncWithDirectory(bool value)
0x4d25  ldloc.3
0x4d26  ldloc.1
0x4d27  ldstr    aUserlicensetyp// "userlicensetype"
0x4d2c  callvirt T0x2B000013
0x4d31  callvirt instance void Microsoft.Crm.ScaleGroupApi.Models.SGUser::set_UserLicenseType(int32 value)
0x4d36  ldloc.3
0x4d37  ldloc.1
0x4d38  ldstr    aAccessmode// "accessmode"
0x4d3d  callvirt T0x2B00002B
0x4d42  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0x4d47  callvirt instance void Microsoft.Crm.ScaleGroupApi.Models.SGUser::set_AccessMode(int32 value)
0x4d4c  ldloc.3
0x4d4d  stloc.s  4
0x4d4f  leave.s  loc_4D5B
0x4d51  ldloc.0
0x4d52  brfalse.s loc_4D5A
0x4d54  ldloc.0
0x4d55  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4d5a  endfinally
0x4d5b  ldloc.s  4
0x4d5d  ret
```
