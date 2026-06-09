# Microsoft.Crm.Service.Dialogs.ConfirmCancelPage::ConfigurePage

- ea: `0x3090`
- end: `0x311c`
- name: `Microsoft.Crm.Service.Dialogs.ConfirmCancelPage::ConfigurePage`
- size: `140`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## string_xrefs

- `0x309c`: `/_static/_controls/ReadForm/ReadFormUtilities.js`
- `0x30eb`: `/_common/styles/dialogs.css.aspx`

## pseudocode

```c

```

## disassembly

```asm
0x3090  ldarg.0
0x3091  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigurePage()
0x3096  ldarg.0
0x3097  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0x309c  ldstr    aStaticControls_1// "/_static/_controls/ReadForm/ReadFormUti"...
0x30a1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x30a6  ldarg.0
0x30a7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x30ac  ldstr    aIid_0// "_iId"
0x30b1  ldarg.0
0x30b2  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x30b7  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x30bc  ldstr    aPid// "pId"
0x30c1  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x30c6  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetGuid(string)
0x30cb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x30d0  ldarg.0
0x30d1  ldc.i4   0x232A
0x30d6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x30db  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x30e0  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::set_CurrentType(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x30e5  ldarg.0
0x30e6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x30eb  ldstr    aCommonStylesDi// "/_common/styles/dialogs.css.aspx"
0x30f0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x30f5  ldarg.0
0x30f6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x30fb  ldstr    aMscrmDialogsco// "Mscrm.DialogsControl"
0x3100  ldnull
0x3101  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0x3106  ldarg.0
0x3107  ldstr    aIncident// "incident"
0x310c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x3111  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3116  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::set_CurrentType(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x311b  ret
```
