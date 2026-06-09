# Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::UpdateItem

- ea: `0x62860`
- end: `0x629a7`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::UpdateItem`
- size: `327`
- prototype: ``
- caller_count: `3`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callers

- `0x602d0`
- `0x61f70`
- `0x620a0`

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
- `0x62860`
- `0x63ca0`
- `0x70120`
- `0x702d0`
- `0x70300`

## string_xrefs

- `0x6288c`: `UpdateItem`
- `0x62996`: `UpdateItem`
- `0x62881`: `UpdateRequest`
- `0x6298b`: `UpdateRequest`
- `0x628ed`: `Updated the crm {0} item {1} on the crm server for the mailbox : {2}.`
- `0x6293e`: `Failed to update the crm {0} item {1} on the crm server for the mailbox : {2}. Exception details : {3}.`

## pseudocode

```c

```

## disassembly

```asm
0x62860  ldarg.1
0x62861  brtrue.s loc_6286E
0x62863  ldstr    aInvalidInput// "Invalid input."
0x62868  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x6286d  throw
0x6286e  ldarg.1
0x6286f  castclass Microsoft.Crm.Asynchronous.EmailConnector.CrmItem
0x62874  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.CrmItem::get_Entity()
0x62879  stloc.0
0x6287a  ldc.i4.0
0x6287b  ldarg.0
0x6287c  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::_context
0x62881  ldstr    aUpdaterequest// "UpdateRequest"
0x62886  ldloc.0
0x62887  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x6288c  ldstr    aUpdateitem// "UpdateItem"
0x62891  ldstr    asc_8A7C2// ""
0x62896  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteCrmServiceExecuteEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string requestName, string entityType, string functionName, [opt] string functionParam)
0x6289b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.UpdateRequest::.ctor()
0x628a0  stloc.1
0x628a1  ldarg.2
0x628a2  brtrue.s loc_628B5
0x628a4  ldarg.0
0x628a5  ldarg.1
0x628a6  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_Context()
0x628ab  call     instance bool Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::IsDuplicateDetectionEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x628b0  brtrue.s loc_628B5
0x628b2  ldc.i4.1
0x628b3  starg.s  2
0x628b5  ldloc.1
0x628b6  ldstr    aSuppressduplic// "SuppressDuplicateDetection"
0x628bb  ldarg.2
0x628bc  box      [mscorlib]System.Boolean
0x628c1  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::set_Item(string, object)
0x628c6  ldloc.1
0x628c7  ldloc.0
0x628c8  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.UpdateRequest::set_Target(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0x628cd  ldarg.0
0x628ce  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::get_CrmService()
0x628d3  ldloc.1
0x628d4  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x628d9  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.UpdateResponse
0x628de  pop
0x628df  ldloc.0
0x628e0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x628e5  call     string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::ToStringValue(valuetype [mscorlib]System.Guid propertyValue)
0x628ea  stloc.2
0x628eb  ldarg.0
0x628ec  ldc.i4.4
0x628ed  ldstr    aUpdatedTheCrm0// "Updated the crm {0} item {1} on the crm"...
0x628f2  ldc.i4.3
0x628f3  newarr   [mscorlib]System.Object
0x628f8  dup
0x628f9  ldc.i4.0
0x628fa  ldarg.1
0x628fb  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_ItemObjectType()
0x62900  box      [Microsoft.Crm]Microsoft.Crm.ItemObjectType
0x62905  stelem.ref
0x62906  dup
0x62907  ldc.i4.1
0x62908  ldloc.2
0x62909  stelem.ref
0x6290a  dup
0x6290b  ldc.i4.2
0x6290c  ldarg.0
0x6290d  call     instance string Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::get_MailboxId()
0x62912  stelem.ref
0x62913  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x62918  ldarg.0
0x62919  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorker Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::_exchangeSyncWorker
0x6291e  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorker::get_StepContext()
0x62923  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.CrmItemFinder Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext::get_CrmFinder()
0x62928  ldloc.0
0x62929  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x6292e  call     valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::GetExchangeItemType(string entityName)
0x62933  ldloc.2
0x62934  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::RecordCausedItemChange(valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType itemType, string itemId)
0x62939  leave.s  loc_629A6
0x6293b  stloc.3
0x6293c  ldarg.0
0x6293d  ldc.i4.2
0x6293e  ldstr    aFailedToUpdate_0// "Failed to update the crm {0} item {1} o"...
0x62943  ldc.i4.4
0x62944  newarr   [mscorlib]System.Object
0x62949  dup
0x6294a  ldc.i4.0
0x6294b  ldarg.1
0x6294c  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_ItemObjectType()
0x62951  box      [Microsoft.Crm]Microsoft.Crm.ItemObjectType
0x62956  stelem.ref
0x62957  dup
0x62958  ldc.i4.1
0x62959  ldarg.1
0x6295a  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_ToCrmId()
0x6295f  stelem.ref
0x62960  dup
0x62961  ldc.i4.2
0x62962  ldarg.0
0x62963  call     instance string Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::get_MailboxId()
0x62968  stelem.ref
0x62969  dup
0x6296a  ldc.i4.3
0x6296b  ldloc.3
0x6296c  ldarg.0
0x6296d  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::_context
0x62972  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x62977  call     string Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorExceptionToString(class [mscorlib]System.Exception e, valuetype [mscorlib]System.Guid orgId)
0x6297c  stelem.ref
0x6297d  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x62982  rethrow
0x62984  ldc.i4.1
0x62985  ldarg.0
0x62986  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::_context
0x6298b  ldstr    aUpdaterequest// "UpdateRequest"
0x62990  ldloc.0
0x62991  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x62996  ldstr    aUpdateitem// "UpdateItem"
0x6299b  ldstr    asc_8A7C2// ""
0x629a0  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteCrmServiceExecuteEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string requestName, string entityType, string functionName, [opt] string functionParam)
0x629a5  endfinally
0x629a6  ret
```
