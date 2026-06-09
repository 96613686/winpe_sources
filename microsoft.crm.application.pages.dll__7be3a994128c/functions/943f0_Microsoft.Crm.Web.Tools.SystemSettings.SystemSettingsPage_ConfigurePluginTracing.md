# Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::ConfigurePluginTracing

- ea: `0x943f0`
- end: `0x944e0`
- name: `Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::ConfigurePluginTracing`
- size: `240`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x90ec0`

## callees

- `0x943f0`

## string_xrefs

- `0x943f7`: `plugintracelogsetting`
- `0x9440c`: `plugintracelogsetting`
- `0x9443e`: `SystemCustomization.SystemSettingsDialog.CustomizationTab.PluginTracing.Labels.Off`
- `0x9445e`: `SystemCustomization.SystemSettingsDialog.CustomizationTab.PluginTracing.Labels.Exception`
- `0x94477`: `PluginTraceLoggingVerboseEnabled`
- `0x944a6`: `SystemCustomization.SystemSettingsDialog.CustomizationTab.PluginTracing.Labels.All`

## pseudocode

```c

```

## disassembly

```asm
0x943f0  ldarg.1
0x943f1  brfalse  loc_944BB
0x943f6  ldarg.1
0x943f7  ldstr    aPlugintracelog// "plugintracelogsetting"
0x943fc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string)
0x94401  brfalse  loc_944BB
0x94406  ldarg.0
0x94407  ldfld    string Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::_OrgXml
0x9440c  ldstr    aPlugintracelog// "plugintracelogsetting"
0x94411  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetNodeValue(string, string)
0x94416  stloc.0
0x94417  ldarg.0
0x94418  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::selectPluginTracingLevels
0x9441d  ldloc.0
0x9441e  callvirt instance int32 [mscorlib]System.String::get_Length()
0x94423  brfalse.s loc_94428
0x94425  ldloc.0
0x94426  br.s     loc_9442D
0x94428  ldstr    a0_1// "0"
0x9442d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::set_Selected(string)
0x94432  ldarg.0
0x94433  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::selectPluginTracingLevels
0x94438  ldarg.0
0x94439  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9443e  ldstr    aSystemcustomiz_189// "SystemCustomization.SystemSettingsDialo"...
0x94443  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x94448  ldstr    a0_1// "0"
0x9444d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddItem(string, string)
0x94452  ldarg.0
0x94453  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::selectPluginTracingLevels
0x94458  ldarg.0
0x94459  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9445e  ldstr    aSystemcustomiz_190// "SystemCustomization.SystemSettingsDialo"...
0x94463  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x94468  ldstr    a1// "1"
0x9446d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddItem(string, string)
0x94472  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x94477  ldstr    aPlugintracelog_0// "PluginTraceLoggingVerboseEnabled"
0x9447c  callvirt T0x2B00002E
0x94481  stloc.1
0x94482  ldc.i4.1
0x94483  stloc.2
0x94484  ldloca.s 1
0x94486  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::GetValueOrDefault()
0x9448b  ldloc.2
0x9448c  beq.s    loc_94491
0x9448e  ldc.i4.0
0x9448f  br.s     loc_94498
0x94491  ldloca.s 1
0x94493  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x94498  brfalse.s loc_944DF
0x9449a  ldarg.0
0x9449b  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::selectPluginTracingLevels
0x944a0  ldarg.0
0x944a1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x944a6  ldstr    aSystemcustomiz_191// "SystemCustomization.SystemSettingsDialo"...
0x944ab  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x944b0  ldstr    a2// "2"
0x944b5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddItem(string, string)
0x944ba  ret
0x944bb  ldarg.0
0x944bc  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::pluginTracingTitle
0x944c1  ldc.i4.0
0x944c2  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x944c7  ldarg.0
0x944c8  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::enablePluginTracingLevel
0x944cd  ldc.i4.0
0x944ce  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x944d3  ldarg.0
0x944d4  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::selectPluginTracingLevels
0x944d9  ldc.i4.0
0x944da  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x944df  ret
```
