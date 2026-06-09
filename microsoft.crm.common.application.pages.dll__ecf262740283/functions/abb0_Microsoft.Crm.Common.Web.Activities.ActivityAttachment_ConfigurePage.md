# Microsoft.Crm.Common.Web.Activities.ActivityAttachment::ConfigurePage

- ea: `0xabb0`
- end: `0xad28`
- name: `Microsoft.Crm.Common.Web.Activities.ActivityAttachment::ConfigurePage`
- size: `376`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0xabb0`
- `0xad30`

## string_xrefs

- `0xabb6`: `/_common/styles/dialogs.css.aspx`
- `0xabe7`: `/_static/_common/styles/AutoToolTip.js`
- `0xaccb`: `_CreateFromId`
- `0xace1`: `_CreateFromType`

## pseudocode

```c

```

## disassembly

```asm
0xabb0  ldarg.0
0xabb1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xabb6  ldstr    aCommonStylesDi// "/_common/styles/dialogs.css.aspx"
0xabbb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xabc0  ldarg.0
0xabc1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xabc6  ldstr    aMscrmDialogsco// "Mscrm.DialogsControl"
0xabcb  ldnull
0xabcc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0xabd1  ldarg.0
0xabd2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xabd7  ldstr    aStaticControls_1// "/_static/_controls/attachment/attachmen"...
0xabdc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xabe1  ldarg.0
0xabe2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xabe7  ldstr    aStaticCommonSt// "/_static/_common/styles/AutoToolTip.js"
0xabec  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xabf1  ldarg.0
0xabf2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xabf7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPath()
0xabfc  ldarg.0
0xabfd  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAttachment Microsoft.Crm.Common.Web.Activities.ActivityAttachment::crmAttachment
0xac02  ldstr    aActivitiesAtta_2// "/Activities/Attachment/edit.aspx"
0xac07  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xac0c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xac11  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAttachment::set_SuccessUrl(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0xac16  ldarg.0
0xac17  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAttachment Microsoft.Crm.Common.Web.Activities.ActivityAttachment::crmAttachment
0xac1c  ldstr    aActivitiesAtta// "/Activities/Attachment/save.aspx"
0xac21  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xac26  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xac2b  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAttachment::set_SaveUrl(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0xac30  ldarg.0
0xac31  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAttachment Microsoft.Crm.Common.Web.Activities.ActivityAttachment::crmAttachment
0xac36  ldstr    aActivitiesAtta_0// "/Activities/Attachment/upload.aspx"
0xac3b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xac40  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xac45  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAttachment::set_UploadHandlerUrl(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0xac4a  ldarg.0
0xac4b  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAttachment Microsoft.Crm.Common.Web.Activities.ActivityAttachment::crmAttachment
0xac50  ldstr    aActivitiesAtta_1// "/Activities/Attachment/download.aspx"
0xac55  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xac5a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xac5f  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAttachment::set_DownloadHandlerUrl(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0xac64  ldarg.0
0xac65  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAttachment Microsoft.Crm.Common.Web.Activities.ActivityAttachment::crmAttachment
0xac6a  ldstr    aActivitymimeat_0// "activitymimeattachment/activitymimeatta"...
0xac6f  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAttachment::set_IdXmlNode(string)
0xac74  ldarg.0
0xac75  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAttachment Microsoft.Crm.Common.Web.Activities.ActivityAttachment::crmAttachment
0xac7a  ldarg.0
0xac7b  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xac80  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xac85  ldstr    aPid// "pId"
0xac8a  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xac8f  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAttachment::set_ParentId(string)
0xac94  ldarg.0
0xac95  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAttachment Microsoft.Crm.Common.Web.Activities.ActivityAttachment::crmAttachment
0xac9a  ldarg.0
0xac9b  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xaca0  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xaca5  ldstr    aPtype// "pType"
0xacaa  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xacaf  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAttachment::set_ParentType(string)
0xacb4  ldarg.0
0xacb5  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAttachment Microsoft.Crm.Common.Web.Activities.ActivityAttachment::crmAttachment
0xacba  ldc.i4.1
0xacbb  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAttachment::set_IsAttachmentDialog(bool)
0xacc0  ldarg.0
0xacc1  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xacc6  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xaccb  ldstr    aCreatefromid// "_CreateFromId"
0xacd0  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xacd5  stloc.0
0xacd6  ldarg.0
0xacd7  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xacdc  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xace1  ldstr    aCreatefromtype// "_CreateFromType"
0xace6  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xaceb  stloc.1
0xacec  ldloc.0
0xaced  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xacf2  brtrue.s loc_AD27
0xacf4  ldloc.1
0xacf5  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xacfa  brtrue.s loc_AD27
0xacfc  ldarg.0
0xacfd  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAttachment Microsoft.Crm.Common.Web.Activities.ActivityAttachment::crmAttachment
0xad02  ldarg.0
0xad03  ldloc.0
0xad04  ldloc.1
0xad05  call     instance bool Microsoft.Crm.Common.Web.Activities.ActivityAttachment::IsAttachmentDisabled(string ParentId, string ParentType)
0xad0a  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAttachment::set_AttachmentDisabled(bool)
0xad0f  ldarg.0
0xad10  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAttachment Microsoft.Crm.Common.Web.Activities.ActivityAttachment::crmAttachment
0xad15  ldloc.0
0xad16  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAttachment::set_ParentId(string)
0xad1b  ldarg.0
0xad1c  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAttachment Microsoft.Crm.Common.Web.Activities.ActivityAttachment::crmAttachment
0xad21  ldloc.1
0xad22  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAttachment::set_ParentType(string)
0xad27  ret
```
