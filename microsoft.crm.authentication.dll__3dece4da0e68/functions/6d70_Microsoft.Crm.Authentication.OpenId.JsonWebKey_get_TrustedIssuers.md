# Microsoft.Crm.Authentication.OpenId.JsonWebKey::get_TrustedIssuers

- ea: `0x6d70`
- end: `0x6d85`
- name: `Microsoft.Crm.Authentication.OpenId.JsonWebKey::get_TrustedIssuers`
- size: `21`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x6d90`
- `0xbba0`

## callees

- `0x6d70`
- `0x6d90`

## pseudocode

```c

```

## disassembly

```asm
0x6d70  ldarg.0
0x6d71  ldfld    class Microsoft.Crm.Authentication.Claims.TrustedIssuerCollection Microsoft.Crm.Authentication.OpenId.JsonWebKey::_trustedIssuers
0x6d76  brtrue.s loc_6D7E
0x6d78  ldarg.0
0x6d79  call     instance void Microsoft.Crm.Authentication.OpenId.JsonWebKey::GetSigningCertificates()
0x6d7e  ldarg.0
0x6d7f  ldfld    class Microsoft.Crm.Authentication.Claims.TrustedIssuerCollection Microsoft.Crm.Authentication.OpenId.JsonWebKey::_trustedIssuers
0x6d84  ret
```
