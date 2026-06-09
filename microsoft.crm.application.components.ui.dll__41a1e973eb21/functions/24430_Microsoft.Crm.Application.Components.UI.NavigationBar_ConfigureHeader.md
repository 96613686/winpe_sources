# Microsoft.Crm.Application.Components.UI.NavigationBar::ConfigureHeader

- ea: `0x24430`
- end: `0x2459f`
- name: `Microsoft.Crm.Application.Components.UI.NavigationBar::ConfigureHeader`
- size: `367`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callees

- `0x2d40`
- `0x2d80`
- `0x2ef0`
- `0x3380`
- `0x38d0`
- `0x39f0`
- `0x23b60`
- `0x24080`
- `0x24320`
- `0x243d0`
- `0x24430`
- `0x245a0`

## string_xrefs

- `0x2449d`: `tabLinksListId`
- `0x244c2`: `subAreaLinksListId`

## pseudocode

```c

```

## disassembly

```asm
0x24430  ldarg.0
0x24431  call     instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::ConfigureHeader()
0x24436  ldarg.0
0x24437  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x2443c  ldstr    aStaticFormsFor// "/_static/_forms/form.js"
0x24441  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string file)
0x24446  ldarg.0
0x24447  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x2444c  ldstr    aNavNavCssAspx// "/_nav/nav.css.aspx"
0x24451  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string file)
0x24456  ldarg.0
0x24457  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x2445c  ldstr    aLocidTreePlus// "LOCID_TREE_PLUS"
0x24461  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x24466  ldstr    aTreeAltExpand// "Tree.Alt.Expand"
0x2446b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x24470  ldc.i4.0
0x24471  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x24476  ldarg.0
0x24477  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x2447c  ldstr    aLocidTreeMinus// "LOCID_TREE_MINUS"
0x24481  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x24486  ldstr    aTreeAltCollaps// "Tree.Alt.Collapse"
0x2448b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x24490  ldc.i4.0
0x24491  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x24496  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x2449b  stloc.0
0x2449c  ldloc.0
0x2449d  ldstr    aTablinkslistid// "tabLinksListId"
0x244a2  ldarg.0
0x244a3  ldfld    class Microsoft.Crm.Application.Components.UI.FormSelector Microsoft.Crm.Application.Components.UI.NavigationBar::_formSelector
0x244a8  brtrue.s loc_244B1
0x244aa  ldsfld   string [mscorlib]System.String::Empty
0x244af  br.s     loc_244BC
0x244b1  ldarg.0
0x244b2  ldfld    class Microsoft.Crm.Application.Components.UI.FormSelector Microsoft.Crm.Application.Components.UI.NavigationBar::_formSelector
0x244b7  callvirt instance string Microsoft.Crm.Application.Components.UI.FormSelector::get_TabLinksListId()
0x244bc  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x244c1  ldloc.0
0x244c2  ldstr    aSubarealinksli// "subAreaLinksListId"
0x244c7  ldstr    aCrmformnavsuba// "crmFormNavSubareas"
0x244cc  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x244d1  ldloc.0
0x244d2  ldstr    aUserid// "userId"
0x244d7  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x244dc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_SystemUserId()
0x244e1  stloc.3
0x244e2  ldloca.s 3
0x244e4  constrained. [mscorlib]System.Guid
0x244ea  callvirt instance string [mscorlib]System.Object::ToString()
0x244ef  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetHashedText(string)
0x244f4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x244f9  ldloc.0
0x244fa  ldstr    aFormnavwidth// "formNavWidth"
0x244ff  ldarg.0
0x24500  call     instance int32 Microsoft.Crm.Application.Components.UI.NavigationBar::get_Width()
0x24505  box      [mscorlib]System.Int32
0x2450a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2450f  ldloc.0
0x24510  ldstr    aFormnavstripwi// "formNavStripWidth"
0x24515  ldstr    a40// "40"
0x2451a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2451f  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x24524  stloc.1
0x24525  ldarg.0
0x24526  ldfld    class Microsoft.Crm.Application.Components.UI.FormSelector Microsoft.Crm.Application.Components.UI.NavigationBar::_formSelector
0x2452b  brfalse.s loc_24543
0x2452d  ldloc.1
0x2452e  ldstr    aFormselector// "formSelector"
0x24533  ldarg.0
0x24534  ldfld    class Microsoft.Crm.Application.Components.UI.FormSelector Microsoft.Crm.Application.Components.UI.NavigationBar::_formSelector
0x24539  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x2453e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x24543  ldarg.0
0x24544  ldloc.0
0x24545  ldloc.1
0x24546  callvirt instance void Microsoft.Crm.Application.Components.UI.NavigationBar::UpdateNavigationControlProperties(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> references)
0x2454b  ldarg.0
0x2454c  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x24551  ldstr    aMscrmFormnavco// "Mscrm.FormNavControl"
0x24556  ldloc.0
0x24557  ldnull
0x24558  ldloc.1
0x24559  ldarg.0
0x2455a  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x2455f  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string componentTypeName, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> events, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> references, string elementId)
0x24564  ldarg.0
0x24565  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x2456a  ldstr    aMscrmFormnavco// "Mscrm.FormNavControl"
0x2456f  ldloc.0
0x24570  call     string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.JsonConverter::ConvertDictionaryToJson(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>)
0x24575  ldnull
0x24576  call     string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.JsonConverter::ConvertDictionaryToJSObject(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>)
0x2457b  ldloc.1
0x2457c  call     string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.JsonConverter::ConvertDictionaryToJson(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>)
0x24581  ldarg.0
0x24582  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x24587  callvirt instance string Microsoft.Crm.Controls.PageResourceManager::GetClientAjaxComponentScript(string componentTypeName, string properties, string events, string references, string elementId)
0x2458c  stloc.2
0x2458d  ldarg.0
0x2458e  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x24593  ldstr    aNavbardata// "navBarData"
0x24598  ldloc.2
0x24599  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, string varValue)
0x2459e  ret
```
