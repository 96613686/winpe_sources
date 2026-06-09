# Microsoft.Crm.Common.Web.Activities.Dialogs.ConvertToCase::ConfigureForm

- ea: `0xcaf0`
- end: `0xcc90`
- name: `Microsoft.Crm.Common.Web.Activities.Dialogs.ConvertToCase::ConfigureForm`
- size: `416`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0xc970`
- `0xc990`
- `0xcaf0`

## pseudocode

```c

```

## disassembly

```asm
0xcaf0  ldarg.0
0xcaf1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0xcaf6  ldarg.0
0xcaf7  call     instance class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Common.Web.Activities.Dialogs.ConvertToCase::get_CustomerLookup()
0xcafc  ldstr    aSingle// "single"
0xcb01  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupStyle(string)
0xcb06  ldarg.0
0xcb07  call     instance class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Common.Web.Activities.Dialogs.ConvertToCase::get_CustomerLookup()
0xcb0c  ldc.i4.2
0xcb0d  newarr   [mscorlib]System.Int32
0xcb12  dup
0xcb13  ldc.i4.0
0xcb14  ldc.i4.1
0xcb15  stelem.i4
0xcb16  dup
0xcb17  ldc.i4.1
0xcb18  ldc.i4.2
0xcb19  stelem.i4
0xcb1a  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupTypes(int32[])
0xcb1f  ldarg.0
0xcb20  call     instance class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Common.Web.Activities.Dialogs.ConvertToCase::get_subjectid()
0xcb25  ldstr    aSubject// "subject"
0xcb2a  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupStyle(string)
0xcb2f  ldarg.0
0xcb30  call     instance class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Common.Web.Activities.Dialogs.ConvertToCase::get_subjectid()
0xcb35  ldc.i4.1
0xcb36  newarr   [mscorlib]System.Int32
0xcb3b  dup
0xcb3c  ldc.i4.0
0xcb3d  ldc.i4   0x81
0xcb42  stelem.i4
0xcb43  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupTypes(int32[])
0xcb48  ldarg.0
0xcb49  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xcb4e  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xcb53  ldstr    aCustomertype// "customerType"
0xcb58  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xcb5d  stloc.0
0xcb5e  ldarg.0
0xcb5f  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xcb64  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xcb69  ldstr    aCustomerid_0// "customerId"
0xcb6e  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xcb73  stloc.1
0xcb74  ldarg.0
0xcb75  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xcb7a  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xcb7f  ldstr    aCustomername// "customerName"
0xcb84  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xcb89  stloc.2
0xcb8a  ldc.i4.0
0xcb8b  stloc.3
0xcb8c  ldloc.0
0xcb8d  brfalse.s loc_CBBD
0xcb8f  ldloc.0
0xcb90  callvirt instance int32 [mscorlib]System.String::get_Length()
0xcb95  brfalse.s loc_CBBD
0xcb97  ldloc.0
0xcb98  ldc.i4.7
0xcb99  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xcb9e  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0xcba3  stloc.3
0xcba4  ldloc.1
0xcba5  brfalse.s loc_CBBD
0xcba7  ldloc.1
0xcba8  callvirt instance int32 [mscorlib]System.String::get_Length()
0xcbad  brfalse.s loc_CBBD
0xcbaf  ldarg.0
0xcbb0  call     instance class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Common.Web.Activities.Dialogs.ConvertToCase::get_CustomerLookup()
0xcbb5  ldloc.1
0xcbb6  ldloc.3
0xcbb7  ldloc.2
0xcbb8  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::AddItem(string, int32, string)
0xcbbd  ldarg.0
0xcbbe  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xcbc3  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xcbc8  ldstr    aSubject// "subject"
0xcbcd  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xcbd2  stloc.s  4
0xcbd4  ldarg.0
0xcbd5  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.HiddenInputControl Microsoft.Crm.Common.Web.Activities.Dialogs.ConvertToCase::subject
0xcbda  ldloc.s  4
0xcbdc  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object)
0xcbe1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xcbe6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0xcbeb  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0xcbf0  stloc.s  5
0xcbf2  ldloc.s  5
0xcbf4  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xcbf9  ldarg.0
0xcbfa  ldfld    int32 Microsoft.Crm.Common.Web.Activities.Dialogs.ConvertToCase::activityType
0xcbff  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0xcc04  stloc.s  6
0xcc06  ldarg.0
0xcc07  ldarg.0
0xcc08  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xcc0d  ldstr    aConvertActivit_2// "Convert_Activity_To_Case_InlineDlg_Titl"...
0xcc12  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xcc17  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogTitle(string)
0xcc1c  ldarg.0
0xcc1d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xcc22  ldarg.0
0xcc23  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xcc28  ldstr    aConvertActivit_3// "Convert_Activity_To_Case_Dlg_Desc"
0xcc2d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xcc32  ldc.i4.1
0xcc33  newarr   [mscorlib]System.Object
0xcc38  dup
0xcc39  ldc.i4.0
0xcc3a  ldloc.s  6
0xcc3c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LocalizedName()
0xcc41  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0xcc46  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0xcc4b  ldloc.s  5
0xcc4d  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::TryGetDescription(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xcc52  stelem.ref
0xcc53  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xcc58  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogDescription(string)
0xcc5d  ldarg.0
0xcc5e  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0xcc63  ldc.i4.1
0xcc64  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::AddStandardButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.StandardDialogButtons)
0xcc69  stloc.s  7
0xcc6b  ldarg.0
0xcc6c  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0xcc71  ldloc.s  7
0xcc73  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButton [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::get_Item(int32)
0xcc78  ldstr    aConvertActivit_4// "Convert_Activity_To_Case_Dlg_ConvertBut"...
0xcc7d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_ResourceId(string)
0xcc82  ldarg.0
0xcc83  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0xcc88  ldc.i4.2
0xcc89  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::AddStandardButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.StandardDialogButtons)
0xcc8e  pop
0xcc8f  ret
```
