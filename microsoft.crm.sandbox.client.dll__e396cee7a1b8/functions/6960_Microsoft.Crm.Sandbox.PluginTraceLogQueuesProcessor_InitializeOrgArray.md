# Microsoft.Crm.Sandbox.PluginTraceLogQueuesProcessor::InitializeOrgArray

- ea: `0x6960`
- end: `0x6993`
- name: `Microsoft.Crm.Sandbox.PluginTraceLogQueuesProcessor::InitializeOrgArray`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x6610`

## pseudocode

```c

```

## disassembly

```asm
0x6960  ldarg.0
0x6961  ldarg.0
0x6962  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord>> Microsoft.Crm.Sandbox.PluginTraceLogQueuesProcessor::_queues
0x6967  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<var<u1>> class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord>>::get_Keys()
0x696c  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<valuetype [mscorlib]System.Guid>::get_Count()
0x6971  newarr   [mscorlib]System.Guid
0x6976  stfld    valuetype [mscorlib]System.Guid[] Microsoft.Crm.Sandbox.PluginTraceLogQueuesProcessor::_orgIds
0x697b  ldarg.0
0x697c  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord>> Microsoft.Crm.Sandbox.PluginTraceLogQueuesProcessor::_queues
0x6981  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<var<u1>> class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord>>::get_Keys()
0x6986  ldarg.0
0x6987  ldfld    valuetype [mscorlib]System.Guid[] Microsoft.Crm.Sandbox.PluginTraceLogQueuesProcessor::_orgIds
0x698c  ldc.i4.0
0x698d  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<valuetype [mscorlib]System.Guid>::CopyTo(var<u1>[], !!T0)
0x6992  ret
```
