# Microsoft.Crm.Service.Application.Pages.CS.Dialog.RunDialogPage::OnPreInit

- ea: `0xfaa0`
- end: `0xfb42`
- name: `Microsoft.Crm.Service.Application.Pages.CS.Dialog.RunDialogPage::OnPreInit`
- size: `162`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0xfaa0`
- `0xfb50`

## pseudocode

```c

```

## disassembly

```asm
0xfaa0  ldarg.0
0xfaa1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::OnPreInit()
0xfaa6  ldarg.0
0xfaa7  ldarg.0
0xfaa8  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xfaad  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xfab2  ldstr    aDialogid// "DialogId"
0xfab7  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xfabc  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xfac1  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Service.Application.Pages.CS.Dialog.RunDialogPage::interactiveWorkflowId
0xfac6  ldarg.0
0xfac7  ldarg.0
0xfac8  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xfacd  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xfad2  ldstr    aObjectid// "ObjectId"
0xfad7  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xfadc  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xfae1  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Service.Application.Pages.CS.Dialog.RunDialogPage::objectId
0xfae6  leave.s  loc_FAFA
0xfae8  pop
0xfae9  ldarg.0
0xfaea  call     instance void Microsoft.Crm.Service.Application.Pages.CS.Dialog.RunDialogPage::InvalidUrlError()
0xfaef  leave.s  loc_FAFA
0xfaf1  pop
0xfaf2  ldarg.0
0xfaf3  call     instance void Microsoft.Crm.Service.Application.Pages.CS.Dialog.RunDialogPage::InvalidUrlError()
0xfaf8  leave.s  loc_FAFA
0xfafa  ldarg.0
0xfafb  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xfb00  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xfb05  ldstr    aEntityname_0// "EntityName"
0xfb0a  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xfb0f  stloc.0
0xfb10  ldarg.0
0xfb11  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xfb16  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0xfb1b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0xfb20  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xfb25  ldloc.0
0xfb26  ldc.i4.1
0xfb27  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0xfb2c  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0xfb31  stfld    int32 Microsoft.Crm.Service.Application.Pages.CS.Dialog.RunDialogPage::otc
0xfb36  leave.s  loc_FB41
0xfb38  pop
0xfb39  ldarg.0
0xfb3a  call     instance void Microsoft.Crm.Service.Application.Pages.CS.Dialog.RunDialogPage::InvalidUrlError()
0xfb3f  leave.s  loc_FB41
0xfb41  ret
```
