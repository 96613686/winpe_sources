# Microsoft.Xrm.Async.Bridges.FromCommonAuth.AuthenticationContextFactory::Create

- ea: `0x2490`
- end: `0x249c`
- name: `Microsoft.Xrm.Async.Bridges.FromCommonAuth.AuthenticationContextFactory::Create`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x2440`

## pseudocode

```c

```

## disassembly

```asm
0x2490  ldarg.1
0x2491  newobj   instance void [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationContext::.ctor(string)
0x2496  newobj   instance void Microsoft.Xrm.Async.Bridges.FromCommonAuth.AuthenticationContextAdapter::.ctor(class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationContext context)
0x249b  ret
```
