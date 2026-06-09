# Microsoft.Crm.Metadata.EntityService::DeleteInternal

- ea: `0x31b10`
- end: `0x32082`
- name: `Microsoft.Crm.Metadata.EntityService::DeleteInternal`
- size: `1394`
- prototype: ``
- caller_count: `1`
- callee_count: `26`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x76780`

## callees

- `0x29080`
- `0x2fff0`
- `0x31070`
- `0x31b10`
- `0x32090`
- `0x321e0`
- `0x35880`
- `0x358b0`
- `0x358d0`
- `0x35900`
- `0x35980`
- `0x362e0`
- `0x36350`
- `0x36570`
- `0x36840`
- `0x36870`
- `0x36880`
- `0x36ac0`
- `0x36c60`
- `0x36c90`
- `0x59c60`
- `0x5a810`
- `0x5ab50`
- `0x64e20`
- `0x69510`
- `0x69650`

## string_xrefs

- `0x31bec`: `autocreateaccessteams`
- `0x31e44`: `autocreateaccessteams`
- `0x31e52`: `autocreateaccessteams`
- `0x31ca5`: `DeleteEntity`
- `0x31caa`: `DeleteEntity`
- `0x32035`: `EntityService.Update caught exception: {0}`
- `0x31b49`: `prvDeleteEntity`

## pseudocode

```c

