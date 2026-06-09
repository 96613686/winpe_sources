# Microsoft.Crm.Application.ProcessControl.Configuration.BpfConfigurator::SetResourceFiles

- ea: `0x4bae0`
- end: `0x4bbde`
- name: `Microsoft.Crm.Application.ProcessControl.Configuration.BpfConfigurator::SetResourceFiles`
- size: `254`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x4b0a0`

## callees

- `0x4bae0`
- `0xea530`
- `0xea6e0`

## string_xrefs

- `0x4bb31`: `/_forms/styles/read.css.aspx`
- `0x4bba3`: `/tools/processcontrol/configuration.css.aspx`
- `0x4bbc3`: `/_static/_common/scripts/CrmServiceProxyFramework.js`
- `0x4bbd3`: `/_static/tools/ProcessConfiguration/ProcessConfiguration.js`

## pseudocode

```c

```

## disassembly

```asm
0x4bae0  ldarg.0
0x4bae1  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x4bae6  ldc.i4.1
0x4bae7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_LoadJQuery(bool)
0x4baec  newobj   instance void Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.ViewModels.ManageRuleCommonViewModel::.ctor()
0x4baf1  callvirt instance class [System]System.Collections.Generic.Queue`1<string> Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.ViewModels.ManageRuleCommonViewModel::get_RequiredScriptReferencesQueue()
0x4baf6  callvirt instance valuetype [System]System.Collections.Generic.Queue`1/Enumerator<var<u1>> class [System]System.Collections.Generic.Queue`1<string>::GetEnumerator()
0x4bafb  stloc.0
0x4bafc  br.s     loc_4BB12
0x4bafe  ldloca.s 0
0x4bb00  call     instance var<u1> valuetype [System]System.Collections.Generic.Queue`1/Enumerator<string>::get_Current()
0x4bb05  stloc.1
0x4bb06  ldarg.0
0x4bb07  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x4bb0c  ldloc.1
0x4bb0d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x4bb12  ldloca.s 0
0x4bb14  call     instance bool valuetype [System]System.Collections.Generic.Queue`1/Enumerator<string>::MoveNext()
0x4bb19  brtrue.s loc_4BAFE
0x4bb1b  leave.s  loc_4BB2B
0x4bb1d  ldloca.s 0
0x4bb1f  constrained. valuetype [System]System.Collections.Generic.Queue`1/Enumerator<string>
0x4bb25  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4bb2a  endfinally
0x4bb2b  ldarg.0
0x4bb2c  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x4bb31  ldstr    aFormsStylesRea// "/_forms/styles/read.css.aspx"
0x4bb36  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x4bb3b  ldarg.0
0x4bb3c  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x4bb41  ldstr    aFormsControlsC// "/_forms/controls/controls.css.aspx"
0x4bb46  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x4bb4b  ldarg.0
0x4bb4c  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x4bb51  ldstr    aNavMenuCssAspx// "/_nav/menu.css.aspx"
0x4bb56  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x4bb5b  ldarg.0
0x4bb5c  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x4bb61  ldstr    aControlsRefres// "/_controls/refreshform/flyoutdialog.css"...
0x4bb66  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x4bb6b  ldarg.0
0x4bb6c  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x4bb71  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4bb76  ldstr    aStaticCss0Busi// "/_static/css/{0}/BusinessRules.css"
0x4bb7b  ldc.i4.1
0x4bb7c  newarr   [mscorlib]System.Object
0x4bb81  dup
0x4bb82  ldc.i4.0
0x4bb83  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x4bb88  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x4bb8d  box      [mscorlib]System.Int32
0x4bb92  stelem.ref
0x4bb93  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4bb98  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x4bb9d  ldarg.0
0x4bb9e  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x4bba3  ldstr    aToolsProcessco// "/tools/processcontrol/configuration.css"...
0x4bba8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x4bbad  ldarg.0
0x4bbae  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x4bbb3  ldstr    aStaticFormsTab// "/_static/_forms/Tabs.js"
0x4bbb8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x4bbbd  ldarg.0
0x4bbbe  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x4bbc3  ldstr    aStaticCommonSc_6// "/_static/_common/scripts/CrmServiceProx"...
0x4bbc8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x4bbcd  ldarg.0
0x4bbce  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x4bbd3  ldstr    aStaticToolsPro// "/_static/tools/ProcessConfiguration/Pro"...
0x4bbd8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x4bbdd  ret
```
