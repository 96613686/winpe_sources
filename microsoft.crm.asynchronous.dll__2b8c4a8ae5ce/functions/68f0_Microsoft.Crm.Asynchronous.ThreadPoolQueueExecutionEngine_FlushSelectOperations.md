# Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::FlushSelectOperations

- ea: `0x68f0`
- end: `0x6950`
- name: `Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::FlushSelectOperations`
- size: `96`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x9ac0`

## callees

- `0x68f0`
- `0x7e90`
- `0xb590`

## pseudocode

```c

```

## disassembly

```asm
0x68f0  ldarg.1
0x68f1  brfalse.s loc_690C
0x68f3  ldarg.2
0x68f4  brfalse.s loc_690C
0x68f6  ldarg.2
0x68f7  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration> Microsoft.Crm.Asynchronous.OrganizationChangedEventArgs::get_InactiveOrganizations()
0x68fc  brfalse.s loc_690C
0x68fe  ldarg.2
0x68ff  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration> Microsoft.Crm.Asynchronous.OrganizationChangedEventArgs::get_InactiveOrganizations()
0x6904  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration>::get_Count()
0x6909  ldc.i4.0
0x690a  bgt.s    loc_690D
0x690c  ret
0x690d  ldarg.2
0x690e  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration> Microsoft.Crm.Asynchronous.OrganizationChangedEventArgs::get_InactiveOrganizations()
0x6913  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration>::GetEnumerator()
0x6918  stloc.0
0x6919  br.s     loc_6936
0x691b  ldloca.s 0
0x691d  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration>::get_Current()
0x6922  stloc.1
0x6923  ldarg.0
0x6924  ldfld    class Microsoft.Crm.Asynchronous.MultiOrgQueue Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::_eventQueue
0x6929  ldloca.s 1
0x692b  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration>::get_Key()
0x6930  ldarg.1
0x6931  callvirt instance void Microsoft.Crm.Asynchronous.MultiOrgQueue::FlushOrgQueue(valuetype [mscorlib]System.Guid orgId, class Microsoft.Crm.Asynchronous.SelectionCriteria handlePausedJob)
0x6936  ldloca.s 0
0x6938  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration>::MoveNext()
0x693d  brtrue.s loc_691B
0x693f  leave.s  loc_694F
0x6941  ldloca.s 0
0x6943  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration>
0x6949  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x694e  endfinally
0x694f  ret
```