```

## disassembly

```asm
0x31b10  ldarg.1
0x31b11  ldstr    aEntityid_0// "entityId"
0x31b16  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x31b1b  ldarg.2
0x31b1c  ldstr    aMetadatahelper// "metadataHelper"
0x31b21  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x31b26  ldarg.s  4
0x31b28  ldstr    aContext// "context"
0x31b2d  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x31b32  ldarg.s  4
0x31b34  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x31b39  pop
0x31b3a  ldarg.0
0x31b3b  ldarg.s  4
0x31b3d  call     instance void Microsoft.Crm.Metadata.EntityService::PreloadSecurityCaches(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x31b42  ldarg.s  4
0x31b44  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x31b49  ldstr    aPrvdeleteentit_0// "prvDeleteEntity"
0x31b4e  ldarg.s  4
0x31b50  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.CustomizationSecurityCache::GetPrivilegeIdFromName(string privilegeName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x31b55  ldarg.s  4
0x31b57  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGlobalDepth(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x31b5c  ldarg.s  4
0x31b5e  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::StartTransactionIfRequired()
0x31b63  stloc.0
0x31b64  ldc.i4.0
0x31b65  stloc.1
0x31b66  ldstr    asc_804C0// ""
0x31b6b  stloc.2
0x31b6c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0x31b71  stloc.3
0x31b72  ldarg.s  4
0x31b74  ldc.i4.1
0x31b75  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.AutoAddRootsContextModifier::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, valuetype [Microsoft.Crm.Core]Microsoft.Crm.AddRootsOption)
0x31b7a  stloc.s  4
0x31b7c  ldarg.s  4
0x31b7e  ldc.i4.1
0x31b7f  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, bool)
0x31b84  stloc.s  5
0x31b86  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x31b8b  ldarg.1
0x31b8c  ldstr    aEntity_0// "Entity"
0x31b91  ldc.i4.s 0x10
0x31b93  newarr   [mscorlib]System.String
0x31b98  dup
0x31b99  ldc.i4.0
0x31b9a  ldstr    aIsactivity// "isactivity"
0x31b9f  stelem.ref
0x31ba0  dup
0x31ba1  ldc.i4.1
0x31ba2  ldstr    aIscustomentity// "iscustomentity"
0x31ba7  stelem.ref
0x31ba8  dup
0x31ba9  ldc.i4.2
0x31baa  ldstr    aIsintersect// "isintersect"
0x31baf  stelem.ref
0x31bb0  dup
0x31bb1  ldc.i4.3
0x31bb2  ldstr    aLogicalname// "logicalname"
0x31bb7  stelem.ref
0x31bb8  dup
0x31bb9  ldc.i4.4
0x31bba  ldstr    aPhysicalname// "physicalname"
0x31bbf  stelem.ref
0x31bc0  dup
0x31bc1  ldc.i4.5
0x31bc2  ldstr    aObjecttypecode_0// "objecttypecode"
0x31bc7  stelem.ref
0x31bc8  dup
0x31bc9  ldc.i4.6
0x31bca  ldstr    aSolutionid// "solutionid"
0x31bcf  stelem.ref
0x31bd0  dup
0x31bd1  ldc.i4.7
0x31bd2  ldstr    aIsactivitypart// "isactivityparty"
0x31bd7  stelem.ref
0x31bd8  dup
0x31bd9  ldc.i4.8
0x31bda  ldstr    aName// "name"
0x31bdf  stelem.ref
0x31be0  dup
0x31be1  ldc.i4.s 9
0x31be3  ldstr    aOwnershiptypem// "ownershiptypemask"
0x31be8  stelem.ref
0x31be9  dup
0x31bea  ldc.i4.s 0xA
0x31bec  ldstr    aAutocreateacce// "autocreateaccessteams"
0x31bf1  stelem.ref
0x31bf2  dup
0x31bf3  ldc.i4.s 0xB
0x31bf5  ldstr    aIsofflineinmob// "isofflineinmobileclient"
0x31bfa  stelem.ref
0x31bfb  dup
0x31bfc  ldc.i4.s 0xC
0x31bfe  ldstr    aIsslaenabled// "isslaenabled"
0x31c03  stelem.ref
0x31c04  dup
0x31c05  ldc.i4.s 0xD
0x31c07  ldstr    aIsbpfentity// "isbpfentity"
0x31c0c  stelem.ref
0x31c0d  dup
0x31c0e  ldc.i4.s 0xE
0x31c10  ldstr    aDataproviderid// "dataproviderid"
0x31c15  stelem.ref
0x31c16  dup
0x31c17  ldc.i4.s 0xF
0x31c19  ldstr    aDatasourceid// "datasourceid"
0x31c1e  stelem.ref
0x31c1f  ldarg.s  4
0x31c21  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x31c26  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::RetrieveMetadataEntity(valuetype [mscorlib]System.Guid, string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x31c2b  stloc.s  6
0x31c2d  ldarg.0
0x31c2e  ldarg.1
0x31c2f  ldarg.s  4
0x31c31  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection Microsoft.Crm.Metadata.EntityService::GetPublishedSecuredAttributes(valuetype [mscorlib]System.Guid entityId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x31c36  stloc.s  7
0x31c38  ldloc.s  6
0x31c3a  ldstr    aObjecttypecode_0// "objecttypecode"
0x31c3f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x31c44  unbox.any [mscorlib]System.Int32
0x31c49  stloc.s  8
0x31c4b  ldloc.s  6
0x31c4d  ldstr    aLogicalname// "logicalname"
0x31c52  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x31c57  castclass [mscorlib]System.String
0x31c5c  stloc.s  9
0x31c5e  ldloc.s  6
0x31c60  ldstr    aIsactivity// "isactivity"
0x31c65  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x31c6a  brtrue.s loc_31C7F
0x31c6c  ldloc.s  6
0x31c6e  ldstr    aIsactivity// "isactivity"
0x31c73  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x31c78  unbox.any [mscorlib]System.Boolean
0x31c7d  br.s     loc_31C80
0x31c7f  ldc.i4.0
0x31c80  stloc.s  0xA
0x31c82  ldloc.s  6
0x31c84  ldstr    aLogicalname// "logicalname"
0x31c89  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x31c8e  castclass [mscorlib]System.String
0x31c93  ldarg.s  4
0x31c95  call     void Microsoft.Crm.Metadata.SiteMapHelper::RemoveEntityFromSiteMap(string entityName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x31c9a  ldarg.0
0x31c9b  ldloc.s  6
0x31c9d  ldarg.s  4
0x31c9f  call     instance void Microsoft.Crm.Metadata.EntityService::ValidateForDelete(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity entity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x31ca4  ldarg.1
0x31ca5  ldstr    aDeleteentity// "DeleteEntity"
0x31caa  ldstr    aDeleteentity// "DeleteEntity"
0x31caf  ldc.i4.0
0x31cb0  ldarg.s  4
0x31cb2  call     void Microsoft.Crm.Metadata.AuditHelper::InvokeAuditMetadataPlugin(valuetype [mscorlib]System.Guid targetId, string messageName, string requestName, bool isAuditEnabled, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x31cb7  ldarg.0
0x31cb8  ldloc.s  6
0x31cba  ldarg.s  4
0x31cbc  call     instance void Microsoft.Crm.Metadata.EntityService::DeleteInvalidRules(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity entity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x31cc1  ldloc.s  8
0x31cc3  ldarg.s  4
0x31cc5  call     void Microsoft.Crm.Metadata.EntityService::DeleteDocumentTemplates(int32 objectTypeCode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x31cca  ldarg.0
0x31ccb  ldloc.s  8
0x31ccd  ldarg.s  4
0x31ccf  call     instance void Microsoft.Crm.Metadata.EntityService::DeleteBusinessRules(int32 objectTypeCode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x31cd4  ldarg.0
0x31cd5  ldloc.s  8
0x31cd7  ldarg.s  4
0x31cd9  call     instance void Microsoft.Crm.Metadata.EntityService::DeleteRollupProperties(int32 objectTypeCode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x31cde  ldloc.s  6
0x31ce0  ldstr    aDataproviderid// "dataproviderid"
0x31ce5  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x31cea  brfalse.s loc_31CF6
0x31cec  ldloc.s  8
0x31cee  ldarg.s  4
0x31cf0  call     bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.CascadeEngine::DeleteAll(int32, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x31cf5  pop
0x31cf6  ldarg.0
0x31cf7  ldloc.s  6
0x31cf9  ldarg.2
0x31cfa  ldarg.s  4
0x31cfc  call     instance void Microsoft.Crm.Metadata.EntityService::DeleteRelationships(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity entity, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper helper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x31d01  ldarg.0
0x31d02  ldloc.s  8
0x31d04  ldarg.s  4
0x31d06  call     instance void Microsoft.Crm.Metadata.EntityService::CancelIncompleteSystemJobs(int32 objectTypeCode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x31d0b  ldarg.0
0x31d0c  ldloc.s  9
0x31d0e  ldarg.s  4
0x31d10  call     instance void Microsoft.Crm.Metadata.EntityService::DeleteEntityMaps(string entityLogicalName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x31d15  ldarg.0
0x31d16  ldloc.s  8
0x31d18  ldarg.s  4
0x31d1a  call     instance void Microsoft.Crm.Metadata.EntityService::DeleteUIData(int32 objectTypeCode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x31d1f  ldarg.0
0x31d20  ldloc.s  9
0x31d22  ldarg.s  4
0x31d24  call     instance void Microsoft.Crm.Metadata.EntityService::DeleteMultiEntitySearchConfiguration(string logicalName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x31d29  ldloc.s  6
0x31d2b  ldstr    aIscustomentity// "iscustomentity"
0x31d30  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x31d35  brtrue.s loc_31D68
0x31d37  ldloc.s  6
0x31d39  ldstr    aIscustomentity// "iscustomentity"
0x31d3e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x31d43  unbox.any [mscorlib]System.Boolean
0x31d48  brfalse.s loc_31D68
0x31d4a  ldloc.s  6
0x31d4c  ldstr    aDataproviderid// "dataproviderid"
0x31d51  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x31d56  ldc.i4.0
0x31d57  ceq
0x31d59  stloc.s  0xD
0x31d5b  ldloc.s  8
0x31d5d  ldloc.s  0xA
0x31d5f  ldloc.s  0xD
0x31d61  ldarg.s  4
0x31d63  call     void Microsoft.Crm.Metadata.SecurityHelper::DeleteEntityHelper(int32 objectTypeCode, bool isEntityActivity, bool isEntityVirtual, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x31d68  ldarg.s  4
0x31d6a  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x31d6f  stloc.s  0xB
0x31d71  ldloc.s  0xB
0x31d73  ldarg.1
0x31d74  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::set_EntityId(valuetype [mscorlib]System.Guid)
0x31d79  ldloc.s  0xB
0x31d7b  ldloc.s  6
0x31d7d  ldstr    aDataproviderid// "dataproviderid"
0x31d82  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x31d87  brtrue.s loc_31D9C
0x31d89  ldloc.s  6
0x31d8b  ldstr    aDataproviderid// "dataproviderid"
0x31d90  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x31d95  unbox.any valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x31d9a  br.s     loc_31DA6
0x31d9c  ldloca.s 0xE
0x31d9e  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x31da4  ldloc.s  0xE
0x31da6  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::set_DataProviderId(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>)
0x31dab  ldloc.s  0xB
0x31dad  ldloc.s  6
0x31daf  ldstr    aDatasourceid// "datasourceid"
0x31db4  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x31db9  brtrue.s loc_31DCE
0x31dbb  ldloc.s  6
0x31dbd  ldstr    aDatasourceid// "datasourceid"
0x31dc2  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x31dc7  unbox.any valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x31dcc  br.s     loc_31DD8
0x31dce  ldloca.s 0xE
0x31dd0  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x31dd6  ldloc.s  0xE
0x31dd8  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::set_DataSourceId(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>)
0x31ddd  ldloc.s  0xB
0x31ddf  ldloc.s  8
0x31de1  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::set_ObjectTypeCode(int32)
0x31de6  ldarg.2
0x31de7  ldloc.s  0xB
0x31de9  ldc.i4.2
0x31dea  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::AddToQueue(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription, valuetype [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.ActionType)
0x31def  ldarg.0
0x31df0  ldloc.s  7
0x31df2  ldarg.2
0x31df3  ldloc.s  8
0x31df5  ldarg.s  4
0x31df7  call     instance void Microsoft.Crm.Metadata.EntityService::DeleteSecuredAttributes(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection securedAttributes, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, int32 objectTypeCode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x31dfc  ldarg.2
0x31dfd  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::ProcessQueue()
0x31e02  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionComponentService::.ctor()
0x31e07  ldarg.1
0x31e08  ldloc.s  6
0x31e0a  ldstr    aSolutionid// "solutionid"
0x31e0f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x31e14  unbox.any [mscorlib]System.Guid
0x31e19  ldarg.s  4
0x31e1b  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionComponentService::RemoveAllSubcomponentsOfRootByObjectId(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x31e20  ldarg.1
0x31e21  ldc.i4.1
0x31e22  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Solution.SolutionComponentMoniker::.ctor(valuetype [mscorlib]System.Guid, int32)
0x31e27  ldarg.s  4
0x31e29  call     void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionComponentHelper::DeleteFromAllSolutions(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Solution.SolutionComponentMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x31e2e  ldarg.0
0x31e2f  ldloc.s  8
0x31e31  ldarg.s  4
0x31e33  call     instance void Microsoft.Crm.Metadata.EntityService::DeleteReplication(int32 objectTypeCode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x31e38  ldarg.0
0x31e39  ldloc.s  8
0x31e3b  ldarg.s  4
0x31e3d  call     instance void Microsoft.Crm.Metadata.EntityService::DeleteEntityRelatedObjects(int32 objectTypeCode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x31e42  ldloc.s  6
0x31e44  ldstr    aAutocreateacce// "autocreateaccessteams"
0x31e49  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x31e4e  brtrue.s loc_31E6D
0x31e50  ldloc.s  6
0x31e52  ldstr    aAutocreateacce// "autocreateaccessteams"
0x31e57  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x31e5c  unbox.any [mscorlib]System.Boolean
0x31e61  brfalse.s loc_31E6D
0x31e63  ldarg.0
0x31e64  ldloc.s  8
0x31e66  ldarg.s  4
  ... truncated ...
```
