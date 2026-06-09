# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeContactsImportStep::Initialize

- ea: `0x7c190`
- end: `0x7c310`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeContactsImportStep::Initialize`
- size: `384`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x4da80`
- `0x52650`
- `0x59a50`
- `0x5a930`
- `0x71ea0`
- `0x7c190`
- `0x7c680`
- `0x829c0`

## string_xrefs

- `0x7c1f2`: `isexchangecontactsimportscheduled`
- `0x7c204`: `isexchangecontactsimportscheduled`
- `0x7c2f8`: `exchangecontactsimportcompletedon`

## pseudocode

```c

```

## disassembly

```asm
0x7c190  ldc.i4.0
0x7c191  stloc.0
0x7c192  ldnull
0x7c193  stloc.1
0x7c194  ldarg.0
0x7c195  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponseCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.UpdateItemResponse>>::get_StepContext()
0x7c19a  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorker Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext::get_Worker()
0x7c19f  callvirt instance class ACTState Microsoft.Crm.Asynchronous.EmailConnector.ACTProviderBase::get_Mailbox()
0x7c1a4  brfalse.s loc_7C1D8
0x7c1a6  ldarg.0
0x7c1a7  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponseCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.UpdateItemResponse>>::get_StepContext()
0x7c1ac  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorker Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext::get_Worker()
0x7c1b1  callvirt instance class ACTState Microsoft.Crm.Asynchronous.EmailConnector.ACTProviderBase::get_Mailbox()
0x7c1b6  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox ACTState::get_InternalMailbox()
0x7c1bb  brfalse.s loc_7C1D8
0x7c1bd  ldarg.0
0x7c1be  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponseCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.UpdateItemResponse>>::get_StepContext()
0x7c1c3  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorker Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext::get_Worker()
0x7c1c8  callvirt instance class ACTState Microsoft.Crm.Asynchronous.EmailConnector.ACTProviderBase::get_Mailbox()
0x7c1cd  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox ACTState::get_InternalMailbox()
0x7c1d2  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_InternalEntity()
0x7c1d7  stloc.1
0x7c1d8  ldarg.0
0x7c1d9  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponseCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.UpdateItemResponse>>::get_StepContext()
0x7c1de  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorker Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext::get_Worker()
0x7c1e3  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorker::get_MailboxId()
0x7c1e8  stloc.2
0x7c1e9  ldloc.1
0x7c1ea  brfalse.s loc_7C214
0x7c1ec  ldloc.1
0x7c1ed  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x7c1f2  ldstr    aIsexchangecont// "isexchangecontactsimportscheduled"
0x7c1f7  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x7c1fc  brfalse.s loc_7C214
0x7c1fe  ldloc.1
0x7c1ff  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x7c204  ldstr    aIsexchangecont// "isexchangecontactsimportscheduled"
0x7c209  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x7c20e  unbox.any [mscorlib]System.Boolean
0x7c213  stloc.0
0x7c214  ldloc.0
0x7c215  brtrue.s loc_7C21C
0x7c217  leave    loc_7C30F
0x7c21c  ldarg.0
0x7c21d  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item>::.ctor()
0x7c222  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeContactsImportStep::contactsToUpdateInExchange
0x7c227  ldarg.0
0x7c228  ldc.i4.3
0x7c229  ldstr    aImportingConta// "Importing contacts from Exchange for th"...
0x7c22e  ldc.i4.1
0x7c22f  newarr   [mscorlib]System.Object
0x7c234  dup
0x7c235  ldc.i4.0
0x7c236  ldloc.2
0x7c237  stelem.ref
0x7c238  call     instance void class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponseCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.UpdateItemResponse>>::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x7c23d  ldarg.0
0x7c23e  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x7c243  stloc.3
0x7c244  ldloca.s 3
0x7c246  call     instance string [mscorlib]System.DateTime::ToString()
0x7c24b  stfld    string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeContactsImportStep::exchangeContactsImportStartedOn
0x7c250  ldarg.0
0x7c251  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeContactsImportStep::ProvisionalFetchChangesForImportingAllExchangeContacts()
0x7c256  ldarg.0
0x7c257  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeContactsImportStep::contactsToUpdateInExchange
0x7c25c  brfalse.s loc_7C297
0x7c25e  ldarg.0
0x7c25f  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeContactsImportStep::contactsToUpdateInExchange
0x7c264  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item>::get_Count()
0x7c269  ldc.i4.0
0x7c26a  ble.s    loc_7C297
0x7c26c  ldarg.0
0x7c26d  ldc.i4.3
0x7c26e  ldstr    aFound0Contacts// "Found {0} contacts to import from Excha"...
0x7c273  ldc.i4.2
0x7c274  newarr   [mscorlib]System.Object
0x7c279  dup
0x7c27a  ldc.i4.0
0x7c27b  ldarg.0
0x7c27c  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeContactsImportStep::contactsToUpdateInExchange
0x7c281  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item>::get_Count()
0x7c286  box      [mscorlib]System.Int32
0x7c28b  stelem.ref
0x7c28c  dup
0x7c28d  ldc.i4.1
0x7c28e  ldloc.2
0x7c28f  stelem.ref
0x7c290  call     instance void class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponseCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.UpdateItemResponse>>::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x7c295  br.s     loc_7C2AD
0x7c297  ldarg.0
0x7c298  ldc.i4.3
0x7c299  ldstr    aNoContactsFoun// "No contacts found in Exchange to import"...
0x7c29e  ldc.i4.1
0x7c29f  newarr   [mscorlib]System.Object
0x7c2a4  dup
0x7c2a5  ldc.i4.0
0x7c2a6  ldloc.2
0x7c2a7  stelem.ref
0x7c2a8  call     instance void class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponseCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.UpdateItemResponse>>::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x7c2ad  leave.s  loc_7C30E
0x7c2af  stloc.s  4
0x7c2b1  ldarg.0
0x7c2b2  ldc.i4.1
0x7c2b3  ldstr    aErrorOccurredW_0// "Error occurred when fetching contacts t"...
0x7c2b8  ldc.i4.2
0x7c2b9  newarr   [mscorlib]System.Object
0x7c2be  dup
0x7c2bf  ldc.i4.0
0x7c2c0  ldloc.2
0x7c2c1  stelem.ref
0x7c2c2  dup
0x7c2c3  ldc.i4.1
0x7c2c4  ldloc.s  4
0x7c2c6  ldarg.0
0x7c2c7  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponseCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.UpdateItemResponse>>::get_ACTContext()
0x7c2cc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x7c2d1  call     string Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorExceptionToString(class [mscorlib]System.Exception e, valuetype [mscorlib]System.Guid orgId)
0x7c2d6  stelem.ref
0x7c2d7  call     instance void class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponseCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.UpdateItemResponse>>::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x7c2dc  ldloc.1
0x7c2dd  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x7c2e2  ldstr    aExchangecontac_9// "exchangecontactsimportstatus"
0x7c2e7  ldc.i4.2
0x7c2e8  box      [mscorlib]System.Int32
0x7c2ed  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Add(var<u1>, !!T0)
0x7c2f2  ldloc.1
0x7c2f3  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x7c2f8  ldstr    aExchangecontac_11// "exchangecontactsimportcompletedon"
0x7c2fd  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x7c302  box      [mscorlib]System.DateTime
0x7c307  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Add(var<u1>, !!T0)
0x7c30c  leave.s  loc_7C30E
0x7c30e  ret
0x7c30f  ret
```
