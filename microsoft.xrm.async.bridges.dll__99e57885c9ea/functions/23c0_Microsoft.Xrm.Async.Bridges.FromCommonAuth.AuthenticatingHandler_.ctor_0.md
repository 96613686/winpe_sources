# Microsoft.Xrm.Async.Bridges.FromCommonAuth.AuthenticatingHandler::.ctor_0

- ea: `0x23c0`
- end: `0x23cf`
- name: `Microsoft.Xrm.Async.Bridges.FromCommonAuth.AuthenticatingHandler::.ctor_0`
- size: `15`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x23b0`

## pseudocode

```c

```

## disassembly

```asm
0x23c0  ldarg.0
0x23c1  ldarg.2
0x23c2  call     instance void [System.Net.Http]System.Net.Http.DelegatingHandler::.ctor(class [System.Net.Http]System.Net.Http.HttpMessageHandler)
0x23c7  ldarg.0
0x23c8  ldarg.1
0x23c9  stfld    class Microsoft.Xrm.Async.Bridges.FromCommonAuth.IAuthProvider Microsoft.Xrm.Async.Bridges.FromCommonAuth.AuthenticatingHandler::authProvider
0x23ce  ret
```
