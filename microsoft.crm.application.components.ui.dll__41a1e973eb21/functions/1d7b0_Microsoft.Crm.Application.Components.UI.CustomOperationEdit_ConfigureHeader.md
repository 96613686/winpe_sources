# Microsoft.Crm.Application.Components.UI.CustomOperationEdit::ConfigureHeader

- ea: `0x1d7b0`
- end: `0x1d9d1`
- name: `Microsoft.Crm.Application.Components.UI.CustomOperationEdit::ConfigureHeader`
- size: `545`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callees

- `0x3380`
- `0x38d0`
- `0x39f0`
- `0x178e0`
- `0x1d1c0`
- `0x1d370`
- `0x1e6e0`
- `0x210c0`
- `0x22890`
- `0x22d20`
- `0x23b60`
- `0x23c50`
- `0x23f10`
- `0x24080`
- `0x26750`

## string_xrefs

- `0x1d99a`: `messageXml`
- `0x1d9ab`: `initialXml`
- `0x1d7cc`: `/_static/_common/scripts/select.js`

## pseudocode

```c

```

## disassembly

```asm
0x1d7b0  ldarg.0
0x1d7b1  call     instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::ConfigureHeader()
0x1d7b6  ldarg.0
0x1d7b7  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1d7bc  ldstr    aControlsListed// "/_controls/listedit/picklistedit.css.as"...
0x1d7c1  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string file)
0x1d7c6  ldarg.0
0x1d7c7  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1d7cc  ldstr    aStaticCommonSc_44// "/_static/_common/scripts/select.js"
0x1d7d1  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string file)
0x1d7d6  ldarg.0
0x1d7d7  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1d7dc  ldstr    aStaticFormsSel_1// "/_static/_forms/selectbehavior.js"
0x1d7e1  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string file)
0x1d7e6  ldarg.0
0x1d7e7  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1d7ec  ldstr    aLocidMaxPickli// "LOCID_MAX_PICKLIST_VALUE"
0x1d7f1  ldarg.0
0x1d7f2  ldstr    aReachedMaxPick// "Reached_Max_Picklist_Value"
0x1d7f7  call     instance string Microsoft.Crm.Application.Components.UI.CustomOperationEdit::GetResourceString(string key)
0x1d7fc  ldc.i4.0
0x1d7fd  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x1d802  ldarg.0
0x1d803  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1d808  ldstr    aLocidAboveMaxP// "LOCID_ABOVE_MAX_PICKLIST_VALUE"
0x1d80d  ldarg.0
0x1d80e  ldstr    aReachedAboveMa// "Reached_Above_Max_Picklist_Value"
0x1d813  call     instance string Microsoft.Crm.Application.Components.UI.CustomOperationEdit::GetResourceString(string key)
0x1d818  ldc.i4.0
0x1d819  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x1d81e  ldarg.0
0x1d81f  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1d824  ldstr    aLocidPicklistD// "LOCID_PICKLIST_DEFAULT_LABEL"
0x1d829  ldarg.0
0x1d82a  ldstr    aWebControlsPic// "Web._controls.picklistedit.item.default"...
0x1d82f  call     instance string Microsoft.Crm.Application.Components.UI.CustomOperationEdit::GetResourceString(string key)
0x1d834  ldc.i4.0
0x1d835  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x1d83a  ldarg.0
0x1d83b  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1d840  ldstr    aLocidValueNotU// "LOCID_VALUE_NOT_UNIQUE"
0x1d845  ldarg.0
0x1d846  ldstr    aSystemcustomiz_0// "SystemCustomization.Validation.Errors.P"...
0x1d84b  call     instance string Microsoft.Crm.Application.Components.UI.CustomOperationEdit::GetResourceString(string key)
0x1d850  ldc.i4.0
0x1d851  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x1d856  ldarg.0
0x1d857  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1d85c  ldstr    aLocidArgumentn// "LOCID_ARGUMENTNAME_ERRORMESSAGE"
0x1d861  ldarg.0
0x1d862  ldstr    aArgumentnameEr// "ArgumentName.ErrorMessage"
0x1d867  call     instance string Microsoft.Crm.Application.Components.UI.CustomOperationEdit::GetResourceString(string key)
0x1d86c  ldc.i4.0
0x1d86d  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x1d872  ldarg.0
0x1d873  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1d878  ldstr    aLocidEntity// "LOCID_ENTITY"
0x1d87d  ldarg.0
0x1d87e  ldstr    aArgumenttypeEn// "ArgumentType.Entity"
0x1d883  call     instance string Microsoft.Crm.Application.Components.UI.CustomOperationEdit::GetResourceString(string key)
0x1d888  ldc.i4.0
0x1d889  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x1d88e  ldarg.0
0x1d88f  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1d894  ldstr    aLocidEntityRef// "LOCID_ENTITY_REFERENCE"
0x1d899  ldarg.0
0x1d89a  ldstr    aArgumenttypeEn_0// "ArgumentType.EntityReference"
0x1d89f  call     instance string Microsoft.Crm.Application.Components.UI.CustomOperationEdit::GetResourceString(string key)
0x1d8a4  ldc.i4.0
0x1d8a5  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x1d8aa  ldarg.0
0x1d8ab  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1d8b0  ldstr    aLocidInputArgu// "LOCID_INPUT_ARGUMENT"
0x1d8b5  ldarg.0
0x1d8b6  ldstr    aWebControlsCus// "Web._controls.customoperationedit.item."...
0x1d8bb  call     instance string Microsoft.Crm.Application.Components.UI.CustomOperationEdit::GetResourceString(string key)
0x1d8c0  ldc.i4.0
0x1d8c1  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x1d8c6  ldarg.0
0x1d8c7  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1d8cc  ldstr    aLocidOutputArg// "LOCID_OUTPUT_ARGUMENT"
0x1d8d1  ldarg.0
0x1d8d2  ldstr    aWebControlsCus_0// "Web._controls.customoperationedit.item."...
0x1d8d7  call     instance string Microsoft.Crm.Application.Components.UI.CustomOperationEdit::GetResourceString(string key)
0x1d8dc  ldc.i4.0
0x1d8dd  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x1d8e2  ldarg.0
0x1d8e3  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1d8e8  ldstr    aLocidRequiredA// "LOCID_REQUIRED_ARGUMENT"
0x1d8ed  ldarg.0
0x1d8ee  ldstr    aWebControlsCus_1// "Web._controls.customoperationedit.item."...
0x1d8f3  call     instance string Microsoft.Crm.Application.Components.UI.CustomOperationEdit::GetResourceString(string key)
0x1d8f8  ldc.i4.0
0x1d8f9  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x1d8fe  ldarg.0
0x1d8ff  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1d904  ldstr    aLocidOptionalA// "LOCID_OPTIONAL_ARGUMENT"
0x1d909  ldarg.0
0x1d90a  ldstr    aWebControlsCus_2// "Web._controls.customoperationedit.item."...
0x1d90f  call     instance string Microsoft.Crm.Application.Components.UI.CustomOperationEdit::GetResourceString(string key)
0x1d914  ldc.i4.0
0x1d915  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x1d91a  ldarg.0
0x1d91b  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1d920  ldstr    aLocidArgumentD// "LOCID_ARGUMENT_DESCRIPTION_TEXT"
0x1d925  ldarg.0
0x1d926  ldstr    aWebControlsCus_3// "Web._controls.customoperationedit.item."...
0x1d92b  call     instance string Microsoft.Crm.Application.Components.UI.CustomOperationEdit::GetResourceString(string key)
0x1d930  ldc.i4.0
0x1d931  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x1d936  ldarg.0
0x1d937  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1d93c  ldstr    aLocidEntityinp// "LOCID_ENTITYINPUTARGNAME_ERRMSG"
0x1d941  ldarg.0
0x1d942  ldstr    aEntityargument// "EntityArgumentName.ErrorMessage"
0x1d947  call     instance string Microsoft.Crm.Application.Components.UI.CustomOperationEdit::GetResourceString(string key)
0x1d94c  ldc.i4.0
0x1d94d  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x1d952  ldarg.0
0x1d953  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1d958  ldstr    aStaticControls_67// "/_static/_controls/ListEdit/CustomOpera"...
0x1d95d  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string file)
0x1d962  newobj   instance void Microsoft.Crm.Application.Components.UI.EditableSelect::.ctor()
0x1d967  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x1d96c  newobj   instance void Microsoft.Crm.Application.Components.UI.Radio::.ctor()
0x1d971  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x1d976  newobj   instance void Microsoft.Crm.Application.Components.UI.Select::.ctor()
0x1d97b  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x1d980  newobj   instance void Microsoft.Crm.Application.Components.UI.TextArea::.ctor()
0x1d985  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x1d98a  newobj   instance void Microsoft.Crm.Application.Components.UI.TextBox::.ctor()
0x1d98f  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x1d994  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x1d999  dup
0x1d99a  ldstr    aMessagexml// "messageXml"
0x1d99f  ldarg.0
0x1d9a0  call     instance string Microsoft.Crm.Application.Components.UI.CustomOperationEdit::get_MessageXml()
0x1d9a5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x1d9aa  dup
0x1d9ab  ldstr    aInitialxml// "initialXml"
0x1d9b0  ldarg.0
0x1d9b1  call     instance string Microsoft.Crm.Application.Components.UI.CustomOperationEdit::get_DataXml()
0x1d9b6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x1d9bb  stloc.0
0x1d9bc  ldarg.0
0x1d9bd  ldstr    aMscrmCustomope// "Mscrm.CustomOperationEdit"
0x1d9c2  ldloc.0
0x1d9c3  ldnull
0x1d9c4  ldnull
0x1d9c5  ldarg.0
0x1d9c6  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1d9cb  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::RegisterClientAjaxComponent(string componentTypeName, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> events, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> references, string elementId)
0x1d9d0  ret
```
