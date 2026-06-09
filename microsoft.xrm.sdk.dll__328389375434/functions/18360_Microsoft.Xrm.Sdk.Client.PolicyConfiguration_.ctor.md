# Microsoft.Xrm.Sdk.Client.PolicyConfiguration::.ctor

- ea: `0x18360`
- end: `0x18374`
- name: `Microsoft.Xrm.Sdk.Client.PolicyConfiguration::.ctor`
- size: `20`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x183f0`
- `0x18410`
- `0x18440`

## callees

- `0x18380`
- `0x183b0`

## pseudocode

```c

```

## disassembly

```asm
0x18360  ldarg.0
0x18361  call     instance void [mscorlib]System.Object::.ctor()
0x18366  ldarg.0
0x18367  ldarg.1
0x18368  call     instance void Microsoft.Xrm.Sdk.Client.PolicyConfiguration::set_XrmPolicy(class Microsoft.Xrm.Sdk.Client.AuthenticationPolicy value)
0x1836d  ldarg.0
0x1836e  call     instance void Microsoft.Xrm.Sdk.Client.PolicyConfiguration::Initialize()
0x18373  ret
```
