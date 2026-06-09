# Microsoft.Xrm.Async.Bridges.FromCommonAuth.ConnectionStringConfigLookup::Find

- ea: `0x2870`
- end: `0x287d`
- name: `Microsoft.Xrm.Async.Bridges.FromCommonAuth.ConnectionStringConfigLookup::Find`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x25f0`

## pseudocode

```c

```

## disassembly

```asm
0x2870  ldarg.0
0x2871  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommonAuth.ConnectionString Microsoft.Xrm.Async.Bridges.FromCommonAuth.ConnectionStringConfigLookup::connectionString
0x2876  ldarg.2
0x2877  callvirt instance string Microsoft.Xrm.Async.Bridges.FromCommonAuth.ConnectionString::get_Item(string key)
0x287c  ret
```
