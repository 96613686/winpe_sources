# Microsoft.Crm.Authentication.UserIdentityAuthorizationManager::UpdateAccessTime

- ea: `0x2020`
- end: `0x2036`
- name: `Microsoft.Crm.Authentication.UserIdentityAuthorizationManager::UpdateAccessTime`
- size: `22`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x31b0`
- `0xc910`

## callees

- `0x2020`
- `0x20a0`
- `0x21d0`

## pseudocode

```c

```

## disassembly

```asm
0x2020  call     class Microsoft.Crm.Authentication.IUserIdentityAuthorizationProvider Microsoft.Crm.Authentication.UserIdentityAuthorizationManager::get_OrganizationAuthenticationProvider()
0x2025  brfalse.s loc_2035
0x2027  call     class Microsoft.Crm.Authentication.IUserIdentityAuthorizationProvider Microsoft.Crm.Authentication.UserIdentityAuthorizationManager::get_OrganizationAuthenticationProvider()
0x202c  ldarg.0
0x202d  ldarg.1
0x202e  ldarg.2
0x202f  ldarg.3
0x2030  callvirt instance void Microsoft.Crm.Authentication.IUserIdentityAuthorizationProvider::UpdateAccessTime(valuetype [mscorlib]System.Guid userId, valuetype [mscorlib]System.Guid organizationId, valuetype Microsoft.Crm.Authentication.UserAuthenticationAccessType accessType, valuetype [mscorlib]System.DateTime accessTime)
0x2035  ret
```
