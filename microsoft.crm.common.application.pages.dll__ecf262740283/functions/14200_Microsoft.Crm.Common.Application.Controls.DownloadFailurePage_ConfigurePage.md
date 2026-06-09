# Microsoft.Crm.Common.Application.Controls.DownloadFailurePage::ConfigurePage

- ea: `0x14200`
- end: `0x1425d`
- name: `Microsoft.Crm.Common.Application.Controls.DownloadFailurePage::ConfigurePage`
- size: `93`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14200`

## string_xrefs

- `0x1424d`: `Web._common.error.downloadfailure.aspx_44`

## pseudocode

```c

```

## disassembly

```asm
0x14200  ldarg.0
0x14201  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x14206  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1420b  ldstr    aHr// "hr"
0x14210  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x14215  stloc.0
0x14216  ldloc.0
0x14217  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1421c  brtrue.s loc_14241
0x1421e  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorLookup::.ctor()
0x14223  ldloc.0
0x14224  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x14229  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorData [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorLookup::GetError(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1422e  stloc.1
0x1422f  ldarg.0
0x14230  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlTableCell Microsoft.Crm.Common.Application.Controls.DownloadFailurePage::tdMessage
0x14235  ldloc.1
0x14236  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorData::get_MessageHtml()
0x1423b  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0x14240  ret
0x14241  ldarg.0
0x14242  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlTableCell Microsoft.Crm.Common.Application.Controls.DownloadFailurePage::tdMessage
0x14247  ldarg.0
0x14248  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1424d  ldstr    aWebCommonError_5// "Web._common.error.downloadfailure.aspx_"...
0x14252  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x14257  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerText(string)
0x1425c  ret
```
