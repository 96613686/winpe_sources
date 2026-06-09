# Microsoft.Crm.Application.Components.UI.PicklistMappingEdit::ConfigureHeader

- ea: `0x1ccf0`
- end: `0x1cd62`
- name: `Microsoft.Crm.Application.Components.UI.PicklistMappingEdit::ConfigureHeader`
- size: `114`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x3380`
- `0x39f0`
- `0x1cb10`
- `0x23b60`
- `0x23f10`
- `0x24080`

## string_xrefs

- `0x1cd3c`: `initialXml`

## pseudocode

```c

```

## disassembly

```asm
0x1ccf0  ldarg.0
0x1ccf1  call     instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::ConfigureHeader()
0x1ccf6  ldarg.0
0x1ccf7  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1ccfc  ldstr    aControlsListed_0// "/_controls/listedit/PicklistEdit.css.as"...
0x1cd01  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string file)
0x1cd06  ldarg.0
0x1cd07  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1cd0c  ldstr    aStaticFormsSel// "/_static/_forms/select.js"
0x1cd11  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string file)
0x1cd16  ldarg.0
0x1cd17  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1cd1c  ldstr    aStaticControls_66// "/_static/_controls/PickListMappingEdit/"...
0x1cd21  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string file)
0x1cd26  ldarg.0
0x1cd27  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1cd2c  ldstr    aStaticToolsSys_0// "/_static/tools/systemcustomization/scri"...
0x1cd31  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string file)
0x1cd36  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x1cd3b  dup
0x1cd3c  ldstr    aInitialxml// "initialXml"
0x1cd41  ldarg.0
0x1cd42  call     instance string Microsoft.Crm.Application.Components.UI.PicklistMappingEdit::get_DataXml()
0x1cd47  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x1cd4c  stloc.0
0x1cd4d  ldarg.0
0x1cd4e  ldstr    aMscrmPicklistm// "Mscrm.PickListMappingEdit"
0x1cd53  ldloc.0
0x1cd54  ldnull
0x1cd55  ldnull
0x1cd56  ldarg.0
0x1cd57  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1cd5c  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::RegisterClientAjaxComponent(string componentTypeName, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> events, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> references, string elementId)
0x1cd61  ret
```
