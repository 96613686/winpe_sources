# Microsoft.Crm.Common.Web.Tools.NetBreeze.NetBreezeConfigurationPage::ConfigureHeader

- ea: `0x8d40`
- end: `0x8da7`
- name: `Microsoft.Crm.Common.Web.Tools.NetBreeze.NetBreezeConfigurationPage::ConfigureHeader`
- size: `103`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, installer_update, broker_com_uri`

## string_xrefs

- `0x8d68`: `/Tools/SocialInsights/cmds/cmd_update.aspx`

## pseudocode

```c

```

## disassembly

```asm
0x8d40  ldarg.0
0x8d41  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::ConfigureHeader()
0x8d46  ldarg.0
0x8d47  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8d4c  ldc.i4.1
0x8d4d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_LoadJQuery(bool)
0x8d52  ldarg.0
0x8d53  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8d58  ldstr    aStaticControls_7// "/_static/_controls/SocialInsights/Socia"...
0x8d5d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x8d62  ldarg.0
0x8d63  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8d68  ldstr    aToolsSocialins// "/Tools/SocialInsights/cmds/cmd_update.a"...
0x8d6d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPath(string)
0x8d72  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8d77  ldstr    aStaticCss0Soci// "/_static/css/{0}/SocialInsights.css"
0x8d7c  ldc.i4.1
0x8d7d  newarr   [mscorlib]System.Object
0x8d82  dup
0x8d83  ldc.i4.0
0x8d84  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x8d89  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x8d8e  box      [mscorlib]System.Int32
0x8d93  stelem.ref
0x8d94  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8d99  stloc.0
0x8d9a  ldarg.0
0x8d9b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8da0  ldloc.0
0x8da1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x8da6  ret
```
