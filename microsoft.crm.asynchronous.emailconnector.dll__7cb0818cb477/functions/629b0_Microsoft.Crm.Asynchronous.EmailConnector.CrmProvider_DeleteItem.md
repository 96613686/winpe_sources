# Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::DeleteItem

- ea: `0x629b0`
- end: `0x62afe`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::DeleteItem`
- size: `334`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callers

- `0x61f20`

## callees

- `0x4da80`
- `0x58a20`
- `0x58b30`
- `0x59000`
- `0x59a30`
- `0x5a9b0`
- `0x5e6d0`
- `0x60b90`
- `0x62580`
- `0x625c0`
- `0x62680`
- `0x629b0`
- `0x702d0`
- `0x70300`

## string_xrefs

- `0x629dc`: `DeleteItem`
- `0x62aed`: `DeleteItem`
- `0x629d1`: `DeleteRequest`
- `0x62ae2`: `DeleteRequest`
- `0x62a38`: `Deleted the crm {0} item {1} on the crm server for the mailbox : {2}.`
- `0x62a94`: `Failed to delete the crm {0} item on the crm server for the mailbox : {1}. Exception details : {2}.`

## pseudocode

```c

```

## disassembly

```asm
0x629b0  ldarg.1
0x629b1  brtrue.s loc_629BE
0x629b3  ldstr    aInvalidInput// "Invalid input."
0x629b8  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x629bd  throw
0x629be  ldarg.1
0x629bf  castclass Microsoft.Crm.Asynchronous.EmailConnector.CrmItem
0x629c4  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.CrmItem::get_Entity()
0x629c9  stloc.0
0x629ca  ldc.i4.0
0x629cb  ldarg.0
0x629cc  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::_context
0x629d1  ldstr    aDeleterequest// "DeleteRequest"
0x629d6  ldloc.0
0x629d7  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x629dc  ldstr    aDeleteitem// "DeleteItem"
0x629e1  ldstr    asc_8A7C2// ""
0x629e6  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteCrmServiceExecuteEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string requestName, string entityType, string functionName, [opt] string functionParam)
0x629eb  ldloc.0
0x629ec  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x629f1  stloc.1
0x629f2  ldloc.0
0x629f3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x629f8  stloc.2
0x629f9  ldloc.1
0x629fa  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x629ff  brtrue   loc_62A8E
0x62a04  ldloc.2
0x62a05  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x62a0a  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x62a0f  brfalse.s loc_62A8E
0x62a11  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.DeleteRequest::.ctor()
0x62a16  stloc.3
0x62a17  ldloc.3
0x62a18  ldloc.1
0x62a19  ldloc.2
0x62a1a  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x62a1f  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.DeleteRequest::set_Target(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference)
0x62a24  ldarg.0
0x62a25  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::get_CrmService()
0x62a2a  ldloc.3
0x62a2b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x62a30  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.DeleteResponse
0x62a35  pop
0x62a36  ldarg.0
0x62a37  ldc.i4.4
0x62a38  ldstr    aDeletedTheCrm0// "Deleted the crm {0} item {1} on the crm"...
0x62a3d  ldc.i4.3
0x62a3e  newarr   [mscorlib]System.Object
0x62a43  dup
0x62a44  ldc.i4.0
0x62a45  ldarg.1
0x62a46  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_ItemObjectType()
0x62a4b  box      [Microsoft.Crm]Microsoft.Crm.ItemObjectType
0x62a50  stelem.ref
0x62a51  dup
0x62a52  ldc.i4.1
0x62a53  ldloc.2
0x62a54  call     string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::ToStringValue(valuetype [mscorlib]System.Guid propertyValue)
0x62a59  stelem.ref
0x62a5a  dup
0x62a5b  ldc.i4.2
0x62a5c  ldarg.0
0x62a5d  call     instance string Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::get_MailboxId()
0x62a62  stelem.ref
0x62a63  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x62a68  ldarg.0
0x62a69  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorker Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::_exchangeSyncWorker
0x62a6e  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorker::get_StepContext()
0x62a73  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.CrmItemFinder Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext::get_CrmFinder()
0x62a78  ldloc.0
0x62a79  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x62a7e  call     valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::GetExchangeItemType(string entityName)
0x62a83  ldloc.2
0x62a84  call     string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::ToStringValue(valuetype [mscorlib]System.Guid propertyValue)
0x62a89  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::RecordCausedItemChange(valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType itemType, string itemId)
0x62a8e  leave.s  loc_62AFD
0x62a90  stloc.s  4
0x62a92  ldarg.0
0x62a93  ldc.i4.2
0x62a94  ldstr    aFailedToDelete_0// "Failed to delete the crm {0} item on th"...
0x62a99  ldc.i4.4
0x62a9a  newarr   [mscorlib]System.Object
0x62a9f  dup
0x62aa0  ldc.i4.0
0x62aa1  ldarg.1
0x62aa2  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_ItemObjectType()
0x62aa7  box      [Microsoft.Crm]Microsoft.Crm.ItemObjectType
0x62aac  stelem.ref
0x62aad  dup
0x62aae  ldc.i4.1
0x62aaf  ldarg.1
0x62ab0  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_ToCrmId()
0x62ab5  stelem.ref
0x62ab6  dup
0x62ab7  ldc.i4.2
0x62ab8  ldarg.0
0x62ab9  call     instance string Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::get_MailboxId()
0x62abe  stelem.ref
0x62abf  dup
0x62ac0  ldc.i4.3
0x62ac1  ldloc.s  4
0x62ac3  ldarg.0
0x62ac4  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::_context
0x62ac9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x62ace  call     string Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorExceptionToString(class [mscorlib]System.Exception e, valuetype [mscorlib]System.Guid orgId)
0x62ad3  stelem.ref
0x62ad4  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x62ad9  rethrow
0x62adb  ldc.i4.1
0x62adc  ldarg.0
0x62add  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::_context
0x62ae2  ldstr    aDeleterequest// "DeleteRequest"
0x62ae7  ldloc.0
0x62ae8  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x62aed  ldstr    aDeleteitem// "DeleteItem"
0x62af2  ldstr    asc_8A7C2// ""
0x62af7  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteCrmServiceExecuteEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string requestName, string entityType, string functionName, [opt] string functionParam)
0x62afc  endfinally
0x62afd  ret
```
