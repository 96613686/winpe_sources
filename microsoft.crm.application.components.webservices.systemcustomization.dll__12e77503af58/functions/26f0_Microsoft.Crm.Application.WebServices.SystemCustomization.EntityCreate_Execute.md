# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::Execute

- ea: `0x26f0`
- end: `0x290e`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::Execute`
- size: `542`
- prototype: ``
- caller_count: `3`
- callee_count: `34`
- tags: `service_task, broker_com_uri`

## callers

- `0x5ed0`
- `0xadc0`
- `0xb020`

## callees

- `0x190`
- `0x1a0`
- `0x2b0`
- `0x330`
- `0x26f0`
- `0x2910`
- `0x2a00`
- `0x2ab0`
- `0x2ad0`
- `0x2b10`
- `0x2b70`
- `0x2b90`
- `0x2bd0`
- `0x2bf0`
- `0x2c10`
- `0x2c30`
- `0x2c60`
- `0x2cb0`
- `0x2cd0`
- `0x2cf0`
- `0x2d10`
- `0x2d80`
- `0x2dc0`
- `0x2e00`
- `0x2e20`
- `0x2e40`
- `0x2e60`
- `0x2e80`
- `0x2ef0`
- `0x2f10`
- `0x2f30`
- `0x2f50`
- `0x2fc0`
- `0x2fe0`

## pseudocode

```c

