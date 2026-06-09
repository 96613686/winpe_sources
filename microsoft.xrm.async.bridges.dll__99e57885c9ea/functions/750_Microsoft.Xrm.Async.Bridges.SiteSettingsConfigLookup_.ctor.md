# Microsoft.Xrm.Async.Bridges.SiteSettingsConfigLookup::.ctor

- ea: `0x750`
- end: `0x765`
- name: `Microsoft.Xrm.Async.Bridges.SiteSettingsConfigLookup::.ctor`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0xe40`

## pseudocode

```c

```

## disassembly

```asm
0x750  ldarg.0
0x751  call     instance void Microsoft.Xrm.Async.Bridges.FromCommon.ConfigLookupBase::.ctor()
0x756  ldarg.0
0x757  ldarg.1
0x758  stfld    string Microsoft.Xrm.Async.Bridges.SiteSettingsConfigLookup::settingName
0x75d  ldarg.0
0x75e  ldarg.2
0x75f  stfld    class Microsoft.Xrm.Async.Bridges.Providers.Crm.ICrmLocatorService Microsoft.Xrm.Async.Bridges.SiteSettingsConfigLookup::locatorService
0x764  ret
```
