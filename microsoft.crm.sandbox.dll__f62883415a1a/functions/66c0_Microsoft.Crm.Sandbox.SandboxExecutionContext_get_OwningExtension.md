# Microsoft.Crm.Sandbox.SandboxExecutionContext::get_OwningExtension

- ea: `0x66c0`
- end: `0x66e0`
- name: `Microsoft.Crm.Sandbox.SandboxExecutionContext::get_OwningExtension`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x66c0`

## pseudocode

```c

```

## disassembly

```asm
0x66c0  ldarg.0
0x66c1  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference Microsoft.Crm.Sandbox.SandboxExecutionContext::_owningExtension
0x66c6  brtrue.s loc_66D9
0x66c8  ldarg.0
0x66c9  ldarg.0
0x66ca  ldfld    unsigned int8[] Microsoft.Crm.Sandbox.SandboxExecutionContext::_serializedOwningExtension
0x66cf  call     T0x2B000018
0x66d4  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference Microsoft.Crm.Sandbox.SandboxExecutionContext::_owningExtension
0x66d9  ldarg.0
0x66da  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference Microsoft.Crm.Sandbox.SandboxExecutionContext::_owningExtension
0x66df  ret
```
