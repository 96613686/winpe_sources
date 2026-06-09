# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeContactsImportStep::ProcessResponse

- ea: `0x7c450`
- end: `0x7c673`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeContactsImportStep::ProcessResponse`
- size: `547`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callees

- `0x4da80`
- `0x52650`
- `0x53440`
- `0x57450`
- `0x57aa0`
- `0x57c00`
- `0x59a50`
- `0x5a930`
- `0x5a980`
- `0x71ea0`
- `0x7c450`
- `0x829c0`

## string_xrefs

- `0x7c5bb`: `exchangecontactsimportcompletedon`
- `0x7c659`: `exchangecontactsimportcompletedon`
- `0x7c57b`: `ExchangeContactsImportStep Statistics: {0} contacts successfully updated, {1} contacts failed to update.`
- `0x7c60f`: `Error occurred when processing update response for contacts to import for mailbox {0}. Exception : {1}.`

## pseudocode

```c

```

## disassembly

```asm
0x7c450  ldarg.0
0x7c451  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponseCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.UpdateItemResponse>>::get_StepContext()
0x7c456  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorker Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext::get_Worker()
0x7c45b  callvirt instance class ACTState Microsoft.Crm.Asynchronous.EmailConnector.ACTProviderBase::get_Mailbox()
0x7c460  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox ACTState::get_InternalMailbox()
0x7c465  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_InternalEntity()
0x7c46a  stloc.0
0x7c46b  ldarg.0
0x7c46c  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeContactsImportStep::contactsToUpdateInExchange
0x7c471  brfalse.s loc_7C481
0x7c473  ldarg.0
0x7c474  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeContactsImportStep::contactsToUpdateInExchange
0x7c479  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item>::get_Count()
0x7c47e  ldc.i4.0
0x7c47f  bgt.s    loc_7C488
0x7c481  ldc.i4.1
0x7c482  stloc.3
0x7c483  leave    loc_7C671
0x7c488  ldc.i4.0
0x7c489  stloc.1
0x7c48a  ldc.i4.0
0x7c48b  stloc.2
0x7c48c  ldc.i4.0
0x7c48d  stloc.s  4
0x7c48f  br       loc_7C567
0x7c494  ldarg.0
0x7c495  call     instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponseCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.UpdateItemResponse>>::get_Result()
0x7c49a  ldloc.s  4
0x7c49c  callvirt instance var<u1> class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponseCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.UpdateItemResponse>::get_Item(!!T0)
0x7c4a1  callvirt instance valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResult [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponse::get_Result()
0x7c4a6  brtrue.s loc_7C4B1
0x7c4a8  ldloc.2
0x7c4a9  ldc.i4.1
0x7c4aa  add
0x7c4ab  stloc.2
0x7c4ac  br       loc_7C561
0x7c4b1  ldloc.1
0x7c4b2  ldc.i4.1
0x7c4b3  add
0x7c4b4  stloc.1
0x7c4b5  ldarg.0
0x7c4b6  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeContactsImportStep::contactsToUpdateInExchange
0x7c4bb  ldloc.s  4
0x7c4bd  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item>::get_Item(!!T0)
0x7c4c2  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ItemId [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::get_Id()
0x7c4c7  callvirt instance string [mscorlib]System.Object::ToString()
0x7c4cc  stloc.s  5
0x7c4ce  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7c4d3  ldstr    aErrorCode0Mess// "Error code: {0}, Message: {1}"
0x7c4d8  ldc.i4.2
0x7c4d9  newarr   [mscorlib]System.Object
0x7c4de  dup
0x7c4df  ldc.i4.0
0x7c4e0  ldarg.0
0x7c4e1  call     instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponseCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.UpdateItemResponse>>::get_Result()
0x7c4e6  ldloc.s  4
0x7c4e8  callvirt instance var<u1> class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponseCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.UpdateItemResponse>::get_Item(!!T0)
0x7c4ed  callvirt instance valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceError [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponse::get_ErrorCode()
0x7c4f2  box      [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceError
0x7c4f7  stelem.ref
0x7c4f8  dup
0x7c4f9  ldc.i4.1
0x7c4fa  ldarg.0
0x7c4fb  call     instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponseCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.UpdateItemResponse>>::get_Result()
0x7c500  ldloc.s  4
0x7c502  callvirt instance var<u1> class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponseCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.UpdateItemResponse>::get_Item(!!T0)
0x7c507  callvirt instance string [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponse::get_ErrorMessage()
0x7c50c  stelem.ref
0x7c50d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x7c512  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncException::.ctor(string message)
0x7c517  stloc.s  6
0x7c519  ldarg.0
0x7c51a  ldc.i4.2
0x7c51b  ldstr    aFailedToTrackC// "Failed to track contact with id {0} in "...
0x7c520  ldc.i4.4
0x7c521  newarr   [mscorlib]System.Object
0x7c526  dup
0x7c527  ldc.i4.0
0x7c528  ldloc.s  5
0x7c52a  stelem.ref
0x7c52b  dup
0x7c52c  ldc.i4.1
0x7c52d  ldarg.0
0x7c52e  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponseCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.UpdateItemResponse>>::get_StepContext()
0x7c533  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorker Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext::get_Worker()
0x7c538  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorker::get_MailboxId()
0x7c53d  stelem.ref
0x7c53e  dup
0x7c53f  ldc.i4.2
0x7c540  ldloc.s  6
0x7c542  ldarg.0
0x7c543  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponseCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.UpdateItemResponse>>::get_ACTContext()
0x7c548  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x7c54d  call     string Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorExceptionToString(class [mscorlib]System.Exception e, valuetype [mscorlib]System.Guid orgId)
0x7c552  stelem.ref
0x7c553  dup
0x7c554  ldc.i4.3
0x7c555  ldc.i4.1
0x7c556  box      [mscorlib]System.Int32
0x7c55b  stelem.ref
0x7c55c  call     instance void class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponseCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.UpdateItemResponse>>::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x7c561  ldloc.s  4
0x7c563  ldc.i4.1
0x7c564  add
0x7c565  stloc.s  4
0x7c567  ldloc.s  4
0x7c569  ldarg.0
0x7c56a  call     instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponseCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.UpdateItemResponse>>::get_Result()
0x7c56f  callvirt instance int32 class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponseCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.UpdateItemResponse>::get_Count()
0x7c574  blt      loc_7C494
0x7c579  ldarg.0
0x7c57a  ldc.i4.3
0x7c57b  ldstr    aExchangecontac_12// "ExchangeContactsImportStep Statistics: "...
0x7c580  ldc.i4.2
0x7c581  newarr   [mscorlib]System.Object
0x7c586  dup
0x7c587  ldc.i4.0
0x7c588  ldloca.s 2
0x7c58a  call     instance string [mscorlib]System.Int32::ToString()
0x7c58f  stelem.ref
0x7c590  dup
0x7c591  ldc.i4.1
0x7c592  ldloca.s 1
0x7c594  call     instance string [mscorlib]System.Int32::ToString()
0x7c599  stelem.ref
0x7c59a  call     instance void class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponseCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.UpdateItemResponse>>::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x7c59f  ldloc.0
0x7c5a0  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x7c5a5  ldstr    aExchangecontac_9// "exchangecontactsimportstatus"
0x7c5aa  ldc.i4.1
0x7c5ab  box      [mscorlib]System.Int32
0x7c5b0  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Add(var<u1>, !!T0)
0x7c5b5  ldloc.0
0x7c5b6  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x7c5bb  ldstr    aExchangecontac_11// "exchangecontactsimportcompletedon"
0x7c5c0  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x7c5c5  box      [mscorlib]System.DateTime
0x7c5ca  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Add(var<u1>, !!T0)
0x7c5cf  ldarg.0
0x7c5d0  ldfld    string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeContactsImportStep::exchangeContactsImportStartedOn
0x7c5d5  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x7c5da  brtrue.s loc_7C607
0x7c5dc  ldarg.0
0x7c5dd  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponseCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.UpdateItemResponse>>::get_StepContext()
0x7c5e2  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext::get_SyncStateService()
0x7c5e7  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncState Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService::get_SyncState()
0x7c5ec  ldarg.0
0x7c5ed  ldfld    string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeContactsImportStep::exchangeContactsImportStartedOn
0x7c5f2  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncState::set_LastExchangeContactsImportTime(string value)
0x7c5f7  ldarg.0
0x7c5f8  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponseCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.UpdateItemResponse>>::get_StepContext()
0x7c5fd  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext::get_SyncStateService()
0x7c602  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService::CommitSyncState()
0x7c607  ldc.i4.1
0x7c608  stloc.3
0x7c609  leave.s  loc_7C671
0x7c60b  stloc.s  7
0x7c60d  ldarg.0
0x7c60e  ldc.i4.1
0x7c60f  ldstr    aErrorOccurredW_2// "Error occurred when processing update r"...
0x7c614  ldc.i4.2
0x7c615  newarr   [mscorlib]System.Object
0x7c61a  dup
0x7c61b  ldc.i4.0
0x7c61c  ldarg.0
0x7c61d  call     instance string class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncAsyncRemoteStep`2<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponseCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.UpdateItemResponse>, class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeFolderSyncState>::get_MailboxId()
0x7c622  stelem.ref
0x7c623  dup
0x7c624  ldc.i4.1
0x7c625  ldloc.s  7
0x7c627  ldarg.0
0x7c628  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponseCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.UpdateItemResponse>>::get_ACTContext()
0x7c62d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x7c632  call     string Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorExceptionToString(class [mscorlib]System.Exception e, valuetype [mscorlib]System.Guid orgId)
0x7c637  stelem.ref
0x7c638  call     instance void class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponseCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.UpdateItemResponse>>::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x7c63d  ldloc.0
0x7c63e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x7c643  ldstr    aExchangecontac_9// "exchangecontactsimportstatus"
0x7c648  ldc.i4.2
0x7c649  box      [mscorlib]System.Int32
0x7c64e  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Add(var<u1>, !!T0)
0x7c653  ldloc.0
0x7c654  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x7c659  ldstr    aExchangecontac_11// "exchangecontactsimportcompletedon"
0x7c65e  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x7c663  box      [mscorlib]System.DateTime
0x7c668  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Add(var<u1>, !!T0)
0x7c66d  ldc.i4.1
0x7c66e  stloc.3
0x7c66f  leave.s  loc_7C671
0x7c671  ldloc.3
0x7c672  ret
```
