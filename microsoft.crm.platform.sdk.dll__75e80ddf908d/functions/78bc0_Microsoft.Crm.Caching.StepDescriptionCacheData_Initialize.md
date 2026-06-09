# Microsoft.Crm.Caching.StepDescriptionCacheData::Initialize

- ea: `0x78bc0`
- end: `0x78e01`
- name: `Microsoft.Crm.Caching.StepDescriptionCacheData::Initialize`
- size: `577`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x78bc0`
- `0x9c500`
- `0x9c570`
- `0x9c9f0`

## string_xrefs

- `0x78bc2`: `asyncautodelete`
- `0x78bd8`: `configuration`
- `0x78cec`: `impersonatinguserid`
- `0x78cfa`: `impersonatinguserid`
- `0x78d52`: `secureconfig`
- `0x78d60`: `secureconfig`
- `0x78d75`: `canusereadonlyconnection`
- `0x78d83`: `canusereadonlyconnection`
- `0x78d98`: `plugintypeid`
- `0x78da6`: `plugintypeid`
- `0x78dde`: `createdby`
- `0x78dec`: `createdby`

## pseudocode

```c

```

## disassembly

```asm
0x78bc0  ldarg.0
0x78bc1  ldarg.1
0x78bc2  ldstr    aAsyncautodelet// "asyncautodelete"
0x78bc7  callvirt instance object Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string attributeName)
0x78bcc  unbox.any [mscorlib]System.Boolean
0x78bd1  stfld    bool Microsoft.Crm.Caching.StepDescriptionCacheData::_asyncAutoDelete
0x78bd6  ldarg.0
0x78bd7  ldarg.1
0x78bd8  ldstr    aConfiguration// "configuration"
0x78bdd  callvirt instance object Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string attributeName)
0x78be2  castclass [mscorlib]System.String
0x78be7  stfld    string Microsoft.Crm.Caching.StepDescriptionCacheData::_configuration
0x78bec  ldarg.0
0x78bed  ldarg.1
0x78bee  ldstr    aDescription// "description"
0x78bf3  callvirt instance object Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string attributeName)
0x78bf8  castclass [mscorlib]System.String
0x78bfd  stfld    string Microsoft.Crm.Caching.StepDescriptionCacheData::_description
0x78c02  ldarg.0
0x78c03  ldarg.1
0x78c04  ldstr    aEventhandlerty// "eventhandlertypecode"
0x78c09  callvirt instance object Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string attributeName)
0x78c0e  unbox.any [mscorlib]System.Int32
0x78c13  stfld    int32 Microsoft.Crm.Caching.StepDescriptionCacheData::_eventHandlerIdType
0x78c18  ldarg.0
0x78c19  ldarg.1
0x78c1a  ldstr    aEventhandler// "eventhandler"
0x78c1f  callvirt instance object Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string attributeName)
0x78c24  unbox.any [mscorlib]System.Guid
0x78c29  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Caching.StepDescriptionCacheData::_eventHandlerId
0x78c2e  ldarg.0
0x78c2f  ldarg.1
0x78c30  ldstr    aIshidden// "ishidden"
0x78c35  callvirt instance object Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string attributeName)
0x78c3a  unbox.any [mscorlib]System.Boolean
0x78c3f  stfld    bool Microsoft.Crm.Caching.StepDescriptionCacheData::_isHidden
0x78c44  ldarg.0
0x78c45  ldarg.1
0x78c46  ldstr    aSdkmessageproc_0// "sdkmessageprocessingstepid"
0x78c4b  callvirt instance object Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string attributeName)
0x78c50  unbox.any [mscorlib]System.Guid
0x78c55  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Caching.StepDescriptionCacheData::_id
0x78c5a  ldarg.0
0x78c5b  ldarg.1
0x78c5c  ldstr    aInvocationsour_0// "invocationsource"
0x78c61  callvirt instance object Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string attributeName)
0x78c66  unbox.any [mscorlib]System.Int32
0x78c6b  stfld    int32 Microsoft.Crm.Caching.StepDescriptionCacheData::_invocationsource
0x78c70  ldarg.0
0x78c71  ldarg.1
0x78c72  ldstr    aMode// "mode"
0x78c77  callvirt instance object Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string attributeName)
0x78c7c  unbox.any [mscorlib]System.Int32
0x78c81  stfld    int32 Microsoft.Crm.Caching.StepDescriptionCacheData::_mode
0x78c86  ldarg.0
0x78c87  ldarg.1
0x78c88  ldstr    aName_0// "name"
0x78c8d  callvirt instance object Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string attributeName)
0x78c92  castclass [mscorlib]System.String
0x78c97  stfld    string Microsoft.Crm.Caching.StepDescriptionCacheData::_name
0x78c9c  ldarg.0
0x78c9d  ldarg.1
0x78c9e  ldstr    aStage// "stage"
0x78ca3  callvirt instance object Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string attributeName)
0x78ca8  unbox.any [mscorlib]System.Int32
0x78cad  stfld    int32 Microsoft.Crm.Caching.StepDescriptionCacheData::_stage
0x78cb2  ldarg.0
0x78cb3  ldarg.1
0x78cb4  ldstr    aSupporteddeplo// "supporteddeployment"
0x78cb9  callvirt instance object Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string attributeName)
0x78cbe  unbox.any [mscorlib]System.Int32
0x78cc3  stfld    int32 Microsoft.Crm.Caching.StepDescriptionCacheData::_supportedDeployment
0x78cc8  ldarg.1
0x78cc9  ldstr    aEventexpander// "eventexpander"
0x78cce  callvirt instance bool Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string attributeName)
0x78cd3  brtrue.s loc_78CEB
0x78cd5  ldarg.0
0x78cd6  ldarg.1
0x78cd7  ldstr    aEventexpander// "eventexpander"
0x78cdc  callvirt instance object Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string attributeName)
0x78ce1  castclass [mscorlib]System.String
0x78ce6  stfld    string Microsoft.Crm.Caching.StepDescriptionCacheData::_eventExpander
0x78ceb  ldarg.1
0x78cec  ldstr    aImpersonatingu// "impersonatinguserid"
0x78cf1  callvirt instance bool Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string attributeName)
0x78cf6  brtrue.s loc_78D0E
0x78cf8  ldarg.0
0x78cf9  ldarg.1
0x78cfa  ldstr    aImpersonatingu// "impersonatinguserid"
0x78cff  callvirt instance object Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string attributeName)
0x78d04  unbox.any [mscorlib]System.Guid
0x78d09  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Caching.StepDescriptionCacheData::_impersonatingUserId
0x78d0e  ldarg.1
0x78d0f  ldstr    aFilteringattri// "filteringattributes"
0x78d14  callvirt instance bool Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string attributeName)
0x78d19  brtrue.s loc_78D45
0x78d1b  ldarg.1
0x78d1c  ldstr    aFilteringattri// "filteringattributes"
0x78d21  callvirt instance object Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string attributeName)
0x78d26  castclass [mscorlib]System.String
0x78d2b  stloc.0
0x78d2c  ldarg.0
0x78d2d  ldloc.0
0x78d2e  ldstr    asc_B8554// ","
0x78d33  call     instance char[] [mscorlib]System.String::ToCharArray()
0x78d38  ldc.i4.1
0x78d39  callvirt instance string[] [mscorlib]System.String::Split(char[], valuetype [mscorlib]System.StringSplitOptions)
0x78d3e  stfld    string[] Microsoft.Crm.Caching.StepDescriptionCacheData::_filteringAttributes
0x78d43  br.s     loc_78D51
0x78d45  ldarg.0
0x78d46  ldc.i4.0
0x78d47  newarr   [mscorlib]System.String
0x78d4c  stfld    string[] Microsoft.Crm.Caching.StepDescriptionCacheData::_filteringAttributes
0x78d51  ldarg.1
0x78d52  ldstr    aSecureconfig// "secureconfig"
0x78d57  callvirt instance bool Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string attributeName)
0x78d5c  brtrue.s loc_78D74
0x78d5e  ldarg.0
0x78d5f  ldarg.1
0x78d60  ldstr    aSecureconfig// "secureconfig"
0x78d65  callvirt instance object Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string attributeName)
0x78d6a  castclass [mscorlib]System.String
0x78d6f  stfld    string Microsoft.Crm.Caching.StepDescriptionCacheData::_secureConfiguration
0x78d74  ldarg.1
0x78d75  ldstr    aCanusereadonly// "canusereadonlyconnection"
0x78d7a  callvirt instance bool Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string attributeName)
0x78d7f  brtrue.s loc_78D97
0x78d81  ldarg.0
0x78d82  ldarg.1
0x78d83  ldstr    aCanusereadonly// "canusereadonlyconnection"
0x78d88  callvirt instance object Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string attributeName)
0x78d8d  unbox.any [mscorlib]System.Boolean
0x78d92  stfld    bool Microsoft.Crm.Caching.StepDescriptionCacheData::_canUseReadOnlyConnection
0x78d97  ldarg.1
0x78d98  ldstr    aPlugintypeid// "plugintypeid"
0x78d9d  callvirt instance bool Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string attributeName)
0x78da2  brtrue.s loc_78DBA
0x78da4  ldarg.0
0x78da5  ldarg.1
0x78da6  ldstr    aPlugintypeid// "plugintypeid"
0x78dab  callvirt instance object Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string attributeName)
0x78db0  unbox.any [mscorlib]System.Guid
0x78db5  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Caching.StepDescriptionCacheData::_pluginTypeId
0x78dba  ldarg.1
0x78dbb  ldstr    aSolutionid_0// "solutionid"
0x78dc0  callvirt instance bool Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string attributeName)
0x78dc5  brtrue.s loc_78DDD
0x78dc7  ldarg.0
0x78dc8  ldarg.1
0x78dc9  ldstr    aSolutionid_0// "solutionid"
0x78dce  callvirt instance object Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string attributeName)
0x78dd3  unbox.any [mscorlib]System.Guid
0x78dd8  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Caching.StepDescriptionCacheData::_solutionId
0x78ddd  ldarg.1
0x78dde  ldstr    aCreatedby_0// "createdby"
0x78de3  callvirt instance bool Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string attributeName)
0x78de8  brtrue.s loc_78E00
0x78dea  ldarg.0
0x78deb  ldarg.1
0x78dec  ldstr    aCreatedby_0// "createdby"
0x78df1  callvirt instance object Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string attributeName)
0x78df6  unbox.any [mscorlib]System.Guid
0x78dfb  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Caching.StepDescriptionCacheData::_createdBy
0x78e00  ret
```
