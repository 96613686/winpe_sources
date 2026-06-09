# Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueDataAccess::GetEvents

- ea: `0x7960`
- end: `0x7a04`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueDataAccess::GetEvents`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x7490`

## callees

- `0x7410`
- `0x7960`
- `0x7b90`

## pseudocode

```c

```

## disassembly

```asm
0x7960  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager>::.ctor()
0x7965  stloc.0
0x7966  ldarg.1
0x7967  ldarg.0
0x7968  ldftn    instance int32 Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueDataAccess::CompareEmailsByProfile(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.EmailConnector.ActivityEntityWrapper activity1, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.EmailConnector.ActivityEntityWrapper activity2)
0x796e  newobj   instance void class [mscorlib]System.Comparison`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.EmailConnector.ActivityEntityWrapper>::.ctor(object, native int)
0x7973  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.EmailConnector.ActivityEntityWrapper>::Sort(class [mscorlib]System.Comparison`1<var<u1>>)
0x7978  ldc.i4.0
0x7979  stloc.1
0x797a  br.s     loc_79F6
0x797c  ldloc.1
0x797d  ldarg.0
0x797e  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueManager Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueDataAccess::_queueManager
0x7983  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IActivityQueueConfiguration Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueManager::get_FullConfiguration()
0x7988  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IActivityQueueConfiguration::get_ActivitiesPerEvent()
0x798d  add
0x798e  ldarg.1
0x798f  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.EmailConnector.ActivityEntityWrapper>::get_Count()
0x7994  blt.s    loc_79A0
0x7996  ldarg.1
0x7997  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.EmailConnector.ActivityEntityWrapper>::get_Count()
0x799c  ldloc.1
0x799d  sub
0x799e  br.s     loc_79B0
0x79a0  ldarg.0
0x79a1  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueManager Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueDataAccess::_queueManager
0x79a6  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IActivityQueueConfiguration Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueManager::get_FullConfiguration()
0x79ab  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IActivityQueueConfiguration::get_ActivitiesPerEvent()
0x79b0  stloc.2
0x79b1  ldarg.0
0x79b2  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x79b7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x79bc  ldc.i4.s 0x32
0x79be  ldarg.1
0x79bf  ldloc.1
0x79c0  ldloc.2
0x79c1  callvirt instance class [mscorlib]System.Collections.Generic.List`1<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.EmailConnector.ActivityEntityWrapper>::GetRange(!!T0, int32)
0x79c6  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.EmailConnector.ActivityEntityWrapper>::AsReadOnly()
0x79cb  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.EmailConnector.ActivityAsyncEvent::.ctor(valuetype [mscorlib]System.Guid, int32, class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.EmailConnector.ActivityEntityWrapper>)
0x79d0  stloc.3
0x79d1  ldloc.0
0x79d2  ldarg.0
0x79d3  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueManager Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueDataAccess::_queueManager
0x79d8  ldloc.3
0x79d9  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.ActivityExecutionManager::.ctor(class Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueManager queueManager, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.EmailConnector.ActivityAsyncEvent asyncEvent)
0x79de  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager>::Add(var<u1>)
0x79e3  ldloc.1
0x79e4  ldarg.0
0x79e5  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueManager Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueDataAccess::_queueManager
0x79ea  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IActivityQueueConfiguration Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueManager::get_FullConfiguration()
0x79ef  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IActivityQueueConfiguration::get_ActivitiesPerEvent()
0x79f4  add
0x79f5  stloc.1
0x79f6  ldloc.1
0x79f7  ldarg.1
0x79f8  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.EmailConnector.ActivityEntityWrapper>::get_Count()
0x79fd  blt      loc_797C
0x7a02  ldloc.0
0x7a03  ret
```
