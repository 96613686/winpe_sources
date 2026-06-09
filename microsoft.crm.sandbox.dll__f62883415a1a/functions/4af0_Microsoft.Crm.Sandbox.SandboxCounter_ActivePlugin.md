# Microsoft.Crm.Sandbox.SandboxCounter::ActivePlugin

- ea: `0x4af0`
- end: `0x4afd`
- name: `Microsoft.Crm.Sandbox.SandboxCounter::ActivePlugin`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x4c10`

## pseudocode

```c

```

## disassembly

```asm
0x4af0  ldarg.0
0x4af1  ldfld    class Microsoft.Crm.Sandbox.SandboxIdTable Microsoft.Crm.Sandbox.SandboxCounter::_activePlugins
0x4af6  ldarg.1
0x4af7  callvirt instance void Microsoft.Crm.Sandbox.SandboxIdTable::Add(valuetype [mscorlib]System.Guid id)
0x4afc  ret
```
