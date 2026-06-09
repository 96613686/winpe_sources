# Microsoft.Crm.Web.Tools.DashboardEditor.ComponentGallery::ConfigureHeader

- ea: `0xbf8f0`
- end: `0xbfa87`
- name: `Microsoft.Crm.Web.Tools.DashboardEditor.ComponentGallery::ConfigureHeader`
- size: `407`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0xbf8f0`

## string_xrefs

- `0xbf8f6`: `/_static/tools/DashboardEditor/scripts/ComponentGallery.js`
- `0xbf926`: `/Tools/DashboardEditor/Dialogs/ComponentGallery.css.aspx`
- `0xbf961`: `Web.DashboardEditor.ComponentGallery.ViewLabel`
- `0xbf981`: `Web.DashboardEditor.ComponentGallery.ChartLabel`
- `0xbf9e3`: `Web.DashboardEditor.ComponentGallery.NoChartsInteractionCentricMessage`
- `0xbfa05`: `Web.DashboardEditor.ComponentGallery.NoChartsMessage`
- `0xbfa27`: `Web.DashboardEditor.ComponentGallery.NoChartsMessage`

## pseudocode

```c

```

## disassembly

```asm
0xbf8f0  ldarg.0
0xbf8f1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xbf8f6  ldstr    aStaticToolsDas_0// "/_static/tools/DashboardEditor/scripts/"...
0xbf8fb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xbf900  ldarg.0
0xbf901  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xbf906  ldstr    aStaticToolsDas// "/_static/tools/DashboardEditor/scripts/"...
0xbf90b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xbf910  ldarg.0
0xbf911  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xbf916  ldstr    aStaticToolsFor// "/_static/tools/formeditor/scripts/objec"...
0xbf91b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xbf920  ldarg.0
0xbf921  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xbf926  ldstr    aToolsDashboard_3// "/Tools/DashboardEditor/Dialogs/Componen"...
0xbf92b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xbf930  ldarg.0
0xbf931  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xbf936  ldstr    aToolsDashboard_4// "/Tools/DashboardEditor/DashboardEditor."...
0xbf93b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xbf940  ldarg.0
0xbf941  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xbf946  ldstr    aGridAppgridCss// "/_grid/appgrid.css.aspx"
0xbf94b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xbf950  ldarg.0
0xbf951  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xbf956  ldstr    aLocidCgView// "LOCID_CG_VIEW"
0xbf95b  ldarg.0
0xbf95c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xbf961  ldstr    aWebDashboarded_32// "Web.DashboardEditor.ComponentGallery.Vi"...
0xbf966  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xbf96b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xbf970  ldarg.0
0xbf971  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xbf976  ldstr    aLocidCgChart// "LOCID_CG_CHART"
0xbf97b  ldarg.0
0xbf97c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xbf981  ldstr    aWebDashboarded_33// "Web.DashboardEditor.ComponentGallery.Ch"...
0xbf986  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xbf98b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xbf990  ldarg.0
0xbf991  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xbf996  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xbf99b  ldstr    aInteractioncen_3// "interactioncentric"
0xbf9a0  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xbf9a5  brfalse.s loc_BFA16
0xbf9a7  ldstr    aTrue_0// "true"
0xbf9ac  ldarg.0
0xbf9ad  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xbf9b2  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xbf9b7  ldstr    aInteractioncen_3// "interactioncentric"
0xbf9bc  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xbf9c1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbf9c6  call     string [mscorlib]System.Convert::ToString(string, class [mscorlib]System.IFormatProvider)
0xbf9cb  call     bool [mscorlib]System.String::op_Equality(string, string)
0xbf9d0  brfalse.s loc_BF9F4
0xbf9d2  ldarg.0
0xbf9d3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xbf9d8  ldstr    aLocidCgNochart// "LOCID_CG_NOCHARTS"
0xbf9dd  ldarg.0
0xbf9de  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xbf9e3  ldstr    aWebDashboarded_34// "Web.DashboardEditor.ComponentGallery.No"...
0xbf9e8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xbf9ed  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xbf9f2  br.s     loc_BFA36
0xbf9f4  ldarg.0
0xbf9f5  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xbf9fa  ldstr    aLocidCgNochart// "LOCID_CG_NOCHARTS"
0xbf9ff  ldarg.0
0xbfa00  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xbfa05  ldstr    aWebDashboarded_35// "Web.DashboardEditor.ComponentGallery.No"...
0xbfa0a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xbfa0f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xbfa14  br.s     loc_BFA36
0xbfa16  ldarg.0
0xbfa17  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xbfa1c  ldstr    aLocidCgNochart// "LOCID_CG_NOCHARTS"
0xbfa21  ldarg.0
0xbfa22  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xbfa27  ldstr    aWebDashboarded_35// "Web.DashboardEditor.ComponentGallery.No"...
0xbfa2c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xbfa31  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xbfa36  ldarg.0
0xbfa37  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xbfa3c  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xbfa41  ldstr    aDashboardcateg// "dashboardCategory"
0xbfa46  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xbfa4b  brfalse.s loc_BFA65
0xbfa4d  ldarg.0
0xbfa4e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xbfa53  ldstr    aIscsr2// "ISCSR2"
0xbfa58  ldc.i4.1
0xbfa59  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0xbfa5e  ldarg.0
0xbfa5f  ldc.i4.1
0xbfa60  stfld    bool Microsoft.Crm.Web.Tools.DashboardEditor.ComponentGallery::isCsrTwo
0xbfa65  ldarg.0
0xbfa66  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xbfa6b  ldstr    aLocidGridPrevi// "LOCID_GRID_PREVIEW_COLUMN_HEADER"
0xbfa70  ldarg.0
0xbfa71  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xbfa76  ldstr    aWebDashboarded_25// "Web.DashboardEditor.GridPreviewColumnHe"...
0xbfa7b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xbfa80  ldc.i4.0
0xbfa81  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xbfa86  ret
```
