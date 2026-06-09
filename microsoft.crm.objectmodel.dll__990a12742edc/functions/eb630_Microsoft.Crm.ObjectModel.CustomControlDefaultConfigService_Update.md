# Microsoft.Crm.ObjectModel.CustomControlDefaultConfigService::Update

- ea: `0xeb630`
- end: `0xeb914`
- name: `Microsoft.Crm.ObjectModel.CustomControlDefaultConfigService::Update`
- size: `740`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x34b90`
- `0xbd940`
- `0xeb630`
- `0xeb920`

## string_xrefs

- `0xeb68c`: `CustomControlDefaultConfig`
- `0xeb833`: `CustomControlDefaultConfig`
- `0xeb64b`: `controldescriptionxml`
- `0xeb6c1`: `controldescriptionxml`
- `0xeb6dd`: `controldescriptionxml`
- `0xeb739`: `controldescriptionxml`
- `0xeb750`: `controldescriptionxml`
- `0xeb76d`: `controldescriptionxml`
- `0xeb784`: `controldescriptionxml`
- `0xeb808`: `controldescriptionxml`
- `0xeb8a4`: `controldescriptionxml`
- `0xeb662`: `eventsxml`
- `0xeb6e8`: `eventsxml`
- `0xeb704`: `eventsxml`
- `0xeb799`: `eventsxml`
- `0xeb7b0`: `eventsxml`
- `0xeb7c4`: `eventsxml`
- `0xeb7db`: `eventsxml`
- `0xeb7ed`: `controldescriptionjson`
- `0xeb89e`: `controldescriptionjson`
- `0xeb67c`: `customcontroldefaultconfigid`
- `0xeb69e`: `customcontroldefaultconfigid`
- `0xeb822`: `customcontroldefaultconfigid`
- `0xeb847`: `customcontroldefaultconfigid`
- `0xeb8e2`: `CustomControl import default config failed to update, because of error {0}.`
- `0xeb8fc`: `CustomControl import default config failed to update, because of error {0}.`

## pseudocode

```c

