# Microsoft.Crm.Authentication.UserIdentityAuthorizationManager::get_OrganizationAuthenticationProvider

- ea: `0x20a0`
- end: `0x20dd`
- name: `Microsoft.Crm.Authentication.UserIdentityAuthorizationManager::get_OrganizationAuthenticationProvider`
- size: `61`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1fa0`
- `0x1fc0`
- `0x1fe0`
- `0x2000`
- `0x2020`
- `0x2040`
- `0x2070`

## callees

- `0x1900`
- `0x20a0`
- `0x20f0`

## string_xrefs

- `0x20c8`: `Microsoft.Crm.Authentication.UserManagementFactory, Microsoft.Crm.Platform.Server, Version={0}, Culture=neutral, PublicKeyToken=31bf3856ad364e35`

## pseudocode

```c

```

## disassembly

```asm
0x20a0  ldsfld   class [mscorlib]System.Func`1<class Microsoft.Crm.Authentication.IUserIdentityAuthorizationProvider> Microsoft.Crm.Authentication.UserIdentityAuthorizationManager::organizationAuthProviderFactory
0x20a5  brfalse.s loc_20B2
0x20a7  ldsfld   class [mscorlib]System.Func`1<class Microsoft.Crm.Authentication.IUserIdentityAuthorizationProvider> Microsoft.Crm.Authentication.UserIdentityAuthorizationManager::organizationAuthProviderFactory
0x20ac  callvirt instance var<u1> class [mscorlib]System.Func`1<class Microsoft.Crm.Authentication.IUserIdentityAuthorizationProvider>::Invoke()
0x20b1  ret
0x20b2  ldsfld   class Microsoft.Crm.Authentication.IUserIdentityAuthorizationProvider Microsoft.Crm.Authentication.UserIdentityAuthorizationManager::organizationAuthProvider
0x20b7  brtrue.s loc_20D7
0x20b9  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInClientContext()
0x20be  brtrue.s loc_20D7
0x20c0  call     valuetype Microsoft.Crm.Authentication.ServiceType Microsoft.Crm.Authentication.UserIdentityAuthorizationManager::get_CurrentServiceType()
0x20c5  ldc.i4.1
0x20c6  bne.un.s loc_20D7
0x20c8  ldstr    aMicrosoftCrmAu// "Microsoft.Crm.Authentication.UserManage"...
0x20cd  call     class Microsoft.Crm.Authentication.IUserIdentityAuthorizationProvider Microsoft.Crm.Authentication.UserIdentityAuthorizationManager::CreateProvider(string typeName)
0x20d2  stsfld   class Microsoft.Crm.Authentication.IUserIdentityAuthorizationProvider Microsoft.Crm.Authentication.UserIdentityAuthorizationManager::organizationAuthProvider
0x20d7  ldsfld   class Microsoft.Crm.Authentication.IUserIdentityAuthorizationProvider Microsoft.Crm.Authentication.UserIdentityAuthorizationManager::organizationAuthProvider
0x20dc  ret
```
