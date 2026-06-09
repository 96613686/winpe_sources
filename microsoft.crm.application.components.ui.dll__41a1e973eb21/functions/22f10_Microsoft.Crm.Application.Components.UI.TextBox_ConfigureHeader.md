# Microsoft.Crm.Application.Components.UI.TextBox::ConfigureHeader

- ea: `0x22f10`
- end: `0x22fb1`
- name: `Microsoft.Crm.Application.Components.UI.TextBox::ConfigureHeader`
- size: `161`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x3380`
- `0x38d0`
- `0x22d50`
- `0x22d70`
- `0x22f10`
- `0x238a0`
- `0x238c0`
- `0x23b60`
- `0x23f10`

## pseudocode

```c

```

## disassembly

```asm
0x22f10  ldarg.0
0x22f11  call     instance void Microsoft.Crm.Application.Components.UI.CrmFormUIControl::ConfigureHeader()
0x22f16  ldarg.0
0x22f17  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x22f1c  ldstr    aLocidDeverrorB_1// "LOCID_DEVERROR_BADTYPE_STRING"
0x22f21  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x22f26  ldstr    aDeverrorBaddat_2// "DevError.BadDataType.String"
0x22f2b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x22f30  ldc.i4.0
0x22f31  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x22f36  ldarg.0
0x22f37  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x22f3c  ldstr    aLocidDeverrorT// "LOCID_DEVERROR_TOO_LONG"
0x22f41  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x22f46  ldstr    aErrorMessage0x_3// "Error_Message_0x80044331"
0x22f4b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x22f50  ldc.i4.0
0x22f51  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x22f56  ldarg.0
0x22f57  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x22f5c  ldstr    aLocidMaxlength// "LOCID_MAXLENGTH_EXCEEDED"
0x22f61  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x22f66  ldstr    aNotesMaxlength// "Notes_MAXLENGTH_EXCEEDED"
0x22f6b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x22f70  ldc.i4.0
0x22f71  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x22f76  ldarg.0
0x22f77  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x22f7c  ldstr    aStaticFormsTex_0// "/_static/_forms/TextInputBehavior.js"
0x22f81  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string file)
0x22f86  ldarg.0
0x22f87  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x22f8c  brtrue.s loc_22F8F
0x22f8e  ret
0x22f8f  ldarg.0
0x22f90  ldarg.0
0x22f91  call     instance string Microsoft.Crm.Application.Components.UI.TextBox::get_ClientSideFormInputBehaviorClassName()
0x22f96  ldnull
0x22f97  ldnull
0x22f98  ldnull
0x22f99  ldarg.0
0x22f9a  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x22f9f  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::RegisterClientAjaxComponent(string componentTypeName, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> events, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> references, string elementId)
0x22fa4  ldarg.0
0x22fa5  ldarg.0
0x22fa6  call     instance string Microsoft.Crm.Application.Components.UI.TextBox::get_ClientSideAttributeClassName()
0x22fab  call     instance void Microsoft.Crm.Application.Components.UI.CrmFormUIControl::RegisterClientSideControl(string attributeClassName)
0x22fb0  ret
```
