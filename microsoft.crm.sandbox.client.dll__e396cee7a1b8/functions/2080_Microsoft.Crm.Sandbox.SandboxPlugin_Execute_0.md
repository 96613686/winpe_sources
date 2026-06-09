# Microsoft.Crm.Sandbox.SandboxPlugin::Execute_0

- ea: `0x2080`
- end: `0x20a9`
- name: `Microsoft.Crm.Sandbox.SandboxPlugin::Execute_0`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1ff0`
- `0x23a0`

## pseudocode

```c

```

## disassembly

```asm
0x2080  ldarg.0
0x2081  ldarg.1
0x2082  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ITracingService
0x2087  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x208c  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x2091  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ITracingService
0x2096  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ITracingService Microsoft.Crm.Sandbox.SandboxPlugin::tracingService
0x209b  ldarg.0
0x209c  ldarg.0
0x209d  ldarg.1
0x209e  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext Microsoft.Crm.Sandbox.SandboxPlugin::GetExecutionContext(class [mscorlib]System.IServiceProvider serviceProvider)
0x20a3  call     instance void Microsoft.Crm.Sandbox.SandboxCodeUnit::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext context)
0x20a8  ret
```
