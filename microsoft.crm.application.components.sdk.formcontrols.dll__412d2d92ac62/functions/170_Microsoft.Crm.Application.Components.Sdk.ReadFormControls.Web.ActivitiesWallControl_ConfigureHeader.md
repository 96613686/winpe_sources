# Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesWallControl::ConfigureHeader

- ea: `0x170`
- end: `0x3db`
- name: `Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesWallControl::ConfigureHeader`
- size: `619`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x130`
- `0x150`
- `0x170`
- `0x540`
- `0x5d0`

## string_xrefs

- `0x194`: `/_static/_common/scripts/jquery_ui_1.8.21.min.js`
- `0x1a4`: `/_static/_common/scripts/SalesCommonImported.js`
- `0x1b4`: `/_static/_common/scripts/CrmInternalUtility.js`
- `0x1c4`: `/_static/_common/scripts/SalesCommonFramework.js`
- `0x1d4`: `/_static/_common/scripts/SalesCrmSoapProxyService.js`
- `0x1e4`: `/_static/_common/scripts/Wall.Interfaces.js`
- `0x1f4`: `/_static/_common/scripts/Wall.Control.js`
- `0x27c`: `isActivityReadEnabled`
- `0x386`: `masterComponentId`
- `0x397`: `isControlReadOnly`

## pseudocode

```c

