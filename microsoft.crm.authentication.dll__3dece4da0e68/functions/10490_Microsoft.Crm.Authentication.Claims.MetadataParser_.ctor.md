# Microsoft.Crm.Authentication.Claims.MetadataParser::.ctor

- ea: `0x10490`
- end: `0x104a8`
- name: `Microsoft.Crm.Authentication.Claims.MetadataParser::.ctor`
- size: `24`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xb7d0`

## callees

- `0x10540`

## string_xrefs

- `0x10497`: `Security Token Service`

## pseudocode

```c

```

## disassembly

```asm
0x10490  ldarg.0
0x10491  call     instance void [mscorlib]System.Object::.ctor()
0x10496  ldarg.0
0x10497  ldstr    aSecurityTokenS// "Security Token Service"
0x1049c  stfld    string Microsoft.Crm.Authentication.Claims.MetadataParser::name
0x104a1  ldarg.0
0x104a2  call     instance void Microsoft.Crm.Authentication.Claims.MetadataParser::InitializeTrustedIssuers()
0x104a7  ret
```
