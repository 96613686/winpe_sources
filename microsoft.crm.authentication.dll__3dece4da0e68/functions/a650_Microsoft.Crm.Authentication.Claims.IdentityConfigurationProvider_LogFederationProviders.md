# Microsoft.Crm.Authentication.Claims.IdentityConfigurationProvider::LogFederationProviders

- ea: `0xa650`
- end: `0xa67f`
- name: `Microsoft.Crm.Authentication.Claims.IdentityConfigurationProvider::LogFederationProviders`
- size: `47`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x149c0`

## callees

- `0xa650`
- `0xa680`

## pseudocode

```c

```

## disassembly

```asm
0xa650  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0xa655  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0xa65a  ldc.i4.2
0xa65b  beq.s    loc_A668
0xa65d  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.CrmAuthenticationContext::get_DefaultFederationProvider()
0xa662  ldarg.0
0xa663  call     void Microsoft.Crm.Authentication.Claims.IdentityConfigurationProvider::LogFederationProvider(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag federationProvider, class [mscorlib]System.Text.StringBuilder messageBuilder)
0xa668  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.CrmAuthenticationContext::get_OrgIdFederationProvider()
0xa66d  ldarg.0
0xa66e  call     void Microsoft.Crm.Authentication.Claims.IdentityConfigurationProvider::LogFederationProvider(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag federationProvider, class [mscorlib]System.Text.StringBuilder messageBuilder)
0xa673  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.CrmAuthenticationContext::get_AzureActiveDirectoryFederationProvider()
0xa678  ldarg.0
0xa679  call     void Microsoft.Crm.Authentication.Claims.IdentityConfigurationProvider::LogFederationProvider(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag federationProvider, class [mscorlib]System.Text.StringBuilder messageBuilder)
0xa67e  ret
```
