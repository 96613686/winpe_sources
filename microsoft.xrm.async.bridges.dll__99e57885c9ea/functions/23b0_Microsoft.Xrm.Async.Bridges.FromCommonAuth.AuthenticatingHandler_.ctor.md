# Microsoft.Xrm.Async.Bridges.FromCommonAuth.AuthenticatingHandler::.ctor

- ea: `0x23b0`
- end: `0x23bd`
- name: `Microsoft.Xrm.Async.Bridges.FromCommonAuth.AuthenticatingHandler::.ctor`
- size: `13`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x3eb0`

## callees

- `0x23c0`

## pseudocode

```c

```

## disassembly

```asm
0x23b0  ldarg.0
0x23b1  ldarg.1
0x23b2  newobj   instance void [System.Net.Http]System.Net.Http.HttpClientHandler::.ctor()
0x23b7  call     instance void Microsoft.Xrm.Async.Bridges.FromCommonAuth.AuthenticatingHandler::.ctor(class Microsoft.Xrm.Async.Bridges.FromCommonAuth.IAuthProvider authProvider, class [System.Net.Http]System.Net.Http.HttpMessageHandler innerHandler)
0x23bc  ret
```
