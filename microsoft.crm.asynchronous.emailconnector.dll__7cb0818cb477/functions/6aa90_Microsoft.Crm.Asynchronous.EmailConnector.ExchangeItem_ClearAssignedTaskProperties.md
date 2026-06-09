# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::ClearAssignedTaskProperties

- ea: `0x6aa90`
- end: `0x6aafd`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::ClearAssignedTaskProperties`
- size: `109`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x64a50`

## callees

- `0x684f0`
- `0x69840`

## string_xrefs

- `0x6aad1`: `crmtaskassigneduniqueid`
- `0x6aaec`: `crmtasktrackeruserid`
- `0x6aab6`: `crmtaskassigneeuserid`
- `0x6aa9b`: `crmtaskassigneruserid`

## pseudocode

```c

```

## disassembly

```asm
0x6aa90  ldarg.0
0x6aa91  call     instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::get_Item()
0x6aa96  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::get_ExchangePropertiesCollection()
0x6aa9b  ldstr    aCrmtaskassigne_1// "crmtaskassigneruserid"
0x6aaa0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition>::get_Item(void)
0x6aaa5  callvirt instance bool [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::RemoveExtendedProperty(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition)
0x6aaaa  pop
0x6aaab  ldarg.0
0x6aaac  call     instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::get_Item()
0x6aab1  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::get_ExchangePropertiesCollection()
0x6aab6  ldstr    aCrmtaskassigne_0// "crmtaskassigneeuserid"
0x6aabb  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition>::get_Item(void)
0x6aac0  callvirt instance bool [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::RemoveExtendedProperty(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition)
0x6aac5  pop
0x6aac6  ldarg.0
0x6aac7  call     instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::get_Item()
0x6aacc  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::get_ExchangePropertiesCollection()
0x6aad1  ldstr    aCrmtaskassigne// "crmtaskassigneduniqueid"
0x6aad6  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition>::get_Item(void)
0x6aadb  callvirt instance bool [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::RemoveExtendedProperty(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition)
0x6aae0  pop
0x6aae1  ldarg.0
0x6aae2  call     instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::get_Item()
0x6aae7  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::get_ExchangePropertiesCollection()
0x6aaec  ldstr    aCrmtasktracker// "crmtasktrackeruserid"
0x6aaf1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition>::get_Item(void)
0x6aaf6  callvirt instance bool [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::RemoveExtendedProperty(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition)
0x6aafb  pop
0x6aafc  ret
```
