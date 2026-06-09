# Microsoft.Crm.Authentication.Claims.HttpHeaderTokenHandler::get_IdentityConfiguration

- ea: `0xf650`
- end: `0xf6a3`
- name: `Microsoft.Crm.Authentication.Claims.HttpHeaderTokenHandler::get_IdentityConfiguration`
- size: `83`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0xf480`
- `0xf600`

## callees

- `0xa440`
- `0xf650`

## pseudocode

```c

```

## disassembly

```asm
0xf650  ldarg.0
0xf651  ldfld    object Microsoft.Crm.Authentication.Claims.HttpHeaderTokenHandler::_objectLock
0xf656  stloc.0
0xf657  ldc.i4.0
0xf658  stloc.1
0xf659  ldloc.0
0xf65a  ldloca.s 1
0xf65c  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0xf661  ldarg.0
0xf662  ldfld    class [System.IdentityModel]System.IdentityModel.Configuration.IdentityConfiguration Microsoft.Crm.Authentication.Claims.HttpHeaderTokenHandler::_identityConfiguration
0xf667  brtrue.s loc_F68E
0xf669  ldarg.0
0xf66a  ldfld    bool Microsoft.Crm.Authentication.Claims.HttpHeaderTokenHandler::_loadCrmServiceConfiguration
0xf66f  brfalse.s loc_F67E
0xf671  ldarg.0
0xf672  call     class [System.IdentityModel]System.IdentityModel.Configuration.IdentityConfiguration Microsoft.Crm.Authentication.Claims.IdentityConfigurationProvider::GetIdentityConfiguration()
0xf677  stfld    class [System.IdentityModel]System.IdentityModel.Configuration.IdentityConfiguration Microsoft.Crm.Authentication.Claims.HttpHeaderTokenHandler::_identityConfiguration
0xf67c  br.s     loc_F68E
0xf67e  ldarg.0
0xf67f  call     class [System.IdentityModel.Services]System.IdentityModel.Services.Configuration.FederationConfiguration [System.IdentityModel.Services]System.IdentityModel.Services.FederatedAuthentication::get_FederationConfiguration()
0xf684  callvirt instance class [System.IdentityModel]System.IdentityModel.Configuration.IdentityConfiguration [System.IdentityModel.Services]System.IdentityModel.Services.Configuration.FederationConfiguration::get_IdentityConfiguration()
0xf689  stfld    class [System.IdentityModel]System.IdentityModel.Configuration.IdentityConfiguration Microsoft.Crm.Authentication.Claims.HttpHeaderTokenHandler::_identityConfiguration
0xf68e  ldarg.0
0xf68f  ldfld    class [System.IdentityModel]System.IdentityModel.Configuration.IdentityConfiguration Microsoft.Crm.Authentication.Claims.HttpHeaderTokenHandler::_identityConfiguration
0xf694  stloc.2
0xf695  leave.s  loc_F6A1
0xf697  ldloc.1
0xf698  brfalse.s loc_F6A0
0xf69a  ldloc.0
0xf69b  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0xf6a0  endfinally
0xf6a1  ldloc.2
0xf6a2  ret
```
