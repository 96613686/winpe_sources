# Microsoft.Crm.Dialogs.EditFieldPermissionDialogPage::HandleGrant

- ea: `0x17880`
- end: `0x17ac6`
- name: `Microsoft.Crm.Dialogs.EditFieldPermissionDialogPage::HandleGrant`
- size: `582`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x17430`

## callees

- `0x17840`
- `0x17880`

## string_xrefs

- `0x17880`: `principalobjectattributeaccess`
- `0x1798a`: `principalobjectattributeaccess`
- `0x17a21`: `principalobjectattributeaccess`
- `0x17899`: `readaccess`
- `0x179b0`: `readaccess`
- `0x179f0`: `readaccess`
- `0x17aa1`: `readaccess`
- `0x178a1`: `updateaccess`
- `0x179d1`: `updateaccess`
- `0x179fe`: `updateaccess`
- `0x17aaf`: `updateaccess`
- `0x178a9`: `principalobjectattributeaccessid`
- `0x17990`: `principalobjectattributeaccessid`
- `0x17a32`: `principalobjectattributeaccessid`

## pseudocode

```c

```

## disassembly

```asm
0x17880  ldstr    aPrincipalobjec// "principalobjectattributeaccess"
0x17885  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::.ctor(string)
0x1788a  stloc.0
0x1788b  ldloc.0
0x1788c  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x17891  ldc.i4.3
0x17892  newarr   [mscorlib]System.String
0x17897  dup
0x17898  ldc.i4.0
0x17899  ldstr    aReadaccess// "readaccess"
0x1789e  stelem.ref
0x1789f  dup
0x178a0  ldc.i4.1
0x178a1  ldstr    aUpdateaccess// "updateaccess"
0x178a6  stelem.ref
0x178a7  dup
0x178a8  ldc.i4.2
0x178a9  ldstr    aPrincipalobjec_0// "principalobjectattributeaccessid"
0x178ae  stelem.ref
0x178af  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumns(string[])
0x178b4  ldloc.0
0x178b5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x178ba  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::get_Conditions()
0x178bf  ldstr    aPrincipalid_0// "principalid"
0x178c4  ldc.i4.0
0x178c5  ldarg.1
0x178c6  box      [mscorlib]System.Guid
0x178cb  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x178d0  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x178d5  pop
0x178d6  ldloc.0
0x178d7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x178dc  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::get_Conditions()
0x178e1  ldstr    aPrincipalidtyp// "principalidtype"
0x178e6  ldc.i4.0
0x178e7  ldarg.2
0x178e8  box      [mscorlib]System.Int32
0x178ed  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x178f2  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x178f7  pop
0x178f8  ldloc.0
0x178f9  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x178fe  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::get_Conditions()
0x17903  ldstr    aObjectid_0// "objectid"
0x17908  ldc.i4.0
0x17909  ldarg.3
0x1790a  box      [mscorlib]System.Guid
0x1790f  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x17914  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x17919  pop
0x1791a  ldloc.0
0x1791b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x17920  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::get_Conditions()
0x17925  ldstr    aObjecttypecode// "objecttypecode"
0x1792a  ldc.i4.0
0x1792b  ldarg.s  4
0x1792d  box      [mscorlib]System.Int32
0x17932  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x17937  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x1793c  pop
0x1793d  ldloc.0
0x1793e  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x17943  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::get_Conditions()
0x17948  ldstr    aAttributeid// "attributeid"
0x1794d  ldc.i4.0
0x1794e  ldarg.s  5
0x17950  box      [mscorlib]System.Guid
0x17955  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x1795a  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x1795f  pop
0x17960  ldloc.0
0x17961  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x17966  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1796b  stloc.1
0x1796c  ldloc.1
0x1796d  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x17972  ldc.i4.0
0x17973  ble      loc_17A14
0x17978  ldloc.1
0x17979  ldc.i4.0
0x1797a  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0x1797f  stloc.2
0x17980  ldarg.s  6
0x17982  ldc.i4.1
0x17983  beq.s    loc_179AA
0x17985  ldarg.s  7
0x17987  ldc.i4.1
0x17988  beq.s    loc_179AA
0x1798a  ldstr    aPrincipalobjec// "principalobjectattributeaccess"
0x1798f  ldloc.2
0x17990  ldstr    aPrincipalobjec_0// "principalobjectattributeaccessid"
0x17995  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x1799a  unbox.any [mscorlib]System.Guid
0x1799f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x179a4  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Delete(string, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x179a9  ret
0x179aa  ldarg.s  6
0x179ac  ldc.i4.2
0x179ad  beq.s    loc_179C8
0x179af  ldloc.2
0x179b0  ldstr    aReadaccess// "readaccess"
0x179b5  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x179ba  unbox.any [mscorlib]System.Boolean
0x179bf  ldarg.s  6
0x179c1  call     bool [mscorlib]System.Convert::ToBoolean(int32)
0x179c6  bne.un.s loc_179EC
0x179c8  ldarg.s  7
0x179ca  ldc.i4.2
0x179cb  beq      loc_17AC5
0x179d0  ldloc.2
0x179d1  ldstr    aUpdateaccess// "updateaccess"
0x179d6  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x179db  unbox.any [mscorlib]System.Boolean
0x179e0  ldarg.s  7
0x179e2  call     bool [mscorlib]System.Convert::ToBoolean(int32)
0x179e7  beq      loc_17AC5
0x179ec  ldarg.0
0x179ed  ldarg.s  6
0x179ef  ldloc.2
0x179f0  ldstr    aReadaccess// "readaccess"
0x179f5  call     instance void Microsoft.Crm.Dialogs.EditFieldPermissionDialogPage::SetStatePOAA(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FieldLevelSecurityAccess state, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity entity, string columnName)
0x179fa  ldarg.0
0x179fb  ldarg.s  7
0x179fd  ldloc.2
0x179fe  ldstr    aUpdateaccess// "updateaccess"
0x17a03  call     instance void Microsoft.Crm.Dialogs.EditFieldPermissionDialogPage::SetStatePOAA(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FieldLevelSecurityAccess state, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity entity, string columnName)
0x17a08  ldloc.2
0x17a09  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x17a0e  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Update(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x17a13  ret
0x17a14  ldarg.s  6
0x17a16  ldc.i4.1
0x17a17  beq.s    loc_17A21
0x17a19  ldarg.s  7
0x17a1b  ldc.i4.1
0x17a1c  bne.un   loc_17AC5
0x17a21  ldstr    aPrincipalobjec// "principalobjectattributeaccess"
0x17a26  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x17a2b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x17a30  stloc.3
0x17a31  ldloc.3
0x17a32  ldstr    aPrincipalobjec_0// "principalobjectattributeaccessid"
0x17a37  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.SequentialGuid::CreateGuid()
0x17a3c  box      [mscorlib]System.Guid
0x17a41  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x17a46  ldloc.3
0x17a47  ldstr    aPrincipalid_0// "principalid"
0x17a4c  ldarg.1
0x17a4d  box      [mscorlib]System.Guid
0x17a52  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x17a57  ldloc.3
0x17a58  ldstr    aPrincipalidtyp// "principalidtype"
0x17a5d  ldarg.2
0x17a5e  box      [mscorlib]System.Int32
0x17a63  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x17a68  ldloc.3
0x17a69  ldstr    aObjectid_0// "objectid"
0x17a6e  ldarg.3
0x17a6f  box      [mscorlib]System.Guid
0x17a74  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x17a79  ldloc.3
0x17a7a  ldstr    aObjecttypecode// "objecttypecode"
0x17a7f  ldarg.s  4
0x17a81  box      [mscorlib]System.Int32
0x17a86  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x17a8b  ldloc.3
0x17a8c  ldstr    aAttributeid// "attributeid"
0x17a91  ldarg.s  5
0x17a93  box      [mscorlib]System.Guid
0x17a98  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x17a9d  ldarg.0
0x17a9e  ldarg.s  6
0x17aa0  ldloc.3
0x17aa1  ldstr    aReadaccess// "readaccess"
0x17aa6  call     instance void Microsoft.Crm.Dialogs.EditFieldPermissionDialogPage::SetStatePOAA(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FieldLevelSecurityAccess state, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity entity, string columnName)
0x17aab  ldarg.0
0x17aac  ldarg.s  7
0x17aae  ldloc.3
0x17aaf  ldstr    aUpdateaccess// "updateaccess"
0x17ab4  call     instance void Microsoft.Crm.Dialogs.EditFieldPermissionDialogPage::SetStatePOAA(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FieldLevelSecurityAccess state, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity entity, string columnName)
0x17ab9  ldloc.3
0x17aba  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x17abf  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Create(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x17ac4  pop
0x17ac5  ret
```
