# Microsoft.Crm.Sandbox.SandboxHostManager::get_SandboxHostsCount

- ea: `0x7d0`
- end: `0x7db`
- name: `Microsoft.Crm.Sandbox.SandboxHostManager::get_SandboxHostsCount`
- size: `11`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x30b0`
- `0x85d0`

## pseudocode

```c

```

## disassembly

```asm
0x7d0  ldsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.SandboxHostInfo> Microsoft.Crm.Sandbox.SandboxHostManager::_hostNames
0x7d5  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.SandboxHostInfo>::get_Count()
0x7da  ret
```