```

## disassembly

```asm
0x170  ldarg.0
0x171  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::ConfigureHeader()
0x176  ldarg.0
0x177  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x17c  ldc.i4.1
0x17d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_LoadJQuery(bool)
0x182  ldarg.0
0x183  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x188  ldc.i4.1
0x189  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_LoadJQueryTemplate(bool)
0x18e  ldarg.0
0x18f  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x194  ldstr    aStaticCommonSc// "/_static/_common/scripts/jquery_ui_1.8."...
0x199  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x19e  ldarg.0
0x19f  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1a4  ldstr    aStaticCommonSc_0// "/_static/_common/scripts/SalesCommonImp"...
0x1a9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x1ae  ldarg.0
0x1af  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1b4  ldstr    aStaticCommonSc_1// "/_static/_common/scripts/CrmInternalUti"...
0x1b9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x1be  ldarg.0
0x1bf  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1c4  ldstr    aStaticCommonSc_2// "/_static/_common/scripts/SalesCommonFra"...
0x1c9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x1ce  ldarg.0
0x1cf  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1d4  ldstr    aStaticCommonSc_3// "/_static/_common/scripts/SalesCrmSoapPr"...
0x1d9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x1de  ldarg.0
0x1df  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1e4  ldstr    aStaticCommonSc_4// "/_static/_common/scripts/Wall.Interface"...
0x1e9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x1ee  ldarg.0
0x1ef  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1f4  ldstr    aStaticCommonSc_5// "/_static/_common/scripts/Wall.Control.j"...
0x1f9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x1fe  ldarg.0
0x1ff  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x204  ldstr    aStaticWallcont// "/_static/WallControl/ActivitiesWallCont"...
0x209  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x20e  ldarg.0
0x20f  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x214  ldstr    aStaticWallcont_0// "/_static/WallControl/ActivitiesWallCont"...
0x219  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x21e  ldarg.0
0x21f  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x224  ldstr    aStaticFormsAct// "/_static/_forms/ActivitiesWallPage.js"
0x229  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x22e  ldarg.0
0x22f  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x234  ldstr    aActivitieswall_0// "activitieswallStrings"
0x239  ldarg.0
0x23a  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesWallControl::GenerateClientStrings()
0x23f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>)
0x244  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x249  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsActivityWallSortingFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x24e  brfalse.s loc_266
0x250  ldarg.0
0x251  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x256  ldstr    aActivitypointe// "activityPointerAttributes"
0x25b  ldarg.0
0x25c  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesWallControl::GetActivityPointerAttributeNames()
0x261  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>)
0x266  ldc.i4   0x1068
0x26b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x270  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x275  stloc.0
0x276  ldarg.0
0x277  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x27c  ldstr    aIsactivityread// "isActivityReadEnabled"
0x281  ldloc.0
0x282  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x287  ldc.i4.1
0x288  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x28d  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::HasPrivilege(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x292  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x297  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x29c  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x2a1  stloc.s  5
0x2a3  ldloca.s 5
0x2a5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2aa  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x2af  stloc.1
0x2b0  ldarg.0
0x2b1  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x2b6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2bb  ldstr    a0MsdynActivity// "{0}msdyn_/ActivityFeeds.Resources.{1}js"
0x2c0  ldc.i4.2
0x2c1  newarr   [mscorlib]System.Object
0x2c6  dup
0x2c7  ldc.i4.0
0x2c8  ldstr    aWebresource// "$webresource:"
0x2cd  stelem.ref
0x2ce  dup
0x2cf  ldc.i4.1
0x2d0  ldloc.1
0x2d1  ldstr    a1033// "1033"
0x2d6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2db  brtrue.s loc_2EA
0x2dd  ldloc.1
0x2de  ldstr    asc_2D4E6// "."
0x2e3  call     string [mscorlib]System.String::Concat(string, string)
0x2e8  br.s     loc_2EF
0x2ea  ldsfld   string [mscorlib]System.String::Empty
0x2ef  stelem.ref
0x2f0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2f5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2fa  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::CreateWebResourceUri(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2ff  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x304  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x309  stloc.2
0x30a  ldstr    aStaticWallcont_1// "/_static/WallControl/ActivitiesWallCont"...
0x30f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x314  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::CreateWebResourceUri(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x319  dup
0x31a  ldc.i4.1
0x31b  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::set_UseVersionStamp(bool)
0x320  callvirt instance string [mscorlib]System.Object::ToString()
0x325  stloc.3
0x326  ldloc.2
0x327  ldstr    aWallcontentpag// "wallContentPageUrl"
0x32c  ldloc.3
0x32d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x332  ldarg.0
0x333  ldfld    string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesWallControl::_entityId
0x338  brfalse.s loc_34B
0x33a  ldloc.2
0x33b  ldstr    aEntityid// "entityId"
0x340  ldarg.0
0x341  ldfld    string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesWallControl::_entityId
0x346  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x34b  ldarg.0
0x34c  ldfld    string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesWallControl::_viewId
0x351  brfalse.s loc_364
0x353  ldloc.2
0x354  ldstr    aViewid// "viewId"
0x359  ldarg.0
0x35a  ldfld    string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesWallControl::_viewId
0x35f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x364  ldarg.0
0x365  ldfld    string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesWallControl::otc
0x36a  brfalse.s loc_37D
0x36c  ldloc.2
0x36d  ldstr    aEntityobjectty// "entityObjectTypeCode"
0x372  ldarg.0
0x373  ldfld    string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesWallControl::otc
0x378  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x37d  ldarg.0
0x37e  call     instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesWallControl::get_MasterComponentId()
0x383  brfalse.s loc_396
0x385  ldloc.2
0x386  ldstr    aMastercomponen// "masterComponentId"
0x38b  ldarg.0
0x38c  call     instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesWallControl::get_MasterComponentId()
0x391  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x396  ldloc.2
0x397  ldstr    aIscontrolreado// "isControlReadOnly"
0x39c  ldarg.0
0x39d  call     instance bool Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesWallControl::get_IsControlReadOnly()
0x3a2  box      [mscorlib]System.Boolean
0x3a7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x3ac  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x3b1  stloc.s  4
0x3b3  ldloc.s  4
0x3b5  ldstr    aEventmanager// "eventManager"
0x3ba  ldstr    aPageCrmeventma// "__Page_crmEventManager"
0x3bf  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x3c4  ldarg.0
0x3c5  ldstr    aMscrmForminput// "Mscrm.FormInputControl.ActivitiesWallPa"...
0x3ca  ldloc.2
0x3cb  ldnull
0x3cc  ldloc.s  4
0x3ce  ldarg.0
0x3cf  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x3d4  ldc.i4.1
0x3d5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::RegisterClientAjaxComponent(string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, string, bool)
0x3da  ret
```
