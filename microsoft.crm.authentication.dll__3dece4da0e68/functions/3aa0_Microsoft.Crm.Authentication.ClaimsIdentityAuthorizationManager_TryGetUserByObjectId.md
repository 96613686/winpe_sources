# Microsoft.Crm.Authentication.ClaimsIdentityAuthorizationManager::TryGetUserByObjectId

- ea: `0x3aa0`
- end: `0x3adf`
- name: `Microsoft.Crm.Authentication.ClaimsIdentityAuthorizationManager::TryGetUserByObjectId`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x3950`

## callees

- `0x1570`
- `0x15b0`
- `0x2000`
- `0x3aa0`

## pseudocode

```c

```

## disassembly

```asm
0x3aa0  ldarg.2
0x3aa1  initobj  Microsoft.Crm.Authentication.CrmUserInfo
0x3aa7  ldarg.1
0x3aa8  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3aad  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3ab2  brfalse.s loc_3AC1
0x3ab4  ldarg.2
0x3ab5  ldarg.1
0x3ab6  ldarg.0
0x3ab7  call     valuetype Microsoft.Crm.Authentication.CrmUserInfo Microsoft.Crm.Authentication.UserIdentityAuthorizationManager::RetrieveUserByObjectId(valuetype [mscorlib]System.Guid directoryObjectId, valuetype [mscorlib]System.Guid organizationId)
0x3abc  stobj    Microsoft.Crm.Authentication.CrmUserInfo
0x3ac1  ldarg.2
0x3ac2  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Authentication.CrmUserInfo::get_UserId()
0x3ac7  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3acc  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3ad1  brfalse.s loc_3ADD
0x3ad3  ldarg.2
0x3ad4  call     instance valuetype Microsoft.Crm.Authentication.SystemUserType Microsoft.Crm.Authentication.CrmUserInfo::get_SystemUserType()
0x3ad9  brtrue.s loc_3ADD
0x3adb  ldc.i4.1
0x3adc  ret
0x3add  ldc.i4.0
0x3ade  ret
```
