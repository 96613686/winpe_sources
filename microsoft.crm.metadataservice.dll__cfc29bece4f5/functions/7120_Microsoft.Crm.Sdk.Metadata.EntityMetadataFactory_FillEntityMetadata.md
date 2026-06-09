# Microsoft.Crm.Sdk.Metadata.EntityMetadataFactory::FillEntityMetadata

- ea: `0x7120`
- end: `0x7e7c`
- name: `Microsoft.Crm.Sdk.Metadata.EntityMetadataFactory::FillEntityMetadata`
- size: `3420`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x6120`
- `0x61b0`

## callees

- `0x7120`
- `0x7e80`
- `0xb7e0`
- `0xc120`

## string_xrefs

- `0x7a2a`: `isrenameable`
- `0x7a38`: `isrenameable`
- `0x7a47`: `isrenameable`
- `0x7442`: `availableforcreate`
- `0x7450`: `availableforcreate`
- `0x746a`: `availableforupdate`
- `0x7478`: `availableforupdate`
- `0x7492`: `availablefordelete`
- `0x74a0`: `availablefordelete`
- `0x74d6`: `isairupdated`
- `0x74e6`: `isairupdated`
- `0x75a3`: `isdocumentrecommendationsenabled`
- `0x76e8`: `isreadingpaneenabled`
- `0x7703`: `isquickcreateenabled`
- `0x7713`: `isquickcreateenabled`
- `0x7981`: `isreadonlyinmobileclient`
- `0x7996`: `isreadonlyinmobileclient`
- `0x79a5`: `canmodifymobileclientreadonly`
- `0x7cb9`: `canmodifymobileclientreadonly`
- `0x7cce`: `canmodifymobileclientreadonly`
- `0x7a74`: `cancreateattributes`
- `0x7a83`: `cancreateattributes`
- `0x7a94`: `cancreatecharts`
- `0x7aa3`: `cancreatecharts`
- `0x7ab4`: `cancreateforms`
- `0x7ac3`: `cancreateforms`
- `0x7ad4`: `cancreateviews`
- `0x7ae3`: `cancreateviews`

## pseudocode

```c

