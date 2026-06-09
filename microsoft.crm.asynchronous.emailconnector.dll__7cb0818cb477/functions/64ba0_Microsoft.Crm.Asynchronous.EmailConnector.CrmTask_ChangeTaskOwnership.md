# Microsoft.Crm.Asynchronous.EmailConnector.CrmTask::ChangeTaskOwnership

- ea: `0x64ba0`
- end: `0x64caa`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.CrmTask::ChangeTaskOwnership`
- size: `266`
- prototype: ``
- caller_count: `3`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x649b0`
- `0x64a10`
- `0x64cb0`

## callees

- `0x516f0`
- `0x60b80`
- `0x60b90`
- `0x63bc0`
- `0x64a90`
- `0x64ad0`
- `0x64ba0`
- `0x64cd0`
- `0x70120`
- `0x701d0`
- `0x702a0`
- `0x70330`
- `0x70730`

## string_xrefs

- `0x64bd1`: `crmtaskassigneeuserid`
- `0x64bc1`: `crmtaskassigneruserid`

## pseudocode

```c

```

## disassembly

```asm
0x64ba0  ldarg.0
0x64ba1  call     instance bool Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::ProcessAssignedTask()
0x64ba6  brfalse  loc_64CA8
0x64bab  ldnull
0x64bac  stloc.0
0x64bad  ldarg.0
0x64bae  call     instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.NonCrmTaskOwnership Microsoft.Crm.Asynchronous.EmailConnector.CrmTask::GetTaskOwnership()
0x64bb3  stloc.1
0x64bb4  ldarg.0
0x64bb5  call     instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.NonCrmTaskAcceptanceState Microsoft.Crm.Asynchronous.EmailConnector.CrmTask::GetTaskAcceptanceState()
0x64bba  stloc.2
0x64bbb  ldarg.0
0x64bbc  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_InputSyncItem()
0x64bc1  ldstr    aCrmtaskassigne_1// "crmtaskassigneruserid"
0x64bc6  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::GetProperty(string propertyName)
0x64bcb  ldarg.0
0x64bcc  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_InputSyncItem()
0x64bd1  ldstr    aCrmtaskassigne_0// "crmtaskassigneeuserid"
0x64bd6  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::GetProperty(string propertyName)
0x64bdb  stloc.3
0x64bdc  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x64be1  brtrue.s loc_64BEB
0x64be3  ldloc.3
0x64be4  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x64be9  brfalse.s loc_64BED
0x64beb  ldc.i4.0
0x64bec  ret
0x64bed  ldsfld   string [mscorlib]System.String::Empty
0x64bf2  stloc.s  4
0x64bf4  ldc.i4.0
0x64bf5  stloc.s  5
0x64bf7  ldloc.2
0x64bf8  ldc.i4.5
0x64bf9  bne.un.s loc_64C1B
0x64bfb  ldarg.0
0x64bfc  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_Context()
0x64c01  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x64c06  ldc.i4   0x8F
0x64c0b  ldc.i4.1
0x64c0c  ldc.i4.0
0x64c0d  ldc.i4.0
0x64c0e  ldc.i4.2
0x64c0f  ldnull
0x64c10  call     class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.ErrorHandler::MailboxErrorInfoWithDynamicLink(valuetype [mscorlib]System.Guid organizationId, int32 traceCode, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorType errorType, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorSource errorSource, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorScope errorScope, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType mailboxOperationType, [opt] string errorString)
0x64c15  stloc.0
0x64c16  ldc.i4.0
0x64c17  stloc.s  5
0x64c19  br.s     loc_64C4D
0x64c1b  ldloc.1
0x64c1c  brtrue.s loc_64C42
0x64c1e  ldloc.2
0x64c1f  ldc.i4.3
0x64c20  bne.un.s loc_64C42
0x64c22  ldarg.0
0x64c23  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_Context()
0x64c28  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x64c2d  ldc.i4   0x91
0x64c32  ldc.i4.1
0x64c33  ldc.i4.0
0x64c34  ldc.i4.0
0x64c35  ldc.i4.2
0x64c36  ldnull
0x64c37  call     class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.ErrorHandler::MailboxErrorInfoWithDynamicLink(valuetype [mscorlib]System.Guid organizationId, int32 traceCode, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorType errorType, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorSource errorSource, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorScope errorScope, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType mailboxOperationType, [opt] string errorString)
0x64c3c  stloc.0
0x64c3d  ldc.i4.0
0x64c3e  stloc.s  5
0x64c40  br.s     loc_64C4D
0x64c42  ldloc.1
0x64c43  ldc.i4.1
0x64c44  bne.un.s loc_64C4D
0x64c46  ldloc.2
0x64c47  ldc.i4.4
0x64c48  bne.un.s loc_64C4D
0x64c4a  ldloc.3
0x64c4b  stloc.s  4
0x64c4d  ldarg.0
0x64c4e  ldloc.0
0x64c4f  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.CrmTask::LogMailboxErrorInfo(class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo errorInfo)
0x64c54  ldloc.s  4
0x64c56  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x64c5b  brtrue.s loc_64CA5
0x64c5d  ldarg.0
0x64c5e  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider Microsoft.Crm.Asynchronous.EmailConnector.CrmItem::get_CrmProvider()
0x64c63  ldarg.0
0x64c64  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.CrmItem::get_Entity()
0x64c69  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x64c6e  ldarg.0
0x64c6f  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_FromCrmId()
0x64c74  ldloc.s  4
0x64c76  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::Assign(string entityName, string entityId, string userId)
0x64c7b  brtrue.s loc_64CA2
0x64c7d  ldarg.0
0x64c7e  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_Context()
0x64c83  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x64c88  ldc.i4   0x8E
0x64c8d  ldc.i4.1
0x64c8e  ldc.i4.0
0x64c8f  ldc.i4.0
0x64c90  ldc.i4.2
0x64c91  ldnull
0x64c92  call     class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.ErrorHandler::MailboxErrorInfoWithDynamicLink(valuetype [mscorlib]System.Guid organizationId, int32 traceCode, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorType errorType, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorSource errorSource, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorScope errorScope, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType mailboxOperationType, [opt] string errorString)
0x64c97  stloc.0
0x64c98  ldarg.0
0x64c99  ldloc.0
0x64c9a  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.CrmTask::LogMailboxErrorInfo(class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo errorInfo)
0x64c9f  ldc.i4.0
0x64ca0  stloc.s  5
0x64ca2  ldc.i4.1
0x64ca3  stloc.s  5
0x64ca5  ldloc.s  5
0x64ca7  ret
0x64ca8  ldc.i4.0
0x64ca9  ret
```
