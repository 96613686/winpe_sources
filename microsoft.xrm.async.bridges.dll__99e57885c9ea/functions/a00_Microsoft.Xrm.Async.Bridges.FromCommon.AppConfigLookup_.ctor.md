# Microsoft.Xrm.Async.Bridges.FromCommon.AppConfigLookup::.ctor

- ea: `0xa00`
- end: `0xa1e`
- name: `Microsoft.Xrm.Async.Bridges.FromCommon.AppConfigLookup::.ctor`
- size: `30`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0xa00`
- `0xe40`

## pseudocode

```c

```

## disassembly

```asm
0xa00  ldarg.0
0xa01  call     instance void Microsoft.Xrm.Async.Bridges.FromCommon.ConfigLookupBase::.ctor()
0xa06  ldarg.0
0xa07  ldarg.1
0xa08  dup
0xa09  brtrue.s loc_A11
0xa0b  pop
0xa0c  call     class [System]System.Collections.Specialized.NameValueCollection [System.Configuration]System.Configuration.ConfigurationManager::get_AppSettings()
0xa11  stfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.Xrm.Async.Bridges.FromCommon.AppConfigLookup::appSettings
0xa16  ldarg.0
0xa17  ldarg.2
0xa18  stfld    char Microsoft.Xrm.Async.Bridges.FromCommon.AppConfigLookup::delimiter
0xa1d  ret
```
