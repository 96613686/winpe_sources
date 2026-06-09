# Microsoft.Crm.Service.Web.CS.UIScriptErrorPage::ShowCustomError

- ea: `0x6560`
- end: `0x65e1`
- name: `Microsoft.Crm.Service.Web.CS.UIScriptErrorPage::ShowCustomError`
- size: `129`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x6430`

## callees

- `0x6560`
- `0x6620`

## pseudocode

```c

```

## disassembly

```asm
0x6560  ldarg.0
0x6561  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6566  ldstr    aWebUiscriptsCu// "Web.UIScripts.CustomError.Title."
0x656b  ldarg.1
0x656c  call     string [mscorlib]System.String::Concat(string, string)
0x6571  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6576  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::TryGetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x657b  stloc.0
0x657c  ldloc.0
0x657d  brtrue.s loc_6590
0x657f  ldarg.0
0x6580  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6585  ldstr    aWebUiscriptsCu_0// "Web.UIScripts.CustomError.Title.Invalid"...
0x658a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x658f  stloc.0
0x6590  ldarg.0
0x6591  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6596  ldstr    aWebUiscriptsCu_1// "Web.UIScripts.CustomError.Header."
0x659b  ldarg.1
0x659c  call     string [mscorlib]System.String::Concat(string, string)
0x65a1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x65a6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::TryGetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x65ab  stloc.1
0x65ac  ldloc.1
0x65ad  brtrue.s loc_65C0
0x65af  ldarg.0
0x65b0  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x65b5  ldstr    aWebUiscriptsCu_2// "Web.UIScripts.CustomError.Header.Invali"...
0x65ba  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x65bf  stloc.1
0x65c0  ldarg.0
0x65c1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x65c6  ldstr    aWebUiscriptsCu_3// "Web.UIScripts.CustomError.Message."
0x65cb  ldarg.1
0x65cc  call     string [mscorlib]System.String::Concat(string, string)
0x65d1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x65d6  stloc.2
0x65d7  ldarg.0
0x65d8  ldloc.1
0x65d9  ldloc.0
0x65da  ldloc.2
0x65db  call     instance void Microsoft.Crm.Service.Web.CS.UIScriptErrorPage::ShowStandardDialog(string header, string title, string message)
0x65e0  ret
```
