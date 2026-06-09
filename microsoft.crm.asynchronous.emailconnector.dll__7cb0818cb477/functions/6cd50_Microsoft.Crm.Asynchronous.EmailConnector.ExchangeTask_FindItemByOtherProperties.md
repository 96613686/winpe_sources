# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeTask::FindItemByOtherProperties

- ea: `0x6cd50`
- end: `0x6cdb8`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeTask::FindItemByOtherProperties`
- size: `104`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x6cdc0`

## callees

- `0x684f0`
- `0x6b1d0`
- `0x6cd50`
- `0x701b0`
- `0x701d0`
- `0x70330`

## string_xrefs

- `0x6cd56`: `crmtaskassigneduniqueid`
- `0x6cd70`: `crmTaskAssignedUniqueId`

## pseudocode

```c

```

## disassembly

```asm
0x6cd50  ldarg.0
0x6cd51  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_InputSyncItem()
0x6cd56  ldstr    aCrmtaskassigne// "crmtaskassigneduniqueid"
0x6cd5b  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::GetProperty(string propertyName)
0x6cd60  stloc.0
0x6cd61  ldloc.0
0x6cd62  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6cd67  brfalse.s loc_6CD6B
0x6cd69  ldnull
0x6cd6a  ret
0x6cd6b  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::get_ExchangePropertiesCollection()
0x6cd70  ldstr    aCrmtaskassigne_2// "crmTaskAssignedUniqueId"
0x6cd75  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition>::get_Item(void)
0x6cd7a  ldloc.0
0x6cd7b  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.SearchFilter/IsEqualTo::.ctor(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.PropertyDefinitionBase, object)
0x6cd80  stloc.1
0x6cd81  ldarg.0
0x6cd82  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IProvider Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_Provider()
0x6cd87  castclass Microsoft.Crm.Asynchronous.EmailConnector.ExchangeProvider
0x6cd8c  ldloc.1
0x6cd8d  ldc.i4.s 9
0x6cd8f  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FolderId::.ctor(valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.WellKnownFolderName)
0x6cd94  ldc.i4.3
0x6cd95  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FindItemsResults`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeProvider::FindItems(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.SearchFilter searchFilter, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FolderId folderId, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType exchangeItemType)
0x6cd9a  stloc.2
0x6cd9b  ldloc.2
0x6cd9c  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<var<u1>> class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FindItemsResults`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item>::get_Items()
0x6cda1  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item>::get_Count()
0x6cda6  ldc.i4.0
0x6cda7  ble.s    loc_6CDB6
0x6cda9  ldloc.2
0x6cdaa  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<var<u1>> class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FindItemsResults`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item>::get_Items()
0x6cdaf  ldc.i4.0
0x6cdb0  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item>::get_Item(!!T0)
0x6cdb5  ret
0x6cdb6  ldnull
0x6cdb7  ret
```
