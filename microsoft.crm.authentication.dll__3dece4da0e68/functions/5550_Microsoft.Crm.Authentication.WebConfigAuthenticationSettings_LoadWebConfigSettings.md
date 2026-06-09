# Microsoft.Crm.Authentication.WebConfigAuthenticationSettings::LoadWebConfigSettings

- ea: `0x5550`
- end: `0x5598`
- name: `Microsoft.Crm.Authentication.WebConfigAuthenticationSettings::LoadWebConfigSettings`
- size: `72`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x5520`

## callees

- `0x51e0`
- `0x51f0`
- `0x5210`
- `0x5550`

## pseudocode

```c

```

## disassembly

```asm
0x5550  ldstr    aCrmAuthenticat// "crm.authentication"
0x5555  call     object [System.Web]System.Web.Configuration.WebConfigurationManager::GetWebApplicationSection(string)
0x555a  stloc.0
0x555b  ldloc.0
0x555c  brfalse.s loc_556C
0x555e  ldarg.0
0x555f  ldloc.0
0x5560  castclass Microsoft.Crm.Authentication.AuthenticationSettingsXml
0x5565  stfld    class Microsoft.Crm.Authentication.AuthenticationSettingsXml Microsoft.Crm.Authentication.WebConfigAuthenticationSettings::_settingsXml
0x556a  br.s     loc_5577
0x556c  ldarg.0
0x556d  newobj   instance void Microsoft.Crm.Authentication.AuthenticationSettingsXml::.ctor()
0x5572  stfld    class Microsoft.Crm.Authentication.AuthenticationSettingsXml Microsoft.Crm.Authentication.WebConfigAuthenticationSettings::_settingsXml
0x5577  ldarg.0
0x5578  ldfld    class Microsoft.Crm.Authentication.AuthenticationSettingsXml Microsoft.Crm.Authentication.WebConfigAuthenticationSettings::_settingsXml
0x557d  callvirt instance bool Microsoft.Crm.Authentication.AuthenticationSettingsXml::get_IfdDisabledSpecified()
0x5582  brfalse.s loc_5597
0x5584  ldarg.0
0x5585  ldfld    class Microsoft.Crm.Authentication.AuthenticationSettingsXml Microsoft.Crm.Authentication.WebConfigAuthenticationSettings::_settingsXml
0x558a  callvirt instance bool Microsoft.Crm.Authentication.AuthenticationSettingsXml::get_IfdDisabled()
0x558f  brfalse.s loc_5597
0x5591  ldc.i4.0
0x5592  call     void [Microsoft.Crm.Core]Microsoft.Crm.AuthenticationType::set_IfdEnabled(bool)
0x5597  ret
```
