# Microsoft.Crm.Application.Components.UI.MocaDateTimeUI::ConfigureHeaderInternal

- ea: `0x16a90`
- end: `0x16b2c`
- name: `Microsoft.Crm.Application.Components.UI.MocaDateTimeUI::ConfigureHeaderInternal`
- size: `156`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x2450`
- `0x3380`
- `0x39f0`
- `0x16790`
- `0x16990`
- `0x169b0`
- `0x16a90`
- `0x238c0`
- `0x23b60`
- `0x23f10`

## string_xrefs

- `0x16afb`: `initComplete`
- `0x16aa2`: `/_common/styles/touchControls.css.aspx`

## pseudocode

```c

```

## disassembly

```asm
0x16a90  ldarg.0
0x16a91  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x16a96  ldc.i4.1
0x16a97  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::set_LoadJQuery(bool value)
0x16a9c  ldarg.0
0x16a9d  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x16aa2  ldstr    aCommonStylesTo// "/_common/styles/touchControls.css.aspx"
0x16aa7  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string file)
0x16aac  ldarg.0
0x16aad  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x16ab2  ldstr    aStaticControls_62// "/_static/_controls/datetimescroller/dat"...
0x16ab7  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string file)
0x16abc  ldarg.0
0x16abd  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x16ac2  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x16ac7  brtrue.s loc_16B2B
0x16ac9  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x16ace  stloc.0
0x16acf  ldarg.0
0x16ad0  call     instance string Microsoft.Crm.Application.Components.UI.DateTimeUIBase::get_OnChangeScript()
0x16ad5  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x16ada  brtrue.s loc_16AED
0x16adc  ldloc.0
0x16add  ldstr    aChange// "change"
0x16ae2  ldarg.0
0x16ae3  call     instance string Microsoft.Crm.Application.Components.UI.DateTimeUIBase::get_OnChangeScript()
0x16ae8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x16aed  ldarg.0
0x16aee  call     instance string Microsoft.Crm.Application.Components.UI.DateTimeUIBase::get_OnInitCompleteScript()
0x16af3  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x16af8  brtrue.s loc_16B0B
0x16afa  ldloc.0
0x16afb  ldstr    aInitcomplete// "initComplete"
0x16b00  ldarg.0
0x16b01  call     instance string Microsoft.Crm.Application.Components.UI.DateTimeUIBase::get_OnInitCompleteScript()
0x16b06  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x16b0b  ldarg.0
0x16b0c  ldarg.0
0x16b0d  callvirt instance string Microsoft.Crm.Application.Components.UI.DateTimeUIBase::get_ClientSideFormInputBehaviorClassName()
0x16b12  ldnull
0x16b13  ldnull
0x16b14  ldnull
0x16b15  ldarg.0
0x16b16  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x16b1b  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::RegisterClientAjaxComponent(string componentTypeName, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> events, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> references, string elementId)
0x16b20  ldarg.0
0x16b21  ldstr    aMscrmDatetimea// "Mscrm.DateTimeAttribute"
0x16b26  call     instance void Microsoft.Crm.Application.Components.UI.CrmFormUIControl::RegisterClientSideControl(string attributeClassName)
0x16b2b  ret
```
