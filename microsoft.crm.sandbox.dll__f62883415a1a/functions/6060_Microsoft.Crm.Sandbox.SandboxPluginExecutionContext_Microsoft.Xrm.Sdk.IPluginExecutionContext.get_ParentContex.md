# Microsoft.Crm.Sandbox.SandboxPluginExecutionContext::Microsoft.Xrm.Sdk.IPluginExecutionContext.get_ParentContext

- ea: `0x6060`
- end: `0x606c`
- name: `Microsoft.Crm.Sandbox.SandboxPluginExecutionContext::Microsoft.Xrm.Sdk.IPluginExecutionContext.get_ParentContext`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x6820`

## pseudocode

```c

```

## disassembly

```asm
0x6060  ldarg.0
0x6061  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext Microsoft.Crm.Sandbox.SandboxExecutionContext::get_ParentContext()
0x6066  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext
0x606b  ret
```
