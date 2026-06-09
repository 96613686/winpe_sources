# Microsoft.Crm.Application.Components.UI.Lookup::ConfigureTouchHeaderInternal

- ea: `0x1f720`
- end: `0x1f810`
- name: `Microsoft.Crm.Application.Components.UI.Lookup::ConfigureTouchHeaderInternal`
- size: `240`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1f3f0`

## callees

- `0x2450`
- `0x3380`
- `0x38d0`
- `0x39f0`
- `0x1f3e0`
- `0x1f720`
- `0x238d0`
- `0x23b60`
- `0x23f10`

## string_xrefs

- `0x1f742`: `/_common/styles/touchControls.css.aspx`

## pseudocode

```c

```

## disassembly

```asm
0x1f720  ldarg.0
0x1f721  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1f726  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1f72b  brtrue   loc_1F80F
0x1f730  ldarg.0
0x1f731  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1f736  ldc.i4.1
0x1f737  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::set_LoadJQuery(bool value)
0x1f73c  ldarg.0
0x1f73d  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1f742  ldstr    aCommonStylesTo// "/_common/styles/touchControls.css.aspx"
0x1f747  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string file)
0x1f74c  ldarg.0
0x1f74d  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1f752  ldstr    aStaticControls_10// "/_static/_controls/editableselect/edita"...
0x1f757  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string file)
0x1f75c  ldarg.0
0x1f75d  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1f762  ldstr    aLocidLookupmat// "LOCID_LOOKUPMATCHBAR_NOMATCH"
0x1f767  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1f76c  ldstr    aTouchlookupmat// "TouchLookupMatchesBar_NoMatchFound"
0x1f771  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1f776  ldc.i4.0
0x1f777  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x1f77c  ldarg.0
0x1f77d  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1f782  ldstr    aLocidLookupmat_0// "LOCID_LOOKUPMATCHBAR_REFINE"
0x1f787  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1f78c  ldstr    aTouchlookupmat_0// "TouchLookupMatchesBar_RefineQuery"
0x1f791  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1f796  ldc.i4.0
0x1f797  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x1f79c  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x1f7a1  stloc.0
0x1f7a2  ldarg.0
0x1f7a3  call     instance class Microsoft.Crm.Application.Components.UI.LookupItemCollection Microsoft.Crm.Application.Components.UI.Lookup::get_Items()
0x1f7a8  call     T0x2B000027
0x1f7ad  ldsfld   class [mscorlib]System.Func`2<class Microsoft.Crm.Application.Components.UI.LookupItem, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.LookupItemInformation.LookupItemInfo> <>c::<>9__57_0
0x1f7b2  dup
0x1f7b3  brtrue.s loc_1F7CC
0x1f7b5  pop
0x1f7b6  ldsfld   class <>c <>c::<>9
0x1f7bb  ldftn    instance class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.LookupItemInformation.LookupItemInfo <>c::<ConfigureTouchHeaderInternal>b__57_0(class Microsoft.Crm.Application.Components.UI.LookupItem item)
0x1f7c1  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.Crm.Application.Components.UI.LookupItem, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.LookupItemInformation.LookupItemInfo>::.ctor(object, native int)
0x1f7c6  dup
0x1f7c7  stsfld   class [mscorlib]System.Func`2<class Microsoft.Crm.Application.Components.UI.LookupItem, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.LookupItemInformation.LookupItemInfo> <>c::<>9__57_0
0x1f7cc  call     T0x2B000028
0x1f7d1  call     T0x2B000029
0x1f7d6  stloc.1
0x1f7d7  ldloc.0
0x1f7d8  ldstr    aInitialtouchlo// "initialTouchLookupItems"
0x1f7dd  ldloc.1
0x1f7de  ldlen
0x1f7df  brfalse.s loc_1F7E4
0x1f7e1  ldloc.1
0x1f7e2  br.s     loc_1F7E5
0x1f7e4  ldnull
0x1f7e5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x1f7ea  ldarg.0
0x1f7eb  ldarg.0
0x1f7ec  ldfld    string Microsoft.Crm.Application.Components.UI.Lookup::_behaviorClassName
0x1f7f1  ldloc.0
0x1f7f2  ldnull
0x1f7f3  ldnull
0x1f7f4  ldarg.0
0x1f7f5  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1f7fa  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::RegisterClientAjaxComponent(string componentTypeName, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> events, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> references, string elementId)
0x1f7ff  ldarg.0
0x1f800  ldstr    aMscrmLookupatt// "Mscrm.LookupAttribute"
0x1f805  ldstr    aMscrmLookupuic// "Mscrm.LookupUIControl"
0x1f80a  call     instance void Microsoft.Crm.Application.Components.UI.CrmFormUIControl::RegisterClientSideControl(string attributeClassName, string controlClassName)
0x1f80f  ret
```
