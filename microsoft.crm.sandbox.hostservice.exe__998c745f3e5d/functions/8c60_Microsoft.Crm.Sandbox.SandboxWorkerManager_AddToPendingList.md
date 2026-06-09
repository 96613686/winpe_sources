# Microsoft.Crm.Sandbox.SandboxWorkerManager::AddToPendingList

- ea: `0x8c60`
- end: `0x8c73`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerManager::AddToPendingList`
- size: `19`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xb250`

## callees

- `0x98f0`

## pseudocode

```c

```

## disassembly

```asm
0x8c60  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [System]System.Uri, class Microsoft.Crm.Sandbox.SandboxWorkerProcess> Microsoft.Crm.Sandbox.SandboxWorkerManager::_terminationWorkers
0x8c65  ldarg.0
0x8c66  callvirt instance class [System]System.Uri Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_Uri()
0x8c6b  ldarg.0
0x8c6c  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [System]System.Uri, class Microsoft.Crm.Sandbox.SandboxWorkerProcess>::TryAdd(var<u1>, !!T0)
0x8c71  pop
0x8c72  ret
```
