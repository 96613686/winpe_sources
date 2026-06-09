# Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.ConfigTargetEndpointConfigLookup::.ctor

- ea: `0x1db0`
- end: `0x1de4`
- name: `Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.ConfigTargetEndpointConfigLookup::.ctor`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x1db0  ldarg.0
0x1db1  ldstr    aX// "x-"
0x1db6  stfld    string Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.ConfigTargetEndpointConfigLookup::sentinelWorkloadPrefix
0x1dbb  ldarg.0
0x1dbc  call     instance void [mscorlib]System.Object::.ctor()
0x1dc1  ldarg.0
0x1dc2  ldarg.1
0x1dc3  ldstr    aProdendpoint// "ProdEndpoint"
0x1dc8  callvirt T0x2B00004D
0x1dcd  stfld    class Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.TargetEndpointConfig Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.ConfigTargetEndpointConfigLookup::prodEndpointConfig
0x1dd2  ldarg.0
0x1dd3  ldarg.1
0x1dd4  ldstr    aTestendpoint// "TestEndpoint"
0x1dd9  callvirt T0x2B00004D
0x1dde  stfld    class Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.TargetEndpointConfig Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.ConfigTargetEndpointConfigLookup::testEndpointConfig
0x1de3  ret
```
