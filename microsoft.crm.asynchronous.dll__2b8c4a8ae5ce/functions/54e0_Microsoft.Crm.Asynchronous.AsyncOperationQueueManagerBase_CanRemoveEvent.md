# Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::CanRemoveEvent

- ea: `0x54e0`
- end: `0x54f6`
- name: `Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::CanRemoveEvent`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x50a0`

## callees

- `0x2e60`
- `0x54e0`

## pseudocode

```c

```

## disassembly

```asm
0x54e0  ldarg.2
0x54e1  isinst   Microsoft.Crm.Asynchronous.AsyncRemoveEventResult
0x54e6  brfalse.s loc_54F4
0x54e8  ldarg.1
0x54e9  callvirt instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.AsyncEvent::get_OrganizationConfiguration()
0x54ee  callvirt instance bool [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_CanRemoveCompletedJobs()
0x54f3  ret
0x54f4  ldc.i4.0
0x54f5  ret
```
