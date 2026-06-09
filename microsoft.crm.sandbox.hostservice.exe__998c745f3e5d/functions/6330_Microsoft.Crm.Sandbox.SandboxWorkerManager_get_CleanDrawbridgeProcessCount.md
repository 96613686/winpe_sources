# Microsoft.Crm.Sandbox.SandboxWorkerManager::get_CleanDrawbridgeProcessCount

- ea: `0x6330`
- end: `0x633b`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerManager::get_CleanDrawbridgeProcessCount`
- size: `11`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x4240`
- `0xba70`
- `0xbf70`

## pseudocode

```c

```

## disassembly

```asm
0x6330  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [System]System.Uri> Microsoft.Crm.Sandbox.SandboxWorkerManager::_cleanDrawbridgeProcessQueue
0x6335  callvirt instance int32 class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [System]System.Uri>::get_Count()
0x633a  ret
```
