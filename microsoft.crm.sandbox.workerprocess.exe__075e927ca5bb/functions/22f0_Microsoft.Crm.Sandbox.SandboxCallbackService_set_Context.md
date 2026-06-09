# Microsoft.Crm.Sandbox.SandboxCallbackService::set_Context

- ea: `0x22f0`
- end: `0x22f8`
- name: `Microsoft.Crm.Sandbox.SandboxCallbackService::set_Context`
- size: `8`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x2880`

## pseudocode

```c

```

## disassembly

```asm
0x22f0  ldarg.0
0x22f1  ldarg.1
0x22f2  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext Microsoft.Crm.Sandbox.SandboxCallbackService::_context
0x22f7  ret
```
