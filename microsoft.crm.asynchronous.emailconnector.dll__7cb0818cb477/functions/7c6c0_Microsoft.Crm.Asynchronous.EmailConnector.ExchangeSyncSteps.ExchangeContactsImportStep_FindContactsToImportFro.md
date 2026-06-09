# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeContactsImportStep::FindContactsToImportFromExchangeByFolder

- ea: `0x7c6c0`
- end: `0x7c8a8`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeContactsImportStep::FindContactsToImportFromExchangeByFolder`
- size: `488`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x7c680`
- `0x7c8b0`

## callees

- `0x57440`
- `0x57aa0`
- `0x5a980`
- `0x5e150`
- `0x684f0`
- `0x6dc80`
- `0x7c6c0`

## string_xrefs

- `0x7c763`: `CrmLinkState`
- `0x7c7cb`: `CrmLinkState`
- `0x7c858`: `{0} contacts fetched from folder {1} for mailbox {2}. {3} would be updated in Exchange.`

## pseudocode

```c

```

## disassembly

```asm
0x7c6c0  ldarg.0
0x7c6c1  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponseCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.UpdateItemResponse>>::get_StepContext()
0x7c6c6  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext::get_SyncStateService()
0x7c6cb  brfalse.s loc_7C6FB
0x7c6cd  ldarg.0
0x7c6ce  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponseCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.UpdateItemResponse>>::get_StepContext()
0x7c6d3  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext::get_SyncStateService()
0x7c6d8  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncState Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService::get_SyncState()
0x7c6dd  brfalse.s loc_7C6FB
0x7c6df  ldarg.0
0x7c6e0  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponseCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.UpdateItemResponse>>::get_StepContext()
0x7c6e5  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext::get_SyncStateService()
0x7c6ea  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncState Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService::get_SyncState()
0x7c6ef  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncState::get_LastExchangeContactsImportTime()
0x7c6f4  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x7c6f9  brfalse.s loc_7C702
0x7c6fb  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x7c700  br.s     loc_7C71C
0x7c702  ldarg.0
0x7c703  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponseCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.UpdateItemResponse>>::get_StepContext()
0x7c708  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext::get_SyncStateService()
0x7c70d  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncState Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService::get_SyncState()
0x7c712  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncState::get_LastExchangeContactsImportTime()
0x7c717  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::Parse(string)
0x7c71c  stloc.0
0x7c71d  ldc.i4.0
0x7c71e  stloc.1
0x7c71f  ldc.i4.0
0x7c720  stloc.2
0x7c721  br       loc_7C89C
0x7c726  ldc.i4   0x7D0
0x7c72b  ldloc.2
0x7c72c  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ItemView::.ctor(int32, int32)
0x7c731  stloc.3
0x7c732  ldloc.3
0x7c733  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.OrderByCollection [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ItemView::get_OrderBy()
0x7c738  ldsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.PropertyDefinition [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ItemSchema::LastModifiedTime
0x7c73d  ldc.i4.1
0x7c73e  callvirt instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.OrderByCollection::Add(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.PropertyDefinitionBase, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.SortDirection)
0x7c743  ldloc.3
0x7c744  ldc.i4.4
0x7c745  newarr   [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.PropertyDefinitionBase
0x7c74a  dup
0x7c74b  ldc.i4.0
0x7c74c  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::get_ExchangePropertiesCollection()
0x7c751  ldstr    aCrmid_2// "CrmId"
0x7c756  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition>::get_Item(void)
0x7c75b  stelem.ref
0x7c75c  dup
0x7c75d  ldc.i4.1
0x7c75e  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::get_ExchangePropertiesCollection()
0x7c763  ldstr    aCrmlinkstate_0// "CrmLinkState"
0x7c768  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition>::get_Item(void)
0x7c76d  stelem.ref
0x7c76e  dup
0x7c76f  ldc.i4.2
0x7c770  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::get_ExchangePropertiesCollection()
0x7c775  ldstr    aCrmobjecttypec_1// "CrmObjectTypeCode"
0x7c77a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition>::get_Item(void)
0x7c77f  stelem.ref
0x7c780  dup
0x7c781  ldc.i4.3
0x7c782  ldsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.PropertyDefinition [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ItemSchema::LastModifiedTime
0x7c787  stelem.ref
0x7c788  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.PropertySet::.ctor(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.PropertyDefinitionBase[])
0x7c78d  callvirt instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ViewBase::set_PropertySet(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.PropertySet)
0x7c792  ldarg.0
0x7c793  ldc.i4.3
0x7c794  ldstr    aInvokingFindit// "Invoking FindItems for mailbox {0} to f"...
0x7c799  ldc.i4.2
0x7c79a  newarr   [mscorlib]System.Object
0x7c79f  dup
0x7c7a0  ldc.i4.0
0x7c7a1  ldarg.0
0x7c7a2  call     instance string class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncAsyncRemoteStep`2<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponseCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.UpdateItemResponse>, class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeFolderSyncState>::get_MailboxId()
0x7c7a7  stelem.ref
0x7c7a8  dup
0x7c7a9  ldc.i4.1
0x7c7aa  ldarg.1
0x7c7ab  callvirt instance string [mscorlib]System.Object::ToString()
0x7c7b0  stelem.ref
0x7c7b1  call     instance void class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponseCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.UpdateItemResponse>>::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x7c7b6  ldarg.0
0x7c7b7  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncAsyncRemoteStep`2<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponseCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.UpdateItemResponse>, class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeFolderSyncState>::get_Service()
0x7c7bc  ldarg.1
0x7c7bd  ldloc.3
0x7c7be  ldarg.3
0x7c7bf  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FindItemsResults`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item> Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::FindItems(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FolderId parentFolderId, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ViewBase view, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType exchangeItemType)
0x7c7c4  stloc.s  4
0x7c7c6  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::get_ExchangePropertiesCollection()
0x7c7cb  ldstr    aCrmlinkstate_0// "CrmLinkState"
0x7c7d0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition>::get_Item(void)
0x7c7d5  stloc.s  5
0x7c7d7  ldc.i4.0
0x7c7d8  stloc.s  6
0x7c7da  ldloc.s  4
0x7c7dc  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FindItemsResults`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item>::GetEnumerator()
0x7c7e1  stloc.s  7
0x7c7e3  br.s     loc_7C835
0x7c7e5  ldloc.s  7
0x7c7e7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item>::get_Current()
0x7c7ec  stloc.s  8
0x7c7ee  ldloc.s  8
0x7c7f0  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::get_LastModifiedTime()
0x7c7f5  ldloc.0
0x7c7f6  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x7c7fb  brfalse.s loc_7C801
0x7c7fd  ldc.i4.1
0x7c7fe  stloc.1
0x7c7ff  br.s     loc_7C83E
0x7c801  ldloc.s  8
0x7c803  call     valuetype Microsoft.Crm.Asynchronous.EmailConnector.LinkState Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemFinder::GetLinkState(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item item)
0x7c808  ldc.i4.2
0x7c809  beq.s    loc_7C835
0x7c80b  ldloc.s  8
0x7c80d  ldloc.s  5
0x7c80f  ldc.r8   1.0
0x7c818  box      [mscorlib]System.Double
0x7c81d  callvirt instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::SetExtendedProperty(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition, object)
0x7c822  ldarg.0
0x7c823  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeContactsImportStep::contactsToUpdateInExchange
0x7c828  ldloc.s  8
0x7c82a  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item>::Add(var<u1>)
0x7c82f  ldloc.s  6
0x7c831  ldc.i4.1
0x7c832  add
0x7c833  stloc.s  6
0x7c835  ldloc.s  7
0x7c837  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x7c83c  brtrue.s loc_7C7E5
0x7c83e  leave.s  loc_7C84C
0x7c840  ldloc.s  7
0x7c842  brfalse.s loc_7C84B
0x7c844  ldloc.s  7
0x7c846  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7c84b  endfinally
0x7c84c  ldloc.2
0x7c84d  ldloc.s  4
0x7c84f  call     T0x2B0000AD
0x7c854  add
0x7c855  stloc.2
0x7c856  ldarg.0
0x7c857  ldc.i4.3
0x7c858  ldstr    a0ContactsFetch// "{0} contacts fetched from folder {1} fo"...
0x7c85d  ldc.i4.4
0x7c85e  newarr   [mscorlib]System.Object
0x7c863  dup
0x7c864  ldc.i4.0
0x7c865  ldloca.s 2
0x7c867  call     instance string [mscorlib]System.Int32::ToString()
0x7c86c  stelem.ref
0x7c86d  dup
0x7c86e  ldc.i4.1
0x7c86f  ldarg.1
0x7c870  callvirt instance string [mscorlib]System.Object::ToString()
0x7c875  stelem.ref
0x7c876  dup
0x7c877  ldc.i4.2
0x7c878  ldarg.0
0x7c879  call     instance string class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncAsyncRemoteStep`2<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponseCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.UpdateItemResponse>, class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeFolderSyncState>::get_MailboxId()
0x7c87e  stelem.ref
0x7c87f  dup
0x7c880  ldc.i4.3
0x7c881  ldloca.s 6
0x7c883  call     instance string [mscorlib]System.Int32::ToString()
0x7c888  stelem.ref
0x7c889  call     instance void class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponseCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.UpdateItemResponse>>::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x7c88e  ldloc.1
0x7c88f  brtrue.s loc_7C89C
0x7c891  ldloc.s  4
0x7c893  callvirt instance bool class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FindItemsResults`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item>::get_MoreAvailable()
0x7c898  ldc.i4.0
0x7c899  ceq
0x7c89b  stloc.1
0x7c89c  ldloc.1
0x7c89d  brfalse  loc_7C726
0x7c8a2  leave.s  loc_7C8A7
0x7c8a4  pop
0x7c8a5  rethrow
0x7c8a7  ret
```
