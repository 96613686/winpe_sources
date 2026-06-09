# Microsoft.Crm.Authentication.Claims.IdentityConfigurationProvider::Initialize

- ea: `0xa390`
- end: `0xa3c6`
- name: `Microsoft.Crm.Authentication.Claims.IdentityConfigurationProvider::Initialize`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0xa390`
- `0xce20`
- `0xea00`

## pseudocode

```c

```

## disassembly

```asm
0xa390  ldarg.0
0xa391  ldstr    aContext// "context"
0xa396  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xa39b  call     class [System.IdentityModel.Services]System.IdentityModel.Services.WSFederationAuthenticationModule [System.IdentityModel.Services]System.IdentityModel.Services.FederatedAuthentication::get_WSFederationAuthenticationModule()
0xa3a0  isinst   Microsoft.Crm.Authentication.Claims.CrmFederatedAuthenticationModule
0xa3a5  stloc.0
0xa3a6  ldloc.0
0xa3a7  brfalse.s loc_A3B0
0xa3a9  ldloc.0
0xa3aa  ldarg.0
0xa3ab  callvirt instance void Microsoft.Crm.Authentication.Claims.CrmFederatedAuthenticationModule::Initialize(class [System.Web]System.Web.HttpApplication context)
0xa3b0  call     class [System.IdentityModel.Services]System.IdentityModel.Services.SessionAuthenticationModule [System.IdentityModel.Services]System.IdentityModel.Services.FederatedAuthentication::get_SessionAuthenticationModule()
0xa3b5  isinst   Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager
0xa3ba  stloc.1
0xa3bb  ldloc.1
0xa3bc  brfalse.s loc_A3C5
0xa3be  ldloc.1
0xa3bf  ldarg.0
0xa3c0  callvirt instance void Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager::Initialize(class [System.Web]System.Web.HttpApplication context)
0xa3c5  ret
```
