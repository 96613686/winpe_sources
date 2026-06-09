# Microsoft.Crm.Application.Controls.RecentlyViewed::ConfigureHeader

- ea: `0xad1a0`
- end: `0xad30d`
- name: `Microsoft.Crm.Application.Controls.RecentlyViewed::ConfigureHeader`
- size: `365`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xad1a0`

## string_xrefs

- `0xad260`: `MenuItem_Label_Copy_Shortcut`
- `0xad256`: `copyShortcutActionTitle`
- `0xad2c2`: `/_static/_common/scripts/main.js`
- `0xad2e2`: `/_static/_common/scripts/salescrmsoapproxyservice.js`
- `0xad2f2`: `/_static/_common/scripts/salescommonframework.js`
- `0xad302`: `RecentlyViewedWebService`

## pseudocode

```c

```

## disassembly

```asm
0xad1a0  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsOnline()
0xad1a5  brfalse  loc_AD30C
0xad1aa  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xad1af  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsEnableRecentlyViewedFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xad1b4  brfalse  loc_AD30C
0xad1b9  ldarg.0
0xad1ba  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::ConfigureHeader()
0xad1bf  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0xad1c4  stloc.0
0xad1c5  ldloc.0
0xad1c6  ldstr    aUserid_1// "userId"
0xad1cb  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0xad1d0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_SystemUserId()
0xad1d5  stloc.1
0xad1d6  ldloca.s 1
0xad1d8  constrained. [mscorlib]System.Guid
0xad1de  callvirt instance string [mscorlib]System.Object::ToString()
0xad1e3  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetHashedText(string)
0xad1e8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xad1ed  ldloc.0
0xad1ee  ldstr    aRecentlyviewed_1// "recentlyViewedHeaderTitle"
0xad1f3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xad1f8  ldstr    aRecentlyviewed_0// "RecentlyViewed_Header_Title"
0xad1fd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xad202  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xad207  ldloc.0
0xad208  ldstr    aRecentlyviewed_2// "recentlyViewedViewsHeaderTitle"
0xad20d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xad212  ldstr    aRecentlyviewed_3// "RecentlyViewed_Views_Header_Title"
0xad217  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xad21c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xad221  ldloc.0
0xad222  ldstr    aPinitemactiont// "pinItemActionTitle"
0xad227  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xad22c  ldstr    aRecentlyviewed_4// "RecentlyViewed_ContextMenu_Label_Pin"
0xad231  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xad236  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xad23b  ldloc.0
0xad23c  ldstr    aUnpinitemactio// "unpinItemActionTitle"
0xad241  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xad246  ldstr    aRecentlyviewed_5// "RecentlyViewed_ContextMenu_Label_Unpin"
0xad24b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xad250  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xad255  ldloc.0
0xad256  ldstr    aCopyshortcutac// "copyShortcutActionTitle"
0xad25b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xad260  ldstr    aMenuitemLabelC_0// "MenuItem_Label_Copy_Shortcut"
0xad265  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xad26a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xad26f  ldloc.0
0xad270  ldstr    aSendshortcutac// "sendShortcutActionTitle"
0xad275  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xad27a  ldstr    aMenuitemLabelS_5// "MenuItem_Label_Send_Shortcut"
0xad27f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xad284  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xad289  ldloc.0
0xad28a  ldstr    aIssaveenabled// "isSaveEnabled"
0xad28f  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_WriteUserEntityUISettings()
0xad294  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xad299  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xad29e  box      [mscorlib]System.Boolean
0xad2a3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xad2a8  ldarg.0
0xad2a9  ldstr    aMscrmRecentlyv// "Mscrm.RecentlyViewed"
0xad2ae  ldloc.0
0xad2af  ldnull
0xad2b0  ldnull
0xad2b1  ldarg.0
0xad2b2  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0xad2b7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::RegisterClientAjaxComponent(string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, string)
0xad2bc  ldarg.0
0xad2bd  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xad2c2  ldstr    aStaticCommonSc_20// "/_static/_common/scripts/main.js"
0xad2c7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xad2cc  ldarg.0
0xad2cd  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xad2d2  ldstr    aStaticControls_11// "/_static/_controls/datetime/date.js"
0xad2d7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xad2dc  ldarg.0
0xad2dd  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xad2e2  ldstr    aStaticCommonSc_33// "/_static/_common/scripts/salescrmsoappr"...
0xad2e7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xad2ec  ldarg.0
0xad2ed  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xad2f2  ldstr    aStaticCommonSc_34// "/_static/_common/scripts/salescommonfra"...
0xad2f7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xad2fc  ldarg.0
0xad2fd  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xad302  ldstr    aRecentlyviewed_6// "RecentlyViewedWebService"
0xad307  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0xad30c  ret
```
