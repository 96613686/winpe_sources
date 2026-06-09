# Microsoft.Crm.Web.Tools.BulkDelete.SummaryPage::ConfigurePage

- ea: `0x8f9f0`
- end: `0x8fb9a`
- name: `Microsoft.Crm.Web.Tools.BulkDelete.SummaryPage::ConfigurePage`
- size: `426`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x8fba0`

## string_xrefs

- `0x8f9f6`: `BulkDelete`
- `0x8fa56`: `BulkDeleteWizard.SummaryPage.EmailNotoficationMe`
- `0x8fa7c`: `BulkDeleteWizard.SummaryPage.EmailSeparator`
- `0x8faa2`: `BulkDeleteWizard.SummaryPage.EmailSeparator`
- `0x8fac8`: `BulkDeleteWizard.SummaryPage.RecurrenceOptionText`
- `0x8faee`: `BulkDeleteWizard.SummaryPage.DateTime`
- `0x8fb14`: `BulkDeleteWizard.SummaryPage.NoQuerySummary`
- `0x8fb44`: `BulkDeleteWizard.SummaryPage.RunNow`

## pseudocode

```c

```

## disassembly

```asm
0x8f9f0  ldarg.0
0x8f9f1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8f9f6  ldstr    aBulkdelete_0// "BulkDelete"
0x8f9fb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0x8fa00  ldarg.0
0x8fa01  ldarg.0
0x8fa02  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x8fa07  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x8fa0c  ldstr    aEntityname_0// "entityName"
0x8fa11  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x8fa16  stfld    string Microsoft.Crm.Web.Tools.BulkDelete.SummaryPage::entityName
0x8fa1b  ldarg.0
0x8fa1c  ldfld    string Microsoft.Crm.Web.Tools.BulkDelete.SummaryPage::entityName
0x8fa21  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8fa26  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetEntityMetadata(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8fa2b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LocalizedName()
0x8fa30  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x8fa35  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x8fa3a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8fa3f  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::TryGetDescription(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8fa44  stloc.0
0x8fa45  ldarg.0
0x8fa46  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8fa4b  ldstr    aLocidEmailme// "LOCID_EMAILME"
0x8fa50  ldarg.0
0x8fa51  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x8fa56  ldstr    aBulkdeletewiza_13// "BulkDeleteWizard.SummaryPage.EmailNotof"...
0x8fa5b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8fa60  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8fa65  ldc.i4.0
0x8fa66  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x8fa6b  ldarg.0
0x8fa6c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8fa71  ldstr    aLocidEmailSepa// "LOCID_EMAIL_SEPARATOR"
0x8fa76  ldarg.0
0x8fa77  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x8fa7c  ldstr    aBulkdeletewiza_14// "BulkDeleteWizard.SummaryPage.EmailSepar"...
0x8fa81  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8fa86  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8fa8b  ldc.i4.0
0x8fa8c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x8fa91  ldarg.0
0x8fa92  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8fa97  ldstr    aLocidEmailSepa// "LOCID_EMAIL_SEPARATOR"
0x8fa9c  ldarg.0
0x8fa9d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x8faa2  ldstr    aBulkdeletewiza_14// "BulkDeleteWizard.SummaryPage.EmailSepar"...
0x8faa7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8faac  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8fab1  ldc.i4.0
0x8fab2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x8fab7  ldarg.0
0x8fab8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8fabd  ldstr    aLocidJobRecurr// "LOCID_JOB_RECURRING"
0x8fac2  ldarg.0
0x8fac3  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x8fac8  ldstr    aBulkdeletewiza_15// "BulkDeleteWizard.SummaryPage.Recurrence"...
0x8facd  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8fad2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8fad7  ldc.i4.0
0x8fad8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x8fadd  ldarg.0
0x8fade  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8fae3  ldstr    aLocidJobNonrec// "LOCID_JOB_NONRECURRING"
0x8fae8  ldarg.0
0x8fae9  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x8faee  ldstr    aBulkdeletewiza_16// "BulkDeleteWizard.SummaryPage.DateTime"
0x8faf3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8faf8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8fafd  ldc.i4.0
0x8fafe  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x8fb03  ldarg.0
0x8fb04  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8fb09  ldstr    aLocidJobCriter// "LOCID_JOB_CRITERIANOTDEFINED"
0x8fb0e  ldarg.0
0x8fb0f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x8fb14  ldstr    aBulkdeletewiza_17// "BulkDeleteWizard.SummaryPage.NoQuerySum"...
0x8fb19  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8fb1e  ldc.i4.1
0x8fb1f  newarr   [mscorlib]System.Object
0x8fb24  dup
0x8fb25  ldc.i4.0
0x8fb26  ldloc.0
0x8fb27  stelem.ref
0x8fb28  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext, object[])
0x8fb2d  ldc.i4.0
0x8fb2e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x8fb33  ldarg.0
0x8fb34  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8fb39  ldstr    aLocidJobSchedu// "LOCID_JOB_SCHEDULENOW"
0x8fb3e  ldarg.0
0x8fb3f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x8fb44  ldstr    aBulkdeletewiza_18// "BulkDeleteWizard.SummaryPage.RunNow"
0x8fb49  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8fb4e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8fb53  ldc.i4.0
0x8fb54  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x8fb59  ldarg.0
0x8fb5a  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x8fb5f  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x8fb64  ldstr    aStartdatetime// "startDateTime"
0x8fb69  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x8fb6e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8fb73  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::Parse(string, class [mscorlib]System.IFormatProvider)
0x8fb78  stloc.1
0x8fb79  ldarg.0
0x8fb7a  ldloca.s 1
0x8fb7c  call     instance string [mscorlib]System.DateTime::ToShortDateString()
0x8fb81  stfld    string Microsoft.Crm.Web.Tools.BulkDelete.SummaryPage::startDate
0x8fb86  ldarg.0
0x8fb87  ldloca.s 1
0x8fb89  call     instance string [mscorlib]System.DateTime::ToShortTimeString()
0x8fb8e  stfld    string Microsoft.Crm.Web.Tools.BulkDelete.SummaryPage::startTime
0x8fb93  ldarg.0
0x8fb94  call     instance void Microsoft.Crm.Web.Tools.BulkDelete.SummaryPage::ConfigureAdvancedFindControl()
0x8fb99  ret
```
