# Microsoft.Crm.Service.Dialogs.ConfirmResolvePage::ConfigurePage

- ea: `0x2e90`
- end: `0x2f06`
- name: `Microsoft.Crm.Service.Dialogs.ConfirmResolvePage::ConfigurePage`
- size: `118`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## string_xrefs

- `0x2e9c`: `/_static/_controls/ReadForm/ReadFormUtilities.js`
- `0x2eeb`: `CustomerService`
- `0x2efb`: `CustomerService`

## pseudocode

```c

```

## disassembly

```asm
0x2e90  ldarg.0
0x2e91  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigurePage()
0x2e96  ldarg.0
0x2e97  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0x2e9c  ldstr    aStaticControls_1// "/_static/_controls/ReadForm/ReadFormUti"...
0x2ea1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x2ea6  ldarg.0
0x2ea7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x2eac  ldstr    aIid_0// "_iId"
0x2eb1  ldarg.0
0x2eb2  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x2eb7  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x2ebc  ldstr    aPid// "pId"
0x2ec1  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x2ec6  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetGuid(string)
0x2ecb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x2ed0  ldarg.0
0x2ed1  ldc.i4   0x232A
0x2ed6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2edb  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2ee0  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::set_CurrentType(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x2ee5  ldarg.0
0x2ee6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x2eeb  ldstr    aCustomerservic// "CustomerService"
0x2ef0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0x2ef5  ldarg.0
0x2ef6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x2efb  ldstr    aCustomerservic// "CustomerService"
0x2f00  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathAshxWebService(string)
0x2f05  ret
```
