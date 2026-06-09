# Microsoft.Xrm.Async.Bridges.FromCommonAuth.AuthenticationContextAdapter::.ctor

- ea: `0x2440`
- end: `0x244e`
- name: `Microsoft.Xrm.Async.Bridges.FromCommonAuth.AuthenticationContextAdapter::.ctor`
- size: `14`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x2490`

## pseudocode

```c

```

## disassembly

```asm
0x2440  ldarg.0
0x2441  call     instance void [mscorlib]System.Object::.ctor()
0x2446  ldarg.0
0x2447  ldarg.1
0x2448  stfld    class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationContext Microsoft.Xrm.Async.Bridges.FromCommonAuth.AuthenticationContextAdapter::context
0x244d  ret
```
