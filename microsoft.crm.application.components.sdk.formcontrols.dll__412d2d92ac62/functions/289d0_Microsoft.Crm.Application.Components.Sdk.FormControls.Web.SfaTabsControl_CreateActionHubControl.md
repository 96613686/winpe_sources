# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SfaTabsControl::CreateActionHubControl

- ea: `0x289d0`
- end: `0x28a66`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SfaTabsControl::CreateActionHubControl`
- size: `150`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x28820`

## callees

- `0x156c0`
- `0x158d0`
- `0x289d0`
- `0x29e70`
- `0x29e90`
- `0x29eb0`
- `0x29f00`
- `0x29f60`

## pseudocode

```c

```

## disassembly

```asm
0x289d0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x289d5  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.ActionCardUtil::IsPreviewEnabledForActionCard(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x289da  brfalse  loc_28A65
0x289df  call     bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.ActivityFeedUtility::GetUserActionCardReadPrivilegeEnabled()
0x289e4  brfalse.s loc_28A65
0x289e6  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsForOutlookClient()
0x289eb  brfalse.s loc_289F4
0x289ed  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsOnline()
0x289f2  brfalse.s loc_28A65
0x289f4  ldarg.1
0x289f5  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsActionHubTabEnabledForEntity(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata)
0x289fa  brfalse.s loc_28A65
0x289fc  newobj   instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ActionHubControl::.ctor()
0x28a01  dup
0x28a02  ldstr    aActionhubcontr// "actionhubcontrol_"
0x28a07  ldarg.0
0x28a08  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x28a0d  call     string [mscorlib]System.String::Concat(string, string)
0x28a12  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x28a17  dup
0x28a18  ldarg.0
0x28a19  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x28a1e  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ActionHubControl::set_MasterComponentId(string value)
0x28a23  stloc.0
0x28a24  ldarg.0
0x28a25  call     instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabsControl::get_Items()
0x28a2a  newobj   instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer::.ctor()
0x28a2f  dup
0x28a30  ldstr    aActionhubtab// "ActionHubTab"
0x28a35  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer::set_TabId(string value)
0x28a3a  dup
0x28a3b  ldloc.0
0x28a3c  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer::set_Control(class [System.Web]System.Web.UI.Control value)
0x28a41  dup
0x28a42  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x28a47  ldstr    aWebToolsFormed// "Web.Tools.FormEditor.Dialogs.field.delv"...
0x28a4c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x28a51  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x28a56  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0x28a5b  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer::set_TabName(string value)
0x28a60  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer>::Add(var<u1>)
0x28a65  ret
```
