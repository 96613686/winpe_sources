# Microsoft.Crm.Authentication.Claims.HeaderAuthentication.AllowedServiceToServiceTenant::Initialize

- ea: `0x13d40`
- end: `0x13db1`
- name: `Microsoft.Crm.Authentication.Claims.HeaderAuthentication.AllowedServiceToServiceTenant::Initialize`
- size: `113`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x13ca0`

## callees

- `0x13d40`
- `0x13dc0`
- `0x155f0`

## string_xrefs

- `0x13d6a`: `AzureAdDirectoryServiceUrl`

## pseudocode

```c

```

## disassembly

```asm
0x13d40  ldarg.0
0x13d41  volatile.
0x13d43  ldfld    modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) class RegisteredEnvironment Microsoft.Crm.Authentication.Claims.HeaderAuthentication.AllowedServiceToServiceTenant::_environment
0x13d48  brtrue.s loc_13DB0
0x13d4a  ldarg.0
0x13d4b  ldfld    object Microsoft.Crm.Authentication.Claims.HeaderAuthentication.AllowedServiceToServiceTenant::_lockObject
0x13d50  stloc.0
0x13d51  ldc.i4.0
0x13d52  stloc.1
0x13d53  ldloc.0
0x13d54  ldloca.s 1
0x13d56  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x13d5b  ldarg.0
0x13d5c  volatile.
0x13d5e  ldfld    modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) class RegisteredEnvironment Microsoft.Crm.Authentication.Claims.HeaderAuthentication.AllowedServiceToServiceTenant::_environment
0x13d63  brtrue.s loc_13DA4
0x13d65  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x13d6a  ldstr    aAzureaddirecto// "AzureAdDirectoryServiceUrl"
0x13d6f  ldc.i4.0
0x13d70  callvirt T0x2B000001
0x13d75  stloc.2
0x13d76  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x13d7b  ldstr    aBypassaudience// "BypassAudienceCheckAppIds"
0x13d80  ldc.i4.0
0x13d81  callvirt T0x2B000001
0x13d86  stloc.3
0x13d87  ldloc.3
0x13d88  brfalse.s loc_13D96
0x13d8a  ldarg.0
0x13d8b  ldloc.3
0x13d8c  call     class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, bool> Microsoft.Crm.Authentication.Claims.HeaderAuthentication.AllowedServiceToServiceTenant::GetAppIds(string appIds)
0x13d91  stfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, bool> Microsoft.Crm.Authentication.Claims.HeaderAuthentication.AllowedServiceToServiceTenant::_bypassAudienceCheckAppIds
0x13d96  ldarg.0
0x13d97  ldloc.2
0x13d98  call     class RegisteredEnvironment RegisteredEnvironment::Get(string msodsGraphUrl)
0x13d9d  volatile.
0x13d9f  stfld    modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) class RegisteredEnvironment Microsoft.Crm.Authentication.Claims.HeaderAuthentication.AllowedServiceToServiceTenant::_environment
0x13da4  leave.s  loc_13DB0
0x13da6  ldloc.1
0x13da7  brfalse.s loc_13DAF
0x13da9  ldloc.0
0x13daa  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x13daf  endfinally
0x13db0  ret
```
