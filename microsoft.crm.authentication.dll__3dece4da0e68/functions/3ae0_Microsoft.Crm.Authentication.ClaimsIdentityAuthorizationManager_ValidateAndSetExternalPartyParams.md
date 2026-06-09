# Microsoft.Crm.Authentication.ClaimsIdentityAuthorizationManager::ValidateAndSetExternalPartyParams

- ea: `0x3ae0`
- end: `0x3b08`
- name: `Microsoft.Crm.Authentication.ClaimsIdentityAuthorizationManager::ValidateAndSetExternalPartyParams`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x3800`

## callees

- `0x1e30`
- `0x1ee0`
- `0x3ae0`

## pseudocode

```c

```

## disassembly

```asm
0x3ae0  ldarg.0
0x3ae1  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.UserType Microsoft.Crm.Authentication.UserIdentityAuthorizationManager::GetUserType(class [System.ServiceModel]System.ServiceModel.OperationContext context)
0x3ae6  stloc.0
0x3ae7  ldloc.0
0x3ae8  ldc.i4.1
0x3ae9  bne.un.s loc_3B00
0x3aeb  ldarg.0
0x3aec  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Authentication.UserIdentityAuthorizationManager::GetCallerRegardingObjectId(class [System.ServiceModel]System.ServiceModel.OperationContext context)
0x3af1  stloc.1
0x3af2  ldarg.1
0x3af3  ldarg.2
0x3af4  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.CrmIdentity::set_CallerId(valuetype [mscorlib]System.Guid)
0x3af9  ldarg.1
0x3afa  ldloc.1
0x3afb  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.UserIdentity::set_CallerRegardingObjectId(valuetype [mscorlib]System.Guid)
0x3b00  ldarg.1
0x3b01  ldloc.0
0x3b02  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.UserIdentity::set_UserType(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.UserType)
0x3b07  ret
```
