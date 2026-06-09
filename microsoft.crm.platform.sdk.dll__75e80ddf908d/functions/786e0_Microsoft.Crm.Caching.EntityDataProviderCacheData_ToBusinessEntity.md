# Microsoft.Crm.Caching.EntityDataProviderCacheData::ToBusinessEntity

- ea: `0x786e0`
- end: `0x7878e`
- name: `Microsoft.Crm.Caching.EntityDataProviderCacheData::ToBusinessEntity`
- size: `174`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x784f0`
- `0x78510`
- `0x78530`
- `0x78570`
- `0x78590`
- `0x785b0`
- `0x785d0`
- `0x785f0`
- `0x9ca70`
- `0x9ce80`

## string_xrefs

- `0x78720`: `createplugin`
- `0x78736`: `updateplugin`
- `0x7874c`: `deleteplugin`
- `0x78762`: `retrieveplugin`
- `0x78778`: `retrievemultipleplugin`

## pseudocode

```c

```

## disassembly

```asm
0x786e0  ldarg.1
0x786e1  ldarg.2
0x786e2  call     class Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.BusinessEntities.EntityClassFactory::CreateInstance(class Microsoft.Crm.Metadata.EntityMetadata metadata, valuetype [mscorlib]System.Guid organizationId)
0x786e7  dup
0x786e8  ldstr    aEntitydataprov// "entitydataproviderid"
0x786ed  ldarg.0
0x786ee  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Caching.EntityDataProviderCacheData::get_Id()
0x786f3  box      [mscorlib]System.Guid
0x786f8  callvirt instance void Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string attributeName, object attributeValue)
0x786fd  dup
0x786fe  ldstr    aName_0// "name"
0x78703  ldarg.0
0x78704  call     instance string Microsoft.Crm.Caching.EntityDataProviderCacheData::get_Name()
0x78709  callvirt instance void Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string attributeName, object attributeValue)
0x7870e  dup
0x7870f  ldstr    aDatasourcelogi// "datasourcelogicalname"
0x78714  ldarg.0
0x78715  call     instance string Microsoft.Crm.Caching.EntityDataProviderCacheData::get_DataSourceLogicalName()
0x7871a  callvirt instance void Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string attributeName, object attributeValue)
0x7871f  dup
0x78720  ldstr    aCreateplugin// "createplugin"
0x78725  ldarg.0
0x78726  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Caching.EntityDataProviderCacheData::get_CreatePlugin()
0x7872b  box      valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x78730  callvirt instance void Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string attributeName, object attributeValue)
0x78735  dup
0x78736  ldstr    aUpdateplugin// "updateplugin"
0x7873b  ldarg.0
0x7873c  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Caching.EntityDataProviderCacheData::get_UpdatePlugin()
0x78741  box      valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x78746  callvirt instance void Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string attributeName, object attributeValue)
0x7874b  dup
0x7874c  ldstr    aDeleteplugin// "deleteplugin"
0x78751  ldarg.0
0x78752  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Caching.EntityDataProviderCacheData::get_DeletePlugin()
0x78757  box      valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x7875c  callvirt instance void Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string attributeName, object attributeValue)
0x78761  dup
0x78762  ldstr    aRetrieveplugin// "retrieveplugin"
0x78767  ldarg.0
0x78768  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Caching.EntityDataProviderCacheData::get_RetrievePlugin()
0x7876d  box      valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x78772  callvirt instance void Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string attributeName, object attributeValue)
0x78777  dup
0x78778  ldstr    aRetrievemultip// "retrievemultipleplugin"
0x7877d  ldarg.0
0x7877e  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Caching.EntityDataProviderCacheData::get_RetrieveMultiplePlugin()
0x78783  box      valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x78788  callvirt instance void Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string attributeName, object attributeValue)
0x7878d  ret
```
