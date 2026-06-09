# Microsoft.Crm.Sandbox.SandboxWorkerManager::RemoveValueFromQueue

- ea: `0x8880`
- end: `0x88cc`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerManager::RemoveValueFromQueue`
- size: `76`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x8620`

## callees

- `0x8880`

## pseudocode

```c

```

## disassembly

```asm
0x8880  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [System]System.Uri> Microsoft.Crm.Sandbox.SandboxWorkerManager::_cleanDrawbridgeProcessQueue
0x8885  callvirt instance int32 class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [System]System.Uri>::get_Count()
0x888a  newobj   instance void class [System]System.Collections.Generic.Queue`1<class [System]System.Uri>::.ctor(int32)
0x888f  stloc.0
0x8890  br.s     loc_88AC
0x8892  ldarg.1
0x8893  ldloca.s 1
0x8895  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [System]System.Uri>::TryDequeue(var<u1>&)
0x889a  brfalse.s loc_88AC
0x889c  ldloc.1
0x889d  ldarg.0
0x889e  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x88a3  brfalse.s loc_88AC
0x88a5  ldloc.0
0x88a6  ldloc.1
0x88a7  callvirt instance void class [System]System.Collections.Generic.Queue`1<class [System]System.Uri>::Enqueue(var<u1>)
0x88ac  ldarg.1
0x88ad  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [System]System.Uri>::get_IsEmpty()
0x88b2  brfalse.s loc_8892
0x88b4  br.s     loc_88C2
0x88b6  ldarg.1
0x88b7  ldloc.0
0x88b8  callvirt instance var<u1> class [System]System.Collections.Generic.Queue`1<class [System]System.Uri>::Dequeue()
0x88bd  callvirt instance void class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [System]System.Uri>::Enqueue(var<u1>)
0x88c2  ldloc.0
0x88c3  callvirt instance int32 class [System]System.Collections.Generic.Queue`1<class [System]System.Uri>::get_Count()
0x88c8  ldc.i4.0
0x88c9  bgt.s    loc_88B6
0x88cb  ret
```
