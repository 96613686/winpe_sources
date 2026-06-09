# Microsoft.Crm.Application.Components.UI.Select::ConfigureHeader

- ea: `0x26650`
- end: `0x26748`
- name: `Microsoft.Crm.Application.Components.UI.Select::ConfigureHeader`
- size: `248`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callees

- `0x3380`
- `0x38d0`
- `0x39f0`
- `0x238a0`
- `0x238d0`
- `0x23b60`
- `0x23c50`
- `0x23f10`
- `0x24280`
- `0x264b0`
- `0x26600`
- `0x26650`

## string_xrefs

- `0x2665c`: `/_common/styles/select.css.aspx`

## pseudocode

```c

```

## disassembly

```asm
0x26650  ldarg.0
0x26651  call     instance void Microsoft.Crm.Application.Components.UI.CrmFormUIControl::ConfigureHeader()
0x26656  ldarg.0
0x26657  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x2665c  ldstr    aCommonStylesSe// "/_common/styles/select.css.aspx"
0x26661  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string file)
0x26666  ldarg.0
0x26667  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x2666c  ldstr    aStaticFormsSel// "/_static/_forms/select.js"
0x26671  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string file)
0x26676  ldarg.0
0x26677  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x2667c  ldstr    aLocidDeverrorB_2// "LOCID_DEVERROR_BADTYPE_PICKLIST"
0x26681  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x26686  ldstr    aDeverrorBaddat_3// "DevError.BadDataType.Picklist"
0x2668b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x26690  ldc.i4.0
0x26691  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x26696  ldarg.0
0x26697  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x2669c  ldstr    aLocidDeverrorB_0// "LOCID_DEVERROR_BADDATATYPE_BOOL"
0x266a1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x266a6  ldstr    aDeverrorBaddat_1// "DevError.BadDataType.Boolean"
0x266ab  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x266b0  ldc.i4.0
0x266b1  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x266b6  ldarg.0
0x266b7  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x266bc  ldstr    aLocidSelectbox// "LOCID_SELECTBOX_BUTTON_ALT"
0x266c1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x266c6  ldstr    aSelectButtonAl// "Select.Button.AltTag"
0x266cb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x266d0  ldc.i4.0
0x266d1  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x266d6  ldarg.0
0x266d7  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControl::get_ReadOnly()
0x266dc  brtrue.s loc_2670C
0x266de  ldarg.0
0x266df  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x266e4  brfalse.s loc_2670C
0x266e6  ldarg.0
0x266e7  ldarg.0
0x266e8  call     instance string Microsoft.Crm.Application.Components.UI.Select::get_ClientSideFormInputBehaviorClassName()
0x266ed  ldnull
0x266ee  ldnull
0x266ef  ldnull
0x266f0  ldarg.0
0x266f1  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x266f6  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::RegisterClientAjaxComponent(string componentTypeName, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> events, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> references, string elementId)
0x266fb  ldarg.0
0x266fc  ldarg.0
0x266fd  call     instance string Microsoft.Crm.Application.Components.UI.Select::get_ClientSideAttributeClassName()
0x26702  ldstr    aMscrmOptionset_0// "Mscrm.OptionSetUIControl"
0x26707  call     instance void Microsoft.Crm.Application.Components.UI.CrmFormUIControl::RegisterClientSideControl(string attributeClassName, string controlClassName)
0x2670c  ldarg.0
0x2670d  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.Crm.Application.Components.UI.Select::_optionGroups
0x26712  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x26717  stloc.0
0x26718  br.s     loc_2672C
0x2671a  ldloc.0
0x2671b  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x26720  castclass Microsoft.Crm.Application.Components.UI.OptionGroup
0x26725  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x2672a  leave.s  loc_26747
0x2672c  ldloc.0
0x2672d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x26732  brtrue.s loc_2671A
0x26734  leave.s  loc_26747
0x26736  ldloc.0
0x26737  isinst   [mscorlib]System.IDisposable
0x2673c  stloc.1
0x2673d  ldloc.1
0x2673e  brfalse.s loc_26746
0x26740  ldloc.1
0x26741  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x26746  endfinally
0x26747  ret
```
