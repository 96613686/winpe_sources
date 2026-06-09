# Microsoft.Crm.Application.Components.UI.PicklistEdit::ConfigureHeader

- ea: `0x1bd00`
- end: `0x1be12`
- name: `Microsoft.Crm.Application.Components.UI.PicklistEdit::ConfigureHeader`
- size: `274`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callees

- `0x2ef0`
- `0x3380`
- `0x38d0`
- `0x39f0`
- `0x1b6f0`
- `0x1b8a0`
- `0x1c7b0`
- `0x210c0`
- `0x23b60`
- `0x23c50`
- `0x23f10`
- `0x24080`

## string_xrefs

- `0x1bddb`: `messageXml`
- `0x1bdec`: `initialXml`

## pseudocode

```c

```

## disassembly

```asm
0x1bd00  ldarg.0
0x1bd01  call     instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::ConfigureHeader()
0x1bd06  ldarg.0
0x1bd07  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1bd0c  ldstr    aControlsListed// "/_controls/listedit/picklistedit.css.as"...
0x1bd11  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string file)
0x1bd16  ldarg.0
0x1bd17  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1bd1c  ldstr    aStaticFormsSel// "/_static/_forms/select.js"
0x1bd21  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string file)
0x1bd26  ldarg.0
0x1bd27  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1bd2c  ldstr    aLocidMaxPickli// "LOCID_MAX_PICKLIST_VALUE"
0x1bd31  ldarg.0
0x1bd32  ldstr    aReachedMaxPick// "Reached_Max_Picklist_Value"
0x1bd37  call     instance string Microsoft.Crm.Application.Components.UI.PicklistEdit::GetResourceString(string key)
0x1bd3c  ldc.i4.0
0x1bd3d  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x1bd42  ldarg.0
0x1bd43  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1bd48  ldstr    aLocidAboveMaxP// "LOCID_ABOVE_MAX_PICKLIST_VALUE"
0x1bd4d  ldarg.0
0x1bd4e  ldstr    aReachedAboveMa// "Reached_Above_Max_Picklist_Value"
0x1bd53  call     instance string Microsoft.Crm.Application.Components.UI.PicklistEdit::GetResourceString(string key)
0x1bd58  ldc.i4.0
0x1bd59  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x1bd5e  ldarg.0
0x1bd5f  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1bd64  ldstr    aLocidPicklistD// "LOCID_PICKLIST_DEFAULT_LABEL"
0x1bd69  ldarg.0
0x1bd6a  ldstr    aWebControlsPic// "Web._controls.picklistedit.item.default"...
0x1bd6f  call     instance string Microsoft.Crm.Application.Components.UI.PicklistEdit::GetResourceString(string key)
0x1bd74  ldc.i4.0
0x1bd75  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x1bd7a  ldarg.0
0x1bd7b  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1bd80  ldstr    aLocidValueNotU// "LOCID_VALUE_NOT_UNIQUE"
0x1bd85  ldarg.0
0x1bd86  ldstr    aSystemcustomiz_0// "SystemCustomization.Validation.Errors.P"...
0x1bd8b  call     instance string Microsoft.Crm.Application.Components.UI.PicklistEdit::GetResourceString(string key)
0x1bd90  ldc.i4.0
0x1bd91  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x1bd96  ldarg.0
0x1bd97  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1bd9c  ldstr    aStaticControls_65// "/_static/_controls/ListEdit/ListEdit.js"
0x1bda1  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string file)
0x1bda6  ldarg.0
0x1bda7  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1bdac  ldstr    aStaticToolsSys_0// "/_static/tools/systemcustomization/scri"...
0x1bdb1  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string file)
0x1bdb6  ldarg.0
0x1bdb7  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1bdbc  ldstr    aPicklisteditis// "picklistEditIsFor"
0x1bdc1  ldstr    aOptionsetdialo// "optionsetDialog"
0x1bdc6  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, string varValue)
0x1bdcb  newobj   instance void Microsoft.Crm.Application.Components.UI.Radio::.ctor()
0x1bdd0  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x1bdd5  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x1bdda  dup
0x1bddb  ldstr    aMessagexml// "messageXml"
0x1bde0  ldarg.0
0x1bde1  call     instance string Microsoft.Crm.Application.Components.UI.PicklistEdit::get_MessageXml()
0x1bde6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x1bdeb  dup
0x1bdec  ldstr    aInitialxml// "initialXml"
0x1bdf1  ldarg.0
0x1bdf2  call     instance string Microsoft.Crm.Application.Components.UI.PicklistEdit::get_DataXml()
0x1bdf7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x1bdfc  stloc.0
0x1bdfd  ldarg.0
0x1bdfe  ldstr    aMscrmListedit// "Mscrm.ListEdit"
0x1be03  ldloc.0
0x1be04  ldnull
0x1be05  ldnull
0x1be06  ldarg.0
0x1be07  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1be0c  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::RegisterClientAjaxComponent(string componentTypeName, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> events, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> references, string elementId)
0x1be11  ret
```
