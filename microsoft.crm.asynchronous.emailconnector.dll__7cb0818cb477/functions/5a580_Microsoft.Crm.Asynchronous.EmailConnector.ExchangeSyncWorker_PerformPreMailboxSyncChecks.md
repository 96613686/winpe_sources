# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorker::PerformPreMailboxSyncChecks

- ea: `0x5a580`
- end: `0x5a6fb`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorker::PerformPreMailboxSyncChecks`
- size: `379`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x5a3d0`

## callees

- `0x7d00`
- `0x42280`
- `0x516f0`
- `0x521e0`
- `0x53440`
- `0x53490`
- `0x58630`
- `0x586b0`
- `0x5a580`

## string_xrefs

- `0x5a5b2`: `User doesn't have the read/write permission for Mailbox Entity`
- `0x5a601`: `User doesn't have write access for ExchangeSyncIdMapping Entity`
- `0x5a654`: `User doesn't have delete access for ExchangeSyncIdMapping Entity`

## pseudocode

```c

```

## disassembly

```asm
0x5a580  ldarg.0
0x5a581  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ACTProviderBase::get_Context()
0x5a586  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeACTAccessConfiguration Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext::get_ACTAccessConfiguration()
0x5a58b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData Microsoft.Crm.Asynchronous.EmailConnector.IMailboxAccessConfiguration::get_Mailbox()
0x5a590  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_RegardingObjectId()
0x5a595  stloc.0
0x5a596  ldloc.0
0x5a597  ldarg.0
0x5a598  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ACTProviderBase::get_Context()
0x5a59d  ldc.i4.2
0x5a59e  newarr   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType
0x5a5a3  dup
0x5a5a4  ldc.i4.0
0x5a5a5  ldc.i4.1
0x5a5a6  stelem.i4
0x5a5a7  dup
0x5a5a8  ldc.i4.1
0x5a5a9  ldc.i4.2
0x5a5aa  stelem.i4
0x5a5ab  call     bool Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::HasMailboxPrivilege(valuetype [mscorlib]System.Guid userId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType[] privilegeTypes)
0x5a5b0  brtrue.s loc_5A5DD
0x5a5b2  ldstr    aUserDoesnTHave// "User doesn't have the read/write permis"...
0x5a5b7  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncException::.ctor(string message)
0x5a5bc  dup
0x5a5bd  ldarg.0
0x5a5be  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ACTProviderBase::get_Context()
0x5a5c3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x5a5c8  ldc.i4   0x96
0x5a5cd  ldc.i4.0
0x5a5ce  ldc.i4.0
0x5a5cf  ldc.i4.3
0x5a5d0  ldc.i4.2
0x5a5d1  ldnull
0x5a5d2  call     class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.ErrorHandler::MailboxErrorInfoWithDynamicLink(valuetype [mscorlib]System.Guid organizationId, int32 traceCode, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorType errorType, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorSource errorSource, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorScope errorScope, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType mailboxOperationType, [opt] string errorString)
0x5a5d7  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncException::set_MailboxErrorInfo(class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo value)
0x5a5dc  throw
0x5a5dd  ldloc.0
0x5a5de  ldarg.0
0x5a5df  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ACTProviderBase::get_Context()
0x5a5e4  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeACTAccessConfiguration Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext::get_ACTAccessConfiguration()
0x5a5e9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData Microsoft.Crm.Asynchronous.EmailConnector.IMailboxAccessConfiguration::get_Mailbox()
0x5a5ee  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_RegardingObjectTypeCode()
0x5a5f3  ldarg.0
0x5a5f4  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ACTProviderBase::get_Context()
0x5a5f9  ldc.i4.2
0x5a5fa  call     bool Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::HasExchangeSyncIdMappingAccess(valuetype [mscorlib]System.Guid userId, int32 userIdTypeCode, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext orgContext, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AccessRights accessRights)
0x5a5ff  brtrue.s loc_5A62C
0x5a601  ldstr    aUserDoesnTHave_0// "User doesn't have write access for Exch"...
0x5a606  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncException::.ctor(string message)
0x5a60b  dup
0x5a60c  ldarg.0
0x5a60d  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ACTProviderBase::get_Context()
0x5a612  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x5a617  ldc.i4   0x96
0x5a61c  ldc.i4.0
0x5a61d  ldc.i4.0
0x5a61e  ldc.i4.3
0x5a61f  ldc.i4.2
0x5a620  ldnull
0x5a621  call     class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.ErrorHandler::MailboxErrorInfoWithDynamicLink(valuetype [mscorlib]System.Guid organizationId, int32 traceCode, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorType errorType, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorSource errorSource, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorScope errorScope, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType mailboxOperationType, [opt] string errorString)
0x5a626  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncException::set_MailboxErrorInfo(class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo value)
0x5a62b  throw
0x5a62c  ldloc.0
0x5a62d  ldarg.0
0x5a62e  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ACTProviderBase::get_Context()
0x5a633  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeACTAccessConfiguration Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext::get_ACTAccessConfiguration()
0x5a638  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData Microsoft.Crm.Asynchronous.EmailConnector.IMailboxAccessConfiguration::get_Mailbox()
0x5a63d  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_RegardingObjectTypeCode()
0x5a642  ldarg.0
0x5a643  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ACTProviderBase::get_Context()
0x5a648  ldc.i4   0x10000
0x5a64d  call     bool Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::HasExchangeSyncIdMappingAccess(valuetype [mscorlib]System.Guid userId, int32 userIdTypeCode, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext orgContext, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AccessRights accessRights)
0x5a652  brtrue.s loc_5A67F
0x5a654  ldstr    aUserDoesnTHave_1// "User doesn't have delete access for Exc"...
0x5a659  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncException::.ctor(string message)
0x5a65e  dup
0x5a65f  ldarg.0
0x5a660  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ACTProviderBase::get_Context()
0x5a665  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x5a66a  ldc.i4   0x96
0x5a66f  ldc.i4.0
0x5a670  ldc.i4.0
0x5a671  ldc.i4.3
0x5a672  ldc.i4.2
0x5a673  ldnull
0x5a674  call     class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.ErrorHandler::MailboxErrorInfoWithDynamicLink(valuetype [mscorlib]System.Guid organizationId, int32 traceCode, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorType errorType, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorSource errorSource, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorScope errorScope, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType mailboxOperationType, [opt] string errorString)
0x5a679  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncException::set_MailboxErrorInfo(class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo value)
0x5a67e  throw
0x5a67f  ldarg.0
0x5a680  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ACTProviderBase::get_Context()
0x5a685  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x5a68a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x5a68f  stloc.1
0x5a690  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.SyncAttributeMappingsCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.SyncAttributeMappingsCache::Instance()
0x5a695  ldarg.0
0x5a696  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ACTProviderBase::get_Context()
0x5a69b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x5a6a0  ldloc.1
0x5a6a1  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISyncAttributeMappingsData>::LookupEntry(void, var<u1>)
0x5a6a6  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeMappingCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISyncAttributeMappingsData::get_SyncAttributeMappings()
0x5a6ab  brfalse.s loc_5A6CF
0x5a6ad  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.SyncAttributeMappingsCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.SyncAttributeMappingsCache::Instance()
0x5a6b2  ldarg.0
0x5a6b3  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ACTProviderBase::get_Context()
0x5a6b8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x5a6bd  ldloc.1
0x5a6be  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISyncAttributeMappingsData>::LookupEntry(void, var<u1>)
0x5a6c3  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeMappingCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISyncAttributeMappingsData::get_SyncAttributeMappings()
0x5a6c8  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeMapping>::get_Count()
0x5a6cd  brtrue.s loc_5A6FA
0x5a6cf  ldstr    aCouldNotFindTh_0// "Could not find the sync attribute mappi"...
0x5a6d4  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncException::.ctor(string message)
0x5a6d9  dup
0x5a6da  ldarg.0
0x5a6db  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ACTProviderBase::get_Context()
0x5a6e0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x5a6e5  ldc.i4   0xBB
0x5a6ea  ldc.i4.0
0x5a6eb  ldc.i4.0
0x5a6ec  ldc.i4.3
0x5a6ed  ldc.i4.2
0x5a6ee  ldnull
0x5a6ef  call     class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.ErrorHandler::MailboxErrorInfoWithDynamicLink(valuetype [mscorlib]System.Guid organizationId, int32 traceCode, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorType errorType, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorSource errorSource, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorScope errorScope, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType mailboxOperationType, [opt] string errorString)
0x5a6f4  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncException::set_MailboxErrorInfo(class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo value)
0x5a6f9  throw
0x5a6fa  ret
```
