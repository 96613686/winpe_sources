# Microsoft.Xrm.Async.Bridges.FromCommonAuth.ConnectionStringConfigLookup::.ctor

- ea: `0x2850`
- end: `0x2868`
- name: `Microsoft.Xrm.Async.Bridges.FromCommonAuth.ConnectionStringConfigLookup::.ctor`
- size: `24`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2890`

## callees

- `0xe40`
- `0x2640`
- `0x2850`

## pseudocode

```c

```

## disassembly

```asm
0x2850  ldarg.0
0x2851  call     instance void Microsoft.Xrm.Async.Bridges.FromCommon.ConfigLookupBase::.ctor()
0x2856  ldarg.1
0x2857  ldloca.s 0
0x2859  call     bool Microsoft.Xrm.Async.Bridges.FromCommonAuth.ConnectionString::TryParse(string connectionString, [out] class Microsoft.Xrm.Async.Bridges.FromCommonAuth.ConnectionString& value)
0x285e  brfalse.s loc_2867
0x2860  ldarg.0
0x2861  ldloc.0
0x2862  stfld    class Microsoft.Xrm.Async.Bridges.FromCommonAuth.ConnectionString Microsoft.Xrm.Async.Bridges.FromCommonAuth.ConnectionStringConfigLookup::connectionString
0x2867  ret
```
