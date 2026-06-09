# Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager::RemoveSessionTokenFromCache

- ea: `0xe660`
- end: `0xe6d9`
- name: `Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager::RemoveSessionTokenFromCache`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0xd5d0`
- `0xe570`

## string_xrefs

- `0xe661`: `token`

## pseudocode

```c

```

## disassembly

```asm
0xe660  ldarg.1
0xe661  ldstr    aToken// "token"
0xe666  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xe66b  ldarg.0
0xe66c  call     instance class [System.IdentityModel.Services]System.IdentityModel.Services.Configuration.FederationConfiguration [System.IdentityModel.Services]System.IdentityModel.Services.HttpModuleBase::get_FederationConfiguration()
0xe671  callvirt instance class [System.IdentityModel]System.IdentityModel.Configuration.IdentityConfiguration [System.IdentityModel.Services]System.IdentityModel.Services.Configuration.FederationConfiguration::get_IdentityConfiguration()
0xe676  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollectionManager [System.IdentityModel]System.IdentityModel.Configuration.IdentityConfiguration::get_SecurityTokenHandlerCollectionManager()
0xe67b  ldstr    asc_1DBD8// ""
0xe680  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollection [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollectionManager::get_Item(string)
0xe685  ldtoken  [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityToken
0xe68a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe68f  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandler [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollection::get_Item(class [mscorlib]System.Type)
0xe694  isinst   [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityTokenHandler
0xe699  ldstr    aHandler// "handler"
0xe69e  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xe6a3  ldarg.1
0xe6a4  stloc.0
0xe6a5  ldloc.0
0xe6a6  callvirt instance string [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityToken::get_EndpointId()
0xe6ab  ldloc.0
0xe6ac  callvirt instance class [System.Runtime.Serialization]System.Xml.UniqueId [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityToken::get_ContextId()
0xe6b1  ldloc.0
0xe6b2  callvirt instance class [System.Runtime.Serialization]System.Xml.UniqueId [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityToken::get_KeyGeneration()
0xe6b7  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityTokenCacheKey::.ctor(string, class [System.Runtime.Serialization]System.Xml.UniqueId, class [System.Runtime.Serialization]System.Xml.UniqueId)
0xe6bc  stloc.1
0xe6bd  ldarg.0
0xe6be  call     instance class [System.IdentityModel.Services]System.IdentityModel.Services.Configuration.FederationConfiguration [System.IdentityModel.Services]System.IdentityModel.Services.HttpModuleBase::get_FederationConfiguration()
0xe6c3  callvirt instance class [System.IdentityModel]System.IdentityModel.Configuration.IdentityConfiguration [System.IdentityModel.Services]System.IdentityModel.Services.Configuration.FederationConfiguration::get_IdentityConfiguration()
0xe6c8  callvirt instance class [System.IdentityModel]System.IdentityModel.Configuration.IdentityModelCaches [System.IdentityModel]System.IdentityModel.Configuration.IdentityConfiguration::get_Caches()
0xe6cd  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityTokenCache [System.IdentityModel]System.IdentityModel.Configuration.IdentityModelCaches::get_SessionSecurityTokenCache()
0xe6d2  ldloc.1
0xe6d3  callvirt instance void [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityTokenCache::Remove(class [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityTokenCacheKey)
0xe6d8  ret
```
