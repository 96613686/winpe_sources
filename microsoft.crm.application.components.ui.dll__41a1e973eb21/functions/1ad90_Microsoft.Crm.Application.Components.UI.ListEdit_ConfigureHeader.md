# Microsoft.Crm.Application.Components.UI.ListEdit::ConfigureHeader

- ea: `0x1ad90`
- end: `0x1ae5d`
- name: `Microsoft.Crm.Application.Components.UI.ListEdit::ConfigureHeader`
- size: `205`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x3380`
- `0x38d0`
- `0x39f0`
- `0x1a8f0`
- `0x1aa80`
- `0x23b60`
- `0x23c50`
- `0x23f10`
- `0x24080`
- `0x26750`

## string_xrefs

- `0x1adbc`: `/_static/_common/styles/AutoToolTip.js`
- `0x1ae1c`: `messageXml`
- `0x1ae2d`: `initialXml`

## pseudocode

```c

```

## disassembly

```asm
0x1ad90  ldarg.0
0x1ad91  call     instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::ConfigureHeader()
0x1ad96  ldarg.0
0x1ad97  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1ad9c  ldstr    aStaticControls_64// "/_static/_controls/listedit/listedit.cs"...
0x1ada1  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string file)
0x1ada6  ldarg.0
0x1ada7  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1adac  ldstr    aStaticFormsSel// "/_static/_forms/select.js"
0x1adb1  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string file)
0x1adb6  ldarg.0
0x1adb7  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1adbc  ldstr    aStaticCommonSt// "/_static/_common/styles/AutoToolTip.js"
0x1adc1  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string file)
0x1adc6  ldarg.0
0x1adc7  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1adcc  ldstr    aStaticControls_65// "/_static/_controls/ListEdit/ListEdit.js"
0x1add1  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string file)
0x1add6  ldarg.0
0x1add7  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1addc  ldstr    aLocidMaxPickli// "LOCID_MAX_PICKLIST_VALUE"
0x1ade1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1ade6  ldstr    aReachedMaxPick// "Reached_Max_Picklist_Value"
0x1adeb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1adf0  ldc.i4.0
0x1adf1  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x1adf6  ldarg.0
0x1adf7  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1adfc  ldstr    aLocidAboveMaxP// "LOCID_ABOVE_MAX_PICKLIST_VALUE"
0x1ae01  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1ae06  ldstr    aReachedAboveMa// "Reached_Above_Max_Picklist_Value"
0x1ae0b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1ae10  ldc.i4.0
0x1ae11  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x1ae16  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x1ae1b  dup
0x1ae1c  ldstr    aMessagexml// "messageXml"
0x1ae21  ldarg.0
0x1ae22  call     instance string Microsoft.Crm.Application.Components.UI.ListEdit::get_MessageXml()
0x1ae27  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x1ae2c  dup
0x1ae2d  ldstr    aInitialxml// "initialXml"
0x1ae32  ldarg.0
0x1ae33  call     instance string Microsoft.Crm.Application.Components.UI.ListEdit::get_DataXml()
0x1ae38  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x1ae3d  stloc.0
0x1ae3e  ldarg.0
0x1ae3f  ldstr    aMscrmListedit// "Mscrm.ListEdit"
0x1ae44  ldloc.0
0x1ae45  ldnull
0x1ae46  ldnull
0x1ae47  ldarg.0
0x1ae48  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1ae4d  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::RegisterClientAjaxComponent(string componentTypeName, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> events, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> references, string elementId)
0x1ae52  newobj   instance void Microsoft.Crm.Application.Components.UI.Select::.ctor()
0x1ae57  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x1ae5c  ret
```
