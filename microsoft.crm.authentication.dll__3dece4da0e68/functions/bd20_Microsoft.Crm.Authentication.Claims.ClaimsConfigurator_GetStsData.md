# Microsoft.Crm.Authentication.Claims.ClaimsConfigurator::GetStsData

- ea: `0xbd20`
- end: `0xbd74`
- name: `Microsoft.Crm.Authentication.Claims.ClaimsConfigurator::GetStsData`
- size: `84`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0xb7f0`
- `0xb9e0`

## callees

- `0x8c30`
- `0xbba0`
- `0xbcd0`
- `0xbd20`

## pseudocode

```c

```

## disassembly

```asm
0xbd20  ldarg.0
0xbd21  ldstr    aFederationprov// "federationProviderId"
0xbd26  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0xbd2b  ldarg.1
0xbd2c  ldstr    aStsurl// "stsUrl"
0xbd31  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xbd36  ldarga.s 0
0xbd38  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmFederationProviderService::get_AzureActiveDirectoryFederationProviderId()
0xbd3d  call     instance bool [mscorlib]System.Guid::Equals(valuetype [mscorlib]System.Guid)
0xbd42  brfalse.s loc_BD58
0xbd44  ldc.i4.2
0xbd45  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0xbd4a  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0xbd4f  bne.un.s loc_BD58
0xbd51  ldarg.1
0xbd52  call     class Microsoft.Crm.Authentication.Claims.StsData Microsoft.Crm.Authentication.Claims.ClaimsConfigurator::RetrieveStsDataFromOpenId(class [System]System.Uri serviceEndpoint)
0xbd57  ret
0xbd58  ldarga.s 0
0xbd5a  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmFederationProviderService::get_ExchangeTokenServerFederationProviderId()
0xbd5f  call     instance bool [mscorlib]System.Guid::Equals(valuetype [mscorlib]System.Guid)
0xbd64  brfalse.s loc_BD6D
0xbd66  ldarg.1
0xbd67  call     class Microsoft.Crm.Authentication.Claims.StsData Microsoft.Crm.Authentication.Claims.ExchangeAuthMetadataDocument::RetrieveStsDataFromExchange(class [System]System.Uri serviceEndpoint)
0xbd6c  ret
0xbd6d  ldarg.1
0xbd6e  call     class Microsoft.Crm.Authentication.Claims.StsData Microsoft.Crm.Authentication.Claims.ClaimsConfigurator::RetrieveStsDataFromMetadatUrl(class [System]System.Uri serviceEndpoint)
0xbd73  ret
```
