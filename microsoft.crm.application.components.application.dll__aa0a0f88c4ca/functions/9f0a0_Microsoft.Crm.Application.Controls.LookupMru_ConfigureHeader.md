# Microsoft.Crm.Application.Controls.LookupMru::ConfigureHeader

- ea: `0x9f0a0`
- end: `0x9f134`
- name: `Microsoft.Crm.Application.Controls.LookupMru::ConfigureHeader`
- size: `148`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## string_xrefs

- `0x9f0d5`: `lookupMruDeleteTooltip`
- `0x9f0df`: `ToolTip_Lookup_DeleteMRU`
- `0x9f129`: `LookupMruWebService`

## pseudocode

```c

```

## disassembly

```asm
0x9f0a0  ldarg.0
0x9f0a1  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::ConfigureHeader()
0x9f0a6  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x9f0ab  stloc.0
0x9f0ac  ldloc.0
0x9f0ad  ldstr    aUserid_1// "userId"
0x9f0b2  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x9f0b7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_SystemUserId()
0x9f0bc  stloc.1
0x9f0bd  ldloca.s 1
0x9f0bf  constrained. [mscorlib]System.Guid
0x9f0c5  callvirt instance string [mscorlib]System.Object::ToString()
0x9f0ca  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetHashedText(string)
0x9f0cf  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x9f0d4  ldloc.0
0x9f0d5  ldstr    aLookupmrudelet// "lookupMruDeleteTooltip"
0x9f0da  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x9f0df  ldstr    aTooltipLookupD// "ToolTip_Lookup_DeleteMRU"
0x9f0e4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9f0e9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x9f0ee  ldarg.0
0x9f0ef  ldstr    aMscrmLookupmru// "Mscrm.LookupMruList"
0x9f0f4  ldloc.0
0x9f0f5  ldnull
0x9f0f6  ldnull
0x9f0f7  ldarg.0
0x9f0f8  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x9f0fd  ldc.i4.1
0x9f0fe  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::RegisterClientAjaxComponent(string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, string, bool)
0x9f103  ldarg.0
0x9f104  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9f109  ldstr    aStaticControls_25// "/_static/_controls/LookupMru/LookupMruL"...
0x9f10e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x9f113  ldarg.0
0x9f114  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9f119  ldstr    aStaticControls_11// "/_static/_controls/datetime/date.js"
0x9f11e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x9f123  ldarg.0
0x9f124  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9f129  ldstr    aLookupmruwebse// "LookupMruWebService"
0x9f12e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0x9f133  ret
```
