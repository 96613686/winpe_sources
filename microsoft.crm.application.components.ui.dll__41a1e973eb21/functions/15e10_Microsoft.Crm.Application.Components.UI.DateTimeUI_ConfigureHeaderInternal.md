# Microsoft.Crm.Application.Components.UI.DateTimeUI::ConfigureHeaderInternal

- ea: `0x15e10`
- end: `0x15fee`
- name: `Microsoft.Crm.Application.Components.UI.DateTimeUI::ConfigureHeaderInternal`
- size: `478`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callees

- `0x38d0`
- `0x39f0`
- `0x15e10`
- `0x16790`
- `0x167a0`
- `0x16990`
- `0x169b0`
- `0x178e0`
- `0x238c0`
- `0x23b60`
- `0x23c50`
- `0x23ef0`
- `0x23f00`
- `0x23f10`

## string_xrefs

- `0x15e50`: `DateTime_Control_ScreenReader_Label`
- `0x15e16`: `/_common/styles/miniCal.css.aspx`
- `0x15fbd`: `initComplete`

## pseudocode

```c

```

## disassembly

```asm
0x15e10  ldarg.0
0x15e11  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x15e16  ldstr    aCommonStylesMi// "/_common/styles/miniCal.css.aspx"
0x15e1b  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string file)
0x15e20  ldarg.0
0x15e21  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x15e26  ldstr    aLocidDateSelec// "LOCID_DATE_SELECT_DATE"
0x15e2b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x15e30  ldstr    aWebFormsStyles_2// "Web._forms.styles.IMG.dtm.htc_27_0"
0x15e35  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x15e3a  ldc.i4.0
0x15e3b  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x15e40  ldarg.0
0x15e41  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x15e46  ldstr    aLocidDatetimeC// "LOCID_DATETIME_CONTROL_FORMAT"
0x15e4b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x15e50  ldstr    aDatetimeContro// "DateTime_Control_ScreenReader_Label"
0x15e55  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x15e5a  ldc.i4.0
0x15e5b  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x15e60  ldarg.0
0x15e61  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x15e66  ldstr    aLocidSelectbox// "LOCID_SELECTBOX_BUTTON_ALT"
0x15e6b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x15e70  ldstr    aSelectButtonAl// "Select.Button.AltTag"
0x15e75  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x15e7a  ldc.i4.0
0x15e7b  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x15e80  ldarg.0
0x15e81  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x15e86  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x15e8b  brtrue.s loc_15EE4
0x15e8d  ldarg.0
0x15e8e  call     instance string Microsoft.Crm.Application.Components.UI.DateTimeUIBase::get_DisplayFormat()
0x15e93  ldstr    aDate// "date"
0x15e98  call     bool [mscorlib]System.String::op_Equality(string, string)
0x15e9d  brtrue.s loc_15EB1
0x15e9f  ldarg.0
0x15ea0  call     instance string Microsoft.Crm.Application.Components.UI.DateTimeUIBase::get_DisplayFormat()
0x15ea5  ldstr    aDatetime// "datetime"
0x15eaa  call     bool [mscorlib]System.String::op_Equality(string, string)
0x15eaf  brfalse.s loc_15EE4
0x15eb1  ldarg.0
0x15eb2  ldstr    aMscrmForminput_7// "Mscrm.FormInputControl.DateTimeImage"
0x15eb7  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x15ebc  dup
0x15ebd  ldstr    aDatetimecontro// "dateTimeControlId"
0x15ec2  ldarg.0
0x15ec3  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x15ec8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x15ecd  ldnull
0x15ece  ldnull
0x15ecf  ldarg.0
0x15ed0  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x15ed5  ldstr    aImg_0// "img"
0x15eda  call     string [mscorlib]System.String::Concat(string, string)
0x15edf  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::RegisterClientAjaxComponent(string componentTypeName, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> events, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> references, string elementId)
0x15ee4  ldarg.0
0x15ee5  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x15eea  ldstr    aLocidSelectbox// "LOCID_SELECTBOX_BUTTON_ALT"
0x15eef  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x15ef4  ldstr    aSelectButtonAl// "Select.Button.AltTag"
0x15ef9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x15efe  ldc.i4.0
0x15eff  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x15f04  ldarg.0
0x15f05  call     instance string Microsoft.Crm.Application.Components.UI.DateTimeUIBase::get_DisplayFormat()
0x15f0a  ldstr    aTime// "time"
0x15f0f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x15f14  brtrue.s loc_15F28
0x15f16  ldarg.0
0x15f17  call     instance string Microsoft.Crm.Application.Components.UI.DateTimeUIBase::get_DisplayFormat()
0x15f1c  ldstr    aDatetime// "datetime"
0x15f21  call     bool [mscorlib]System.String::op_Equality(string, string)
0x15f26  brfalse.s loc_15F7E
0x15f28  ldarg.0
0x15f29  newobj   instance void Microsoft.Crm.Application.Components.UI.EditableSelect::.ctor()
0x15f2e  stfld    class Microsoft.Crm.Application.Components.UI.EditableSelect Microsoft.Crm.Application.Components.UI.DateTimeUI::_select
0x15f33  ldarg.0
0x15f34  ldfld    class Microsoft.Crm.Application.Components.UI.EditableSelect Microsoft.Crm.Application.Components.UI.DateTimeUI::_select
0x15f39  ldarg.0
0x15f3a  call     instance bool Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_AutoRegisterClientComponent()
0x15f3f  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_AutoRegisterClientComponent(bool value)
0x15f44  ldarg.0
0x15f45  ldfld    class Microsoft.Crm.Application.Components.UI.EditableSelect Microsoft.Crm.Application.Components.UI.DateTimeUI::_select
0x15f4a  ldarg.0
0x15f4b  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x15f50  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x15f55  brtrue.s loc_15F69
0x15f57  ldarg.0
0x15f58  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x15f5d  ldstr    aTime_0// "Time"
0x15f62  call     string [mscorlib]System.String::Concat(string, string)
0x15f67  br.s     loc_15F6E
0x15f69  ldstr    asc_3280A// ""
0x15f6e  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x15f73  ldarg.0
0x15f74  ldfld    class Microsoft.Crm.Application.Components.UI.EditableSelect Microsoft.Crm.Application.Components.UI.DateTimeUI::_select
0x15f79  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x15f7e  ldarg.0
0x15f7f  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x15f84  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x15f89  brtrue.s loc_15FED
0x15f8b  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x15f90  stloc.0
0x15f91  ldarg.0
0x15f92  call     instance string Microsoft.Crm.Application.Components.UI.DateTimeUIBase::get_OnChangeScript()
0x15f97  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x15f9c  brtrue.s loc_15FAF
0x15f9e  ldloc.0
0x15f9f  ldstr    aChange// "change"
0x15fa4  ldarg.0
0x15fa5  call     instance string Microsoft.Crm.Application.Components.UI.DateTimeUIBase::get_OnChangeScript()
0x15faa  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x15faf  ldarg.0
0x15fb0  call     instance string Microsoft.Crm.Application.Components.UI.DateTimeUIBase::get_OnInitCompleteScript()
0x15fb5  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x15fba  brtrue.s loc_15FCD
0x15fbc  ldloc.0
0x15fbd  ldstr    aInitcomplete// "initComplete"
0x15fc2  ldarg.0
0x15fc3  call     instance string Microsoft.Crm.Application.Components.UI.DateTimeUIBase::get_OnInitCompleteScript()
0x15fc8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x15fcd  ldarg.0
0x15fce  ldarg.0
0x15fcf  callvirt instance string Microsoft.Crm.Application.Components.UI.DateTimeUIBase::get_ClientSideFormInputBehaviorClassName()
0x15fd4  ldnull
0x15fd5  ldnull
0x15fd6  ldnull
0x15fd7  ldarg.0
0x15fd8  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x15fdd  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::RegisterClientAjaxComponent(string componentTypeName, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> events, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> references, string elementId)
0x15fe2  ldarg.0
0x15fe3  ldstr    aMscrmDatetimea// "Mscrm.DateTimeAttribute"
0x15fe8  call     instance void Microsoft.Crm.Application.Components.UI.CrmFormUIControl::RegisterClientSideControl(string attributeClassName)
0x15fed  ret
```
