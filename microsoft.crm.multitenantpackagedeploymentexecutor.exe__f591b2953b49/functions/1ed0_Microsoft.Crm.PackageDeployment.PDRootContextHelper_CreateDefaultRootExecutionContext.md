# Microsoft.Crm.PackageDeployment.PDRootContextHelper::CreateDefaultRootExecutionContext

- ea: `0x1ed0`
- end: `0x1ee9`
- name: `Microsoft.Crm.PackageDeployment.PDRootContextHelper::CreateDefaultRootExecutionContext`
- size: `25`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1e60`

## pseudocode

```c

```

## disassembly

```asm
0x1ed0  ldc.i4.6
0x1ed1  ldnull
0x1ed2  ldnull
0x1ed3  ldnull
0x1ed4  ldnull
0x1ed5  ldnull
0x1ed6  ldarga.s 0
0x1ed8  ldstr    aD// "D"
0x1edd  call     instance string [mscorlib]System.Guid::ToString(string)
0x1ee2  ldnull
0x1ee3  newobj   instance void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmRootExecutionContext::.ctor(valuetype [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.TraceVerbosity, string, string, string, string, string, string, string)
0x1ee8  ret
```