```

## disassembly

```asm
0x26f0  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.Organization::get_CurrentSettings()
0x26f5  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.OrganizationFeature::CreateCustomEntity
0x26fa  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::IsFeatureDisabled(valuetype [mscorlib]System.Guid)
0x26ff  brfalse.s loc_2712
0x2701  ldc.i4   0x8004B042
0x2706  ldc.i4.0
0x2707  newarr   [mscorlib]System.Object
0x270c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x2711  throw
0x2712  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_CreateEntity()
0x2717  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x271c  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2721  brtrue.s loc_2734
0x2723  ldc.i4   0x80040277
0x2728  ldc.i4.0
0x2729  newarr   [mscorlib]System.Object
0x272e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x2733  throw
0x2734  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2739  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x273e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x2743  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2748  stloc.0
0x2749  ldloc.0
0x274a  ldarg.1
0x274b  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetSchemaParams(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo entityInfo, class Microsoft.Crm.Application.WebServices.ParameterBag parameterBag)
0x2750  ldloc.0
0x2751  ldarg.1
0x2752  ldstr    aDisplayareas// "displayareas"
0x2757  callvirt instance class Microsoft.Crm.Application.WebServices.ParameterBag Microsoft.Crm.Application.WebServices.ParameterBag::GetBag(string name)
0x275c  call     class [mscorlib]System.Collections.IDictionary Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetDisplayAreaParams(class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x2761  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo::set_DisplayAreas(class [mscorlib]System.Collections.IDictionary)
0x2766  ldloc.0
0x2767  ldarg.1
0x2768  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetEntityColor(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo entityInfo, class Microsoft.Crm.Application.WebServices.ParameterBag parameterBag)
0x276d  ldloc.0
0x276e  ldarg.1
0x276f  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetActivityParams(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo entityInfo, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x2774  ldloc.0
0x2775  ldarg.1
0x2776  ldstr    aRichclient// "richclient"
0x277b  callvirt instance class Microsoft.Crm.Application.WebServices.ParameterBag Microsoft.Crm.Application.WebServices.ParameterBag::GetBag(string name)
0x2780  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetRichClientParams(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo entityInfo, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x2785  ldloc.0
0x2786  ldarg.1
0x2787  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetMailMergeParams(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo entityInfo, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x278c  ldloc.0
0x278d  ldarg.1
0x278e  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetDuplicateDetectionParams(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo entityInfo, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x2793  ldloc.0
0x2794  ldarg.1
0x2795  ldstr    aAssociatedenti// "associatedentity"
0x279a  callvirt instance class Microsoft.Crm.Application.WebServices.ParameterBag Microsoft.Crm.Application.WebServices.ParameterBag::GetBag(string name)
0x279f  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetAssociatedEntityParams(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo entityInfo, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x27a4  ldloc.0
0x27a5  ldarg.1
0x27a6  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetConnectionsParams(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo entityInfo, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x27ab  ldloc.0
0x27ac  ldarg.1
0x27ad  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetBusinessProcessParams(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo entityInfo, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x27b2  ldloc.0
0x27b3  ldarg.1
0x27b4  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetInteractionCentricParams(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo entityInfo, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x27b9  ldloc.0
0x27ba  ldarg.1
0x27bb  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetAuditParams(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo entityInfo, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x27c0  ldloc.0
0x27c1  ldarg.1
0x27c2  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetChangeTrackingParams(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo entityInfo, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x27c7  ldloc.0
0x27c8  ldarg.1
0x27c9  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetDocumentManagementParams(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo entityInfo, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x27ce  ldloc.0
0x27cf  ldarg.1
0x27d0  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetVirtualEntityParams(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo entityInfo, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x27d5  ldloc.0
0x27d6  ldarg.1
0x27d7  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetExternalNameParams(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo entityInfo, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x27dc  ldloc.0
0x27dd  ldarg.1
0x27de  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetExternalCollectionNameParams(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo entityInfo, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x27e3  ldloc.0
0x27e4  ldarg.1
0x27e5  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetOneNoteIntegrationParams(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo entityInfo, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x27ea  ldloc.0
0x27eb  ldarg.1
0x27ec  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetKnowledgeManagementParams(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo entityInfo, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x27f1  ldloc.0
0x27f2  ldarg.1
0x27f3  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetDocumentRecommendationParams(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo entityInfo, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x27f8  ldloc.0
0x27f9  ldarg.1
0x27fa  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetAutoCreateAccessTeamsParams(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo entityInfo, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x27ff  ldloc.0
0x2800  ldarg.1
0x2801  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetCollaborationParams(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo entityInfo, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x2806  ldloc.0
0x2807  ldarg.1
0x2808  ldstr    aAttribute// "attribute"
0x280d  callvirt instance class Microsoft.Crm.Application.WebServices.ParameterBag Microsoft.Crm.Application.WebServices.ParameterBag::GetBag(string name)
0x2812  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetAttributeParams(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo entityInfo, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x2817  ldloc.0
0x2818  ldarg.1
0x2819  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetMobileParams(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo entityInfo, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x281e  ldloc.0
0x281f  ldarg.1
0x2820  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetReadingPaneParams(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo entityInfo, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x2825  ldloc.0
0x2826  ldarg.1
0x2827  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetQuickCreateParams(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo entityInfo, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x282c  ldloc.0
0x282d  ldarg.1
0x282e  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetCustomHelpParams(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo entityInfo, class Microsoft.Crm.Application.WebServices.ParameterBag parameterBag)
0x2833  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2838  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsSLAFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x283d  brfalse.s loc_2846
0x283f  ldloc.0
0x2840  ldarg.1
0x2841  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetSlaParams(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo entityInfo, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x2846  ldloc.0
0x2847  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OwnershipTypes [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo::get_OwnershipTypeMask()
0x284c  ldc.i4.1
0x284d  bne.un.s loc_2858
0x284f  ldloc.0
0x2850  ldc.i4.1
0x2851  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo::set_IsHSMEnabled(bool)
0x2856  br.s     loc_285F
0x2858  ldloc.0
0x2859  ldc.i4.0
0x285a  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo::set_IsHSMEnabled(bool)
0x285f  ldloc.0
0x2860  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo::get_DataProviderId()
0x2865  stloc.2
0x2866  ldloca.s 2
0x2868  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x286d  brfalse.s loc_287D
0x286f  ldloc.0
0x2870  ldc.i4.0
0x2871  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo::set_CanChangeTrackingBeEnabled(bool)
0x2876  ldloc.0
0x2877  ldc.i4.0
0x2878  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo::set_CanCreateCharts(bool)
0x287d  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x2882  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x2887  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_OnePartyModel()
0x288c  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::get_Name()
0x2891  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2896  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x289b  brfalse.s loc_28BB
0x289d  ldarg.1
0x289e  ldstr    aIsenabledforex// "isenabledforexternalchannels"
0x28a3  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x28a8  brfalse.s loc_28BB
0x28aa  ldloc.0
0x28ab  ldarg.1
0x28ac  ldstr    aIsenabledforex// "isenabledforexternalchannels"
0x28b1  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name)
0x28b6  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo::set_IsEnabledForExternalChannels(bool)
0x28bb  ldarg.1
0x28bc  ldstr    aSitemapid// "sitemapid"
0x28c1  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x28c6  brfalse.s loc_28D9
0x28c8  ldloc.0
0x28c9  ldarg.1
0x28ca  ldstr    aSitemapid// "sitemapid"
0x28cf  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.WebServices.ParameterBag::GetGuid(string name)
0x28d4  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo::set_SiteMapId(valuetype [mscorlib]System.Guid)
0x28d9  ldloc.0
0x28da  call     class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityService [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityServiceFactory::CreateEntityService(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo)
0x28df  ldloc.0
0x28e0  ldarg.0
0x28e1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x28e6  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x28eb  brtrue.s loc_28F0
0x28ed  ldarg.0
0x28ee  br.s     loc_28F5
0x28f0  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::DefaultSolutionId
0x28f5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityService::Create(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo, valuetype [mscorlib]System.Guid)
0x28fa  stloc.1
0x28fb  ldloc.0
0x28fc  ldloc.1
0x28fd  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::LogCreateEntity(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo entityInfo, valuetype [mscorlib]System.Guid entityId)
0x2902  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2907  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.SystemCustomization.SCUtil::FlushMetadataCache(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x290c  ldloc.1
0x290d  ret
```
