# Microsoft.Crm.Sandbox.Client.Throttling.ThrottlingParameterInspector::.ctor

- ea: `0x6dc0`
- end: `0x6de7`
- name: `Microsoft.Crm.Sandbox.Client.Throttling.ThrottlingParameterInspector::.ctor`
- size: `39`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x6d90`

## callees

- `0x6dc0`

## string_xrefs

- `0x6dd4`: `configurationFactory`

## pseudocode

```c

```

## disassembly

```asm
0x6dc0  ldarg.0
0x6dc1  newobj   instance void [Microsoft.Crm.Extensibility]Microsoft.Crm.Extensibility.ODataV4.Throttling.RequestThrottlingEngine::.ctor()
0x6dc6  stfld    class [Microsoft.Crm.Extensibility]Microsoft.Crm.Extensibility.ODataV4.Throttling.RequestThrottlingEngine Microsoft.Crm.Sandbox.Client.Throttling.ThrottlingParameterInspector::throttlingEngine
0x6dcb  ldarg.0
0x6dcc  call     instance void [mscorlib]System.Object::.ctor()
0x6dd1  ldarg.1
0x6dd2  brtrue.s loc_6DDF
0x6dd4  ldstr    aConfigurationf// "configurationFactory"
0x6dd9  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x6dde  throw
0x6ddf  ldarg.0
0x6de0  ldarg.1
0x6de1  stfld    class [Microsoft.Crm.Extensibility]Microsoft.Crm.Extensibility.ODataV4.Throttling.IThrottlingConfigurationFactory Microsoft.Crm.Sandbox.Client.Throttling.ThrottlingParameterInspector::configurationFactory
0x6de6  ret
```
