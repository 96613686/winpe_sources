# Microsoft.Crm.Application.Controls.AppModuleContainer::ConfigureHeader

- ea: `0xa6010`
- end: `0xa63aa`
- name: `Microsoft.Crm.Application.Controls.AppModuleContainer::ConfigureHeader`
- size: `922`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0xa6010`
- `0xa63b0`
- `0xa64f0`
- `0xa6900`
- `0xa69f0`

## string_xrefs

- `0xa6091`: `/_static/_common/scripts/jquery_ui_1.8.21.min.js`
- `0xa60a1`: `/_static/_common/scripts/AppModuleAccessibility.js`
- `0xa61de`: `ComponentState`

## pseudocode

```c

```

## disassembly

```asm
0xa6010  ldarg.0
0xa6011  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::ConfigureHeader()
0xa6016  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa601b  pop
0xa601c  ldarg.0
0xa601d  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xa6022  ldc.i4.1
0xa6023  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_LoadJQuery(bool)
0xa6028  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0xa602d  stloc.0
0xa602e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa6033  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0xa6038  ldc.i4.0
0xa6039  ldc.i4.0
0xa603a  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0xa603f  stloc.1
0xa6040  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0xa6045  pop
0xa6046  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache::Instance()
0xa604b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa6050  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_UserId()
0xa6055  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa605a  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser>::LookupEntry(void, var<u1>)
0xa605f  callvirt instance class [mscorlib]System.TimeZone [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_TimeZone()
0xa6064  stloc.2
0xa6065  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.AppModule.AppModuleData>::.ctor()
0xa606a  stloc.3
0xa606b  ldarg.0
0xa606c  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xa6071  ldstr    aControlsAppmod// "/_controls/AppModuleContainer/appmodule"...
0xa6076  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xa607b  ldarg.0
0xa607c  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xa6081  ldstr    aStaticControls_39// "/_static/_controls/AppModuleContainer/A"...
0xa6086  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xa608b  ldarg.0
0xa608c  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xa6091  ldstr    aStaticCommonSc_2// "/_static/_common/scripts/jquery_ui_1.8."...
0xa6096  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xa609b  ldarg.0
0xa609c  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xa60a1  ldstr    aStaticCommonSc_32// "/_static/_common/scripts/AppModuleAcces"...
0xa60a6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xa60ab  ldarg.0
0xa60ac  call     instance void Microsoft.Crm.Application.Controls.AppModuleContainer::SetResourceIdsForAppModule()
0xa60b1  ldarg.0
0xa60b2  ldarg.0
0xa60b3  ldfld    string Microsoft.Crm.Application.Controls.AppModuleContainer::appModuleEntityLogicalName
0xa60b8  ldc.i4.1
0xa60b9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa60be  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::HasPrivilege(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AccessRights, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa60c3  stfld    bool Microsoft.Crm.Application.Controls.AppModuleContainer::hasReadAccessToAppModuleEntity
0xa60c8  ldarg.0
0xa60c9  ldstr    aWebresource_0// "WebResource"
0xa60ce  call     instance string [mscorlib]System.String::ToLower()
0xa60d3  ldc.i4.1
0xa60d4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa60d9  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::HasPrivilege(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AccessRights, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa60de  stfld    bool Microsoft.Crm.Application.Controls.AppModuleContainer::hasAccessToWebResourceEntity
0xa60e3  ldarg.0
0xa60e4  call     instance class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.AppModule.AppModuleData Microsoft.Crm.Application.Controls.AppModuleContainer::GetLegacyCRMApp()
0xa60e9  stloc.s  4
0xa60eb  ldloc.s  4
0xa60ed  brfalse.s loc_A6119
0xa60ef  ldloc.s  4
0xa60f1  ldloc.2
0xa60f2  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0xa60f7  callvirt instance valuetype [mscorlib]System.DateTime [mscorlib]System.TimeZone::ToLocalTime(valuetype [mscorlib]System.DateTime)
0xa60fc  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa6101  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_UserId()
0xa6106  ldloc.1
0xa6107  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Formatting.CrmFormatter::FormatDate(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa610c  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.AppModule.AppModuleData::PublishedOn
0xa6111  ldloc.3
0xa6112  ldloc.s  4
0xa6114  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.AppModule.AppModuleData>::Add(var<u1>)
0xa6119  ldarg.0
0xa611a  ldfld    bool Microsoft.Crm.Application.Controls.AppModuleContainer::hasReadAccessToAppModuleEntity
0xa611f  brfalse  loc_A6313
0xa6124  ldarg.0
0xa6125  ldarg.0
0xa6126  call     instance bool Microsoft.Crm.Application.Controls.AppModuleContainer::HasPrivilegesForAppModuleEntity()
0xa612b  stfld    bool Microsoft.Crm.Application.Controls.AppModuleContainer::isAppModuleAdmin
0xa6130  ldarg.0
0xa6131  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Application.Controls.AppModuleContainer::RetrieveAppModuleList()
0xa6136  stloc.s  5
0xa6138  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa613d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0xa6142  ldc.i4.0
0xa6143  ldc.i4.0
0xa6144  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0xa6149  stloc.s  6
0xa614b  ldloc.s  5
0xa614d  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0xa6152  stloc.s  7
0xa6154  br       loc_A62E4
0xa6159  ldloc.s  7
0xa615b  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xa6160  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0xa6165  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::.ctor()
0xa616a  stloc.s  8
0xa616c  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.AppModule.AppModuleData::.ctor()
0xa6171  stloc.s  9
0xa6173  dup
0xa6174  dup
0xa6175  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Metadata()
0xa617a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0xa617f  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Name()
0xa6184  ldloc.s  9
0xa6186  ldflda   valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.AppModule.AppModuleData::AppModuleId
0xa618b  callvirt T0x2B00005B
0xa6190  pop
0xa6191  dup
0xa6192  ldstr    aName_0// "Name"
0xa6197  ldloc.s  9
0xa6199  ldflda   string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.AppModule.AppModuleData::Name
0xa619e  callvirt T0x2B000081
0xa61a3  pop
0xa61a4  dup
0xa61a5  ldstr    aDescription_0// "Description"
0xa61aa  ldloc.s  9
0xa61ac  ldflda   string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.AppModule.AppModuleData::Description
0xa61b1  callvirt T0x2B000081
0xa61b6  pop
0xa61b7  dup
0xa61b8  ldstr    aPublisherFrien// "publisher.friendlyname"
0xa61bd  ldloc.s  9
0xa61bf  ldflda   string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.AppModule.AppModuleData::PublisherName
0xa61c4  callvirt T0x2B000081
0xa61c9  pop
0xa61ca  dup
0xa61cb  ldstr    aFormfactor// "FormFactor"
0xa61d0  ldloc.s  9
0xa61d2  ldflda   int32 [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.AppModule.AppModuleData::FormFactor
0xa61d7  callvirt T0x2B000082
0xa61dc  pop
0xa61dd  dup
0xa61de  ldstr    aComponentstate_0// "ComponentState"
0xa61e3  ldloc.s  9
0xa61e5  ldflda   int32 [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.AppModule.AppModuleData::ComponentState
0xa61ea  callvirt T0x2B000082
0xa61ef  pop
0xa61f0  dup
0xa61f1  ldstr    aIsdefault_0// "IsDefault"
0xa61f6  ldloc.s  9
0xa61f8  ldflda   bool [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.AppModule.AppModuleData::IsDefault
0xa61fd  callvirt T0x2B000083
0xa6202  pop
0xa6203  dup
0xa6204  ldstr    aUrl_0// "Url"
0xa6209  ldloc.s  9
0xa620b  ldflda   string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.AppModule.AppModuleData::Url
0xa6210  callvirt T0x2B000081
0xa6215  pop
0xa6216  dup
0xa6217  ldstr    aClienttype// "ClientType"
0xa621c  ldloc.s  9
0xa621e  ldflda   int32 [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.AppModule.AppModuleData::ClientType
0xa6223  callvirt T0x2B000082
0xa6228  pop
0xa6229  dup
0xa622a  ldstr    aWebresourceDis// "webresource.displayname"
0xa622f  ldloc.s  9
0xa6231  ldflda   string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.AppModule.AppModuleData::IconName
0xa6236  callvirt T0x2B000081
0xa623b  pop
0xa623c  dup
0xa623d  ldstr    aUniquename_0// "UniqueName"
0xa6242  ldloc.s  9
0xa6244  ldflda   string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.AppModule.AppModuleData::UniqueName
0xa6249  callvirt T0x2B000081
0xa624e  pop
0xa624f  dup
0xa6250  ldstr    aPublishedon_0// "PublishedOn"
0xa6255  ldloca.s 8
0xa6257  callvirt T0x2B000084
0xa625c  brfalse.s loc_A6285
0xa625e  ldloc.s  9
0xa6260  ldloc.2
0xa6261  ldloc.s  8
0xa6263  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::get_UniversalTime()
0xa6268  callvirt instance valuetype [mscorlib]System.DateTime [mscorlib]System.TimeZone::ToLocalTime(valuetype [mscorlib]System.DateTime)
0xa626d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa6272  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_UserId()
0xa6277  ldloc.s  6
0xa6279  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Formatting.CrmFormatter::FormatDate(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa627e  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.AppModule.AppModuleData::PublishedOn
0xa6283  br.s     loc_A6291
0xa6285  ldloc.s  9
0xa6287  ldsfld   string [mscorlib]System.String::Empty
0xa628c  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.AppModule.AppModuleData::PublishedOn
0xa6291  dup
0xa6292  ldstr    aWebresourceNam// "webresource.name"
0xa6297  ldloc.s  9
0xa6299  ldflda   string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.AppModule.AppModuleData::IconPath
0xa629e  callvirt T0x2B000081
0xa62a3  pop
0xa62a4  ldstr    aSolutionid_0// "SolutionId"
0xa62a9  ldloc.s  9
0xa62ab  ldflda   valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.AppModule.AppModuleData::SolutionId
0xa62b0  callvirt T0x2B00005B
0xa62b5  pop
0xa62b6  ldloc.s  9
0xa62b8  ldloc.s  9
0xa62ba  ldfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.AppModule.AppModuleData::Name
0xa62bf  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0xa62c4  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.AppModule.AppModuleData::Name
0xa62c9  ldloc.s  9
0xa62cb  ldloc.s  9
0xa62cd  ldfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.AppModule.AppModuleData::Description
0xa62d2  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0xa62d7  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.AppModule.AppModuleData::Description
0xa62dc  ldloc.3
0xa62dd  ldloc.s  9
0xa62df  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.AppModule.AppModuleData>::Add(var<u1>)
0xa62e4  ldloc.s  7
0xa62e6  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xa62eb  brtrue   loc_A6159
0xa62f0  leave.s  loc_A6313
0xa62f2  ldloc.s  7
0xa62f4  isinst   [mscorlib]System.IDisposable
0xa62f9  stloc.s  0xA
0xa62fb  ldloc.s  0xA
0xa62fd  brfalse.s loc_A6306
0xa62ff  ldloc.s  0xA
0xa6301  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa6306  endfinally
0xa6307  ldloc.s  6
0xa6309  brfalse.s loc_A6312
0xa630b  ldloc.s  6
0xa630d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa6312  endfinally
0xa6313  ldarg.0
0xa6314  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<int32> [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::subscribedEvents
0xa6319  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<int32>::get_Count()
0xa631e  ldc.i4.0
0xa631f  ble.s    loc_A6332
0xa6321  ldloc.0
0xa6322  ldstr    aSubscribedeven// "subscribedEvents"
0xa6327  ldarg.0
0xa6328  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<int32> [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::subscribedEvents
0xa632d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xa6332  ldloc.0
0xa6333  ldstr    aTilesdata// "tilesData"
0xa6338  ldloc.3
0xa6339  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xa633e  ldloc.0
0xa633f  ldstr    aIsadmin// "isAdmin"
0xa6344  ldarg.0
0xa6345  ldfld    bool Microsoft.Crm.Application.Controls.AppModuleContainer::isAppModuleAdmin
0xa634a  box      [mscorlib]System.Boolean
0xa634f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xa6354  ldloc.0
0xa6355  ldstr    aIssystemadmin// "isSystemAdmin"
0xa635a  ldarg.0
0xa635b  ldfld    bool Microsoft.Crm.Application.Controls.AppModuleContainer::isSystemAdmin
0xa6360  box      [mscorlib]System.Boolean
0xa6365  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xa636a  ldloc.0
0xa636b  ldstr    aDefaultsolutio// "defaultSolutionId"
0xa6370  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::DefaultSolutionId
0xa6375  box      [mscorlib]System.Guid
0xa637a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xa637f  ldloc.0
0xa6380  ldstr    aCanpublishcust// "canPublishCustomization"
0xa6385  ldloc.1
0xa6386  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.SystemCustomizationSecurity::CheckPublishPrivileges(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa638b  box      [mscorlib]System.Boolean
0xa6390  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xa6395  ldarg.0
0xa6396  ldstr    aMscrmAppmodule// "Mscrm.AppModuleContainer"
0xa639b  ldloc.0
0xa639c  ldnull
0xa639d  ldnull
0xa639e  ldarg.0
0xa639f  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0xa63a4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::RegisterClientAjaxComponent(string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, string)
0xa63a9  ret
```
