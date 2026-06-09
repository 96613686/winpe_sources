# Microsoft.Crm.Service.Application.Pages.SM.ResourceSchedule::ConfigurePage

- ea: `0x12080`
- end: `0x1212e`
- name: `Microsoft.Crm.Service.Application.Pages.SM.ResourceSchedule::ConfigurePage`
- size: `174`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x12080`

## string_xrefs

- `0x12096`: `/_static/_common/scripts/stage.js`

## pseudocode

```c

```

## disassembly

```asm
0x12080  ldarg.0
0x12081  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x12086  ldstr    aNavMenuCssAspx// "/_nav/menu.css.aspx"
0x1208b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x12090  ldarg.0
0x12091  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x12096  ldstr    aStaticCommonSc_3// "/_static/_common/scripts/stage.js"
0x1209b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x120a0  ldarg.0
0x120a1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x120a6  ldstr    aViewid_0// "_viewId"
0x120ab  ldstr    a8e1583765dad46// "{8E158376-5DAD-466B-B9F0-7107F8C32813}"
0x120b0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x120b5  ldarg.0
0x120b6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x120bb  ldstr    aSubareatype_0// "_subareaType"
0x120c0  ldstr    aAppforsched// "appforsched"
0x120c5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x120ca  ldsfld   string [mscorlib]System.String::Empty
0x120cf  stloc.0
0x120d0  ldarg.0
0x120d1  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x120d6  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x120db  ldstr    aId// "id"
0x120e0  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x120e5  stloc.1
0x120e6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x120eb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x120f0  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x120f5  ldstr    aSmResourcesche// "/SM/ResourceSchedules.aspx parameters: "...
0x120fa  ldc.i4.1
0x120fb  newarr   [mscorlib]System.Object
0x12100  dup
0x12101  ldc.i4.0
0x12102  ldloc.1
0x12103  stelem.ref
0x12104  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x12109  ldloc.1
0x1210a  brfalse.s loc_1211C
0x1210c  ldloc.1
0x1210d  callvirt instance int32 [mscorlib]System.String::get_Length()
0x12112  ldc.i4.0
0x12113  ble.s    loc_1211C
0x12115  ldloc.1
0x12116  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetGuid(string)
0x1211b  stloc.0
0x1211c  ldarg.0
0x1211d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x12122  ldstr    aEntityidstring// "_entityIdString"
0x12127  ldloc.0
0x12128  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x1212d  ret
```
