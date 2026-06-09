# Microsoft.Crm.Sandbox.SandboxPluginExecutionContext::SerializeForTransmit

- ea: `0x60a0`
- end: `0x60bc`
- name: `Microsoft.Crm.Sandbox.SandboxPluginExecutionContext::SerializeForTransmit`
- size: `28`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x60a0`
- `0x6820`
- `0x68c0`

## pseudocode

```c

```

## disassembly

```asm
0x60a0  ldarg.0
0x60a1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext Microsoft.Crm.Sandbox.SandboxExecutionContext::get_ParentContext()
0x60a6  isinst   Microsoft.Crm.Sandbox.SandboxPluginExecutionContext
0x60ab  stloc.0
0x60ac  ldloc.0
0x60ad  brfalse.s loc_60B5
0x60af  ldloc.0
0x60b0  callvirt instance void Microsoft.Crm.Sandbox.SandboxExecutionContext::SerializeForTransmit()
0x60b5  ldarg.0
0x60b6  call     instance void Microsoft.Crm.Sandbox.SandboxExecutionContext::SerializeForTransmit()
0x60bb  ret
```
