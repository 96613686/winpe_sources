# Microsoft.Crm.Web.Tools.Admin.OrgInsightsChartPage::OnPreInit

- ea: `0x88c10`
- end: `0x88d10`
- name: `Microsoft.Crm.Web.Tools.Admin.OrgInsightsChartPage::OnPreInit`
- size: `256`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x88c10`
- `0x89040`

## string_xrefs

- `0x88c1b`: `OrgInsightsConfigurationid`
- `0x88c3c`: `isuserOrgInsightsConfiguration`
- `0x88c7e`: `OrgInsightsConfigurationId`
- `0x88c91`: `OrgInsightsConfigurationId`
- `0x88cab`: `isUserOrgInsightsConfiguration`
- `0x88cbe`: `isUserOrgInsightsConfiguration`

## pseudocode

```c

```

## disassembly

```asm
0x88c10  ldarg.0
0x88c11  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x88c16  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x88c1b  ldstr    aOrginsightscon// "OrgInsightsConfigurationid"
0x88c20  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x88c25  ldarg.0
0x88c26  ldflda   valuetype [mscorlib]System.Guid Microsoft.Crm.Web.Tools.Admin.OrgInsightsChartPage::_OrgInsightsConfigurationId
0x88c2b  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x88c30  pop
0x88c31  ldarg.0
0x88c32  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x88c37  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x88c3c  ldstr    aIsuserorginsig// "isuserOrgInsightsConfiguration"
0x88c41  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x88c46  ldarg.0
0x88c47  ldflda   bool Microsoft.Crm.Web.Tools.Admin.OrgInsightsChartPage::_isUserOrgInsightsConfiguration
0x88c4c  call     bool [mscorlib]System.Boolean::TryParse(string, bool&)
0x88c51  pop
0x88c52  ldarg.0
0x88c53  call     instance void Microsoft.Crm.Web.Tools.Admin.OrgInsightsChartPage::ReadVisualizationParameters()
0x88c58  ldarg.0
0x88c59  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Web.Tools.Admin.OrgInsightsChartPage::_OrgInsightsConfigurationId
0x88c5e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x88c63  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x88c68  brfalse.s loc_88CDE
0x88c6a  ldarg.0
0x88c6b  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Web.Tools.Admin.OrgInsightsChartPage::_parameters
0x88c70  callvirt instance int32 [System]System.Collections.Specialized.NameObjectCollectionBase::get_Count()
0x88c75  ldc.i4.0
0x88c76  ble.s    loc_88CDE
0x88c78  ldarg.0
0x88c79  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Web.Tools.Admin.OrgInsightsChartPage::_parameters
0x88c7e  ldstr    aOrginsightscon_0// "OrgInsightsConfigurationId"
0x88c83  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x88c88  brfalse.s loc_88CA5
0x88c8a  ldarg.0
0x88c8b  ldarg.0
0x88c8c  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Web.Tools.Admin.OrgInsightsChartPage::_parameters
0x88c91  ldstr    aOrginsightscon_0// "OrgInsightsConfigurationId"
0x88c96  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x88c9b  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x88ca0  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Web.Tools.Admin.OrgInsightsChartPage::_OrgInsightsConfigurationId
0x88ca5  ldarg.0
0x88ca6  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Web.Tools.Admin.OrgInsightsChartPage::_parameters
0x88cab  ldstr    aIsuserorginsig_0// "isUserOrgInsightsConfiguration"
0x88cb0  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x88cb5  brfalse.s loc_88CDE
0x88cb7  ldarg.0
0x88cb8  ldarg.0
0x88cb9  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Web.Tools.Admin.OrgInsightsChartPage::_parameters
0x88cbe  ldstr    aIsuserorginsig_0// "isUserOrgInsightsConfiguration"
0x88cc3  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x88cc8  ldstr    aTrue_0// "true"
0x88ccd  ldc.i4.3
0x88cce  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x88cd3  brtrue.s loc_88CD8
0x88cd5  ldc.i4.0
0x88cd6  br.s     loc_88CD9
0x88cd8  ldc.i4.1
0x88cd9  stfld    bool Microsoft.Crm.Web.Tools.Admin.OrgInsightsChartPage::_isUserOrgInsightsConfiguration
0x88cde  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.OrgInsights.OrgInsightsTelemetryEvents [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.OrgInsights.OrgInsightsTelemetryEvents::get_Instance()
0x88ce3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x88ce8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x88ced  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_ApplicationVersion()
0x88cf2  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_UserPuid()
0x88cf7  ldarg.0
0x88cf8  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Web.Tools.Admin.OrgInsightsChartPage::_OrgInsightsConfigurationId
0x88cfd  ldarg.0
0x88cfe  ldfld    bool Microsoft.Crm.Web.Tools.Admin.OrgInsightsChartPage::_isUserOrgInsightsConfiguration
0x88d03  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.OrgInsights.OrgInsightsTelemetryEvents::ChartRequested(valuetype [mscorlib]System.Guid, string, string, valuetype [mscorlib]System.Guid, bool)
0x88d08  ldarg.0
0x88d09  ldarg.1
0x88d0a  call     instance void [System.Web]System.Web.UI.Page::OnPreInit(class [mscorlib]System.EventArgs)
0x88d0f  ret
```
