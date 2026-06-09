# Microsoft.Crm.Sandbox.SandboxExecutionContext::set_OwningExtension

- ea: `0x66e0`
- end: `0x66e8`
- name: `Microsoft.Crm.Sandbox.SandboxExecutionContext::set_OwningExtension`
- size: `8`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x6120`

## pseudocode

```c

```

## disassembly

```asm
0x66e0  ldarg.0
0x66e1  ldarg.1
0x66e2  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference Microsoft.Crm.Sandbox.SandboxExecutionContext::_owningExtension
0x66e7  ret
```
