# Microsoft.Crm.Sandbox.SandboxWorkerManager::BackgroundCreateNewWorkerProcess

- ea: `0x7df0`
- end: `0x7e26`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerManager::BackgroundCreateNewWorkerProcess`
- size: `54`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x6f40`
- `0x74f0`
- `0xc450`

## callees

- `0x7df0`

## pseudocode

```c

```

## disassembly

```asm
0x7df0  ldarg.0
0x7df1  brfalse.s loc_7E00
0x7df3  ldsflda  int32 Microsoft.Crm.Sandbox.SandboxWorkerManager::_waitingStartupDrawbridgeProcess
0x7df8  call     int32 [mscorlib]System.Threading.Interlocked::Increment(int32&)
0x7dfd  pop
0x7dfe  br.s     loc_7E0B
0x7e00  ldsflda  int32 Microsoft.Crm.Sandbox.SandboxWorkerManager::_waitingStartupNativeProcess
0x7e05  call     int32 [mscorlib]System.Threading.Interlocked::Increment(int32&)
0x7e0a  pop
0x7e0b  ldarg.0
0x7e0c  brfalse.s loc_7E1A
0x7e0e  ldsfld   class [System]System.Collections.Concurrent.BlockingCollection`1<bool> Microsoft.Crm.Sandbox.SandboxWorkerManager::_drawbridgeProcessQueue
0x7e13  ldarg.0
0x7e14  callvirt instance void class [System]System.Collections.Concurrent.BlockingCollection`1<bool>::Add(var<u1>)
0x7e19  ret
0x7e1a  ldsfld   class [System]System.Collections.Concurrent.BlockingCollection`1<bool> Microsoft.Crm.Sandbox.SandboxWorkerManager::_nativeProcessQueue
0x7e1f  ldarg.0
0x7e20  callvirt instance void class [System]System.Collections.Concurrent.BlockingCollection`1<bool>::Add(var<u1>)
0x7e25  ret
```
