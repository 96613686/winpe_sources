# Microsoft.Crm.Asynchronous.EmailConnector.CrmTask::.ctor

- ea: `0x647a0`
- end: `0x647e7`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.CrmTask::.ctor`
- size: `71`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x70ce0`

## callees

- `0x64dd0`
- `0x70000`
- `0x700c0`

## string_xrefs

- `0x647b4`: `settaskpercentcomplete`
- `0x647d0`: `crmtaskassigneduniqueid`

## pseudocode

```c

```

## disassembly

```asm
0x647a0  ldarg.0
0x647a1  ldarg.1
0x647a2  ldarg.2
0x647a3  ldarg.3
0x647a4  ldstr    aTask_0// "task"
0x647a9  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.CrmTaskItem::.ctor(class Microsoft.Crm.Asynchronous.EmailConnector.IProvider provider, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, string entityName)
0x647ae  ldarg.0
0x647af  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.SetPropertyDelegateFunction> Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_SetPropertyDelegates()
0x647b4  ldstr    aSettaskpercent// "settaskpercentcomplete"
0x647b9  ldarg.0
0x647ba  ldftn    instance bool Microsoft.Crm.Asynchronous.EmailConnector.CrmTask::SetTaskPercentComplete()
0x647c0  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.SetPropertyDelegateFunction::.ctor(object object, native int method)
0x647c5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.SetPropertyDelegateFunction>::Add(var<u1>, !!T0)
0x647ca  ldarg.0
0x647cb  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.SetPropertyDelegateFunction> Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_SetPropertyDelegates()
0x647d0  ldstr    aCrmtaskassigne// "crmtaskassigneduniqueid"
0x647d5  ldarg.0
0x647d6  ldftn    instance bool Microsoft.Crm.Asynchronous.EmailConnector.CrmTask::SetTaskAssignedUniqueId()
0x647dc  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.SetPropertyDelegateFunction::.ctor(object object, native int method)
0x647e1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.SetPropertyDelegateFunction>::Add(var<u1>, !!T0)
0x647e6  ret
```
