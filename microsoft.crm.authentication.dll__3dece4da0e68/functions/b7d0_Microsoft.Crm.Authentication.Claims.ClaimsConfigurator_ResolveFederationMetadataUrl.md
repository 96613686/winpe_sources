# Microsoft.Crm.Authentication.Claims.ClaimsConfigurator::ResolveFederationMetadataUrl

- ea: `0xb7d0`
- end: `0xb7e6`
- name: `Microsoft.Crm.Authentication.Claims.ClaimsConfigurator::ResolveFederationMetadataUrl`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0xbcd0`

## callees

- `0xb7d0`
- `0x10490`
- `0x10550`

## pseudocode

```c

```

## disassembly

```asm
0xb7d0  ldsfld   class Microsoft.Crm.Authentication.Claims.MetadataParser Microsoft.Crm.Authentication.Claims.ClaimsConfigurator::_overrideMetadataParser
0xb7d5  dup
0xb7d6  brtrue.s loc_B7DE
0xb7d8  pop
0xb7d9  newobj   instance void Microsoft.Crm.Authentication.Claims.MetadataParser::.ctor()
0xb7de  dup
0xb7df  ldarg.0
0xb7e0  callvirt instance void Microsoft.Crm.Authentication.Claims.MetadataParser::GetStsFederationMetadata(class [System]System.Uri stsLocationUri)
0xb7e5  ret
```
