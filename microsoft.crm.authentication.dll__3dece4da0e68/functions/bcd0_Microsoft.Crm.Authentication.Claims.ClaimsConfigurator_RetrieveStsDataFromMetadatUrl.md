# Microsoft.Crm.Authentication.Claims.ClaimsConfigurator::RetrieveStsDataFromMetadatUrl

- ea: `0xbcd0`
- end: `0xbd19`
- name: `Microsoft.Crm.Authentication.Claims.ClaimsConfigurator::RetrieveStsDataFromMetadatUrl`
- size: `73`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0xbd20`

## callees

- `0xb7d0`
- `0xbdc0`
- `0xbde0`
- `0xbe00`
- `0xbe20`
- `0xbe40`
- `0xbe50`
- `0x104d0`
- `0x10500`
- `0x10510`
- `0x10520`
- `0x10530`

## pseudocode

```c

```

## disassembly

```asm
0xbcd0  ldarg.0
0xbcd1  call     class Microsoft.Crm.Authentication.Claims.MetadataParser Microsoft.Crm.Authentication.Claims.ClaimsConfigurator::ResolveFederationMetadataUrl(class [System]System.Uri stsUrl)
0xbcd6  stloc.0
0xbcd7  newobj   instance void Microsoft.Crm.Authentication.Claims.StsData::.ctor()
0xbcdc  dup
0xbcdd  ldloc.0
0xbcde  callvirt instance string Microsoft.Crm.Authentication.Claims.MetadataParser::get_Name()
0xbce3  callvirt instance void Microsoft.Crm.Authentication.Claims.StsData::set_Name(string value)
0xbce8  dup
0xbce9  ldloc.0
0xbcea  callvirt instance class [System]System.Uri Microsoft.Crm.Authentication.Claims.MetadataParser::get_MetadataUri()
0xbcef  callvirt instance void Microsoft.Crm.Authentication.Claims.StsData::set_ActiveMetadataExchangeUri(class [System]System.Uri value)
0xbcf4  dup
0xbcf5  ldloc.0
0xbcf6  callvirt instance class [System]System.Uri Microsoft.Crm.Authentication.Claims.MetadataParser::get_ActiveUri()
0xbcfb  callvirt instance void Microsoft.Crm.Authentication.Claims.StsData::set_ActiveUri(class [System]System.Uri value)
0xbd00  dup
0xbd01  ldloc.0
0xbd02  callvirt instance class [System]System.Uri Microsoft.Crm.Authentication.Claims.MetadataParser::get_PassiveUri()
0xbd07  callvirt instance void Microsoft.Crm.Authentication.Claims.StsData::set_PassiveUri(class [System]System.Uri value)
0xbd0c  dup
0xbd0d  ldloc.0
0xbd0e  callvirt instance class Microsoft.Crm.Authentication.Claims.TrustedIssuerCollection Microsoft.Crm.Authentication.Claims.MetadataParser::get_TrustedIssuers()
0xbd13  callvirt instance void Microsoft.Crm.Authentication.Claims.StsData::set_TrustedIssuers(class Microsoft.Crm.Authentication.Claims.TrustedIssuerCollection value)
0xbd18  ret
```
