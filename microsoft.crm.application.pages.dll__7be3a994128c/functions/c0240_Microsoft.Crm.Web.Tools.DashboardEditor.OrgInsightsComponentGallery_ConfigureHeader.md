# Microsoft.Crm.Web.Tools.DashboardEditor.OrgInsightsComponentGallery::ConfigureHeader

- ea: `0xc0240`
- end: `0xc02e1`
- name: `Microsoft.Crm.Web.Tools.DashboardEditor.OrgInsightsComponentGallery::ConfigureHeader`
- size: `161`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0xc0246`: `/_static/tools/DashboardEditor/scripts/OrgInsightsComponentGallery.js`
- `0xc0276`: `/Tools/DashboardEditor/Dialogs/OrgInsightsComponentGallery.css.aspx`
- `0xc02a6`: `LOCID_CG_OrgInsightsConfiguration`
- `0xc02b1`: `Web.DashboardEditor.OrgInsightsComponentGallery.ChartLabel`
- `0xc02c6`: `LOCID_CG_NOOrgInsightsConfigurations`
- `0xc02d1`: `Web.DashboardEditor.OrgInsightsComponentGallery.NoChartsMessage`

## pseudocode

```c

```

## disassembly

```asm
0xc0240  ldarg.0
0xc0241  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xc0246  ldstr    aStaticToolsDas_1// "/_static/tools/DashboardEditor/scripts/"...
0xc024b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xc0250  ldarg.0
0xc0251  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xc0256  ldstr    aStaticToolsDas// "/_static/tools/DashboardEditor/scripts/"...
0xc025b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xc0260  ldarg.0
0xc0261  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xc0266  ldstr    aStaticToolsFor// "/_static/tools/formeditor/scripts/objec"...
0xc026b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xc0270  ldarg.0
0xc0271  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xc0276  ldstr    aToolsDashboard_5// "/Tools/DashboardEditor/Dialogs/OrgInsig"...
0xc027b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xc0280  ldarg.0
0xc0281  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xc0286  ldstr    aToolsDashboard_4// "/Tools/DashboardEditor/DashboardEditor."...
0xc028b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xc0290  ldarg.0
0xc0291  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xc0296  ldstr    aGridAppgridCss// "/_grid/appgrid.css.aspx"
0xc029b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xc02a0  ldarg.0
0xc02a1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xc02a6  ldstr    aLocidCgOrginsi// "LOCID_CG_OrgInsightsConfiguration"
0xc02ab  ldarg.0
0xc02ac  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xc02b1  ldstr    aWebDashboarded_39// "Web.DashboardEditor.OrgInsightsComponen"...
0xc02b6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc02bb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xc02c0  ldarg.0
0xc02c1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xc02c6  ldstr    aLocidCgNoorgin// "LOCID_CG_NOOrgInsightsConfigurations"
0xc02cb  ldarg.0
0xc02cc  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xc02d1  ldstr    aWebDashboarded_40// "Web.DashboardEditor.OrgInsightsComponen"...
0xc02d6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc02db  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xc02e0  ret
```
