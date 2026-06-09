# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemFinder::GetChangeTypeFromExchange

- ea: `0x5e050`
- end: `0x5e14c`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemFinder::GetChangeTypeFromExchange`
- size: `252`
- prototype: ``
- caller_count: `3`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x5ce00`
- `0x5ced0`
- `0x7dd60`

## callees

- `0xabc0`
- `0xac40`
- `0xb8e0`
- `0x422e0`
- `0x422f0`
- `0x4afb0`
- `0x4afc0`
- `0x4b060`
- `0x5de90`
- `0x5e050`
- `0x5e150`
- `0x5e1e0`
- `0x5e240`
- `0x5e4b0`
- `0x6abc0`
- `0x712a0`

## string_xrefs

- `0x5e09a`: `crmLinkState`
- `0x5e0a7`: `crmLinkState`

## pseudocode

```c

```

## disassembly

```asm
0x5e050  ldarg.2
0x5e051  brfalse.s loc_5E05A
0x5e053  ldarg.2
0x5e054  ldc.i4.1
0x5e055  bne.un   loc_5E144
0x5e05a  ldarg.1
0x5e05b  call     valuetype Microsoft.Crm.Asynchronous.EmailConnector.LinkState Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemFinder::GetLinkState(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item item)
0x5e060  stloc.0
0x5e061  ldarg.1
0x5e062  call     string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemFinder::GetCrmId(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item item)
0x5e067  stloc.1
0x5e068  ldarg.1
0x5e069  call     valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::GetObjectTypeFromExchange(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item item)
0x5e06e  stloc.2
0x5e06f  ldarg.3
0x5e070  call     bool Microsoft.Crm.Asynchronous.EmailConnector.CrmHelper::IsSSSCustomPropertyFCBEnabled(valuetype [mscorlib]System.Guid organizationId)
0x5e075  brfalse.s loc_5E0BE
0x5e077  ldloc.2
0x5e078  ldc.i4   0x1069
0x5e07d  beq.s    loc_5E08F
0x5e07f  ldloc.2
0x5e080  ldc.i4   0x109B
0x5e085  beq.s    loc_5E08F
0x5e087  ldloc.2
0x5e088  ldc.i4   0x1F40
0x5e08d  bne.un.s loc_5E0BE
0x5e08f  ldarg.1
0x5e090  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeHelper::ExtractExtendedPropertiesFromCustomPropertyAppointment(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item item)
0x5e095  stloc.3
0x5e096  ldloc.3
0x5e097  brfalse.s loc_5E0BE
0x5e099  ldloc.3
0x5e09a  ldstr    aCrmlinkstate// "crmLinkState"
0x5e09f  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x5e0a4  brfalse.s loc_5E0B7
0x5e0a6  ldloc.3
0x5e0a7  ldstr    aCrmlinkstate// "crmLinkState"
0x5e0ac  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x5e0b1  call     int32 [mscorlib]System.Convert::ToInt32(string)
0x5e0b6  stloc.0
0x5e0b7  ldarg.1
0x5e0b8  ldloc.3
0x5e0b9  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemFinder::ProcessCustomProperties(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item item, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> customProperties)
0x5e0be  ldarg.0
0x5e0bf  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_Context()
0x5e0c4  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ICategorizedItemManager Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext::get_CategorizedItemManager()
0x5e0c9  brfalse.s loc_5E117
0x5e0cb  ldarg.0
0x5e0cc  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_Context()
0x5e0d1  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext::get_IsCategorizedTrackingEnabled()
0x5e0d6  brfalse.s loc_5E117
0x5e0d8  ldarg.0
0x5e0d9  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeCategoryItemMapper Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemFinder::exchangeCategoryItemMapper
0x5e0de  ldarg.1
0x5e0df  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategoryItem Microsoft.Crm.Asynchronous.EmailConnector.IExchangeCategoryItemMapper::MapExchangeItemToExchangeCategoryItem(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item exchangeItem)
0x5e0e4  stloc.s  4
0x5e0e6  ldarg.0
0x5e0e7  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.ILinkStateEvaluator Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemFinder::linkStateEvaluator
0x5e0ec  ldloc.0
0x5e0ed  ldarg.0
0x5e0ee  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_Context()
0x5e0f3  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ICategorizedItemManager Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext::get_CategorizedItemManager()
0x5e0f8  ldloc.s  4
0x5e0fa  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.ICategorizedItemManager::IsTrackedUsingCategories(class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategoryItem exchangeCategoryItem)
0x5e0ff  ldarg.0
0x5e100  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_Context()
0x5e105  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ICategorizedItemManager Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext::get_CategorizedItemManager()
0x5e10a  ldloc.s  4
0x5e10c  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.ICategorizedItemManager::IsUnTrackedUsingCategories(class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategoryItem exchangeCategoryItem)
0x5e111  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.LinkState Microsoft.Crm.Asynchronous.EmailConnector.ILinkStateEvaluator::GetLinkStateWhenCategoryTrackingIsEnabled(valuetype Microsoft.Crm.Asynchronous.EmailConnector.LinkState exchangeLinkState, bool isTrackedUsingCategories, bool isUnTrackedUsingCategories)
0x5e116  stloc.0
0x5e117  ldloc.0
0x5e118  ldc.i4.1
0x5e119  bne.un.s loc_5E128
0x5e11b  ldarg.1
0x5e11c  call     valuetype Microsoft.Crm.Asynchronous.EmailConnector.SssPromoteTracker Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemFinder::GetSssPromoteTracker(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item item)
0x5e121  ldc.i4.1
0x5e122  bne.un.s loc_5E126
0x5e124  ldc.i4.0
0x5e125  ret
0x5e126  ldc.i4.1
0x5e127  ret
0x5e128  ldloc.0
0x5e129  ldc.i4.3
0x5e12a  bne.un.s loc_5E12E
0x5e12c  ldc.i4.4
0x5e12d  ret
0x5e12e  ldloc.0
0x5e12f  ldc.i4.4
0x5e130  bne.un.s loc_5E134
0x5e132  ldc.i4.5
0x5e133  ret
0x5e134  ldloc.0
0x5e135  ldc.i4.2
0x5e136  bne.un.s loc_5E14A
0x5e138  ldloc.1
0x5e139  call     bool Microsoft.Crm.Asynchronous.EmailConnector.CrmHelper::IsValidCrmId(string crmIdString)
0x5e13e  brfalse.s loc_5E142
0x5e140  ldc.i4.3
0x5e141  ret
0x5e142  ldc.i4.0
0x5e143  ret
0x5e144  ldarg.2
0x5e145  ldc.i4.2
0x5e146  bne.un.s loc_5E14A
0x5e148  ldc.i4.2
0x5e149  ret
0x5e14a  ldc.i4.0
0x5e14b  ret
```
