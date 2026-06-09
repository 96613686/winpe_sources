# Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.ManageAttributePage::ConfigureMenus

- ea: `0xb74f0`
- end: `0xb76c5`
- name: `Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.ManageAttributePage::ConfigureMenus`
- size: `469`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0xb74f0`
- `0xbaed0`
- `0x10f4c0`

## string_xrefs

- `0xb7526`: `ManageAttributePage.CreateMode.Title`
- `0xb7567`: `ManageAttributePage.CreateMode.Title.Line2`
- `0xb75bc`: `ManageAttributePage.UpdateMode.Title`
- `0xb7610`: `ManageAttributePage.UpdateMode.Title.Line2`

## pseudocode

```c

```

## disassembly

```asm
0xb74f0  ldarg.0
0xb74f1  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppMenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmMenuBar
0xb74f6  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppGenericMenuBar
0xb74fb  stloc.0
0xb74fc  ldarg.0
0xb74fd  ldfld    valuetype Mode Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.ManageAttributePage::_mode
0xb7502  stloc.1
0xb7503  ldloc.1
0xb7504  switch   loc_B751A, loc_B75B0, loc_B75B0
0xb7515  br       loc_B765D
0xb751a  ldarg.0
0xb751b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb7520  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0xb7525  ldarg.0
0xb7526  ldstr    aManageattribut_6// "ManageAttributePage.CreateMode.Title"
0xb752b  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.ManageAttributePage::GetSCString(string name)
0xb7530  ldc.i4.1
0xb7531  newarr   [mscorlib]System.Object
0xb7536  dup
0xb7537  ldc.i4.0
0xb7538  ldarg.0
0xb7539  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.ManageAttributePage::_entityMD
0xb753e  ldc.i4.1
0xb753f  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0xb7544  stelem.ref
0xb7545  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xb754a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_Title(string)
0xb754f  ldloc.0
0xb7550  ldarg.0
0xb7551  ldstr    aManageattribut_7// "ManageAttributePage.Title.Line1"
0xb7556  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.ManageAttributePage::GetSCString(string name)
0xb755b  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppGenericMenuBar::set_TitleType(string)
0xb7560  ldloc.0
0xb7561  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0xb7566  ldarg.0
0xb7567  ldstr    aManageattribut_8// "ManageAttributePage.CreateMode.Title.Li"...
0xb756c  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.ManageAttributePage::GetSCString(string name)
0xb7571  ldc.i4.1
0xb7572  newarr   [mscorlib]System.Object
0xb7577  dup
0xb7578  ldc.i4.0
0xb7579  ldarg.0
0xb757a  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.ManageAttributePage::_entityMD
0xb757f  ldc.i4.1
0xb7580  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0xb7585  stelem.ref
0xb7586  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xb758b  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppGenericMenuBar::set_TitleName(string)
0xb7590  ldarg.0
0xb7591  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.PowerAppsNavBar Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.ManageAttributePage::_powerAppsNavBar
0xb7596  ldarg.0
0xb7597  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xb759c  ldstr    aFormTitleNew// "Form_Title_New"
0xb75a1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xb75a6  stfld    string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.PowerAppsNavBar::ComponentName
0xb75ab  br       loc_B765D
0xb75b0  ldarg.0
0xb75b1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb75b6  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0xb75bb  ldarg.0
0xb75bc  ldstr    aManageattribut_9// "ManageAttributePage.UpdateMode.Title"
0xb75c1  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.ManageAttributePage::GetSCString(string name)
0xb75c6  ldc.i4.2
0xb75c7  newarr   [mscorlib]System.Object
0xb75cc  dup
0xb75cd  ldc.i4.0
0xb75ce  ldarg.0
0xb75cf  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.ManageAttributePage::_attributeMD
0xb75d4  call     string AttributeInfo::GetDisplayName(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attributeMD)
0xb75d9  stelem.ref
0xb75da  dup
0xb75db  ldc.i4.1
0xb75dc  ldarg.0
0xb75dd  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.ManageAttributePage::_attributeMD
0xb75e2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Entity()
0xb75e7  ldc.i4.1
0xb75e8  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0xb75ed  stelem.ref
0xb75ee  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xb75f3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_Title(string)
0xb75f8  ldloc.0
0xb75f9  ldarg.0
0xb75fa  ldstr    aManageattribut_7// "ManageAttributePage.Title.Line1"
0xb75ff  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.ManageAttributePage::GetSCString(string name)
0xb7604  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppGenericMenuBar::set_TitleType(string)
0xb7609  ldloc.0
0xb760a  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0xb760f  ldarg.0
0xb7610  ldstr    aManageattribut_10// "ManageAttributePage.UpdateMode.Title.Li"...
0xb7615  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.ManageAttributePage::GetSCString(string name)
0xb761a  ldc.i4.2
0xb761b  newarr   [mscorlib]System.Object
0xb7620  dup
0xb7621  ldc.i4.0
0xb7622  ldarg.0
0xb7623  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.ManageAttributePage::_attributeMD
0xb7628  call     string AttributeInfo::GetDisplayName(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attributeMD)
0xb762d  stelem.ref
0xb762e  dup
0xb762f  ldc.i4.1
0xb7630  ldarg.0
0xb7631  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.ManageAttributePage::_attributeMD
0xb7636  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Entity()
0xb763b  ldc.i4.1
0xb763c  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0xb7641  stelem.ref
0xb7642  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xb7647  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppGenericMenuBar::set_TitleName(string)
0xb764c  ldarg.0
0xb764d  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.PowerAppsNavBar Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.ManageAttributePage::_powerAppsNavBar
0xb7652  ldloc.0
0xb7653  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppGenericMenuBar::get_TitleName()
0xb7658  stfld    string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.PowerAppsNavBar::ComponentName
0xb765d  ldloc.0
0xb765e  ldarg.0
0xb765f  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.ManageAttributePage::_attributeMD
0xb7664  brtrue.s loc_B7673
0xb7666  ldarg.0
0xb7667  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.ManageAttributePage::_entityMD
0xb766c  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0xb7671  br.s     loc_B7683
0xb7673  ldarg.0
0xb7674  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.ManageAttributePage::_attributeMD
0xb7679  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Entity()
0xb767e  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0xb7683  ldc.i4.7
0xb7684  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xb7689  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconUtil::GetIconPath(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xb768e  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppGenericMenuBar::set_CustomIconPath(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0xb7693  ldloc.0
0xb7694  ldc.i4.1
0xb7695  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppMenuBar::set_ShowToolBar(bool)
0xb769a  ldloc.0
0xb769b  ldarg.0
0xb769c  ldftn    instance void Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.ManageAttributePage::ToolBarReady(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs e)
0xb76a2  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuReadyEventHandler::.ctor(object, native int)
0xb76a7  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppMenuBar::set_OnToolBarReady(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuReadyEventHandler)
0xb76ac  ldloc.0
0xb76ad  ldarg.0
0xb76ae  ldftn    instance void Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.ManageAttributePage::MenuReady(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs e)
0xb76b4  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuReadyEventHandler::.ctor(object, native int)
0xb76b9  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppMenuBar::set_OnMenuReady(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuReadyEventHandler)
0xb76be  ldloc.0
0xb76bf  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppMenuBar::Execute()
0xb76c4  ret
```
