# Microsoft.Xrm.Sdk.Utility.ConfigurationProviderFactory::CreateConfigurationProvider_0

- ea: `0x4a0`
- end: `0x4e8`
- name: `Microsoft.Xrm.Sdk.Utility.ConfigurationProviderFactory::CreateConfigurationProvider_0`
- size: `72`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x490`

## callees

- `0x10`
- `0x4a0`
- `0x4f0`

## pseudocode

```c

```

## disassembly

```asm
0x4a0  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x4a5  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x4aa  ldc.i4.2
0x4ab  beq.s    loc_4B4
0x4ad  ldarg.0
0x4ae  call     class Microsoft.Xrm.Sdk.Utility.ConfigurationProvider Microsoft.Xrm.Sdk.Utility.ConfigurationProviderFactory::CreateConfigurationProviderInternal(valuetype Microsoft.Xrm.Sdk.Utility.ProviderType serviceType)
0x4b3  ret
0x4b4  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x4b9  ldstr    aDiscoveryrole// "DiscoveryRole"
0x4be  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider::GetServerSetting(string)
0x4c3  stloc.0
0x4c4  ldloc.0
0x4c5  brfalse.s loc_4DA
0x4c7  ldarg.0
0x4c8  call     class Microsoft.Xrm.Sdk.Utility.ConfigurationProvider Microsoft.Xrm.Sdk.Utility.ConfigurationProviderFactory::CreateConfigurationProviderInternal(valuetype Microsoft.Xrm.Sdk.Utility.ProviderType serviceType)
0x4cd  dup
0x4ce  ldloc.0
0x4cf  unbox.any [Microsoft.Crm.Core]Microsoft.Crm.DiscoveryRole
0x4d4  callvirt instance void Microsoft.Xrm.Sdk.Utility.ConfigurationProvider::set_DiscoveryRole(valuetype [Microsoft.Crm.Core]Microsoft.Crm.DiscoveryRole value)
0x4d9  ret
0x4da  ldarg.0
0x4db  call     class Microsoft.Xrm.Sdk.Utility.ConfigurationProvider Microsoft.Xrm.Sdk.Utility.ConfigurationProviderFactory::CreateConfigurationProviderInternal(valuetype Microsoft.Xrm.Sdk.Utility.ProviderType serviceType)
0x4e0  dup
0x4e1  ldc.i4.0
0x4e2  callvirt instance void Microsoft.Xrm.Sdk.Utility.ConfigurationProvider::set_DiscoveryRole(valuetype [Microsoft.Crm.Core]Microsoft.Crm.DiscoveryRole value)
0x4e7  ret
```
