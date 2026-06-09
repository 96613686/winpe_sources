# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.UploadAttachmentsInExchangeStep::UpdateExchangeItemAttachments

- ea: `0x80150`
- end: `0x801f1`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.UploadAttachmentsInExchangeStep::UpdateExchangeItemAttachments`
- size: `161`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x80000`

## callees

- `0x58bb0`
- `0x5a910`
- `0x69840`
- `0x70300`
- `0x7fef0`
- `0x80150`
- `0x80200`
- `0x802a0`
- `0x80320`

## string_xrefs

- `0x8015c`: `UploadAttachmentsInExchangeStep.UpdateExchangeItemAttachments`
- `0x801cc`: `UploadAttachmentsInExchangeStep.UpdateExchangeItemAttachments`

## pseudocode

```c

```

## disassembly

```asm
0x80150  ldc.i4.0
0x80151  ldarg.0
0x80152  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<bool>::get_StepContext()
0x80157  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext::get_Context()
0x8015c  ldstr    aUploadattachme// "UploadAttachmentsInExchangeStep.UpdateE"...
0x80161  ldarg.1
0x80162  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeData::get_ExchangeItem()
0x80167  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_ItemObjectType()
0x8016c  stloc.0
0x8016d  ldloca.s 0
0x8016f  constrained. [Microsoft.Crm]Microsoft.Crm.ItemObjectType
0x80175  callvirt instance string [mscorlib]System.Object::ToString()
0x8017a  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteExchangeServiceExecuteEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string requestName, string itemType)
0x8017f  ldarg.0
0x80180  ldarg.1
0x80181  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeData::get_ExchangeItem()
0x80186  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.UploadAttachmentsInExchangeStep::HandleUpdate(class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem exchangeItem)
0x8018b  ldarg.1
0x8018c  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeData::get_ExchangeItem()
0x80191  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::get_Item()
0x80196  callvirt instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceObject::Load()
0x8019b  ldarg.0
0x8019c  ldarg.1
0x8019d  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeData::get_ExchangeItem()
0x801a2  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.UploadAttachmentsInExchangeStep::UpdateAttachmentIds(class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem exchangeItem)
0x801a7  ldarg.0
0x801a8  ldarg.1
0x801a9  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeData::get_ExchangeItem()
0x801ae  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.UploadAttachmentsInExchangeStep::HandleUpdate(class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem exchangeItem)
0x801b3  leave.s  loc_801F0
0x801b5  stloc.1
0x801b6  ldarg.0
0x801b7  ldloc.1
0x801b8  ldarg.1
0x801b9  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.UploadAttachmentsInExchangeStep::HandlePerItemException(class [mscorlib]System.Exception ex, class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeData exchangeData)
0x801be  leave.s  loc_801F0
0x801c0  ldc.i4.1
0x801c1  ldarg.0
0x801c2  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<bool>::get_StepContext()
0x801c7  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext::get_Context()
0x801cc  ldstr    aUploadattachme// "UploadAttachmentsInExchangeStep.UpdateE"...
0x801d1  ldarg.1
0x801d2  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeData::get_ExchangeItem()
0x801d7  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_ItemObjectType()
0x801dc  stloc.0
0x801dd  ldloca.s 0
0x801df  constrained. [Microsoft.Crm]Microsoft.Crm.ItemObjectType
0x801e5  callvirt instance string [mscorlib]System.Object::ToString()
0x801ea  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteExchangeServiceExecuteEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string requestName, string itemType)
0x801ef  endfinally
0x801f0  ret
```
