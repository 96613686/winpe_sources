# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeTaskItem::ValidateItem

- ea: `0x6d450`
- end: `0x6d518`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeTaskItem::ValidateItem`
- size: `200`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x516f0`
- `0x53440`
- `0x53490`
- `0x6d420`
- `0x6d450`
- `0x70120`
- `0x70720`

## string_xrefs

- `0x6d478`: `Synchronization for recurring task is not supported.`
- `0x6d500`: `Synchronization for assigned task is not supported.`

## pseudocode

```c

```

## disassembly

```asm
0x6d450  ldarg.0
0x6d451  call     instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Task Microsoft.Crm.Asynchronous.EmailConnector.ExchangeTaskItem::get_TaskItem()
0x6d456  callvirt instance bool [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Task::get_IsRecurring()
0x6d45b  brfalse.s loc_6D48A
0x6d45d  ldarg.0
0x6d45e  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_Context()
0x6d463  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x6d468  ldc.i4   0x80
0x6d46d  ldc.i4.1
0x6d46e  ldc.i4.3
0x6d46f  ldc.i4.0
0x6d470  ldc.i4.2
0x6d471  ldnull
0x6d472  call     class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.ErrorHandler::MailboxErrorInfoWithDynamicLink(valuetype [mscorlib]System.Guid organizationId, int32 traceCode, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorType errorType, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorSource errorSource, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorScope errorScope, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType mailboxOperationType, [opt] string errorString)
0x6d477  stloc.0
0x6d478  ldstr    aSynchronizatio// "Synchronization for recurring task is n"...
0x6d47d  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncException::.ctor(string message)
0x6d482  dup
0x6d483  ldloc.0
0x6d484  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncException::set_MailboxErrorInfo(class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo value)
0x6d489  throw
0x6d48a  ldarg.0
0x6d48b  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0x6d490  ldarg.0
0x6d491  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_Context()
0x6d496  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x6d49b  ldarg.0
0x6d49c  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_Context()
0x6d4a1  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x6d4a6  call     instance bool Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::IsAssignedTaskFeatureEnabled(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings orgSettings)
0x6d4ab  brtrue.s loc_6D512
0x6d4ad  ldarg.0
0x6d4ae  call     instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Task Microsoft.Crm.Asynchronous.EmailConnector.ExchangeTaskItem::get_TaskItem()
0x6d4b3  callvirt instance valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.TaskMode [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Task::get_Mode()
0x6d4b8  ldc.i4.1
0x6d4b9  beq.s    loc_6D4E5
0x6d4bb  ldarg.0
0x6d4bc  call     instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Task Microsoft.Crm.Asynchronous.EmailConnector.ExchangeTaskItem::get_TaskItem()
0x6d4c1  callvirt instance valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.TaskMode [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Task::get_Mode()
0x6d4c6  ldc.i4.2
0x6d4c7  beq.s    loc_6D4E5
0x6d4c9  ldarg.0
0x6d4ca  call     instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Task Microsoft.Crm.Asynchronous.EmailConnector.ExchangeTaskItem::get_TaskItem()
0x6d4cf  callvirt instance valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.TaskMode [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Task::get_Mode()
0x6d4d4  ldc.i4.3
0x6d4d5  beq.s    loc_6D4E5
0x6d4d7  ldarg.0
0x6d4d8  call     instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Task Microsoft.Crm.Asynchronous.EmailConnector.ExchangeTaskItem::get_TaskItem()
0x6d4dd  callvirt instance valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.TaskMode [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Task::get_Mode()
0x6d4e2  ldc.i4.5
0x6d4e3  bne.un.s loc_6D512
0x6d4e5  ldarg.0
0x6d4e6  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_Context()
0x6d4eb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x6d4f0  ldc.i4   0x81
0x6d4f5  ldc.i4.1
0x6d4f6  ldc.i4.3
0x6d4f7  ldc.i4.0
0x6d4f8  ldc.i4.2
0x6d4f9  ldnull
0x6d4fa  call     class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.ErrorHandler::MailboxErrorInfoWithDynamicLink(valuetype [mscorlib]System.Guid organizationId, int32 traceCode, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorType errorType, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorSource errorSource, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorScope errorScope, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType mailboxOperationType, [opt] string errorString)
0x6d4ff  stloc.1
0x6d500  ldstr    aSynchronizatio_0// "Synchronization for assigned task is no"...
0x6d505  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncException::.ctor(string message)
0x6d50a  dup
0x6d50b  ldloc.1
0x6d50c  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncException::set_MailboxErrorInfo(class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo value)
0x6d511  throw
0x6d512  leave.s  loc_6D517
0x6d514  pop
0x6d515  leave.s  loc_6D517
0x6d517  ret
```
