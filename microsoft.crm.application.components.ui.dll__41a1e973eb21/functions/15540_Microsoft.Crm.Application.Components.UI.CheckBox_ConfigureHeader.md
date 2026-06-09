# Microsoft.Crm.Application.Components.UI.CheckBox::ConfigureHeader

- ea: `0x15540`
- end: `0x155b7`
- name: `Microsoft.Crm.Application.Components.UI.CheckBox::ConfigureHeader`
- size: `119`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x3380`
- `0x38d0`
- `0x15540`
- `0x155c0`
- `0x15600`
- `0x15620`
- `0x238a0`
- `0x238c0`
- `0x23b60`
- `0x23f10`

## pseudocode

```c

```

## disassembly

```asm
0x15540  ldarg.0
0x15541  call     instance void Microsoft.Crm.Application.Components.UI.CrmFormUIControl::ConfigureHeader()
0x15546  ldarg.0
0x15547  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1554c  ldstr    aLocidDeverrorB_0// "LOCID_DEVERROR_BADDATATYPE_BOOL"
0x15551  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x15556  ldstr    aDeverrorBaddat_1// "DevError.BadDataType.Boolean"
0x1555b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x15560  ldc.i4.0
0x15561  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x15566  ldarg.0
0x15567  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1556c  ldstr    aStaticFormsChe_0// "/_static/_forms/checkbox.js"
0x15571  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string file)
0x15576  ldarg.0
0x15577  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1557c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x15581  brtrue.s loc_155B6
0x15583  ldarg.0
0x15584  call     instance string Microsoft.Crm.Application.Components.UI.CheckBox::get_ClassName()
0x15589  ldstr    aMsCrmCheckbox// "ms-crm-CheckBox"
0x1558e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x15593  brfalse.s loc_155AA
0x15595  ldarg.0
0x15596  ldarg.0
0x15597  call     instance string Microsoft.Crm.Application.Components.UI.CheckBox::get_ClientSideFormInputBehaviorClassName()
0x1559c  ldnull
0x1559d  ldnull
0x1559e  ldnull
0x1559f  ldarg.0
0x155a0  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x155a5  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::RegisterClientAjaxComponent(string componentTypeName, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> events, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> references, string elementId)
0x155aa  ldarg.0
0x155ab  ldarg.0
0x155ac  call     instance string Microsoft.Crm.Application.Components.UI.CheckBox::get_ClientSideAttributeClassName()
0x155b1  call     instance void Microsoft.Crm.Application.Components.UI.CrmFormUIControl::RegisterClientSideControl(string attributeClassName)
0x155b6  ret
```
