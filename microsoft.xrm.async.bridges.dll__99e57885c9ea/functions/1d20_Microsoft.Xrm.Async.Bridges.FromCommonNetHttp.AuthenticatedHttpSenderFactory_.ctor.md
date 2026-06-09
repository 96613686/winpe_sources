# Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.AuthenticatedHttpSenderFactory::.ctor

- ea: `0x1d20`
- end: `0x1d4d`
- name: `Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.AuthenticatedHttpSenderFactory::.ctor`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xab0`

## pseudocode

```c

```

## disassembly

```asm
0x1d20  ldarg.0
0x1d21  call     instance void [mscorlib]System.Object::.ctor()
0x1d26  ldarg.1
0x1d27  ldstr    aConnectionstri// "connectionStringSecretKey"
0x1d2c  call     T0x2B000024
0x1d31  call     class Microsoft.Xrm.Async.Bridges.FromCommon.ArgumentAssertion`1<string> Microsoft.Xrm.Async.Bridges.FromCommon.Args::IsNotNullOrEmpty(class Microsoft.Xrm.Async.Bridges.FromCommon.ArgumentAssertion`1<string> arg)
0x1d36  pop
0x1d37  ldarg.0
0x1d38  ldarg.1
0x1d39  stfld    string Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.AuthenticatedHttpSenderFactory::connectionStringSecretKey
0x1d3e  ldarg.0
0x1d3f  ldarg.2
0x1d40  stfld    class Microsoft.Xrm.Async.Bridges.FromCommonAuth.IOAuthTokenProviderFactory Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.AuthenticatedHttpSenderFactory::tokenProviderFactory
0x1d45  ldarg.0
0x1d46  ldarg.3
0x1d47  stfld    class Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.IAuthProviderEvents Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.AuthenticatedHttpSenderFactory::events
0x1d4c  ret
```
