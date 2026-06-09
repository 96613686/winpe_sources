# Microsoft.Crm.Sandbox.SandboxWorkerManager::get_CleanNativeProcessCount

- ea: `0x6320`
- end: `0x632b`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerManager::get_CleanNativeProcessCount`
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
0x6320  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [System]System.Uri> Microsoft.Crm.Sandbox.SandboxWorkerManager::_cleanNativeProcessQueue
0x6325  callvirt instance int32 class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [System]System.Uri>::get_Count()
0x632a  ret
```
