# Microsoft.Crm.Sales.Application.Pages.Tools.Business.Salesperson::ConfigurePage

- ea: `0x600`
- end: `0x6f9`
- name: `Microsoft.Crm.Sales.Application.Pages.Tools.Business.Salesperson::ConfigurePage`
- size: `249`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0x616`: `/_static/_common/scripts/stage.js`

## pseudocode

```c

```

## disassembly

```asm
0x600  ldarg.0
0x601  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x606  ldstr    aControlsNaviga// "/_controls/navigation/map.css.aspx"
0x60b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x610  ldarg.0
0x611  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x616  ldstr    aStaticCommonSc// "/_static/_common/scripts/stage.js"
0x61b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x620  ldarg.0
0x621  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x626  ldstr    aStaticFormsAdd// "/_static/_forms/addrelated.js"
0x62b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x630  ldarg.0
0x631  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x636  ldstr    aStaticControls// "/_static/_controls/lookup/lookup.js"
0x63b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x640  ldarg.0
0x641  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x646  ldstr    aStaticBizTeams// "/_static/biz/teams/members.js"
0x64b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x650  ldarg.0
0x651  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x656  ldstr    aGridCmdsCmdAdd// "/_grid/cmds/cmd_adduserteam.aspx"
0x65b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPath(string)
0x660  ldarg.0
0x661  ldstr    aSystemuser// "systemuser"
0x666  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x66b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x670  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::set_CurrentType(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x675  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.Organization::get_CurrentSettings()
0x67a  stloc.0
0x67b  ldloc.0
0x67c  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_FiscalCalendarStart()
0x681  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x686  call     bool [mscorlib]System.DateTime::op_Inequality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x68b  ldstr    aFiscalCalendar// "Fiscal calendar start has not been set "...
0x690  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x695  ldarg.0
0x696  ldloc.0
0x697  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_FiscalCalendarStart()
0x69c  call     valuetype [mscorlib]System.DateTime [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Util::GetCurrentFiscalYearStartDate(valuetype [mscorlib]System.DateTime)
0x6a1  stfld    valuetype [mscorlib]System.DateTime Microsoft.Crm.Sales.Application.Pages.Tools.Business.Salesperson::dt
0x6a6  ldarg.0
0x6a7  ldarg.0
0x6a8  ldfld    valuetype [mscorlib]System.DateTime Microsoft.Crm.Sales.Application.Pages.Tools.Business.Salesperson::dt
0x6ad  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Util::GetCurrentFiscalPeriod(valuetype [mscorlib]System.DateTime)
0x6b2  stfld    string Microsoft.Crm.Sales.Application.Pages.Tools.Business.Salesperson::period
0x6b7  ldarg.0
0x6b8  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Sales.Application.Pages.Tools.Business.Salesperson::crmGrid
0x6bd  ldstr    a79183c450e5848// "{79183C45-0E58-4860-8354-BCE2D7A475C9}"
0x6c2  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid::set_ViewId(string)
0x6c7  ldarg.0
0x6c8  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Sales.Application.Pages.Tools.Business.Salesperson::crmGrid
0x6cd  ldstr    aDate// "date"
0x6d2  ldarg.0
0x6d3  ldfld    valuetype [mscorlib]System.DateTime Microsoft.Crm.Sales.Application.Pages.Tools.Business.Salesperson::dt
0x6d8  call     string [Microsoft.Crm]Microsoft.Crm.CrmCalendarUtil::DateTimeToIsoDateTimeString(valuetype [mscorlib]System.DateTime)
0x6dd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::AddParameter(string, string)
0x6e2  ldarg.0
0x6e3  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Sales.Application.Pages.Tools.Business.Salesperson::crmGrid
0x6e8  ldstr    aPeriod// "period"
0x6ed  ldarg.0
0x6ee  ldfld    string Microsoft.Crm.Sales.Application.Pages.Tools.Business.Salesperson::period
0x6f3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::AddParameter(string, string)
0x6f8  ret
```
