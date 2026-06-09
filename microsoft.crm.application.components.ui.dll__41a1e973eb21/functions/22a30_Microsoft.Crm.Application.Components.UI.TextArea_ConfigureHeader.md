# Microsoft.Crm.Application.Components.UI.TextArea::ConfigureHeader

- ea: `0x22a30`
- end: `0x22ab1`
- name: `Microsoft.Crm.Application.Components.UI.TextArea::ConfigureHeader`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x3380`
- `0x38d0`
- `0x229f0`
- `0x22a10`
- `0x22a30`
- `0x238a0`
- `0x238c0`
- `0x23b60`
- `0x23f10`

## pseudocode

```c

```

## disassembly

```asm
0x22a30  ldarg.0
0x22a31  call     instance void Microsoft.Crm.Application.Components.UI.CrmFormUIControl::ConfigureHeader()
0x22a36  ldarg.0
0x22a37  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x22a3c  ldstr    aLocidDeverrorB_1// "LOCID_DEVERROR_BADTYPE_STRING"
0x22a41  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x22a46  ldstr    aDeverrorBaddat_2// "DevError.BadDataType.String"
0x22a4b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x22a50  ldc.i4.0
0x22a51  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x22a56  ldarg.0
0x22a57  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x22a5c  ldstr    aLocidExceededM// "LOCID_EXCEEDED_MAX_CHARS_MASK"
0x22a61  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x22a66  ldstr    aWebFormsStyles_5// "Web._forms.styles.TEXTAREA.htc_11_0"
0x22a6b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x22a70  ldc.i4.0
0x22a71  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x22a76  ldarg.0
0x22a77  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x22a7c  ldstr    aStaticFormsTex_0// "/_static/_forms/TextInputBehavior.js"
0x22a81  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string file)
0x22a86  ldarg.0
0x22a87  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x22a8c  brtrue.s loc_22A8F
0x22a8e  ret
0x22a8f  ldarg.0
0x22a90  ldarg.0
0x22a91  call     instance string Microsoft.Crm.Application.Components.UI.TextArea::get_ClientSideFormInputBehaviorClassName()
0x22a96  ldnull
0x22a97  ldnull
0x22a98  ldnull
0x22a99  ldarg.0
0x22a9a  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x22a9f  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::RegisterClientAjaxComponent(string componentTypeName, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> events, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> references, string elementId)
0x22aa4  ldarg.0
0x22aa5  ldarg.0
0x22aa6  call     instance string Microsoft.Crm.Application.Components.UI.TextArea::get_ClientSideAttributeClassName()
0x22aab  call     instance void Microsoft.Crm.Application.Components.UI.CrmFormUIControl::RegisterClientSideControl(string attributeClassName)
0x22ab0  ret
```
