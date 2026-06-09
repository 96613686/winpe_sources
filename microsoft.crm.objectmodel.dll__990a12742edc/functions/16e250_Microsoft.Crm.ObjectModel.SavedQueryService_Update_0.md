# Microsoft.Crm.ObjectModel.SavedQueryService::Update_0

- ea: `0x16e250`
- end: `0x16e334`
- name: `Microsoft.Crm.ObjectModel.SavedQueryService::Update_0`
- size: `228`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x197770`

## callees

- `0x317f0`
- `0x16e250`
- `0x16e340`
- `0x16e460`
- `0x16f750`

## string_xrefs

- `0x16e2d4`: `layoutjson`
- `0x16e25f`: `fetchxml`
- `0x16e2af`: `fetchxml`
- `0x16e2bc`: `fetchxml`
- `0x16e281`: `layoutxml`
- `0x16e2db`: `layoutxml`
- `0x16e304`: `isInSavedQueryUninstallContext`
- `0x16e319`: `isInSavedQueryUninstallContext`

## pseudocode

```c

```

## disassembly

```asm
0x16e250  ldarg.s  4
0x16e252  brfalse.s loc_16E25E
0x16e254  ldarg.0
0x16e255  ldarg.1
0x16e256  ldc.i4.1
0x16e257  ldarg.3
0x16e258  ldarg.2
0x16e259  call     instance void Microsoft.Crm.ObjectModel.SavedQueryService::ValidateSavedQuery(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity savedquery, bool isForUpdate, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache dynamicCache, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x16e25e  ldarg.1
0x16e25f  ldstr    aFetchxml// "fetchxml"
0x16e264  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x16e269  brtrue.s loc_16E280
0x16e26b  ldarg.1
0x16e26c  ldstr    aOfflinesqlquer// "offlinesqlquery"
0x16e271  ldarg.0
0x16e272  ldarg.1
0x16e273  ldc.i4.1
0x16e274  ldarg.3
0x16e275  ldarg.2
0x16e276  call     instance string Microsoft.Crm.ObjectModel.SavedQueryService::AddOfflineSqlQueryAttribute(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, bool isUpdate, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache cache, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x16e27b  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x16e280  ldarg.1
0x16e281  ldstr    aLayoutxml// "layoutxml"
0x16e286  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x16e28b  brtrue.s loc_16E2F6
0x16e28d  ldarg.1
0x16e28e  ldstr    aReturnedtypeco// "returnedtypecode"
0x16e293  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x16e298  brtrue.s loc_16E2AC
0x16e29a  ldarg.1
0x16e29b  ldstr    aReturnedtypeco// "returnedtypecode"
0x16e2a0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x16e2a5  unbox.any [mscorlib]System.Int32
0x16e2aa  br.s     loc_16E2AD
0x16e2ac  ldc.i4.m1
0x16e2ad  stloc.0
0x16e2ae  ldarg.1
0x16e2af  ldstr    aFetchxml// "fetchxml"
0x16e2b4  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x16e2b9  brtrue.s loc_16E2CD
0x16e2bb  ldarg.1
0x16e2bc  ldstr    aFetchxml// "fetchxml"
0x16e2c1  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x16e2c6  callvirt instance string [mscorlib]System.Object::ToString()
0x16e2cb  br.s     loc_16E2D2
0x16e2cd  ldsfld   string [mscorlib]System.String::Empty
0x16e2d2  stloc.1
0x16e2d3  ldarg.1
0x16e2d4  ldstr    aLayoutjson// "layoutjson"
0x16e2d9  ldloc.1
0x16e2da  ldarg.1
0x16e2db  ldstr    aLayoutxml// "layoutxml"
0x16e2e0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x16e2e5  callvirt instance string [mscorlib]System.Object::ToString()
0x16e2ea  ldloc.0
0x16e2eb  ldarg.2
0x16e2ec  call     string Microsoft.Crm.MetadataService.Utility.ClientMetadataHelper::GetPopulatedLayoutJson(string fetchXml, string layoutXml, int32 primaryEntityTypeCode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x16e2f1  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x16e2f6  ldarg.0
0x16e2f7  ldarg.1
0x16e2f8  ldarg.2
0x16e2f9  call     instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::UpdateEntityInternal(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x16e2fe  ldarg.2
0x16e2ff  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0x16e304  ldstr    aIsinsavedquery// "isInSavedQueryUninstallContext"
0x16e309  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x16e30e  brtrue.s loc_16E313
0x16e310  ldc.i4.0
0x16e311  br.s     loc_16E328
0x16e313  ldarg.2
0x16e314  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0x16e319  ldstr    aIsinsavedquery// "isInSavedQueryUninstallContext"
0x16e31e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x16e323  unbox.any [mscorlib]System.Boolean
0x16e328  brtrue.s loc_16E333
0x16e32a  ldarg.0
0x16e32b  ldarg.1
0x16e32c  ldarg.3
0x16e32d  ldarg.2
0x16e32e  call     instance void Microsoft.Crm.ObjectModel.SavedQueryService::UpdateSearchablePropertiesOnAttributeMetadata(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity updatedSavedQuery, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache cache, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x16e333  ret
```
