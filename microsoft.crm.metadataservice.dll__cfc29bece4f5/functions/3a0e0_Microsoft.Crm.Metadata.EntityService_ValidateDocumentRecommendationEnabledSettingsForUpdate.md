# Microsoft.Crm.Metadata.EntityService::ValidateDocumentRecommendationEnabledSettingsForUpdate

- ea: `0x3a0e0`
- end: `0x3a249`
- name: `Microsoft.Crm.Metadata.EntityService::ValidateDocumentRecommendationEnabledSettingsForUpdate`
- size: `361`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x39620`

## callees

- `0x360b0`
- `0x3a0e0`
- `0x3ce20`
- `0x3cf40`
- `0x3cf60`
- `0x3d7b0`

## string_xrefs

- `0x3a0eb`: `isdocumentrecommendationsenabled`
- `0x3a101`: `isdocumentrecommendationsenabled`
- `0x3a10e`: `isdocumentrecommendationsenabled`

## pseudocode

```c

```

## disassembly

```asm
0x3a0e0  ldarg.1
0x3a0e1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag Microsoft.Crm.Metadata.EntityUpdateInfo::get_EntityDescription()
0x3a0e6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag::get_InnerEntityData()
0x3a0eb  ldstr    aIsdocumentreco// "isdocumentrecommendationsenabled"
0x3a0f0  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNullOrNameInvalid(string)
0x3a0f5  brtrue.s loc_3A0FF
0x3a0f7  ldarg.1
0x3a0f8  callvirt instance bool Microsoft.Crm.Metadata.EntityUpdateInfo::get_IsDocumentRecommendationsEnabled()
0x3a0fd  br.s     loc_3A100
0x3a0ff  ldc.i4.0
0x3a100  ldarg.2
0x3a101  ldstr    aIsdocumentreco// "isdocumentrecommendationsenabled"
0x3a106  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNullOrNameInvalid(string)
0x3a10b  brtrue.s loc_3A11F
0x3a10d  ldarg.2
0x3a10e  ldstr    aIsdocumentreco// "isdocumentrecommendationsenabled"
0x3a113  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x3a118  unbox.any [mscorlib]System.Boolean
0x3a11d  br.s     loc_3A120
0x3a11f  ldc.i4.0
0x3a120  stloc.0
0x3a121  brfalse  loc_3A248
0x3a126  ldloc.0
0x3a127  brtrue   loc_3A248
0x3a12c  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x3a131  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x3a136  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_DocumentRecommendations()
0x3a13b  ldarg.3
0x3a13c  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3a141  brtrue.s loc_3A153
0x3a143  ldstr    aTheDocumentSug// "The document suggestions feature is not"...
0x3a148  ldc.i4   0x80071019
0x3a14d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x3a152  throw
0x3a153  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x3a158  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x3a15d  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_SharePointS2S()
0x3a162  ldarg.3
0x3a163  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3a168  brtrue.s loc_3A17A
0x3a16a  ldstr    aSharepointServ// "SharePoint server-based SharePoint inte"...
0x3a16f  ldc.i4   0x80071017
0x3a174  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x3a179  throw
0x3a17a  ldarg.1
0x3a17b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag Microsoft.Crm.Metadata.EntityUpdateInfo::get_EntityDescription()
0x3a180  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag::get_InnerEntityData()
0x3a185  ldstr    aIsdocumentmana// "isdocumentmanagementenabled"
0x3a18a  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x3a18f  brtrue.s loc_3A1A9
0x3a191  ldarg.1
0x3a192  callvirt instance bool Microsoft.Crm.Metadata.EntityUpdateInfo::get_IsDocumentManagementEnabled()
0x3a197  brtrue.s loc_3A1DB
0x3a199  ldstr    aDocumentManage// "Document management not enabled for thi"...
0x3a19e  ldc.i4   0x80071011
0x3a1a3  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x3a1a8  throw
0x3a1a9  ldarg.2
0x3a1aa  ldstr    aIsdocumentmana// "isdocumentmanagementenabled"
0x3a1af  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x3a1b4  brtrue.s loc_3A1C8
0x3a1b6  ldarg.2
0x3a1b7  ldstr    aIsdocumentmana// "isdocumentmanagementenabled"
0x3a1bc  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x3a1c1  unbox.any [mscorlib]System.Boolean
0x3a1c6  br.s     loc_3A1C9
0x3a1c8  ldc.i4.0
0x3a1c9  brtrue.s loc_3A1DB
0x3a1cb  ldstr    aDocumentManage// "Document management not enabled for thi"...
0x3a1d0  ldc.i4   0x80071011
0x3a1d5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x3a1da  throw
0x3a1db  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x3a1e0  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x3a1e5  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_AdvancedSimilaritySearch()
0x3a1ea  ldarg.3
0x3a1eb  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3a1f0  brtrue.s loc_3A202
0x3a1f2  ldstr    aSimilarityRule// "Similarity rules not enabled."
0x3a1f7  ldc.i4   0x80071018
0x3a1fc  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x3a201  throw
0x3a202  ldarg.0
0x3a203  ldarg.1
0x3a204  ldarg.3
0x3a205  call     instance bool Microsoft.Crm.Metadata.EntityService::IsActiveSimilarityRuleAvailableForEntityForUpdate(class Microsoft.Crm.Metadata.EntityUpdateInfo entityInfo, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3a20a  brtrue.s loc_3A21C
0x3a20c  ldstr    aNoSimilarityRu// "No similarity rule active for this enti"...
0x3a211  ldc.i4   0x80071016
0x3a216  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x3a21b  throw
0x3a21c  ldarg.1
0x3a21d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag Microsoft.Crm.Metadata.EntityUpdateInfo::get_EntityDescription()
0x3a222  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_IsCustomEntity()
0x3a227  brtrue.s loc_3A231
0x3a229  ldarg.1
0x3a22a  callvirt instance string Microsoft.Crm.Metadata.EntityUpdateInfo::get_LogicalName()
0x3a22f  br.s     loc_3A236
0x3a231  ldstr    aCustomEntity// "Custom Entity"
0x3a236  stloc.1
0x3a237  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SharePointEventSource [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SharePointEventSource::get_Instance()
0x3a23c  ldarg.3
0x3a23d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x3a242  ldloc.1
0x3a243  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SharePointEventSource::LogDocRecEnabled(valuetype [mscorlib]System.Guid, string)
0x3a248  ret
```
