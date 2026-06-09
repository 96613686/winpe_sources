# Microsoft.Crm.Authentication.Claims.ClaimsConfigurator::.cctor

- ea: `0xbd80`
- end: `0xbd91`
- name: `Microsoft.Crm.Authentication.Claims.ClaimsConfigurator::.cctor`
- size: `17`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0xbd80`: `FederationMetadata/2007-06/FederationMetadata.xml`

## pseudocode

```c

```

## disassembly

```asm
0xbd80  ldstr    aFederationmeta// "FederationMetadata/2007-06/FederationMe"...
0xbd85  stsfld   string Microsoft.Crm.Authentication.Claims.ClaimsConfigurator::crmFederationMetadataPath
0xbd8a  ldnull
0xbd8b  stsfld   class Microsoft.Crm.Authentication.Claims.MetadataParser Microsoft.Crm.Authentication.Claims.ClaimsConfigurator::_overrideMetadataParser
0xbd90  ret
```
