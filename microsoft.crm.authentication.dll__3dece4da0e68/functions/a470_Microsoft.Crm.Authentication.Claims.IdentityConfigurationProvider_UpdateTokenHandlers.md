# Microsoft.Crm.Authentication.Claims.IdentityConfigurationProvider::UpdateTokenHandlers

- ea: `0xa470`
- end: `0xa5df`
- name: `Microsoft.Crm.Authentication.Claims.IdentityConfigurationProvider::UpdateTokenHandlers`
- size: `367`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x149c0`

## callees

- `0x87e0`
- `0x9bc0`
- `0x9cc0`
- `0xa470`
- `0xa5e0`
- `0xab70`
- `0xe040`
- `0x109c0`

## pseudocode

```c

```

## disassembly

```asm
0xa470  ldarg.0
0xa471  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollectionManager [System.IdentityModel]System.IdentityModel.Configuration.IdentityConfiguration::get_SecurityTokenHandlerCollectionManager()
0xa476  ldstr    asc_1DBD8// ""
0xa47b  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollection [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollectionManager::get_Item(string)
0xa480  call     T0x2B000019
0xa485  stloc.0
0xa486  ldarg.0
0xa487  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollectionManager [System.IdentityModel]System.IdentityModel.Configuration.IdentityConfiguration::get_SecurityTokenHandlerCollectionManager()
0xa48c  ldstr    asc_1DBD8// ""
0xa491  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollection [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollectionManager::get_Item(string)
0xa496  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollection::get_Configuration()
0xa49b  stloc.1
0xa49c  ldarg.0
0xa49d  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollectionManager [System.IdentityModel]System.IdentityModel.Configuration.IdentityConfiguration::get_SecurityTokenHandlerCollectionManager()
0xa4a2  ldstr    asc_1DBD8// ""
0xa4a7  ldloc.0
0xa4a8  ldloc.1
0xa4a9  newobj   instance void Microsoft.Crm.Authentication.Claims.CrmSecurityTokenHandlerCollection::.ctor(class [mscorlib]System.Collections.Generic.List`1<class [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandler> handlers, class [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration configuration)
0xa4ae  callvirt instance void [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollectionManager::set_Item(string, class [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollection)
0xa4b3  ldarg.0
0xa4b4  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollectionManager [System.IdentityModel]System.IdentityModel.Configuration.IdentityConfiguration::get_SecurityTokenHandlerCollectionManager()
0xa4b9  ldstr    asc_1DBD8// ""
0xa4be  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollection [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollectionManager::get_Item(string)
0xa4c3  ldtoken  [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityToken
0xa4c8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa4cd  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandler [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollection::get_Item(class [mscorlib]System.Type)
0xa4d2  stloc.2
0xa4d3  ldloc.2
0xa4d4  brfalse.s loc_A53C
0xa4d6  call     bool [Microsoft.Crm.Core]Microsoft.Crm.CrmAuthenticationContext::get_IsLoadBalanced()
0xa4db  brfalse.s loc_A531
0xa4dd  ldarg.0
0xa4de  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollectionManager [System.IdentityModel]System.IdentityModel.Configuration.IdentityConfiguration::get_SecurityTokenHandlerCollectionManager()
0xa4e3  ldstr    asc_1DBD8// ""
0xa4e8  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollection [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollectionManager::get_Item(string)
0xa4ed  ldloc.2
0xa4ee  callvirt instance bool class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandler>::Remove(var<u1>)
0xa4f3  pop
0xa4f4  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0xa4f9  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0xa4fe  ldc.i4.2
0xa4ff  bne.un.s loc_A50A
0xa501  newobj   instance void Microsoft.Crm.Authentication.Claims.LegacySessionSecurityTokenHandler::.ctor()
0xa506  stloc.s  7
0xa508  br.s     loc_A511
0xa50a  newobj   instance void Microsoft.Crm.Authentication.Claims.RsaEncryptedSessionSecurityTokenHandler::.ctor()
0xa50f  stloc.s  7
0xa511  ldloc.s  7
0xa513  call     void Microsoft.Crm.Authentication.Claims.IdentityConfigurationProvider::SetTokenLifetime(class [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityTokenHandler sessionHandler)
0xa518  ldarg.0
0xa519  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollectionManager [System.IdentityModel]System.IdentityModel.Configuration.IdentityConfiguration::get_SecurityTokenHandlerCollectionManager()
0xa51e  ldstr    asc_1DBD8// ""
0xa523  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollection [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollectionManager::get_Item(string)
0xa528  ldloc.s  7
0xa52a  callvirt instance void [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollection::AddOrReplace(class [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandler)
0xa52f  br.s     loc_A53C
0xa531  ldloc.2
0xa532  isinst   [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityTokenHandler
0xa537  call     void Microsoft.Crm.Authentication.Claims.IdentityConfigurationProvider::SetTokenLifetime(class [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityTokenHandler sessionHandler)
0xa53c  newobj   instance void Microsoft.Crm.Authentication.Claims.SecurityTokenRequirementHandler::.ctor()
0xa541  stloc.3
0xa542  ldarg.0
0xa543  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollectionManager [System.IdentityModel]System.IdentityModel.Configuration.IdentityConfiguration::get_SecurityTokenHandlerCollectionManager()
0xa548  ldstr    asc_1DBD8// ""
0xa54d  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollection [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollectionManager::get_Item(string)
0xa552  ldtoken  [System.IdentityModel]System.IdentityModel.Tokens.SamlSecurityToken
0xa557  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa55c  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandler [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollection::get_Item(class [mscorlib]System.Type)
0xa561  isinst   [System.IdentityModel]System.IdentityModel.Tokens.SamlSecurityTokenHandler
0xa566  stloc.s  4
0xa568  ldloc.s  4
0xa56a  brfalse.s loc_A574
0xa56c  ldloc.s  4
0xa56e  ldloc.3
0xa56f  callvirt instance void [System.IdentityModel]System.IdentityModel.Tokens.SamlSecurityTokenHandler::set_SamlSecurityTokenRequirement(class [System.IdentityModel]System.IdentityModel.Tokens.SamlSecurityTokenRequirement)
0xa574  ldarg.0
0xa575  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollectionManager [System.IdentityModel]System.IdentityModel.Configuration.IdentityConfiguration::get_SecurityTokenHandlerCollectionManager()
0xa57a  ldstr    asc_1DBD8// ""
0xa57f  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollection [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollectionManager::get_Item(string)
0xa584  ldtoken  [System.IdentityModel]System.IdentityModel.Tokens.Saml2SecurityToken
0xa589  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa58e  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandler [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollection::get_Item(class [mscorlib]System.Type)
0xa593  isinst   [System.IdentityModel]System.IdentityModel.Tokens.Saml2SecurityTokenHandler
0xa598  stloc.s  5
0xa59a  ldloc.s  5
0xa59c  brfalse.s loc_A5A6
0xa59e  ldloc.s  5
0xa5a0  ldloc.3
0xa5a1  callvirt instance void [System.IdentityModel]System.IdentityModel.Tokens.Saml2SecurityTokenHandler::set_SamlSecurityTokenRequirement(class [System.IdentityModel]System.IdentityModel.Tokens.SamlSecurityTokenRequirement)
0xa5a6  newobj   instance void Microsoft.Crm.Authentication.Claims.XrmJwtSecurityTokenHandler::.ctor()
0xa5ab  stloc.s  6
0xa5ad  ldarg.0
0xa5ae  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollectionManager [System.IdentityModel]System.IdentityModel.Configuration.IdentityConfiguration::get_SecurityTokenHandlerCollectionManager()
0xa5b3  ldstr    asc_1DBD8// ""
0xa5b8  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollection [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollectionManager::get_Item(string)
0xa5bd  ldloc.s  6
0xa5bf  callvirt instance void [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollection::AddOrReplace(class [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandler)
0xa5c4  ldarg.0
0xa5c5  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollectionManager [System.IdentityModel]System.IdentityModel.Configuration.IdentityConfiguration::get_SecurityTokenHandlerCollectionManager()
0xa5ca  ldstr    asc_1DBD8// ""
0xa5cf  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollection [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollectionManager::get_Item(string)
0xa5d4  newobj   instance void Microsoft.Crm.Authentication.Claims.ExchangeJwtSecurityTokenHandler::.ctor()
0xa5d9  callvirt instance void [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollection::AddOrReplace(class [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandler)
0xa5de  ret
```
