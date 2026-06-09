# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::BreakLinkToCrm

- ea: `0x6a840`
- end: `0x6aa88`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::BreakLinkToCrm`
- size: `584`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x681b0`

## callees

- `0x684f0`
- `0x69840`
- `0x69950`
- `0x6a4d0`
- `0x6a530`
- `0x6a670`
- `0x6a830`
- `0x6a840`
- `0x700e0`
- `0x702d0`

## string_xrefs

- `0x6a851`: `CrmLinkState`
- `0x6a995`: `CrmServiceId`
- `0x6a887`: `CrmXml`
- `0x6aa25`: `CrmXml`
- `0x6a9e6`: `CrmSecondLinkState`
- `0x6aa65`: `Broke the to crm link for the item {0} on the exchange server for the mailbox : {1}.`

## pseudocode

```c

```

## disassembly

```asm
0x6a840  ldarg.1
0x6a841  brfalse  loc_6AA13
0x6a846  ldarg.0
0x6a847  call     instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::get_Item()
0x6a84c  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::get_ExchangePropertiesCollection()
0x6a851  ldstr    aCrmlinkstate_0// "CrmLinkState"
0x6a856  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition>::get_Item(void)
0x6a85b  callvirt instance bool [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::RemoveExtendedProperty(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition)
0x6a860  pop
0x6a861  ldarg.0
0x6a862  call     instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::get_Item()
0x6a867  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::get_ExchangePropertiesCollection()
0x6a86c  ldstr    aCrmid_2// "CrmId"
0x6a871  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition>::get_Item(void)
0x6a876  callvirt instance bool [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::RemoveExtendedProperty(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition)
0x6a87b  pop
0x6a87c  ldarg.0
0x6a87d  call     instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::get_Item()
0x6a882  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::get_ExchangePropertiesCollection()
0x6a887  ldstr    aCrmxml_0// "CrmXml"
0x6a88c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition>::get_Item(void)
0x6a891  callvirt instance bool [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::RemoveExtendedProperty(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition)
0x6a896  pop
0x6a897  ldarg.0
0x6a898  call     instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::get_Item()
0x6a89d  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::get_ExchangePropertiesCollection()
0x6a8a2  ldstr    aCrmorgid// "CrmOrgId"
0x6a8a7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition>::get_Item(void)
0x6a8ac  callvirt instance bool [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::RemoveExtendedProperty(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition)
0x6a8b1  pop
0x6a8b2  ldarg.0
0x6a8b3  call     instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::get_Item()
0x6a8b8  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::get_ExchangePropertiesCollection()
0x6a8bd  ldstr    aCrmpartyinfo_0// "CrmPartyInfo"
0x6a8c2  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition>::get_Item(void)
0x6a8c7  callvirt instance bool [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::RemoveExtendedProperty(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition)
0x6a8cc  pop
0x6a8cd  ldarg.0
0x6a8ce  call     instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::get_Item()
0x6a8d3  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::get_ExchangePropertiesCollection()
0x6a8d8  ldstr    aCrmregardingid_1// "CrmRegardingId"
0x6a8dd  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition>::get_Item(void)
0x6a8e2  callvirt instance bool [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::RemoveExtendedProperty(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition)
0x6a8e7  pop
0x6a8e8  ldarg.0
0x6a8e9  call     instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::get_Item()
0x6a8ee  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::get_ExchangePropertiesCollection()
0x6a8f3  ldstr    aCrmregardingob_1// "CrmRegardingObjectType"
0x6a8f8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition>::get_Item(void)
0x6a8fd  callvirt instance bool [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::RemoveExtendedProperty(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition)
0x6a902  pop
0x6a903  ldarg.0
0x6a904  call     instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::get_Item()
0x6a909  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::get_ExchangePropertiesCollection()
0x6a90e  ldstr    aCrmregardingna_0// "CrmRegardingName"
0x6a913  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition>::get_Item(void)
0x6a918  callvirt instance bool [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::RemoveExtendedProperty(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition)
0x6a91d  pop
0x6a91e  ldarg.0
0x6a91f  call     instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::get_Item()
0x6a924  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::get_ExchangePropertiesCollection()
0x6a929  ldstr    aCrmparentaccou_2// "CrmParentAccountId"
0x6a92e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition>::get_Item(void)
0x6a933  callvirt instance bool [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::RemoveExtendedProperty(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition)
0x6a938  pop
0x6a939  ldarg.0
0x6a93a  call     instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::get_Item()
0x6a93f  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::get_ExchangePropertiesCollection()
0x6a944  ldstr    aCrmparentobjec_1// "CrmParentObjectType"
0x6a949  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition>::get_Item(void)
0x6a94e  callvirt instance bool [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::RemoveExtendedProperty(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition)
0x6a953  pop
0x6a954  ldarg.0
0x6a955  call     instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::get_Item()
0x6a95a  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::get_ExchangePropertiesCollection()
0x6a95f  ldstr    aCrmparentaccou_3// "CrmParentAccountName"
0x6a964  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition>::get_Item(void)
0x6a969  callvirt instance bool [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::RemoveExtendedProperty(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition)
0x6a96e  pop
0x6a96f  ldarg.0
0x6a970  call     instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::get_Item()
0x6a975  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::get_ExchangePropertiesCollection()
0x6a97a  ldstr    aCrmownerid_1// "CrmOwnerId"
0x6a97f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition>::get_Item(void)
0x6a984  callvirt instance bool [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::RemoveExtendedProperty(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition)
0x6a989  pop
0x6a98a  ldarg.0
0x6a98b  call     instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::get_Item()
0x6a990  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::get_ExchangePropertiesCollection()
0x6a995  ldstr    aCrmserviceid_1// "CrmServiceId"
0x6a99a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition>::get_Item(void)
0x6a99f  callvirt instance bool [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::RemoveExtendedProperty(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition)
0x6a9a4  pop
0x6a9a5  ldarg.0
0x6a9a6  call     instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::get_Item()
0x6a9ab  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::get_ExchangePropertiesCollection()
0x6a9b0  ldstr    aCrmobjecttypec_1// "CrmObjectTypeCode"
0x6a9b5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition>::get_Item(void)
0x6a9ba  callvirt instance bool [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::RemoveExtendedProperty(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition)
0x6a9bf  pop
0x6a9c0  ldarg.0
0x6a9c1  call     instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::get_Item()
0x6a9c6  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::get_ExchangePropertiesCollection()
0x6a9cb  ldstr    aCrmsecondpaged// "CrmSecondPageData"
0x6a9d0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition>::get_Item(void)
0x6a9d5  callvirt instance bool [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::RemoveExtendedProperty(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition)
0x6a9da  pop
0x6a9db  ldarg.0
0x6a9dc  call     instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::get_Item()
0x6a9e1  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::get_ExchangePropertiesCollection()
0x6a9e6  ldstr    aCrmsecondlinks_0// "CrmSecondLinkState"
0x6a9eb  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition>::get_Item(void)
0x6a9f0  callvirt instance bool [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::RemoveExtendedProperty(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition)
0x6a9f5  pop
0x6a9f6  ldarg.0
0x6a9f7  call     instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::get_Item()
0x6a9fc  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::get_ExchangePropertiesCollection()
0x6aa01  ldstr    aCrmentryid_0// "CrmEntryId"
0x6aa06  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition>::get_Item(void)
0x6aa0b  callvirt instance bool [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::RemoveExtendedProperty(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition)
0x6aa10  pop
0x6aa11  br.s     loc_6AA50
0x6aa13  ldarg.0
0x6aa14  ldc.i4.0
0x6aa15  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::SetCrmLinkState(valuetype Microsoft.Crm.Asynchronous.EmailConnector.LinkState linkState)
0x6aa1a  ldarg.0
0x6aa1b  call     instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::get_Item()
0x6aa20  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::get_ExchangePropertiesCollection()
0x6aa25  ldstr    aCrmxml_0// "CrmXml"
0x6aa2a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition>::get_Item(void)
0x6aa2f  callvirt instance bool [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::RemoveExtendedProperty(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition)
0x6aa34  pop
0x6aa35  ldarg.0
0x6aa36  call     instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::get_Item()
0x6aa3b  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::get_ExchangePropertiesCollection()
0x6aa40  ldstr    aCrmpartyinfo// "crmpartyinfo"
0x6aa45  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition>::get_Item(void)
0x6aa4a  callvirt instance bool [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::RemoveExtendedProperty(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition)
0x6aa4f  pop
0x6aa50  ldarg.0
0x6aa51  ldc.i4.0
0x6aa52  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::SetCrmCategoriesAndCategortyTracker(valuetype Microsoft.Crm.Asynchronous.EmailConnector.LinkState linkState)
0x6aa57  ldarg.0
0x6aa58  ldarg.0
0x6aa59  callvirt instance int32 Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::get_OutlookIcon()
0x6aa5e  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::SetIconIndex(int32 iconIndex)
0x6aa63  ldarg.0
0x6aa64  ldc.i4.4
0x6aa65  ldstr    aBrokeTheToCrmL// "Broke the to crm link for the item {0} "...
0x6aa6a  ldc.i4.2
0x6aa6b  newarr   [mscorlib]System.Object
0x6aa70  dup
0x6aa71  ldc.i4.0
0x6aa72  ldarg.0
0x6aa73  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_ToCrmId()
0x6aa78  stelem.ref
0x6aa79  dup
0x6aa7a  ldc.i4.1
0x6aa7b  ldarg.0
0x6aa7c  call     instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_MailboxId()
0x6aa81  stelem.ref
0x6aa82  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x6aa87  ret
```
