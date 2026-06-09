# Microsoft.Crm.Sandbox.PluginTraceLogQueuesProcessor::TryGetNextQueue

- ea: `0x6920`
- end: `0x6957`
- name: `Microsoft.Crm.Sandbox.PluginTraceLogQueuesProcessor::TryGetNextQueue`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x67d0`

## callees

- `0x6920`
- `0x69f0`

## pseudocode

```c

```

## disassembly

```asm
0x6920  ldsfld   object Microsoft.Crm.Sandbox.PluginTraceLogQueuesProcessor::_lockObject
0x6925  stloc.0
0x6926  ldc.i4.0
0x6927  stloc.1
0x6928  ldloc.0
0x6929  ldloca.s 1
0x692b  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x6930  ldarg.0
0x6931  ldfld    class Microsoft.Crm.Sandbox.RoundRobinIterator Microsoft.Crm.Sandbox.PluginTraceLogQueuesProcessor::_queueIterator
0x6936  ldarg.0
0x6937  ldfld    valuetype [mscorlib]System.Guid[] Microsoft.Crm.Sandbox.PluginTraceLogQueuesProcessor::_orgIds
0x693c  ldarg.0
0x693d  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord>> Microsoft.Crm.Sandbox.PluginTraceLogQueuesProcessor::_queues
0x6942  ldarg.1
0x6943  callvirt instance bool Microsoft.Crm.Sandbox.RoundRobinIterator::TryGetNextQueue(valuetype [mscorlib]System.Guid[] ids, class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord>> queues, [out] class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord>& nextQueue)
0x6948  stloc.2
0x6949  leave.s  loc_6955
0x694b  ldloc.1
0x694c  brfalse.s loc_6954
0x694e  ldloc.0
0x694f  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x6954  endfinally
0x6955  ldloc.2
0x6956  ret
```
