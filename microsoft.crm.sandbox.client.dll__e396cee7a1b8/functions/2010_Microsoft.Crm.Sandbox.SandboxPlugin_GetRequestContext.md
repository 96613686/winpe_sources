# Microsoft.Crm.Sandbox.SandboxPlugin::GetRequestContext

- ea: `0x2010`
- end: `0x2024`
- name: `Microsoft.Crm.Sandbox.SandboxPlugin::GetRequestContext`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x2010  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionContext::.ctor()
0x2015  stloc.0
0x2016  ldarg.1
0x2017  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext
0x201c  ldloc.0
0x201d  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionContext::FromPluginExecutionContext(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext)
0x2022  ldloc.0
0x2023  ret
```
