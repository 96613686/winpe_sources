# Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager::GetQueueDataAccess

- ea: `0xa1a0`
- end: `0xa1b8`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager::GetQueueDataAccess`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x7e00`
- `0x96c0`
- `0x9ee0`
- `0xa1a0`

## pseudocode

```c

```

## disassembly

```asm
0xa1a0  ldarg.0
0xa1a1  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncDebugContext Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager::get_DebugContext()
0xa1a6  brfalse.s loc_A1B0
0xa1a8  ldarg.0
0xa1a9  ldarg.1
0xa1aa  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccessDebug::.ctor(class Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager queueManager, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration configuration)
0xa1af  ret
0xa1b0  ldarg.0
0xa1b1  ldarg.1
0xa1b2  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::.ctor(class Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager queueManager, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration configuration)
0xa1b7  ret
```
