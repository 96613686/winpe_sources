# Microsoft.Crm.ObjectModel.SavedQueryService::Create_0

- ea: `0x16f070`
- end: `0x16f1b0`
- name: `Microsoft.Crm.ObjectModel.SavedQueryService::Create_0`
- size: `320`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x16f260`

## callees

- `0x317f0`
- `0x16e340`
- `0x16e620`
- `0x16f070`
- `0x16f1b0`
- `0x16f270`
- `0x16f750`

## string_xrefs

- `0x16f129`: `layoutjson`
- `0x16f0b4`: `fetchxml`
- `0x16f104`: `fetchxml`
- `0x16f111`: `fetchxml`
- `0x16f199`: `fetchxml`
- `0x16f0d6`: `layoutxml`
- `0x16f130`: `layoutxml`

## pseudocode

```c

```

## disassembly

```asm
0x16f070  ldarg.s  4
0x16f072  brfalse.s loc_16F07E
0x16f074  ldarg.0
0x16f075  ldarg.1
0x16f076  ldc.i4.0
0x16f077  ldarg.3
0x16f078  ldarg.2
0x16f079  call     instance void Microsoft.Crm.ObjectModel.SavedQueryService::ValidateSavedQuery(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity savedquery, bool isForUpdate, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache dynamicCache, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x16f07e  ldarg.0
0x16f07f  ldarg.1
0x16f080  ldarg.2
0x16f081  ldarg.3
0x16f082  call     instance void Microsoft.Crm.ObjectModel.SavedQueryService::ValidateQuickFindSavedQueryCreate(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache cache)
0x16f087  ldarg.2
0x16f088  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0x16f08d  ldstr    aGenerateofflin// "generateOfflineSqlQueryForView"
0x16f092  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x16f097  brtrue.s loc_16F09C
0x16f099  ldc.i4.1
0x16f09a  br.s     loc_16F0B1
0x16f09c  ldarg.2
0x16f09d  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0x16f0a2  ldstr    aGenerateofflin// "generateOfflineSqlQueryForView"
0x16f0a7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x16f0ac  unbox.any [mscorlib]System.Boolean
0x16f0b1  brfalse.s loc_16F0D5
0x16f0b3  ldarg.1
0x16f0b4  ldstr    aFetchxml// "fetchxml"
0x16f0b9  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x16f0be  brtrue.s loc_16F0D5
0x16f0c0  ldarg.1
0x16f0c1  ldstr    aOfflinesqlquer// "offlinesqlquery"
0x16f0c6  ldarg.0
0x16f0c7  ldarg.1
0x16f0c8  ldc.i4.0
0x16f0c9  ldnull
0x16f0ca  ldarg.2
0x16f0cb  call     instance string Microsoft.Crm.ObjectModel.SavedQueryService::AddOfflineSqlQueryAttribute(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, bool isUpdate, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache cache, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x16f0d0  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x16f0d5  ldarg.1
0x16f0d6  ldstr    aLayoutxml// "layoutxml"
0x16f0db  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x16f0e0  brtrue.s loc_16F14B
0x16f0e2  ldarg.1
0x16f0e3  ldstr    aReturnedtypeco// "returnedtypecode"
0x16f0e8  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x16f0ed  brtrue.s loc_16F101
0x16f0ef  ldarg.1
0x16f0f0  ldstr    aReturnedtypeco// "returnedtypecode"
0x16f0f5  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x16f0fa  unbox.any [mscorlib]System.Int32
0x16f0ff  br.s     loc_16F102
0x16f101  ldc.i4.m1
0x16f102  stloc.2
0x16f103  ldarg.1
0x16f104  ldstr    aFetchxml// "fetchxml"
0x16f109  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x16f10e  brtrue.s loc_16F122
0x16f110  ldarg.1
0x16f111  ldstr    aFetchxml// "fetchxml"
0x16f116  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x16f11b  callvirt instance string [mscorlib]System.Object::ToString()
0x16f120  br.s     loc_16F127
0x16f122  ldsfld   string [mscorlib]System.String::Empty
0x16f127  stloc.3
0x16f128  ldarg.1
0x16f129  ldstr    aLayoutjson// "layoutjson"
0x16f12e  ldloc.3
0x16f12f  ldarg.1
0x16f130  ldstr    aLayoutxml// "layoutxml"
0x16f135  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x16f13a  callvirt instance string [mscorlib]System.Object::ToString()
0x16f13f  ldloc.2
0x16f140  ldarg.2
0x16f141  call     string Microsoft.Crm.MetadataService.Utility.ClientMetadataHelper::GetPopulatedLayoutJson(string fetchXml, string layoutXml, int32 primaryEntityTypeCode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x16f146  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x16f14b  ldarg.0
0x16f14c  ldarg.1
0x16f14d  ldarg.2
0x16f14e  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x16f153  stloc.0
0x16f154  ldarg.2
0x16f155  ldarg.1
0x16f156  ldloc.0
0x16f157  ldstr    aSavedquery// "SavedQuery"
0x16f15c  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::AddComponentToDependencyComponentCollection(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, string)
0x16f161  ldarg.2
0x16f162  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x16f167  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionId()
0x16f16c  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::SystemSolutionId
0x16f171  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x16f176  stloc.1
0x16f177  ldarg.s  5
0x16f179  brfalse.s loc_16F1AF
0x16f17b  ldloc.1
0x16f17c  brtrue.s loc_16F1AF
0x16f17e  ldarg.1
0x16f17f  ldnull
0x16f180  call     bool Microsoft.Crm.ObjectModel.SavedQueryService::IsSavedQueryTypeDefaultQuickFind(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity retrievedEntity)
0x16f185  brfalse.s loc_16F1AF
0x16f187  ldarg.0
0x16f188  ldarg.1
0x16f189  ldstr    aReturnedtypeco// "returnedtypecode"
0x16f18e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x16f193  unbox.any [mscorlib]System.Int32
0x16f198  ldarg.1
0x16f199  ldstr    aFetchxml// "fetchxml"
0x16f19e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x16f1a3  castclass [mscorlib]System.String
0x16f1a8  ldarg.2
0x16f1a9  ldc.i4.0
0x16f1aa  call     instance void Microsoft.Crm.ObjectModel.SavedQueryService::ProcessAndUpdateSearchableAttributes(int32 returnedTypeCode, string fetchxml, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, [opt] bool processOnlyCustomFields)
0x16f1af  ret
```
