# Microsoft.Crm.Common.Web.Tools.Yammer.YammerConfiguration::RenderCancelButton

- ea: `0x7d10`
- end: `0x7da6`
- name: `Microsoft.Crm.Common.Web.Tools.Yammer.YammerConfiguration::RenderCancelButton`
- size: `150`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x7c50`

## callees

- `0x7d10`

## string_xrefs

- `0x7d2a`: `Web.Tools.Yammer.Config.CancelButton`

## pseudocode

```c

```

## disassembly

```asm
0x7d10  ldstr    aToolsAdminAdmi// "/tools/admin/admin.aspx"
0x7d15  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x7d1a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7d1f  callvirt instance string [mscorlib]System.Object::ToString()
0x7d24  stloc.0
0x7d25  ldstr    aButtoncancel// "buttonCancel"
0x7d2a  ldstr    aWebToolsYammer_4// "Web.Tools.Yammer.Config.CancelButton"
0x7d2f  stloc.1
0x7d30  ldarg.0
0x7d31  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7d36  ldloc.1
0x7d37  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7d3c  stloc.2
0x7d3d  ldstr    aWindowParentLo// "window.parent.location.href='"
0x7d42  ldloc.0
0x7d43  ldstr    asc_213B2// "';"
0x7d48  call     string [mscorlib]System.String::Concat(string, string, string)
0x7d4d  stloc.3
0x7d4e  ldnull
0x7d4f  ldloc.3
0x7d50  ldc.i4.0
0x7d51  ldstr    aMsCrmFooterbut// "ms-crm-FooterButton"
0x7d56  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::.ctor(string, string, string, bool, string)
0x7d5b  stloc.s  4
0x7d5d  ldloc.s  4
0x7d5f  ldloc.2
0x7d60  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetAccessKey(string)
0x7d65  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_AccessKey(string)
0x7d6a  ldloc.s  4
0x7d6c  ldloc.2
0x7d6d  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::DecorateAccessKey(string)
0x7d72  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0x7d77  ldloc.s  4
0x7d79  ldarg.0
0x7d7a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7d7f  ldloc.1
0x7d80  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7d85  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_Title(string)
0x7d8a  ldarg.1
0x7d8b  ldloc.s  4
0x7d8d  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::get_OuterHtml()
0x7d92  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x7d97  leave.s  loc_7DA5
0x7d99  ldloc.s  4
0x7d9b  brfalse.s loc_7DA4
0x7d9d  ldloc.s  4
0x7d9f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7da4  endfinally
0x7da5  ret
```