```

## disassembly

```asm
0xeb630  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0xeb635  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0xeb63a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_EditableGridControlJsEvents()
0xeb63f  ldarg.2
0xeb640  call     bool Microsoft.Crm.ObjectModel.FeatureControlUtilities::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail featureName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0xeb645  brfalse  loc_EB807
0xeb64a  ldarg.1
0xeb64b  ldstr    aControldescrip_2// "controldescriptionxml"
0xeb650  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xeb655  castclass [mscorlib]System.String
0xeb65a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xeb65f  brfalse.s loc_EB67B
0xeb661  ldarg.1
0xeb662  ldstr    aEventsxml// "eventsxml"
0xeb667  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xeb66c  castclass [mscorlib]System.String
0xeb671  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xeb676  brtrue   loc_EB8C1
0xeb67b  ldarg.1
0xeb67c  ldstr    aCustomcontrold_4// "customcontroldefaultconfigid"
0xeb681  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xeb686  unbox.any [mscorlib]System.Guid
0xeb68b  stloc.0
0xeb68c  ldstr    aCustomcontrold// "CustomControlDefaultConfig"
0xeb691  ldarg.2
0xeb692  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0xeb697  stloc.1
0xeb698  ldloc.1
0xeb699  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xeb69e  ldstr    aCustomcontrold_4// "customcontroldefaultconfigid"
0xeb6a3  ldc.i4.0
0xeb6a4  ldloc.0
0xeb6a5  box      [mscorlib]System.Guid
0xeb6aa  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xeb6af  pop
0xeb6b0  ldloc.1
0xeb6b1  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0xeb6b6  ldstr    aPrimaryentityt// "primaryentitytypecode"
0xeb6bb  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0xeb6c0  ldarg.1
0xeb6c1  ldstr    aControldescrip_2// "controldescriptionxml"
0xeb6c6  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xeb6cb  castclass [mscorlib]System.String
0xeb6d0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xeb6d5  brfalse.s loc_EB6E7
0xeb6d7  ldloc.1
0xeb6d8  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0xeb6dd  ldstr    aControldescrip_2// "controldescriptionxml"
0xeb6e2  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0xeb6e7  ldarg.1
0xeb6e8  ldstr    aEventsxml// "eventsxml"
0xeb6ed  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xeb6f2  castclass [mscorlib]System.String
0xeb6f7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xeb6fc  brfalse.s loc_EB70E
0xeb6fe  ldloc.1
0xeb6ff  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0xeb704  ldstr    aEventsxml// "eventsxml"
0xeb709  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0xeb70e  ldarg.0
0xeb70f  ldloc.0
0xeb710  ldarg.1
0xeb711  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_PlatformName()
0xeb716  ldarg.2
0xeb717  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xeb71c  ldloc.1
0xeb71d  ldarg.2
0xeb71e  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveUnpublished(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xeb723  stloc.2
0xeb724  ldloc.2
0xeb725  ldstr    aPrimaryentityt// "primaryentitytypecode"
0xeb72a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xeb72f  unbox.any [mscorlib]System.Int32
0xeb734  stloc.3
0xeb735  ldnull
0xeb736  stloc.s  4
0xeb738  ldarg.1
0xeb739  ldstr    aControldescrip_2// "controldescriptionxml"
0xeb73e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xeb743  castclass [mscorlib]System.String
0xeb748  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xeb74d  brtrue.s loc_EB76C
0xeb74f  ldarg.1
0xeb750  ldstr    aControldescrip_2// "controldescriptionxml"
0xeb755  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xeb75a  castclass [mscorlib]System.String
0xeb75f  stloc.s  4
0xeb761  ldarg.0
0xeb762  ldarg.1
0xeb763  ldloc.3
0xeb764  ldarg.2
0xeb765  call     instance void Microsoft.Crm.ObjectModel.CustomControlDefaultConfigService::ValidateControlDescriptionXml(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, int32 primaryEntityTypeCode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xeb76a  br.s     loc_EB795
0xeb76c  ldloc.2
0xeb76d  ldstr    aControldescrip_2// "controldescriptionxml"
0xeb772  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xeb777  castclass [mscorlib]System.String
0xeb77c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xeb781  brtrue.s loc_EB795
0xeb783  ldloc.2
0xeb784  ldstr    aControldescrip_2// "controldescriptionxml"
0xeb789  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xeb78e  castclass [mscorlib]System.String
0xeb793  stloc.s  4
0xeb795  ldnull
0xeb796  stloc.s  5
0xeb798  ldarg.1
0xeb799  ldstr    aEventsxml// "eventsxml"
0xeb79e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xeb7a3  castclass [mscorlib]System.String
0xeb7a8  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xeb7ad  brtrue.s loc_EB7C3
0xeb7af  ldarg.1
0xeb7b0  ldstr    aEventsxml// "eventsxml"
0xeb7b5  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xeb7ba  castclass [mscorlib]System.String
0xeb7bf  stloc.s  5
0xeb7c1  br.s     loc_EB7EC
0xeb7c3  ldloc.2
0xeb7c4  ldstr    aEventsxml// "eventsxml"
0xeb7c9  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xeb7ce  castclass [mscorlib]System.String
0xeb7d3  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xeb7d8  brtrue.s loc_EB7EC
0xeb7da  ldloc.2
0xeb7db  ldstr    aEventsxml// "eventsxml"
0xeb7e0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xeb7e5  castclass [mscorlib]System.String
0xeb7ea  stloc.s  5
0xeb7ec  ldarg.1
0xeb7ed  ldstr    aControldescrip_5// "controldescriptionjson"
0xeb7f2  ldloc.s  4
0xeb7f4  ldloc.s  5
0xeb7f6  ldloc.3
0xeb7f7  ldarg.2
0xeb7f8  call     string Microsoft.Crm.MetadataService.Utility.ClientMetadataHelper::ConvertControlDescriptionXMLtoJson(string controlDescription, string eventsXml, int32 primaryEntityTypeCode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xeb7fd  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0xeb802  br       loc_EB8C1
0xeb807  ldarg.1
0xeb808  ldstr    aControldescrip_2// "controldescriptionxml"
0xeb80d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xeb812  castclass [mscorlib]System.String
0xeb817  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xeb81c  brtrue   loc_EB8C1
0xeb821  ldarg.1
0xeb822  ldstr    aCustomcontrold_4// "customcontroldefaultconfigid"
0xeb827  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xeb82c  unbox.any [mscorlib]System.Guid
0xeb831  stloc.s  6
0xeb833  ldstr    aCustomcontrold// "CustomControlDefaultConfig"
0xeb838  ldarg.2
0xeb839  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0xeb83e  stloc.s  7
0xeb840  ldloc.s  7
0xeb842  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xeb847  ldstr    aCustomcontrold_4// "customcontroldefaultconfigid"
0xeb84c  ldc.i4.0
0xeb84d  ldloc.s  6
0xeb84f  box      [mscorlib]System.Guid
0xeb854  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xeb859  pop
0xeb85a  ldloc.s  7
0xeb85c  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0xeb861  ldstr    aPrimaryentityt// "primaryentitytypecode"
0xeb866  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0xeb86b  ldarg.0
0xeb86c  ldloc.s  6
0xeb86e  ldarg.1
0xeb86f  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_PlatformName()
0xeb874  ldarg.2
0xeb875  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xeb87a  ldloc.s  7
0xeb87c  ldarg.2
0xeb87d  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xeb882  ldstr    aPrimaryentityt// "primaryentitytypecode"
0xeb887  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xeb88c  unbox.any [mscorlib]System.Int32
0xeb891  stloc.s  8
0xeb893  ldarg.0
0xeb894  ldarg.1
0xeb895  ldloc.s  8
0xeb897  ldarg.2
0xeb898  call     instance void Microsoft.Crm.ObjectModel.CustomControlDefaultConfigService::ValidateControlDescriptionXml(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, int32 primaryEntityTypeCode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xeb89d  ldarg.1
0xeb89e  ldstr    aControldescrip_5// "controldescriptionjson"
0xeb8a3  ldarg.1
0xeb8a4  ldstr    aControldescrip_2// "controldescriptionxml"
0xeb8a9  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xeb8ae  castclass [mscorlib]System.String
0xeb8b3  ldnull
0xeb8b4  ldloc.s  8
0xeb8b6  ldarg.2
0xeb8b7  call     string Microsoft.Crm.MetadataService.Utility.ClientMetadataHelper::ConvertControlDescriptionXMLtoJson(string controlDescription, string eventsXml, int32 primaryEntityTypeCode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xeb8bc  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0xeb8c1  ldarg.0
0xeb8c2  ldarg.1
0xeb8c3  ldarg.2
0xeb8c4  call     instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xeb8c9  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CustomControlConfigurationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CustomControlConfigurationCache::Instance()
0xeb8ce  ldarg.2
0xeb8cf  callvirt instance void class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<int32, string>::Flush(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xeb8d4  leave.s  loc_EB913
0xeb8d6  stloc.s  9
0xeb8d8  ldloc.s  9
0xeb8da  ldarg.2
0xeb8db  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xeb8e0  ldc.i4.s 0x11
0xeb8e2  ldstr    aCustomcontrolI_0// "CustomControl import default config fai"...
0xeb8e7  ldc.i4.1
0xeb8e8  newarr   [mscorlib]System.Object
0xeb8ed  dup
0xeb8ee  ldc.i4.0
0xeb8ef  ldloc.s  9
0xeb8f1  callvirt instance string [mscorlib]System.Exception::get_Message()
0xeb8f6  stelem.ref
0xeb8f7  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xeb8fc  ldstr    aCustomcontrolI_0// "CustomControl import default config fai"...
0xeb901  ldloc.s  9
0xeb903  callvirt instance string [mscorlib]System.Exception::get_Message()
0xeb908  call     string [mscorlib]System.String::Format(string, object)
0xeb90d  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0xeb912  throw
0xeb913  ret
```
