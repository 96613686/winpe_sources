# Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueDataAccess::SelectEvents

- ea: `0x7490`
- end: `0x7516`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueDataAccess::SelectEvents`
- size: `134`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x4e00`
- `0x7490`
- `0x7520`
- `0x7960`
- `0x7b90`

## pseudocode

```c

```

## disassembly

```asm
0x7490  ldarg.0
0x7491  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x7496  call     bool Microsoft.Crm.Asynchronous.OrgServerSideSyncSettings::IsActivityQueueEnabled(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration orgConfiguration)
0x749b  brtrue.s loc_74A3
0x749d  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager>::.ctor()
0x74a2  ret
0x74a3  ldarg.0
0x74a4  ldarg.1
0x74a5  ldarg.0
0x74a6  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueManager Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueDataAccess::_queueManager
0x74ab  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IActivityQueueConfiguration Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueManager::get_FullConfiguration()
0x74b0  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IActivityQueueConfiguration::get_ActivitiesPerEvent()
0x74b5  mul
0x74b6  call     instance class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.EmailConnector.ActivityEntityWrapper> Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueDataAccess::SelectOutgoingActivities(int32 numberOfActivities)
0x74bb  stloc.0
0x74bc  ldarg.0
0x74bd  ldloc.0
0x74be  call     instance class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager> Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueDataAccess::GetEvents(class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.EmailConnector.ActivityEntityWrapper> activities)
0x74c3  stloc.1
0x74c4  ldarg.0
0x74c5  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x74ca  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x74cf  ldc.i4.s 0x15
0x74d1  ldstr    a01SelectingUpT// "{0}-{1}: Selecting up to {2} operations"...
0x74d6  ldc.i4.4
0x74d7  newarr   [mscorlib]System.Object
0x74dc  dup
0x74dd  ldc.i4.0
0x74de  ldarg.0
0x74df  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueManager Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueDataAccess::_queueManager
0x74e4  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_InstanceName()
0x74e9  stelem.ref
0x74ea  dup
0x74eb  ldc.i4.1
0x74ec  ldarg.0
0x74ed  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueManager Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueDataAccess::_queueManager
0x74f2  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_Name()
0x74f7  stelem.ref
0x74f8  dup
0x74f9  ldc.i4.2
0x74fa  ldarg.1
0x74fb  box      [mscorlib]System.Int32
0x7500  stelem.ref
0x7501  dup
0x7502  ldc.i4.3
0x7503  ldloc.1
0x7504  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager>::get_Count()
0x7509  box      [mscorlib]System.Int32
0x750e  stelem.ref
0x750f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7514  ldloc.1
0x7515  ret
```
