# Microsoft.Crm.Sandbox.SandboxPluginExecutionContext::FromPluginExecutionContext

- ea: `0x5ff0`
- end: `0x603b`
- name: `Microsoft.Crm.Sandbox.SandboxPluginExecutionContext::FromPluginExecutionContext`
- size: `75`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x5ff0`

## callees

- `0x5ff0`
- `0x60c0`
- `0x6120`
- `0x6840`
- `0x6870`

## pseudocode

```c

```

## disassembly

```asm
0x5ff0  ldarg.0
0x5ff1  brfalse.s loc_5FF6
0x5ff3  ldarg.1
0x5ff4  brtrue.s loc_5FFA
0x5ff6  ldnull
0x5ff7  starg.s  1
0x5ff9  ret
0x5ffa  ldarg.0
0x5ffb  ldarg.1
0x5ffc  call     void Microsoft.Crm.Sandbox.SandboxExecutionContext::FromExecutionContext(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext fromContext, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext toContext)
0x6001  ldarg.1
0x6002  isinst   Microsoft.Crm.Sandbox.SandboxPluginExecutionContext
0x6007  stloc.0
0x6008  ldloc.0
0x6009  ldarg.0
0x600a  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext::get_Stage()
0x600f  callvirt instance void Microsoft.Crm.Sandbox.SandboxExecutionContext::set_Stage(int32 value)
0x6014  ldarg.0
0x6015  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext::get_ParentContext()
0x601a  brfalse.s loc_603A
0x601c  newobj   instance void Microsoft.Crm.Sandbox.SandboxPluginExecutionContext::.ctor()
0x6021  stloc.1
0x6022  ldloc.0
0x6023  ldloc.1
0x6024  callvirt instance void Microsoft.Crm.Sandbox.SandboxExecutionContext::set_ParentContext(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext value)
0x6029  ldarg.0
0x602a  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext::get_ParentContext()
0x602f  ldarg.1
0x6030  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext::get_ParentContext()
0x6035  call     void Microsoft.Crm.Sandbox.SandboxPluginExecutionContext::FromPluginExecutionContext(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext fromContext, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext toContext)
0x603a  ret
```
