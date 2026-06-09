# Microsoft.Crm.Asynchronous.EmailConnector.UpdateExchangeItemsStep::Initialize

- ea: `0x40970`
- end: `0x40b36`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.UpdateExchangeItemsStep::Initialize`
- size: `454`
- prototype: ``
- caller_count: `0`
- callee_count: `22`
- tags: `installer_update, broker_com_uri`

## callees

- `0xabc0`
- `0x144f0`
- `0x2acf0`
- `0x2ad10`
- `0x2ad30`
- `0x2ad50`
- `0x32840`
- `0x32860`
- `0x32a60`
- `0x3ab40`
- `0x403e0`
- `0x40410`
- `0x40440`
- `0x40660`
- `0x406d0`
- `0x40790`
- `0x40840`
- `0x40940`
- `0x40970`
- `0x417a0`
- `0x41a20`
- `0x42060`

## string_xrefs

- `0x409d4`: `LinkStateTracker: 0 <CRM_LINK_STATE_TRACKER_NOT_TRACKED>.`
- `0x40aa4`: `Properties to be updated in exchange for email with ExchangeId {0} and CrmId {1}: {2}`

## pseudocode

```c

```

## disassembly

```asm
0x40970  ldarg.0
0x40971  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x40976  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x4097b  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.CrmExchangeEmailMessage> Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_EmailMessageUpdates()
0x40980  stloc.0
0x40981  ldarg.0
0x40982  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.UpdateItemType Microsoft.Crm.Asynchronous.EmailConnector.UpdateExchangeItemsStep::request
0x40987  ldc.i4.2
0x40988  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.UpdateItemType::set_ConflictResolution(valuetype Microsoft.Crm.Asynchronous.EmailConnector.ConflictResolutionType value)
0x4098d  ldarg.0
0x4098e  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.UpdateItemType Microsoft.Crm.Asynchronous.EmailConnector.UpdateExchangeItemsStep::request
0x40993  ldc.i4.0
0x40994  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.UpdateItemType::set_MessageDisposition(valuetype Microsoft.Crm.Asynchronous.EmailConnector.MessageDispositionType value)
0x40999  ldarg.0
0x4099a  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.UpdateItemType Microsoft.Crm.Asynchronous.EmailConnector.UpdateExchangeItemsStep::request
0x4099f  ldc.i4.1
0x409a0  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.UpdateItemType::set_MessageDispositionSpecified(bool value)
0x409a5  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ItemChangeType>::.ctor()
0x409aa  stloc.1
0x409ab  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x409b0  stloc.2
0x409b1  ldc.i4.0
0x409b2  stloc.3
0x409b3  br       loc_40B0C
0x409b8  ldloc.0
0x409b9  ldloc.3
0x409ba  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.CrmExchangeEmailMessage>::get_Item(!!T0)
0x409bf  stloc.s  4
0x409c1  ldarg.0
0x409c2  ldloc.s  4
0x409c4  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ItemChangeType Microsoft.Crm.Asynchronous.EmailConnector.UpdateExchangeItemsStep::GetLinkStateTrackerItemChange(class Microsoft.Crm.Asynchronous.EmailConnector.CrmExchangeEmailMessage crmExchangeEmailMessage)
0x409c9  stloc.s  5
0x409cb  ldloc.1
0x409cc  ldloc.s  5
0x409ce  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ItemChangeType>::Add(var<u1>)
0x409d3  ldloc.2
0x409d4  ldstr    aLinkstatetrack// "LinkStateTracker: 0 <CRM_LINK_STATE_TRA"...
0x409d9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x409de  pop
0x409df  ldarg.0
0x409e0  ldloc.s  4
0x409e2  ldloc.2
0x409e3  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ItemChangeType Microsoft.Crm.Asynchronous.EmailConnector.UpdateExchangeItemsStep::GetCrmIdItemChange(class Microsoft.Crm.Asynchronous.EmailConnector.CrmExchangeEmailMessage crmExchangeEmailMessage, class [mscorlib]System.Text.StringBuilder changedItems)
0x409e8  stloc.s  6
0x409ea  ldloc.s  6
0x409ec  brfalse.s loc_409F6
0x409ee  ldloc.1
0x409ef  ldloc.s  6
0x409f1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ItemChangeType>::Add(var<u1>)
0x409f6  ldarg.0
0x409f7  ldloc.s  4
0x409f9  ldloc.2
0x409fa  ldloc.1
0x409fb  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ItemChangeType Microsoft.Crm.Asynchronous.EmailConnector.UpdateExchangeItemsStep::GetLinkStateItemChange(class Microsoft.Crm.Asynchronous.EmailConnector.CrmExchangeEmailMessage crmExchangeEmailMessage, class [mscorlib]System.Text.StringBuilder changedItems, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ItemChangeType> itemChangeList)
0x40a00  stloc.s  7
0x40a02  ldloc.s  7
0x40a04  brfalse.s loc_40A0E
0x40a06  ldloc.1
0x40a07  ldloc.s  7
0x40a09  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ItemChangeType>::Add(var<u1>)
0x40a0e  ldarg.0
0x40a0f  ldloc.s  4
0x40a11  ldloc.2
0x40a12  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ItemChangeType Microsoft.Crm.Asynchronous.EmailConnector.UpdateExchangeItemsStep::GetRegardingObjectIdItemChange(class Microsoft.Crm.Asynchronous.EmailConnector.CrmExchangeEmailMessage crmExchangeEmailMessage, class [mscorlib]System.Text.StringBuilder changedItems)
0x40a17  stloc.s  8
0x40a19  ldloc.s  8
0x40a1b  brfalse.s loc_40A25
0x40a1d  ldloc.1
0x40a1e  ldloc.s  8
0x40a20  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ItemChangeType>::Add(var<u1>)
0x40a25  ldarg.0
0x40a26  ldloc.s  4
0x40a28  ldloc.2
0x40a29  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ItemChangeType Microsoft.Crm.Asynchronous.EmailConnector.UpdateExchangeItemsStep::GetRegardingObjectNameItemChange(class Microsoft.Crm.Asynchronous.EmailConnector.CrmExchangeEmailMessage crmExchangeEmailMessage, class [mscorlib]System.Text.StringBuilder changedItems)
0x40a2e  stloc.s  9
0x40a30  ldloc.s  9
0x40a32  brfalse.s loc_40A3C
0x40a34  ldloc.1
0x40a35  ldloc.s  9
0x40a37  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ItemChangeType>::Add(var<u1>)
0x40a3c  ldarg.0
0x40a3d  ldloc.s  4
0x40a3f  ldloc.2
0x40a40  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ItemChangeType Microsoft.Crm.Asynchronous.EmailConnector.UpdateExchangeItemsStep::GetRegardingObjectTypeCodeItemChange(class Microsoft.Crm.Asynchronous.EmailConnector.CrmExchangeEmailMessage crmExchangeEmailMessage, class [mscorlib]System.Text.StringBuilder changedItems)
0x40a45  stloc.s  0xA
0x40a47  ldloc.s  0xA
0x40a49  brfalse.s loc_40A53
0x40a4b  ldloc.1
0x40a4c  ldloc.s  0xA
0x40a4e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ItemChangeType>::Add(var<u1>)
0x40a53  ldarg.0
0x40a54  ldloc.s  4
0x40a56  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ItemChangeType Microsoft.Crm.Asynchronous.EmailConnector.UpdateExchangeItemsStep::GetCrmIsFollowedItemChange(class Microsoft.Crm.Asynchronous.EmailConnector.CrmExchangeEmailMessage crmExchangeEmailMessage)
0x40a5b  stloc.s  0xB
0x40a5d  ldloc.s  0xB
0x40a5f  brfalse.s loc_40A69
0x40a61  ldloc.1
0x40a62  ldloc.s  0xB
0x40a64  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ItemChangeType>::Add(var<u1>)
0x40a69  ldarg.0
0x40a6a  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Context
0x40a6f  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.IActivityProviderContext::get_AsyncEvent()
0x40a74  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_OrganizationId()
0x40a79  call     bool Microsoft.Crm.Asynchronous.EmailConnector.CrmHelper::IsSSSCustomPropertyFCBEnabled(valuetype [mscorlib]System.Guid organizationId)
0x40a7e  brfalse.s loc_40AA2
0x40a80  ldarg.0
0x40a81  ldloc.s  4
0x40a83  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ItemChangeType Microsoft.Crm.Asynchronous.EmailConnector.UpdateExchangeItemsStep::GetCustomPropertiesItemChange(class Microsoft.Crm.Asynchronous.EmailConnector.CrmExchangeEmailMessage crmExchangeEmailMessage)
0x40a88  stloc.s  0xC
0x40a8a  ldloc.s  0xC
0x40a8c  brfalse.s loc_40AA2
0x40a8e  ldloc.1
0x40a8f  ldloc.s  0xC
0x40a91  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ItemChangeType>::Add(var<u1>)
0x40a96  ldloc.2
0x40a97  ldstr    aCustomProperty// "Custom Property."
0x40a9c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x40aa1  pop
0x40aa2  ldarg.0
0x40aa3  ldc.i4.4
0x40aa4  ldstr    aPropertiesToBe// "Properties to be updated in exchange fo"...
0x40aa9  ldc.i4.3
0x40aaa  newarr   [mscorlib]System.Object
0x40aaf  dup
0x40ab0  ldc.i4.0
0x40ab1  ldloc.s  4
0x40ab3  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage Microsoft.Crm.Asynchronous.EmailConnector.CrmExchangeEmailMessage::get_EmailMessage()
0x40ab8  brfalse.s loc_40AC8
0x40aba  ldloc.s  4
0x40abc  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage Microsoft.Crm.Asynchronous.EmailConnector.CrmExchangeEmailMessage::get_EmailMessage()
0x40ac1  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ItemIdType Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage::get_Id()
0x40ac6  brtrue.s loc_40ACF
0x40ac8  ldsfld   string [mscorlib]System.String::Empty
0x40acd  br.s     loc_40AE0
0x40acf  ldloc.s  4
0x40ad1  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage Microsoft.Crm.Asynchronous.EmailConnector.CrmExchangeEmailMessage::get_EmailMessage()
0x40ad6  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ItemIdType Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage::get_Id()
0x40adb  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.ItemIdType::get_Id()
0x40ae0  stelem.ref
0x40ae1  dup
0x40ae2  ldc.i4.1
0x40ae3  ldloc.s  4
0x40ae5  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.EmailConnector.CrmExchangeEmailMessage::get_CrmId()
0x40aea  box      [mscorlib]System.Guid
0x40aef  stelem.ref
0x40af0  dup
0x40af1  ldc.i4.2
0x40af2  ldloc.2
0x40af3  callvirt instance string [mscorlib]System.Object::ToString()
0x40af8  stelem.ref
0x40af9  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x40afe  ldloc.0
0x40aff  ldloc.3
0x40b00  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.CrmExchangeEmailMessage>::RemoveAt(int32)
0x40b05  ldloc.2
0x40b06  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Clear()
0x40b0b  pop
0x40b0c  ldloc.3
0x40b0d  ldloc.0
0x40b0e  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.CrmExchangeEmailMessage>::get_Count()
0x40b13  blt      loc_409B8
0x40b18  ldarg.0
0x40b19  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.UpdateItemType Microsoft.Crm.Asynchronous.EmailConnector.UpdateExchangeItemsStep::request
0x40b1e  ldloc.1
0x40b1f  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ItemChangeType>::ToArray()
0x40b24  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.UpdateItemType::set_ItemChanges(class Microsoft.Crm.Asynchronous.EmailConnector.ItemChangeType[] value)
0x40b29  ldarg.0
0x40b2a  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.UpdateItemType Microsoft.Crm.Asynchronous.EmailConnector.UpdateExchangeItemsStep::request
0x40b2f  ldc.i4.2
0x40b30  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.UpdateItemType::set_ConflictResolution(valuetype Microsoft.Crm.Asynchronous.EmailConnector.ConflictResolutionType value)
0x40b35  ret
```
