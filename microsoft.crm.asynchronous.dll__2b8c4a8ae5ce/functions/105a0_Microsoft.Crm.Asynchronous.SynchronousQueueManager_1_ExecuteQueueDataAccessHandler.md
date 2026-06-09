# Microsoft.Crm.Asynchronous.SynchronousQueueManager`1::ExecuteQueueDataAccessHandler

- ea: `0x105a0`
- end: `0x105d5`
- name: `Microsoft.Crm.Asynchronous.SynchronousQueueManager`1::ExecuteQueueDataAccessHandler`
- size: `53`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x105a0`
- `0x15310`

## string_xrefs

- `0x105aa`: `Unexpected service operation`

## pseudocode

```c

```

## disassembly

```asm
0x105a0  ldarg.2
0x105a1  isinst   Microsoft.Crm.Asynchronous.Operations.QueueManagementOperation
0x105a6  dup
0x105a7  ldnull
0x105a8  cgt.un
0x105aa  ldstr    aUnexpectedServ// "Unexpected service operation"
0x105af  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x105b4  callvirt instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.Operations.OrganizationOperation::get_OrganizationConfiguration()
0x105b9  stloc.0
0x105ba  ldloc.0
0x105bb  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationState()
0x105c0  ldc.i4.1
0x105c1  beq.s    loc_105C4
0x105c3  ret
0x105c4  ldarg.0
0x105c5  ldloc.0
0x105c6  callvirt instance var<u1> class Microsoft.Crm.Asynchronous.SynchronousQueueManager`1<var<u1>>::GetQueueDataAccess(!!T0)
0x105cb  stloc.1
0x105cc  ldarg.1
0x105cd  ldloc.1
0x105ce  ldloc.0
0x105cf  callvirt instance void class OrganizationQueueDataAccessHandler<var<u1>>::Invoke(var<u1>, !!T0)
0x105d4  ret
```
