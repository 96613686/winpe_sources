# Microsoft.Crm.Sandbox.SandboxCallManager::get_Instance

- ea: `0xc0`
- end: `0xc6`
- name: `Microsoft.Crm.Sandbox.SandboxCallManager::get_Instance`
- size: `6`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x4b0`
- `0x5180`
- `0x7f90`
- `0x80e0`
- `0x8dc0`

## pseudocode

```c

```

## disassembly

```asm
0xc0  ldsfld   class Microsoft.Crm.Sandbox.SandboxCallManager Microsoft.Crm.Sandbox.SandboxCallManager::_singleton
0xc5  ret
```
