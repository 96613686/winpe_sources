# Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.ConfigTargetEndpointConfigLookup::Find

- ea: `0x1df0`
- end: `0x1e0c`
- name: `Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.ConfigTargetEndpointConfigLookup::Find`
- size: `28`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1df0`

## pseudocode

```c

```

## disassembly

```asm
0x1df0  ldarg.1
0x1df1  ldarg.0
0x1df2  ldfld    string Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.ConfigTargetEndpointConfigLookup::sentinelWorkloadPrefix
0x1df7  callvirt instance bool [mscorlib]System.String::StartsWith(string)
0x1dfc  brfalse.s loc_1E05
0x1dfe  ldarg.0
0x1dff  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.TargetEndpointConfig Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.ConfigTargetEndpointConfigLookup::testEndpointConfig
0x1e04  ret
0x1e05  ldarg.0
0x1e06  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.TargetEndpointConfig Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.ConfigTargetEndpointConfigLookup::prodEndpointConfig
0x1e0b  ret
```
