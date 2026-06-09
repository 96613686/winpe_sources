# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemFinder::PagedFindItemMappingIdsByFolder

- ea: `0x5cb00`
- end: `0x5cc85`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemFinder::PagedFindItemMappingIdsByFolder`
- size: `389`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x5cd00`
- `0x7ecb0`

## callees

- `0x58c10`
- `0x5c820`
- `0x5c940`
- `0x5cac0`
- `0x5cb00`
- `0x5cc90`
- `0x5e4b0`
- `0x684f0`
- `0x6dc20`

## string_xrefs

- `0x5cb2d`: `Mapping IDs are defined only for Calendars or Contacts or Tasks`
- `0x5cb49`: `CrmLinkState`
- `0x5cb69`: `CrmLinkState`
- `0x5cbca`: `CrmLinkState`

## pseudocode

```c

```

## disassembly

```asm
0x5cb00  ldc.i4.0
0x5cb01  ldarg.0
0x5cb02  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_Context()
0x5cb07  ldstr    aPagedfinditemm// "PagedFindItemMappingIdsByFolder"
0x5cb0c  ldstr    asc_8A7C2// ""
0x5cb11  ldstr    asc_8A7C2// ""
0x5cb16  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteVerboseEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string functionName, [opt] string functionParam1, [opt] string functionParam2)
0x5cb1b  ldarg.0
0x5cb1c  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemFinder::get__monitoredExchangeService()
0x5cb21  stloc.0
0x5cb22  ldarg.0
0x5cb23  ldarg.2
0x5cb24  call     instance valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemFinder::GetObjectTypeFromFolderClass(string folderClass)
0x5cb29  stloc.1
0x5cb2a  ldloc.1
0x5cb2b  brtrue.s loc_5CB3D
0x5cb2d  ldstr    aMappingIdsAreD// "Mapping IDs are defined only for Calend"...
0x5cb32  ldstr    aFolderclass// "folderClass"
0x5cb37  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x5cb3c  throw
0x5cb3d  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.SearchFilter>::.ctor()
0x5cb42  stloc.2
0x5cb43  ldloc.2
0x5cb44  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::get_ExchangePropertiesCollection()
0x5cb49  ldstr    aCrmlinkstate_0// "CrmLinkState"
0x5cb4e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition>::get_Item(void)
0x5cb53  ldc.i4.2
0x5cb54  box      [mscorlib]System.Int32
0x5cb59  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.SearchFilter/IsEqualTo::.ctor(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.PropertyDefinitionBase, object)
0x5cb5e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.SearchFilter>::Add(var<u1>)
0x5cb63  ldloc.2
0x5cb64  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::get_ExchangePropertiesCollection()
0x5cb69  ldstr    aCrmlinkstate_0// "CrmLinkState"
0x5cb6e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition>::get_Item(void)
0x5cb73  ldc.i4.0
0x5cb74  box      [mscorlib]System.Int32
0x5cb79  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.SearchFilter/IsEqualTo::.ctor(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.PropertyDefinitionBase, object)
0x5cb7e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.SearchFilter>::Add(var<u1>)
0x5cb83  ldc.i4.1
0x5cb84  ldloc.2
0x5cb85  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.SearchFilter>::ToArray()
0x5cb8a  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.SearchFilter/SearchFilterCollection::.ctor(valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.LogicalOperator, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.SearchFilter[])
0x5cb8f  stloc.3
0x5cb90  ldc.i4.0
0x5cb91  stloc.s  4
0x5cb93  ldc.i4.0
0x5cb94  stloc.s  5
0x5cb96  br       loc_5CC7D
0x5cb9b  ldc.i4   0x2710
0x5cba0  ldloc.s  5
0x5cba2  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ItemView::.ctor(int32, int32)
0x5cba7  stloc.s  6
0x5cba9  ldloc.s  6
0x5cbab  ldc.i4.4
0x5cbac  newarr   [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.PropertyDefinitionBase
0x5cbb1  dup
0x5cbb2  ldc.i4.0
0x5cbb3  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::get_ExchangePropertiesCollection()
0x5cbb8  ldstr    aCrmid_2// "CrmId"
0x5cbbd  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition>::get_Item(void)
0x5cbc2  stelem.ref
0x5cbc3  dup
0x5cbc4  ldc.i4.1
0x5cbc5  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::get_ExchangePropertiesCollection()
0x5cbca  ldstr    aCrmlinkstate_0// "CrmLinkState"
0x5cbcf  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition>::get_Item(void)
0x5cbd4  stelem.ref
0x5cbd5  dup
0x5cbd6  ldc.i4.2
0x5cbd7  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::get_ExchangePropertiesCollection()
0x5cbdc  ldstr    aCrmobjecttypec_1// "CrmObjectTypeCode"
0x5cbe1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition>::get_Item(void)
0x5cbe6  stelem.ref
0x5cbe7  dup
0x5cbe8  ldc.i4.3
0x5cbe9  ldsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.PropertyDefinition [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ItemSchema::LastModifiedTime
0x5cbee  stelem.ref
0x5cbef  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.PropertySet::.ctor(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.PropertyDefinitionBase[])
0x5cbf4  callvirt instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ViewBase::set_PropertySet(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.PropertySet)
0x5cbf9  ldloc.0
0x5cbfa  ldarg.1
0x5cbfb  ldloc.3
0x5cbfc  ldloc.s  6
0x5cbfe  ldarg.s  4
0x5cc00  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FindItemsResults`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item> Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::FindItems(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FolderId parentFolderId, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.SearchFilter searchFilter, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ViewBase view, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType exchangeItemType)
0x5cc05  stloc.s  7
0x5cc07  ldloc.s  7
0x5cc09  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FindItemsResults`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item>::GetEnumerator()
0x5cc0e  stloc.s  8
0x5cc10  br.s     loc_5CC33
0x5cc12  ldloc.s  8
0x5cc14  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item>::get_Current()
0x5cc19  stloc.s  9
0x5cc1b  ldarg.0
0x5cc1c  ldloc.s  9
0x5cc1e  ldloc.1
0x5cc1f  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemFinder::GetItemChangeInfo(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item item, valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType defaultItemObjectType)
0x5cc24  stloc.s  0xA
0x5cc26  ldloc.s  0xA
0x5cc28  brfalse.s loc_5CC33
0x5cc2a  ldarg.0
0x5cc2b  ldarg.3
0x5cc2c  ldloc.s  0xA
0x5cc2e  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemFinder::AddMappingCollection(class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Asynchronous.EmailConnector.LinkState, class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo>> mappingIdCollection, class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo syncItemInfo)
0x5cc33  ldloc.s  8
0x5cc35  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5cc3a  brtrue.s loc_5CC12
0x5cc3c  leave.s  loc_5CC4A
0x5cc3e  ldloc.s  8
0x5cc40  brfalse.s loc_5CC49
0x5cc42  ldloc.s  8
0x5cc44  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5cc49  endfinally
0x5cc4a  ldloc.s  5
0x5cc4c  ldloc.s  7
0x5cc4e  call     T0x2B0000AD
0x5cc53  add
0x5cc54  stloc.s  5
0x5cc56  ldloc.s  7
0x5cc58  callvirt instance bool class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FindItemsResults`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item>::get_MoreAvailable()
0x5cc5d  ldc.i4.0
0x5cc5e  ceq
0x5cc60  stloc.s  4
0x5cc62  ldc.i4.1
0x5cc63  ldarg.0
0x5cc64  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_Context()
0x5cc69  ldstr    aPagedfinditemm// "PagedFindItemMappingIdsByFolder"
0x5cc6e  ldstr    asc_8A7C2// ""
0x5cc73  ldstr    asc_8A7C2// ""
0x5cc78  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteVerboseEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string functionName, [opt] string functionParam1, [opt] string functionParam2)
0x5cc7d  ldloc.s  4
0x5cc7f  brfalse  loc_5CB9B
0x5cc84  ret
```
