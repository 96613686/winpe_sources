# Microsoft.Crm.Sandbox.SandboxWorkerManager::RemoveFromPendingList

- ea: `0x8c80`
- end: `0x8cb8`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerManager::RemoveFromPendingList`
- size: `56`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xb430`

## callees

- `0x9770`
- `0x98f0`

## string_xrefs

- `0x8c8b`: `SandboxWorkerManager.RemoveFromPendingList: Removing worker process from _terminationWorkers: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x8c80  ldnull
0x8c81  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x8c86  ldc.i4.3
0x8c87  ldc.i4.s 0x26
0x8c89  ldc.i4.0
0x8c8a  ldc.i4.1
0x8c8b  ldstr    aSandboxworkerm_99// "SandboxWorkerManager.RemoveFromPendingL"...
0x8c90  ldc.i4.1
0x8c91  newarr   [mscorlib]System.Object
0x8c96  dup
0x8c97  ldc.i4.0
0x8c98  ldarg.0
0x8c99  callvirt instance string Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_FullId()
0x8c9e  stelem.ref
0x8c9f  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::Trace(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [System]System.Diagnostics.TraceLevel, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, int32, bool, string, object[])
0x8ca4  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [System]System.Uri, class Microsoft.Crm.Sandbox.SandboxWorkerProcess> Microsoft.Crm.Sandbox.SandboxWorkerManager::_terminationWorkers
0x8ca9  ldarg.0
0x8caa  callvirt instance class [System]System.Uri Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_Uri()
0x8caf  ldloca.s 0
0x8cb1  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [System]System.Uri, class Microsoft.Crm.Sandbox.SandboxWorkerProcess>::TryRemove(var<u1>, !!T0)
0x8cb6  pop
0x8cb7  ret
```
