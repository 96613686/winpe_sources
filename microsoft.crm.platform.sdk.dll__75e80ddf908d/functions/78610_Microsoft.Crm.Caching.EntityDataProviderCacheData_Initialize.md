# Microsoft.Crm.Caching.EntityDataProviderCacheData::Initialize

- ea: `0x78610`
- end: `0x786d7`
- name: `Microsoft.Crm.Caching.EntityDataProviderCacheData::Initialize`
- size: `199`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x78500`
- `0x78520`
- `0x78540`
- `0x78560`
- `0x78580`
- `0x785a0`
- `0x785c0`
- `0x785e0`
- `0x78600`
- `0x78790`
- `0x9c500`

## string_xrefs

- `0x7866a`: `createplugin`
- `0x78680`: `updateplugin`
- `0x78696`: `deleteplugin`
- `0x786ac`: `retrieveplugin`
- `0x786c2`: `retrievemultipleplugin`

## pseudocode

```c

```

## disassembly

```asm
0x78610  ldarg.0
0x78611  ldarg.1
0x78612  ldstr    aEntitydataprov// "entitydataproviderid"
0x78617  callvirt instance object Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string attributeName)
0x7861c  unbox.any [mscorlib]System.Guid
0x78621  call     instance void Microsoft.Crm.Caching.EntityDataProviderCacheData::set_Id(valuetype [mscorlib]System.Guid value)
0x78626  ldarg.0
0x78627  ldarg.1
0x78628  ldstr    aName_0// "name"
0x7862d  callvirt instance object Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string attributeName)
0x78632  castclass [mscorlib]System.String
0x78637  call     instance void Microsoft.Crm.Caching.EntityDataProviderCacheData::set_Name(string value)
0x7863c  ldarg.0
0x7863d  ldarg.1
0x7863e  ldstr    aDatasourcelogi// "datasourcelogicalname"
0x78643  callvirt instance object Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string attributeName)
0x78648  castclass [mscorlib]System.String
0x7864d  call     instance void Microsoft.Crm.Caching.EntityDataProviderCacheData::set_DataSourceLogicalName(string value)
0x78652  ldarg.0
0x78653  ldarg.1
0x78654  ldstr    aOrganizationid_1// "organizationid"
0x78659  callvirt instance object Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string attributeName)
0x7865e  unbox.any [mscorlib]System.Guid
0x78663  call     instance void Microsoft.Crm.Caching.EntityDataProviderCacheData::set_OrganizationId(valuetype [mscorlib]System.Guid value)
0x78668  ldarg.0
0x78669  ldarg.1
0x7866a  ldstr    aCreateplugin// "createplugin"
0x7866f  callvirt instance object Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string attributeName)
0x78674  call     valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Caching.EntityDataProviderCacheData::GetPluginId(object attributeValue)
0x78679  call     instance void Microsoft.Crm.Caching.EntityDataProviderCacheData::set_CreatePlugin(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> value)
0x7867e  ldarg.0
0x7867f  ldarg.1
0x78680  ldstr    aUpdateplugin// "updateplugin"
0x78685  callvirt instance object Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string attributeName)
0x7868a  call     valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Caching.EntityDataProviderCacheData::GetPluginId(object attributeValue)
0x7868f  call     instance void Microsoft.Crm.Caching.EntityDataProviderCacheData::set_UpdatePlugin(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> value)
0x78694  ldarg.0
0x78695  ldarg.1
0x78696  ldstr    aDeleteplugin// "deleteplugin"
0x7869b  callvirt instance object Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string attributeName)
0x786a0  call     valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Caching.EntityDataProviderCacheData::GetPluginId(object attributeValue)
0x786a5  call     instance void Microsoft.Crm.Caching.EntityDataProviderCacheData::set_DeletePlugin(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> value)
0x786aa  ldarg.0
0x786ab  ldarg.1
0x786ac  ldstr    aRetrieveplugin// "retrieveplugin"
0x786b1  callvirt instance object Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string attributeName)
0x786b6  call     valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Caching.EntityDataProviderCacheData::GetPluginId(object attributeValue)
0x786bb  call     instance void Microsoft.Crm.Caching.EntityDataProviderCacheData::set_RetrievePlugin(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> value)
0x786c0  ldarg.0
0x786c1  ldarg.1
0x786c2  ldstr    aRetrievemultip// "retrievemultipleplugin"
0x786c7  callvirt instance object Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string attributeName)
0x786cc  call     valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Caching.EntityDataProviderCacheData::GetPluginId(object attributeValue)
0x786d1  call     instance void Microsoft.Crm.Caching.EntityDataProviderCacheData::set_RetrieveMultiplePlugin(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> value)
0x786d6  ret
```
