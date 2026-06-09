# Microsoft.Crm.Sandbox.SandboxCodeUnit::Execute_0

- ea: `0x23a0`
- end: `0x23d0`
- name: `Microsoft.Crm.Sandbox.SandboxCodeUnit::Execute_0`
- size: `48`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x2080`
- `0x34d0`

## callees

- `0x8db0`

## pseudocode

```c

```

## disassembly

```asm
0x23a0  newobj   instance void <>c__DisplayClass24_0::.ctor()
0x23a5  stloc.0
0x23a6  ldloc.0
0x23a7  ldarg.1
0x23a8  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext <>c__DisplayClass24_0::context
0x23ad  ldloc.0
0x23ae  ldarg.0
0x23af  stfld    class Microsoft.Crm.Sandbox.SandboxCodeUnit <>c__DisplayClass24_0::<>4__this
0x23b4  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Sandbox.SandboxCodeUnit::Logger
0x23b9  call     var<u1> class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class [Microsoft.Crm.Sandbox.Helper]Microsoft.Crm.Sandbox.SandboxExecutionActivityType>::get_Instance()
0x23be  ldloc.0
0x23bf  ldftn    instance void <>c__DisplayClass24_0::<Execute>b__0()
0x23c5  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x23ca  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryExtensions::Execute(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryActivityType, class [mscorlib]System.Action)
0x23cf  ret
```
