# Microsoft.Crm.Web.Tools.SystemSettings.QuickFindConfiguration::ConfigureForm

- ea: `0x96e00`
- end: `0x96f0f`
- name: `Microsoft.Crm.Web.Tools.SystemSettings.QuickFindConfiguration::ConfigureForm`
- size: `271`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x96e00`

## string_xrefs

- `0x96ee6`: `SystemCustomization.QuickFindConfiguration.Note`
- `0x96ef9`: `SystemCustomization.QuickFindConfiguration.NoteForCategorizedSearchText`
- `0x96e1e`: `SystemCustomization.QuickFindConfiguration.PageTitle`
- `0x96e4b`: `SystemCustomization.QuickFindConfiguration.PageDescriptionForCategorizedSearch`
- `0x96e86`: `SystemCustomization.QuickFindConfiguration.PageDescription`

## pseudocode

```c

```

## disassembly

```asm
0x96e00  ldarg.0
0x96e01  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0x96e06  ldarg.0
0x96e07  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::_Form
0x96e0c  ldc.i4.1
0x96e0d  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ShowHeader(bool)
0x96e12  ldarg.0
0x96e13  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::_Form
0x96e18  ldarg.0
0x96e19  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x96e1e  ldstr    aSystemcustomiz_233// "SystemCustomization.QuickFindConfigurat"...
0x96e23  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x96e28  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x96e2d  ldarg.0
0x96e2e  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::_orgContext
0x96e33  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.ElasticSearchIndexUtility::IsElasticSearchEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x96e38  brfalse.s loc_96E75
0x96e3a  ldarg.0
0x96e3b  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::_Form
0x96e40  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x96e45  ldarg.0
0x96e46  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x96e4b  ldstr    aSystemcustomiz_234// "SystemCustomization.QuickFindConfigurat"...
0x96e50  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x96e55  ldc.i4.1
0x96e56  newarr   [mscorlib]System.Object
0x96e5b  dup
0x96e5c  ldc.i4.0
0x96e5d  ldarg.0
0x96e5e  ldfld    int32 Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::_maxNumberOfEntitiesAllowed
0x96e63  box      [mscorlib]System.Int32
0x96e68  stelem.ref
0x96e69  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x96e6e  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x96e73  br.s     loc_96EAE
0x96e75  ldarg.0
0x96e76  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::_Form
0x96e7b  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x96e80  ldarg.0
0x96e81  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x96e86  ldstr    aSystemcustomiz_235// "SystemCustomization.QuickFindConfigurat"...
0x96e8b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x96e90  ldc.i4.1
0x96e91  newarr   [mscorlib]System.Object
0x96e96  dup
0x96e97  ldc.i4.0
0x96e98  ldarg.0
0x96e99  ldfld    int32 Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::_maxNumberOfEntitiesAllowed
0x96e9e  box      [mscorlib]System.Int32
0x96ea3  stelem.ref
0x96ea4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x96ea9  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x96eae  ldarg.0
0x96eaf  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::_Form
0x96eb4  ldc.i4.5
0x96eb5  newarr   [mscorlib]System.String
0x96eba  dup
0x96ebb  ldc.i4.0
0x96ebc  ldarg.0
0x96ebd  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::_Form
0x96ec2  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::get_DialogTitle()
0x96ec7  stelem.ref
0x96ec8  dup
0x96ec9  ldc.i4.1
0x96eca  ldarg.0
0x96ecb  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::_Form
0x96ed0  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::get_DialogDescription()
0x96ed5  stelem.ref
0x96ed6  dup
0x96ed7  ldc.i4.2
0x96ed8  ldstr    asc_11E6FC// " "
0x96edd  stelem.ref
0x96ede  dup
0x96edf  ldc.i4.3
0x96ee0  ldarg.0
0x96ee1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x96ee6  ldstr    aSystemcustomiz_224// "SystemCustomization.QuickFindConfigurat"...
0x96eeb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x96ef0  stelem.ref
0x96ef1  dup
0x96ef2  ldc.i4.4
0x96ef3  ldarg.0
0x96ef4  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x96ef9  ldstr    aSystemcustomiz_225// "SystemCustomization.QuickFindConfigurat"...
0x96efe  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x96f03  stelem.ref
0x96f04  call     string [mscorlib]System.String::Concat(string[])
0x96f09  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_HeaderTextForNarration(string)
0x96f0e  ret
```
