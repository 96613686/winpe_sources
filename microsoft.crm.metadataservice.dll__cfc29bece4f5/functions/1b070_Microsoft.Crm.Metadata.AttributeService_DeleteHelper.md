# Microsoft.Crm.Metadata.AttributeService::DeleteHelper

- ea: `0x1b070`
- end: `0x1b441`
- name: `Microsoft.Crm.Metadata.AttributeService::DeleteHelper`
- size: `977`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x75750`

## callees

- `0x1b070`
- `0x1b450`
- `0x1ba60`
- `0x1bb50`
- `0x22b70`
- `0x22fc0`
- `0x23060`
- `0x4edf0`
- `0x502f0`
- `0x5a810`

## string_xrefs

- `0x1b0dd`: `linkedattributeid`
- `0x1b0f5`: `linkedattributeid`
- `0x1b103`: `linkedattributeid`
- `0x1b087`: `prvDeleteAttribute`
- `0x1b3fb`: `AttributeService.Delete caught exception: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x1b070  ldc.i4.0
0x1b071  stloc.0
0x1b072  ldstr    asc_804C0// ""
0x1b077  stloc.1
0x1b078  ldc.i4.0
0x1b079  stloc.2
0x1b07a  ldarg.3
0x1b07b  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1b080  pop
0x1b081  ldarg.3
0x1b082  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x1b087  ldstr    aPrvdeleteattri// "prvDeleteAttribute"
0x1b08c  ldarg.3
0x1b08d  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.CustomizationSecurityCache::GetPrivilegeIdFromName(string privilegeName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1b092  ldarg.3
0x1b093  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGlobalDepth(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1b098  ldarg.3
0x1b099  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::StartTransactionIfRequired()
0x1b09e  stloc.3
0x1b09f  ldarg.0
0x1b0a0  ldarg.1
0x1b0a1  ldarg.3
0x1b0a2  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeService::ValidateForDelete(valuetype [mscorlib]System.Guid attributeId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1b0a7  stloc.s  4
0x1b0a9  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x1b0ae  ldloc.s  4
0x1b0b0  ldstr    aAttribute// "Attribute"
0x1b0b5  ldc.i4.6
0x1b0b6  newarr   [mscorlib]System.String
0x1b0bb  dup
0x1b0bc  ldc.i4.0
0x1b0bd  ldstr    aName// "name"
0x1b0c2  stelem.ref
0x1b0c3  dup
0x1b0c4  ldc.i4.1
0x1b0c5  ldstr    aEntityid// "entityid"
0x1b0ca  stelem.ref
0x1b0cb  dup
0x1b0cc  ldc.i4.2
0x1b0cd  ldstr    aLogicalname// "logicalname"
0x1b0d2  stelem.ref
0x1b0d3  dup
0x1b0d4  ldc.i4.3
0x1b0d5  ldstr    aColumnnumber_0// "columnnumber"
0x1b0da  stelem.ref
0x1b0db  dup
0x1b0dc  ldc.i4.4
0x1b0dd  ldstr    aLinkedattribut// "linkedattributeid"
0x1b0e2  stelem.ref
0x1b0e3  dup
0x1b0e4  ldc.i4.5
0x1b0e5  ldstr    aSourcetype// "sourcetype"
0x1b0ea  stelem.ref
0x1b0eb  ldarg.3
0x1b0ec  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::RetrieveMetadataEntity(valuetype [mscorlib]System.Guid, string, string[], class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1b0f1  stloc.s  5
0x1b0f3  ldloc.s  5
0x1b0f5  ldstr    aLinkedattribut// "linkedattributeid"
0x1b0fa  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x1b0ff  brtrue.s loc_1B114
0x1b101  ldloc.s  5
0x1b103  ldstr    aLinkedattribut// "linkedattributeid"
0x1b108  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x1b10d  unbox.any [mscorlib]System.Guid
0x1b112  br.s     loc_1B119
0x1b114  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1b119  stloc.s  6
0x1b11b  ldloc.s  5
0x1b11d  ldstr    aEntityid// "entityid"
0x1b122  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x1b127  unbox.any [mscorlib]System.Guid
0x1b12c  stloc.s  7
0x1b12e  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x1b133  ldloc.s  7
0x1b135  ldstr    aEntity_0// "Entity"
0x1b13a  ldc.i4.5
0x1b13b  newarr   [mscorlib]System.String
0x1b140  dup
0x1b141  ldc.i4.0
0x1b142  ldstr    aEntityid// "entityid"
0x1b147  stelem.ref
0x1b148  dup
0x1b149  ldc.i4.1
0x1b14a  ldstr    aName// "name"
0x1b14f  stelem.ref
0x1b150  dup
0x1b151  ldc.i4.2
0x1b152  ldstr    aLogicalname// "logicalname"
0x1b157  stelem.ref
0x1b158  dup
0x1b159  ldc.i4.3
0x1b15a  ldstr    aObjecttypecode_0// "objecttypecode"
0x1b15f  stelem.ref
0x1b160  dup
0x1b161  ldc.i4.4
0x1b162  ldstr    aIsactivitypart// "isactivityparty"
0x1b167  stelem.ref
0x1b168  ldarg.3
0x1b169  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::RetrieveMetadataEntity(valuetype [mscorlib]System.Guid, string, string[], class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1b16e  stloc.s  8
0x1b170  ldloc.s  6
0x1b172  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1b177  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1b17c  brfalse.s loc_1B187
0x1b17e  ldloc.s  6
0x1b180  ldarg.2
0x1b181  ldarg.3
0x1b182  call     void Microsoft.Crm.Metadata.AttributeService::UpdateLinkedAttributeCanBeSecured(valuetype [mscorlib]System.Guid linkedAttributeId, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1b187  ldarg.0
0x1b188  ldloc.s  5
0x1b18a  ldstr    aLogicalname// "logicalname"
0x1b18f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x1b194  castclass [mscorlib]System.String
0x1b199  ldloc.s  8
0x1b19b  ldstr    aLogicalname// "logicalname"
0x1b1a0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x1b1a5  castclass [mscorlib]System.String
0x1b1aa  ldarg.3
0x1b1ab  call     instance void Microsoft.Crm.Metadata.AttributeService::DeleteInvalidRuleConditionsAndUnpublishRule(string attributeLogicalName, string entityLogicalName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1b1b0  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x1b1b5  ldloc.s  4
0x1b1b7  ldarg.3
0x1b1b8  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x1b1bd  ldloca.s 9
0x1b1bf  callvirt instance bool [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::TryGetEntityRelationshipIds(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>&)
0x1b1c4  brfalse.s loc_1B230
0x1b1c6  ldloc.s  9
0x1b1c8  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::GetEnumerator()
0x1b1cd  stloc.s  0xD
0x1b1cf  br.s     loc_1B1E8
0x1b1d1  ldloca.s 0xD
0x1b1d3  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>::get_Current()
0x1b1d8  stloc.s  0xE
0x1b1da  newobj   instance void Microsoft.Crm.Metadata.RelationshipService::.ctor()
0x1b1df  ldloc.s  0xE
0x1b1e1  ldarg.2
0x1b1e2  ldarg.3
0x1b1e3  call     instance void Microsoft.Crm.Metadata.RelationshipService::DeleteInternal(valuetype [mscorlib]System.Guid entityRelationshipId, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1b1e8  ldloca.s 0xD
0x1b1ea  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>::MoveNext()
0x1b1ef  brtrue.s loc_1B1D1
0x1b1f1  leave.s  loc_1B201
0x1b1f3  ldloca.s 0xD
0x1b1f5  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>
0x1b1fb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1b200  endfinally
0x1b201  ldloc.s  9
0x1b203  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x1b208  ldc.i4.1
0x1b209  ble      loc_1B2A6
0x1b20e  ldarg.0
0x1b20f  ldloc.s  4
0x1b211  ldloc.s  8
0x1b213  ldstr    aObjecttypecode_0// "objecttypecode"
0x1b218  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x1b21d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1b222  call     int32 [mscorlib]System.Convert::ToInt32(object, class [mscorlib]System.IFormatProvider)
0x1b227  ldarg.2
0x1b228  ldarg.3
0x1b229  call     instance void Microsoft.Crm.Metadata.AttributeService::Delete(valuetype [mscorlib]System.Guid attributeId, int32 parentEntityTypeCode, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1b22e  br.s     loc_1B2A6
0x1b230  ldarg.0
0x1b231  ldloc.s  4
0x1b233  ldloc.s  8
0x1b235  ldstr    aObjecttypecode_0// "objecttypecode"
0x1b23a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x1b23f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1b244  call     int32 [mscorlib]System.Convert::ToInt32(object, class [mscorlib]System.IFormatProvider)
0x1b249  ldarg.2
0x1b24a  ldarg.3
0x1b24b  call     instance void Microsoft.Crm.Metadata.AttributeService::Delete(valuetype [mscorlib]System.Guid attributeId, int32 parentEntityTypeCode, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1b250  ldarg.0
0x1b251  ldloc.s  5
0x1b253  ldstr    aName// "name"
0x1b258  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x1b25d  castclass [mscorlib]System.String
0x1b262  ldloc.s  8
0x1b264  ldstr    aName// "name"
0x1b269  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x1b26e  castclass [mscorlib]System.String
0x1b273  ldarg.3
0x1b274  call     instance void Microsoft.Crm.Metadata.AttributeService::DeleteAttributeMaps(string attributeName, string entityName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1b279  ldloc.s  8
0x1b27b  ldstr    aObjecttypecode_0// "objecttypecode"
0x1b280  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x1b285  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1b28a  call     int32 [mscorlib]System.Convert::ToInt32(object, class [mscorlib]System.IFormatProvider)
0x1b28f  ldloc.s  5
0x1b291  ldstr    aName// "name"
0x1b296  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x1b29b  castclass [mscorlib]System.String
0x1b2a0  ldarg.3
0x1b2a1  call     void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.StringMapService::DeleteHelper(int32, string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1b2a6  ldarg.2
0x1b2a7  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::ProcessQueue()
0x1b2ac  ldloc.s  8
0x1b2ae  ldstr    aIsactivitypart// "isactivityparty"
0x1b2b3  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x1b2b8  brtrue.s loc_1B304
0x1b2ba  ldloc.s  8
0x1b2bc  ldstr    aIsactivitypart// "isactivityparty"
0x1b2c1  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x1b2c6  unbox.any [mscorlib]System.Boolean
0x1b2cb  brfalse.s loc_1B304
0x1b2cd  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.EmailSearchService::.ctor()
0x1b2d2  ldarg.3
0x1b2d3  ldloc.s  8
0x1b2d5  ldstr    aObjecttypecode_0// "objecttypecode"
0x1b2da  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x1b2df  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1b2e4  call     int32 [mscorlib]System.Convert::ToInt32(object, class [mscorlib]System.IFormatProvider)
0x1b2e9  ldloc.s  5
0x1b2eb  ldstr    aColumnnumber_0// "columnnumber"
0x1b2f0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x1b2f5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1b2fa  call     int32 [mscorlib]System.Convert::ToInt32(object, class [mscorlib]System.IFormatProvider)
0x1b2ff  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.EmailSearchService::DeleteRowsOfAttribute(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, int32, int32)
0x1b304  ldstr    aRollupproperti// "RollupProperties"
0x1b309  ldarg.3
0x1b30a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1b30f  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ServiceClassFactory::CreateInstance(string, valuetype [mscorlib]System.Guid)
0x1b314  stloc.s  0xB
0x1b316  ldloc.s  5
0x1b318  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityMoniker [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Moniker()
0x1b31d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityMoniker::get_Id()
0x1b322  ldstr    aRollupproperti// "RollupProperties"
0x1b327  ldarg.3
0x1b328  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1b32d  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, valuetype [mscorlib]System.Guid)
0x1b332  stloc.s  0xC
0x1b334  ldloc.s  5
0x1b336  ldstr    aSourcetype// "sourcetype"
0x1b33b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x1b340  unbox.any [mscorlib]System.Int32
0x1b345  ldc.i4.2
0x1b346  bne.un.s loc_1B362
0x1b348  ldloc.s  0xB
0x1b34a  ldloc.s  0xC
0x1b34c  ldarg.3
0x1b34d  ldloca.s 0xA
0x1b34f  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::TryRetrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity&)
0x1b354  brfalse.s loc_1B360
0x1b356  ldloc.s  0xB
0x1b358  ldloc.s  0xC
0x1b35a  ldarg.3
0x1b35b  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Delete(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1b360  ldc.i4.1
0x1b361  stloc.2
0x1b362  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x1b367  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x1b36c  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_OnePartyModel()
0x1b371  ldarg.3
0x1b372  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1b377  brfalse.s loc_1B3A2
0x1b379  ldarg.0
0x1b37a  ldloc.s  5
0x1b37c  ldstr    aLogicalname// "logicalname"
0x1b381  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x1b386  castclass [mscorlib]System.String
0x1b38b  ldloc.s  8
0x1b38d  ldstr    aLogicalname// "logicalname"
0x1b392  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x1b397  castclass [mscorlib]System.String
0x1b39c  ldarg.3
0x1b39d  call     instance void Microsoft.Crm.Metadata.AttributeService::UpdateExternalPartyOrgSettings(string logicalName, string entityLogicalName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1b3a2  ldarg.3
0x1b3a3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_MetadataCache()
0x1b3a8  ldstr    aUsersearchface// "UserSearchFacet"
0x1b3ad  ldc.i4.0
0x1b3ae  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x1b3b3  brfalse.s loc_1B3E2
0x1b3b5  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.UserSearchFacetService::.ctor()
0x1b3ba  ldarg.3
0x1b3bb  ldloc.s  8
0x1b3bd  ldstr    aLogicalname// "logicalname"
0x1b3c2  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x1b3c7  castclass [mscorlib]System.String
0x1b3cc  ldloc.s  5
0x1b3ce  ldstr    aLogicalname// "logicalname"
0x1b3d3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x1b3d8  castclass [mscorlib]System.String
0x1b3dd  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.UserSearchFacetService::DeleteUserSearchFacets(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, string, string)
0x1b3e2  ldloc.3
0x1b3e3  brfalse.s loc_1B3EB
0x1b3e5  ldarg.3
0x1b3e6  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::CommitTransaction()
0x1b3eb  ldc.i4.1
0x1b3ec  stloc.0
0x1b3ed  leave.s  loc_1B440
0x1b3ef  stloc.s  0xF
0x1b3f1  ldloc.s  0xF
0x1b3f3  ldarg.3
0x1b3f4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1b3f9  ldc.i4.s 0x19
0x1b3fb  ldstr    aAttributeservi_2// "AttributeService.Delete caught exceptio"...
0x1b400  ldc.i4.1
0x1b401  newarr   [mscorlib]System.Object
0x1b406  dup
0x1b407  ldc.i4.0
0x1b408  ldloc.s  0xF
  ... truncated ...
```
