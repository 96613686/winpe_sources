# Microsoft.Crm.Sdk.Metadata.MetadataConverter::CreateEntityEntity

- ea: `0x9ff0`
- end: `0xa93b`
- name: `Microsoft.Crm.Sdk.Metadata.MetadataConverter::CreateEntityEntity`
- size: `2379`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x8e40`
- `0x8ec0`

## callees

- `0x9ff0`
- `0xa940`
- `0xa960`
- `0xc550`

## string_xrefs

- `0xa8c9`: `isrenameable`
- `0xa822`: `availableforcreate`
- `0xa852`: `availableforupdate`
- `0xa882`: `availablefordelete`
- `0xa510`: `isdocumentrecommendationsenabled`
- `0xa624`: `isquickcreateenabled`
- `0xa2f7`: `isreadonlyinmobileclient`
- `0xa8da`: `cancreatecharts`
- `0xa8eb`: `cancreateforms`
- `0xa8fc`: `cancreateviews`
- `0xa6cc`: `autocreateaccessteams`

## pseudocode

```c

```

## disassembly

```asm
0x9ff0  ldstr    aEntity_0// "Entity"
0x9ff5  ldarg.0
0x9ff6  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Sdk.Metadata.MetadataConverter::_context
0x9ffb  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa000  stloc.0
0xa001  ldarg.1
0xa002  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase::get_MetadataId()
0xa007  stloc.1
0xa008  ldloca.s 1
0xa00a  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0xa00f  brfalse.s loc_A02B
0xa011  ldarg.1
0xa012  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase::get_MetadataId()
0xa017  stloc.1
0xa018  ldloca.s 1
0xa01a  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0xa01f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xa024  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xa029  brfalse.s loc_A07D
0xa02b  ldarg.2
0xa02c  ldc.i4   0x1000
0xa031  and
0xa032  ldc.i4   0x1000
0xa037  bne.un.s loc_A04B
0xa039  ldarg.1
0xa03a  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xa03f  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0xa044  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase::set_MetadataId(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>)
0xa049  br.s     loc_A07D
0xa04b  ldarg.0
0xa04c  ldfld    class Microsoft.Crm.Sdk.Metadata.MetadataLoader Microsoft.Crm.Sdk.Metadata.MetadataConverter::_loader
0xa051  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xa056  ldarg.1
0xa057  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_LogicalName()
0xa05c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Sdk.Metadata.MetadataLoader::LoadEntiy(valuetype [mscorlib]System.Guid entityId, string entityName)
0xa061  stloc.2
0xa062  ldarg.1
0xa063  ldloc.2
0xa064  ldstr    aEntityid// "entityid"
0xa069  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0xa06e  unbox.any [mscorlib]System.Guid
0xa073  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0xa078  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase::set_MetadataId(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>)
0xa07d  ldloc.0
0xa07e  ldstr    aEntityid// "entityid"
0xa083  ldarg.1
0xa084  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase::get_MetadataId()
0xa089  stloc.1
0xa08a  ldloca.s 1
0xa08c  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0xa091  box      [mscorlib]System.Guid
0xa096  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0xa09b  ldloc.0
0xa09c  ldstr    aName// "name"
0xa0a1  ldarg.1
0xa0a2  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_SchemaName()
0xa0a7  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0xa0ac  ldloc.0
0xa0ad  ldstr    aExternalname// "externalname"
0xa0b2  ldarg.1
0xa0b3  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_ExternalName()
0xa0b8  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0xa0bd  ldloc.0
0xa0be  ldstr    aExternalcollec// "externalcollectionname"
0xa0c3  ldarg.1
0xa0c4  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_ExternalCollectionName()
0xa0c9  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0xa0ce  ldloc.0
0xa0cf  ldstr    aEntityhelpurl// "entityhelpurl"
0xa0d4  ldarg.1
0xa0d5  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_EntityHelpUrl()
0xa0da  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0xa0df  ldloc.0
0xa0e0  ldstr    aIconlargename// "iconlargename"
0xa0e5  ldarg.1
0xa0e6  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_IconLargeName()
0xa0eb  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0xa0f0  ldloc.0
0xa0f1  ldstr    aIconmediumname// "iconmediumname"
0xa0f6  ldarg.1
0xa0f7  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_IconMediumName()
0xa0fc  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0xa101  ldloc.0
0xa102  ldstr    aIconsmallname// "iconsmallname"
0xa107  ldarg.1
0xa108  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_IconSmallName()
0xa10d  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0xa112  ldloc.0
0xa113  ldstr    aIconvectorname// "iconvectorname"
0xa118  ldarg.1
0xa119  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_IconVectorName()
0xa11e  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0xa123  ldloc.0
0xa124  ldstr    aEntitycolor// "entitycolor"
0xa129  ldarg.1
0xa12a  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_EntityColor()
0xa12f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0xa134  ldarg.1
0xa135  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_EntitySetName()
0xa13a  brfalse.s loc_A152
0xa13c  ldloc.0
0xa13d  ldstr    aEntitysetname// "entitysetname"
0xa142  ldarg.1
0xa143  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_EntitySetName()
0xa148  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0xa14d  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0xa152  ldarg.1
0xa153  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BooleanManagedProperty [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_IsDuplicateDetectionEnabled()
0xa158  brfalse.s loc_A175
0xa15a  ldloc.0
0xa15b  ldstr    aIsduplicateche// "isduplicatechecksupported"
0xa160  ldarg.1
0xa161  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BooleanManagedProperty [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_IsDuplicateDetectionEnabled()
0xa166  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ManagedProperty`1<bool>::get_Value()
0xa16b  box      [mscorlib]System.Boolean
0xa170  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0xa175  ldarg.1
0xa176  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BooleanManagedProperty [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_IsValidForQueue()
0xa17b  brfalse.s loc_A198
0xa17d  ldloc.0
0xa17e  ldstr    aIscollaboratio// "iscollaboration"
0xa183  ldarg.1
0xa184  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BooleanManagedProperty [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_IsValidForQueue()
0xa189  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ManagedProperty`1<bool>::get_Value()
0xa18e  box      [mscorlib]System.Boolean
0xa193  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0xa198  ldarg.1
0xa199  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_AutoRouteToOwnerQueue()
0xa19e  stloc.3
0xa19f  ldloca.s 3
0xa1a1  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xa1a6  brfalse.s loc_A1D6
0xa1a8  ldarg.1
0xa1a9  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_AutoRouteToOwnerQueue()
0xa1ae  stloc.3
0xa1af  ldloca.s 3
0xa1b1  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xa1b6  brfalse.s loc_A1D6
0xa1b8  ldloc.0
0xa1b9  ldstr    aAutoroutetoown// "autoroutetoownerqueue"
0xa1be  ldarg.1
0xa1bf  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_AutoRouteToOwnerQueue()
0xa1c4  stloc.3
0xa1c5  ldloca.s 3
0xa1c7  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0xa1cc  box      [mscorlib]System.Boolean
0xa1d1  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0xa1d6  ldarg.1
0xa1d7  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BooleanManagedProperty [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_IsConnectionsEnabled()
0xa1dc  brfalse.s loc_A1F9
0xa1de  ldloc.0
0xa1df  ldstr    aIsconnectionse// "isconnectionsenabled"
0xa1e4  ldarg.1
0xa1e5  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BooleanManagedProperty [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_IsConnectionsEnabled()
0xa1ea  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ManagedProperty`1<bool>::get_Value()
0xa1ef  box      [mscorlib]System.Boolean
0xa1f4  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0xa1f9  ldarg.1
0xa1fa  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BooleanManagedProperty [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_IsMailMergeEnabled()
0xa1ff  brfalse.s loc_A21C
0xa201  ldloc.0
0xa202  ldstr    aIsmailmergeena// "ismailmergeenabled"
0xa207  ldarg.1
0xa208  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BooleanManagedProperty [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_IsMailMergeEnabled()
0xa20d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ManagedProperty`1<bool>::get_Value()
0xa212  box      [mscorlib]System.Boolean
0xa217  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0xa21c  ldarg.1
0xa21d  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BooleanManagedProperty [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_IsAuditEnabled()
0xa222  brfalse.s loc_A23F
0xa224  ldloc.0
0xa225  ldstr    aIsauditenabled// "isauditenabled"
0xa22a  ldarg.1
0xa22b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BooleanManagedProperty [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_IsAuditEnabled()
0xa230  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ManagedProperty`1<bool>::get_Value()
0xa235  box      [mscorlib]System.Boolean
0xa23a  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0xa23f  ldsfld   class [mscorlib]System.Version [Microsoft.Crm]Microsoft.Crm.CrmVersions::CarinaVersion
0xa244  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.VersionUtility::IsCarinaVersion(class [mscorlib]System.Version)
0xa249  brfalse.s loc_A279
0xa24b  ldarg.1
0xa24c  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_ChangeTrackingEnabled()
0xa251  stloc.3
0xa252  ldloca.s 3
0xa254  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xa259  brfalse.s loc_A279
0xa25b  ldloc.0
0xa25c  ldstr    aChangetracking// "changetrackingenabled"
0xa261  ldarg.1
0xa262  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_ChangeTrackingEnabled()
0xa267  stloc.3
0xa268  ldloca.s 3
0xa26a  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0xa26f  box      [mscorlib]System.Boolean
0xa274  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0xa279  ldsfld   class [mscorlib]System.Version [Microsoft.Crm]Microsoft.Crm.CrmVersions::CarinaVersion
0xa27e  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.VersionUtility::IsCarinaVersion(class [mscorlib]System.Version)
0xa283  brfalse.s loc_A2A8
0xa285  ldarg.1
0xa286  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BooleanManagedProperty [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_CanChangeTrackingBeEnabled()
0xa28b  brfalse.s loc_A2A8
0xa28d  ldloc.0
0xa28e  ldstr    aCanchangetrack// "canchangetrackingbeenabled"
0xa293  ldarg.1
0xa294  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BooleanManagedProperty [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_CanChangeTrackingBeEnabled()
0xa299  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ManagedProperty`1<bool>::get_Value()
0xa29e  box      [mscorlib]System.Boolean
0xa2a3  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0xa2a8  ldarg.1
0xa2a9  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BooleanManagedProperty [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_IsVisibleInMobile()
0xa2ae  brfalse.s loc_A2CB
0xa2b0  ldloc.0
0xa2b1  ldstr    aIsvisibleinmob// "isvisibleinmobile"
0xa2b6  ldarg.1
0xa2b7  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BooleanManagedProperty [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_IsVisibleInMobile()
0xa2bc  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ManagedProperty`1<bool>::get_Value()
0xa2c1  box      [mscorlib]System.Boolean
0xa2c6  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0xa2cb  ldarg.1
0xa2cc  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BooleanManagedProperty [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_IsVisibleInMobileClient()
0xa2d1  brfalse.s loc_A2EE
0xa2d3  ldloc.0
0xa2d4  ldstr    aIsvisibleinmob_0// "isvisibleinmobileclient"
0xa2d9  ldarg.1
0xa2da  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BooleanManagedProperty [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_IsVisibleInMobileClient()
0xa2df  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ManagedProperty`1<bool>::get_Value()
0xa2e4  box      [mscorlib]System.Boolean
0xa2e9  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0xa2ee  ldarg.1
0xa2ef  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BooleanManagedProperty [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_IsReadOnlyInMobileClient()
0xa2f4  brfalse.s loc_A311
0xa2f6  ldloc.0
0xa2f7  ldstr    aIsreadonlyinmo// "isreadonlyinmobileclient"
0xa2fc  ldarg.1
0xa2fd  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BooleanManagedProperty [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_IsReadOnlyInMobileClient()
0xa302  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ManagedProperty`1<bool>::get_Value()
0xa307  box      [mscorlib]System.Boolean
0xa30c  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0xa311  ldarg.1
0xa312  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BooleanManagedProperty [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_IsOfflineInMobileClient()
0xa317  brfalse.s loc_A334
0xa319  ldloc.0
0xa31a  ldstr    aIsofflineinmob// "isofflineinmobileclient"
0xa31f  ldarg.1
0xa320  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BooleanManagedProperty [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_IsOfflineInMobileClient()
0xa325  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ManagedProperty`1<bool>::get_Value()
0xa32a  box      [mscorlib]System.Boolean
0xa32f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0xa334  ldarg.1
0xa335  callvirt instance valuetype [mscorlib]System.Nullable`1<int32> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_DaysSinceRecordLastModified()
0xa33a  stloc.s  4
0xa33c  ldloca.s 4
0xa33e  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0xa343  brfalse.s loc_A364
0xa345  ldloc.0
0xa346  ldstr    aDayssincerecor// "dayssincerecordlastmodified"
0xa34b  ldarg.1
0xa34c  callvirt instance valuetype [mscorlib]System.Nullable`1<int32> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_DaysSinceRecordLastModified()
0xa351  stloc.s  4
0xa353  ldloca.s 4
0xa355  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0xa35a  box      [mscorlib]System.Int32
0xa35f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0xa364  ldarg.1
0xa365  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_MobileOfflineFilters()
0xa36a  brfalse.s loc_A37D
0xa36c  ldloc.0
0xa36d  ldstr    aMobileofflinef// "mobileofflinefilters"
0xa372  ldarg.1
0xa373  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_MobileOfflineFilters()
0xa378  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0xa37d  ldarg.1
0xa37e  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_IsAvailableOffline()
0xa383  stloc.3
0xa384  ldloca.s 3
0xa386  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xa38b  brfalse.s loc_A3E9
0xa38d  ldloc.0
0xa38e  ldstr    aIsreplicated// "isreplicated"
0xa393  ldarg.1
0xa394  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_IsAvailableOffline()
0xa399  stloc.3
0xa39a  ldloca.s 3
0xa39c  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0xa3a1  box      [mscorlib]System.Boolean
0xa3a6  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0xa3ab  ldarg.1
0xa3ac  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_IsCustomEntity()
0xa3b1  stloc.3
0xa3b2  ldloca.s 3
0xa3b4  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xa3b9  brfalse.s loc_A3E9
0xa3bb  ldarg.1
0xa3bc  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_IsCustomEntity()
0xa3c1  stloc.3
0xa3c2  ldloca.s 3
0xa3c4  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0xa3c9  brfalse.s loc_A3E9
0xa3cb  ldloc.0
0xa3cc  ldstr    aIsreplicationu// "isreplicationuserfiltered"
  ... truncated ...
```