```

## disassembly

```asm
0x7120  ldarg.1
0x7121  ldstr    aEntityid// "entityid"
0x7126  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x712b  unbox.any [mscorlib]System.Guid
0x7130  stloc.0
0x7131  ldarg.0
0x7132  ldloc.0
0x7133  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x7138  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase::set_MetadataId(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>)
0x713d  ldarg.0
0x713e  ldarg.1
0x713f  ldstr    aName// "name"
0x7144  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x7149  castclass [mscorlib]System.String
0x714e  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::set_SchemaName(string)
0x7153  ldarg.0
0x7154  ldarg.1
0x7155  ldstr    aLogicalname// "logicalname"
0x715a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x715f  castclass [mscorlib]System.String
0x7164  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::set_LogicalName(string)
0x7169  ldarg.0
0x716a  ldarg.1
0x716b  ldstr    aPhysicalname// "physicalname"
0x7170  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x7175  castclass [mscorlib]System.String
0x717a  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::set_PhysicalName(string)
0x717f  ldarg.0
0x7180  ldarg.1
0x7181  ldstr    aExternalname// "externalname"
0x7186  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x718b  castclass [mscorlib]System.String
0x7190  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::set_ExternalName(string)
0x7195  ldarg.0
0x7196  ldarg.1
0x7197  ldstr    aExternalcollec// "externalcollectionname"
0x719c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x71a1  castclass [mscorlib]System.String
0x71a6  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::set_ExternalCollectionName(string)
0x71ab  ldarg.0
0x71ac  ldarg.2
0x71ad  ldloc.0
0x71ae  ldstr    aDescription// "Description"
0x71b3  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Label Microsoft.Crm.Sdk.Metadata.MetadataLoader::LoadLocalizedNames(valuetype [mscorlib]System.Guid objectId, string objectColumnName)
0x71b8  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::set_Description(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Label)
0x71bd  ldarg.0
0x71be  ldarg.2
0x71bf  ldloc.0
0x71c0  ldstr    aLocalizedname// "LocalizedName"
0x71c5  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Label Microsoft.Crm.Sdk.Metadata.MetadataLoader::LoadLocalizedNames(valuetype [mscorlib]System.Guid objectId, string objectColumnName)
0x71ca  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::set_DisplayName(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Label)
0x71cf  ldarg.0
0x71d0  ldarg.2
0x71d1  ldloc.0
0x71d2  ldstr    aLocalizedcolle// "LocalizedCollectionName"
0x71d7  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Label Microsoft.Crm.Sdk.Metadata.MetadataLoader::LoadLocalizedNames(valuetype [mscorlib]System.Guid objectId, string objectColumnName)
0x71dc  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::set_DisplayCollectionName(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Label)
0x71e1  ldarg.1
0x71e2  ldstr    aIsactivity// "isactivity"
0x71e7  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x71ec  brtrue.s loc_7209
0x71ee  ldarg.0
0x71ef  ldarg.1
0x71f0  ldstr    aIsactivity// "isactivity"
0x71f5  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x71fa  unbox.any [mscorlib]System.Boolean
0x71ff  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x7204  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::set_IsActivity(valuetype [mscorlib]System.Nullable`1<bool>)
0x7209  ldarg.1
0x720a  ldstr    aIsactivitypart// "isactivityparty"
0x720f  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x7214  brtrue.s loc_7231
0x7216  ldarg.0
0x7217  ldarg.1
0x7218  ldstr    aIsactivitypart// "isactivityparty"
0x721d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x7222  unbox.any [mscorlib]System.Boolean
0x7227  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x722c  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::set_IsActivityParty(valuetype [mscorlib]System.Nullable`1<bool>)
0x7231  ldarg.1
0x7232  ldstr    aRecurrencebase// "recurrencebaseentityid"
0x7237  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x723c  brfalse.s loc_7278
0x723e  ldarg.1
0x723f  ldstr    aRecurrencebase// "recurrencebaseentityid"
0x7244  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x7249  unbox.any [mscorlib]System.Guid
0x724e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x7253  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x7258  brfalse.s loc_7278
0x725a  ldarg.1
0x725b  ldstr    aRecurrencebase// "recurrencebaseentityid"
0x7260  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x7265  unbox.any [mscorlib]System.Guid
0x726a  stloc.1
0x726b  ldarg.0
0x726c  ldarg.2
0x726d  ldloc.1
0x726e  callvirt instance string Microsoft.Crm.Sdk.Metadata.MetadataLoader::GetEntityName(valuetype [mscorlib]System.Guid entityId)
0x7273  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::set_RecurrenceBaseEntityLogicalName(string)
0x7278  ldarg.0
0x7279  ldarg.1
0x727a  ldstr    aIsreplicated// "isreplicated"
0x727f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x7284  unbox.any [mscorlib]System.Boolean
0x7289  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x728e  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::set_IsAvailableOffline(valuetype [mscorlib]System.Nullable`1<bool>)
0x7293  ldarg.0
0x7294  ldarg.1
0x7295  ldstr    aIscustomentity// "iscustomentity"
0x729a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x729f  unbox.any [mscorlib]System.Boolean
0x72a4  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x72a9  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::set_IsCustomEntity(valuetype [mscorlib]System.Nullable`1<bool>)
0x72ae  ldarg.0
0x72af  ldarg.1
0x72b0  ldstr    aIsintersect// "isintersect"
0x72b5  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x72ba  unbox.any [mscorlib]System.Boolean
0x72bf  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x72c4  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::set_IsIntersect(valuetype [mscorlib]System.Nullable`1<bool>)
0x72c9  ldarg.0
0x72ca  ldarg.1
0x72cb  ldstr    aCantriggerwork// "cantriggerworkflow"
0x72d0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x72d5  unbox.any [mscorlib]System.Boolean
0x72da  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x72df  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::set_CanTriggerWorkflow(valuetype [mscorlib]System.Nullable`1<bool>)
0x72e4  ldarg.0
0x72e5  ldarg.1
0x72e6  ldstr    aWorkflowsuppor// "workflowsupport"
0x72eb  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x72f0  unbox.any [mscorlib]System.Int32
0x72f5  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x72fa  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::set_WorkflowSupport(valuetype [mscorlib]System.Nullable`1<int32>)
0x72ff  ldarg.0
0x7300  ldarg.1
0x7301  ldstr    aAutoroutetoown// "autoroutetoownerqueue"
0x7306  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x730b  unbox.any [mscorlib]System.Boolean
0x7310  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x7315  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::set_AutoRouteToOwnerQueue(valuetype [mscorlib]System.Nullable`1<bool>)
0x731a  ldarg.1
0x731b  ldstr    aEntityhelpurl// "entityhelpurl"
0x7320  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x7325  brtrue.s loc_733D
0x7327  ldarg.0
0x7328  ldarg.1
0x7329  ldstr    aEntityhelpurl// "entityhelpurl"
0x732e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x7333  castclass [mscorlib]System.String
0x7338  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::set_EntityHelpUrl(string)
0x733d  ldarg.1
0x733e  ldstr    aEntityhelpurle// "entityhelpurlenabled"
0x7343  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x7348  brtrue.s loc_7365
0x734a  ldarg.0
0x734b  ldarg.1
0x734c  ldstr    aEntityhelpurle// "entityhelpurlenabled"
0x7351  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x7356  unbox.any [mscorlib]System.Boolean
0x735b  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x7360  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::set_EntityHelpUrlEnabled(valuetype [mscorlib]System.Nullable`1<bool>)
0x7365  ldarg.1
0x7366  ldstr    aIconlargename// "iconlargename"
0x736b  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x7370  brtrue.s loc_7388
0x7372  ldarg.0
0x7373  ldarg.1
0x7374  ldstr    aIconlargename// "iconlargename"
0x7379  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x737e  castclass [mscorlib]System.String
0x7383  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::set_IconLargeName(string)
0x7388  ldarg.1
0x7389  ldstr    aIconmediumname// "iconmediumname"
0x738e  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x7393  brtrue.s loc_73AB
0x7395  ldarg.0
0x7396  ldarg.1
0x7397  ldstr    aIconmediumname// "iconmediumname"
0x739c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x73a1  castclass [mscorlib]System.String
0x73a6  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::set_IconMediumName(string)
0x73ab  ldarg.1
0x73ac  ldstr    aIconsmallname// "iconsmallname"
0x73b1  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x73b6  brtrue.s loc_73CE
0x73b8  ldarg.0
0x73b9  ldarg.1
0x73ba  ldstr    aIconsmallname// "iconsmallname"
0x73bf  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x73c4  castclass [mscorlib]System.String
0x73c9  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::set_IconSmallName(string)
0x73ce  ldarg.1
0x73cf  ldstr    aIconvectorname// "iconvectorname"
0x73d4  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x73d9  brtrue.s loc_73F1
0x73db  ldarg.0
0x73dc  ldarg.1
0x73dd  ldstr    aIconvectorname// "iconvectorname"
0x73e2  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x73e7  castclass [mscorlib]System.String
0x73ec  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::set_IconVectorName(string)
0x73f1  ldarg.1
0x73f2  ldstr    aAvailableforre// "availableforretrieve"
0x73f7  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x73fc  brtrue.s loc_7419
0x73fe  ldarg.0
0x73ff  ldarg.1
0x7400  ldstr    aAvailableforre// "availableforretrieve"
0x7405  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x740a  unbox.any [mscorlib]System.Int32
0x740f  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x7414  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::set_AvailableForRetrieve(valuetype [mscorlib]System.Nullable`1<int32>)
0x7419  ldarg.1
0x741a  ldstr    aAvailableforre_0// "availableforretrievemultiple"
0x741f  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x7424  brtrue.s loc_7441
0x7426  ldarg.0
0x7427  ldarg.1
0x7428  ldstr    aAvailableforre_0// "availableforretrievemultiple"
0x742d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x7432  unbox.any [mscorlib]System.Int32
0x7437  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x743c  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::set_AvailableForRetrieveMultiple(valuetype [mscorlib]System.Nullable`1<int32>)
0x7441  ldarg.1
0x7442  ldstr    aAvailableforcr// "availableforcreate"
0x7447  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x744c  brtrue.s loc_7469
0x744e  ldarg.0
0x744f  ldarg.1
0x7450  ldstr    aAvailableforcr// "availableforcreate"
0x7455  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x745a  unbox.any [mscorlib]System.Int32
0x745f  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x7464  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::set_AvailableForCreate(valuetype [mscorlib]System.Nullable`1<int32>)
0x7469  ldarg.1
0x746a  ldstr    aAvailableforup// "availableforupdate"
0x746f  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x7474  brtrue.s loc_7491
0x7476  ldarg.0
0x7477  ldarg.1
0x7478  ldstr    aAvailableforup// "availableforupdate"
0x747d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x7482  unbox.any [mscorlib]System.Int32
0x7487  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x748c  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::set_AvailableForUpdate(valuetype [mscorlib]System.Nullable`1<int32>)
0x7491  ldarg.1
0x7492  ldstr    aAvailableforde// "availablefordelete"
0x7497  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x749c  brtrue.s loc_74B9
0x749e  ldarg.0
0x749f  ldarg.1
0x74a0  ldstr    aAvailableforde// "availablefordelete"
0x74a5  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x74aa  unbox.any [mscorlib]System.Int32
0x74af  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x74b4  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::set_AvailableForDelete(valuetype [mscorlib]System.Nullable`1<int32>)
0x74b9  ldarg.0
0x74ba  ldarg.1
0x74bb  ldstr    aIsimportable// "isimportable"
0x74c0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x74c5  unbox.any [mscorlib]System.Boolean
0x74ca  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x74cf  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::set_IsImportable(valuetype [mscorlib]System.Nullable`1<bool>)
0x74d4  ldarg.0
0x74d5  ldarg.1
0x74d6  ldstr    aIsairupdated// "isairupdated"
0x74db  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNameValid(string)
0x74e0  brtrue.s loc_74E5
0x74e2  ldnull
0x74e3  br.s     loc_74F0
0x74e5  ldarg.1
0x74e6  ldstr    aIsairupdated// "isairupdated"
0x74eb  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x74f0  unbox.any valuetype [mscorlib]System.Nullable`1<bool>
0x74f5  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::set_IsAIRUpdated(valuetype [mscorlib]System.Nullable`1<bool>)
0x74fa  ldarg.0
0x74fb  ldarg.1
0x74fc  ldstr    aIschildentity// "ischildentity"
0x7501  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x7506  unbox.any [mscorlib]System.Boolean
0x750b  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x7510  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::set_IsChildEntity(valuetype [mscorlib]System.Nullable`1<bool>)
0x7515  ldarg.0
0x7516  ldarg.1
0x7517  ldstr    aObjecttypecode_0// "objecttypecode"
0x751c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x7521  unbox.any [mscorlib]System.Int32
0x7526  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x752b  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::set_ObjectTypeCode(valuetype [mscorlib]System.Nullable`1<int32>)
0x7530  ldarg.0
0x7531  ldarg.1
0x7532  ldstr    aOwnershiptypem// "ownershiptypemask"
0x7537  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x753c  unbox.any [mscorlib]System.Int32
0x7541  call     valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OwnershipTypes Microsoft.Crm.Sdk.Metadata.EntityMetadataFactory::GetOwnershipTypes(int32 ownershipMasks)
0x7546  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OwnershipTypes>::.ctor(var<u1>)
0x754b  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::set_OwnershipType(valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OwnershipTypes>)
0x7550  ldarg.0
  ... truncated ...
```
