# Microsoft.Crm.Application.Pages.Tools.FormEditor.Dialogs.FieldPropertiesPage::SetArticleTabHeader

- ea: `0xe4340`
- end: `0xe4a2a`
- name: `Microsoft.Crm.Application.Pages.Tools.FormEditor.Dialogs.FieldPropertiesPage::SetArticleTabHeader`
- size: `1770`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0xe3e60`

## callees

- `0xe4340`
- `0xe9360`
- `0xe94e0`
- `0xe95f0`

## string_xrefs

- `0xe4366`: `/_common/styles/dialogs.css.aspx`
- `0xe4417`: `/_static/_common/styles/AutoToolTip.js`
- `0xe4346`: `/_common/styles/select.css.aspx`
- `0xe451c`: `LOCID_ACTIONS_COPY`
- `0xe4527`: `KMControl.SearchKMArticles.CopyArticleIconAltText`

## pseudocode

```c

```

## disassembly

```asm
0xe4340  ldarg.0
0xe4341  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe4346  ldstr    aCommonStylesSe// "/_common/styles/select.css.aspx"
0xe434b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xe4350  ldarg.0
0xe4351  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe4356  ldstr    aNavTabsCssAspx// "/_nav/tabs.css.aspx"
0xe435b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xe4360  ldarg.0
0xe4361  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe4366  ldstr    aCommonStylesDi// "/_common/styles/dialogs.css.aspx"
0xe436b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xe4370  ldarg.0
0xe4371  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe4376  ldstr    aMscrmDialogsco// "Mscrm.DialogsControl"
0xe437b  ldnull
0xe437c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0xe4381  ldarg.0
0xe4382  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe4387  ldstr    aToolsFormedito_5// "/tools/formeditor/styles/dialogs.css.as"...
0xe438c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xe4391  ldarg.0
0xe4392  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe4397  ldstr    aFormsControlsC// "/_forms/controls/controls.css.aspx"
0xe439c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xe43a1  ldarg.0
0xe43a2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe43a7  ldstr    aToolsFieldsele// "/_tools/fieldselect/fieldselect.css.asp"...
0xe43ac  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xe43b1  ldarg.0
0xe43b2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe43b7  ldstr    aStaticFormsSel// "/_static/_forms/select.js"
0xe43bc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xe43c1  ldarg.0
0xe43c2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe43c7  ldstr    aStaticToolsFor// "/_static/tools/formeditor/scripts/objec"...
0xe43cc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xe43d1  ldarg.0
0xe43d2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe43d7  ldstr    aStaticToolsFor_3// "/_static/tools/formeditor/scripts/dialo"...
0xe43dc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xe43e1  ldarg.0
0xe43e2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe43e7  ldstr    aStaticToolsFor_1// "/_static/tools/formeditor/scripts/util."...
0xe43ec  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xe43f1  ldarg.0
0xe43f2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe43f7  ldstr    aStaticToolsFor_0// "/_static/tools/formeditor/scripts/field"...
0xe43fc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xe4401  ldarg.0
0xe4402  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe4407  ldstr    aStaticToolsFie// "/_static/_tools/fieldselect/fieldselect"...
0xe440c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xe4411  ldarg.0
0xe4412  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe4417  ldstr    aStaticCommonSt// "/_static/_common/styles/AutoToolTip.js"
0xe441c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xe4421  ldarg.0
0xe4422  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe4427  ldstr    aLocidValidRows// "LOCID_VALID_ROWSPERPAGE"
0xe442c  ldarg.0
0xe442d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe4432  ldstr    aFormeditorDial_17// "Formeditor_Dialogs_SearchWidget_Invalid"...
0xe4437  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe443c  ldc.i4.0
0xe443d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe4442  ldarg.0
0xe4443  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe4448  ldstr    aWebToolsFormed_36// "Web.Tools.FormEditor.Ribbon.Button.SubG"...
0xe444d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe4452  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0xe4457  callvirt instance string [mscorlib]System.String::ToLower(class [mscorlib]System.Globalization.CultureInfo)
0xe445c  stloc.0
0xe445d  ldarg.0
0xe445e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe4463  ldstr    aLocidFormedSub// "LOCID_FORMED_SUBGRID_COLSPAN"
0xe4468  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0xe446d  ldarg.0
0xe446e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe4473  ldstr    aAddcolumnCapti// "AddColumn_Caption"
0xe4478  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe447d  ldc.i4.1
0xe447e  newarr   [mscorlib]System.Object
0xe4483  dup
0xe4484  ldc.i4.0
0xe4485  ldloc.0
0xe4486  stelem.ref
0xe4487  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xe448c  ldc.i4.0
0xe448d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe4492  ldarg.0
0xe4493  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe4498  ldstr    aLocidViewsShow_1// "LOCID_VIEWS_SHOW_ALL_ACTIONS"
0xe449d  ldarg.0
0xe449e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe44a3  ldstr    aWebToolsFormed_37// "Web.Tools.FormEditor.Dialogs.section.Ar"...
0xe44a8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe44ad  ldc.i4.0
0xe44ae  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe44b3  ldarg.0
0xe44b4  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe44b9  ldstr    aLocidViewsShow_2// "LOCID_VIEWS_SHOW_SEL_ACTIONS"
0xe44be  ldarg.0
0xe44bf  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe44c4  ldstr    aWebToolsFormed_38// "Web.Tools.FormEditor.Dialogs.section.Ar"...
0xe44c9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe44ce  ldc.i4.0
0xe44cf  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe44d4  ldarg.0
0xe44d5  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe44da  ldstr    aLocidActionsAs// "LOCID_ACTIONS_ASSOCIATE"
0xe44df  ldarg.0
0xe44e0  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe44e5  ldstr    aKmcontrolSearc_0// "KMControl.SearchKMArticles.AssociateArt"...
0xe44ea  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe44ef  ldc.i4.0
0xe44f0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe44f5  ldarg.0
0xe44f6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe44fb  ldstr    aLocidActionsDi// "LOCID_ACTIONS_DISASSOCIATE"
0xe4500  ldarg.0
0xe4501  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe4506  ldstr    aKmcontrolSearc_1// "KMControl.SearchKMArticles.Disassociate"...
0xe450b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe4510  ldc.i4.0
0xe4511  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe4516  ldarg.0
0xe4517  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe451c  ldstr    aLocidActionsCo// "LOCID_ACTIONS_COPY"
0xe4521  ldarg.0
0xe4522  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe4527  ldstr    aKmcontrolSearc_2// "KMControl.SearchKMArticles.CopyArticleI"...
0xe452c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe4531  ldc.i4.0
0xe4532  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe4537  ldarg.0
0xe4538  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe453d  ldstr    aLocidActionsEm// "LOCID_ACTIONS_EMAIL"
0xe4542  ldarg.0
0xe4543  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe4548  ldstr    aKmcontrolSearc_3// "KMControl.SearchKMArticles.EmailArticle"...
0xe454d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe4552  ldc.i4.0
0xe4553  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe4558  ldarg.0
0xe4559  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe455e  ldstr    aLocidActionsEm_0// "LOCID_ACTIONS_EMAILCONTENT"
0xe4563  ldarg.0
0xe4564  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe4569  ldstr    aKmcontrolSearc_4// "KMControl.SearchKMArticles.EmailArticle"...
0xe456e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe4573  ldc.i4.0
0xe4574  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe4579  ldarg.0
0xe457a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe457f  ldstr    aLocidActionsPo// "LOCID_ACTIONS_POPOUT"
0xe4584  ldarg.0
0xe4585  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe458a  ldstr    aKmcontrolSearc_5// "KMControl.SearchKMArticles.PopOutAltTex"...
0xe458f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe4594  ldc.i4.0
0xe4595  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe459a  ldarg.0
0xe459b  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Application.Pages.Tools.FormEditor.Dialogs.FieldPropertiesPage::allowChangeFiltersLabel
0xe45a0  ldarg.0
0xe45a1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe45a6  ldstr    aWebToolsFormed_39// "Web.Tools.FormEditor.Dialogs.section.Ar"...
0xe45ab  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe45b0  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerText(string)
0xe45b5  ldarg.0
0xe45b6  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Application.Pages.Tools.FormEditor.Dialogs.FieldPropertiesPage::allowChangeFiltersLabel
0xe45bb  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xe45c0  ldstr    aTitle// "title"
0xe45c5  ldarg.0
0xe45c6  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe45cb  ldstr    aWebToolsFormed_40// "Web.Tools.FormEditor.Dialogs.section.Ar"...
0xe45d0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe45d5  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xe45da  ldarg.0
0xe45db  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Application.Pages.Tools.FormEditor.Dialogs.FieldPropertiesPage::enableAutomaticSuggestionsLabel
0xe45e0  ldarg.0
0xe45e1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe45e6  ldstr    aWebToolsFormed_41// "Web.Tools.FormEditor.Dialogs.section.Ar"...
0xe45eb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe45f0  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerText(string)
0xe45f5  ldarg.0
0xe45f6  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Application.Pages.Tools.FormEditor.Dialogs.FieldPropertiesPage::enableAutomaticSuggestionsLabel
0xe45fb  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xe4600  ldstr    aTitle// "title"
0xe4605  ldarg.0
0xe4606  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe460b  ldstr    aWebToolsFormed_42// "Web.Tools.FormEditor.Dialogs.section.Ar"...
0xe4610  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe4615  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xe461a  ldarg.0
0xe461b  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Application.Pages.Tools.FormEditor.Dialogs.FieldPropertiesPage::showLanguageFilterLabel
0xe4620  ldarg.0
0xe4621  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe4626  ldstr    aWebToolsFormed_43// "Web.Tools.FormEditor.Dialogs.section.Ar"...
0xe462b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe4630  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerText(string)
0xe4635  ldarg.0
0xe4636  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Application.Pages.Tools.FormEditor.Dialogs.FieldPropertiesPage::showLanguageFilterLabel
0xe463b  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xe4640  ldstr    aTitle// "title"
0xe4645  ldarg.0
0xe4646  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe464b  ldstr    aWebToolsFormed_44// "Web.Tools.FormEditor.Dialogs.section.Ar"...
0xe4650  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe4655  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xe465a  ldarg.0
0xe465b  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Application.Pages.Tools.FormEditor.Dialogs.FieldPropertiesPage::showDepartmentFilterLabel
0xe4660  ldarg.0
0xe4661  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe4666  ldstr    aWebToolsFormed_45// "Web.Tools.FormEditor.Dialogs.section.Ar"...
0xe466b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe4670  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerText(string)
0xe4675  ldarg.0
0xe4676  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Application.Pages.Tools.FormEditor.Dialogs.FieldPropertiesPage::showDepartmentFilterLabel
0xe467b  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xe4680  ldstr    aTitle// "title"
0xe4685  ldarg.0
0xe4686  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe468b  ldstr    aWebToolsFormed_46// "Web.Tools.FormEditor.Dialogs.section.Ar"...
0xe4690  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe4695  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xe469a  ldarg.0
0xe469b  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Application.Pages.Tools.FormEditor.Dialogs.FieldPropertiesPage::enableRatingLabel
0xe46a0  ldarg.0
0xe46a1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe46a6  ldstr    aWebToolsFormed_47// "Web.Tools.FormEditor.Dialogs.section.Ar"...
0xe46ab  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe46b0  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerText(string)
0xe46b5  ldarg.0
0xe46b6  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Application.Pages.Tools.FormEditor.Dialogs.FieldPropertiesPage::enableRatingLabel
0xe46bb  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xe46c0  ldstr    aTitle// "title"
0xe46c5  ldarg.0
0xe46c6  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe46cb  ldstr    aWebToolsFormed_48// "Web.Tools.FormEditor.Dialogs.section.Ar"...
0xe46d0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe46d5  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xe46da  ldarg.0
0xe46db  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Number Microsoft.Crm.Application.Pages.Tools.FormEditor.Dialogs.FieldPropertiesPage::RowsPerPage
0xe46e0  ldc.i4.0
0xe46e1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Number::set_Precision(int32)
0xe46e6  ldarg.0
0xe46e7  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Number Microsoft.Crm.Application.Pages.Tools.FormEditor.Dialogs.FieldPropertiesPage::RowsPerPage
0xe46ec  ldc.r8   1.0
0xe46f5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Number::set_MinValue(float64)
0xe46fa  ldarg.0
0xe46fb  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Number Microsoft.Crm.Application.Pages.Tools.FormEditor.Dialogs.FieldPropertiesPage::RowsPerPage
0xe4700  ldc.r8   20.0
0xe4709  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Number::set_MaxValue(float64)
0xe470e  ldarg.0
0xe470f  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Number Microsoft.Crm.Application.Pages.Tools.FormEditor.Dialogs.FieldPropertiesPage::RowsPerPage
0xe4714  ldc.r8   10.0
0xe471d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Number::set_Value(float64)
0xe4722  ldarg.0
0xe4723  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Pages.Tools.FormEditor.Dialogs.FieldPropertiesPage::primaryCustomer
0xe4728  ldnull
0xe4729  ldnull
0xe472a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddItem(string, string)
0xe472f  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::.ctor()
0xe4734  pop
0xe4735  ldarg.0
0xe4736  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xe473b  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xe4740  ldstr    aObjecttypecode_0// "objectTypeCode"
0xe4745  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xe474a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xe474f  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0xe4754  stloc.1
0xe4755  ldloc.1
0xe4756  ldc.i4.0
0xe4757  call     class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>> Microsoft.Crm.Application.Pages.Tools.FormEditor.Dialogs.KMControlHelper::RetrieveAttributeList(int32 entityObjCode, bool isReferencedField)
0xe475c  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::GetEnumerator()
0xe4761  stloc.2
0xe4762  br.s     loc_E4785
0xe4764  ldloca.s 2
0xe4766  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::get_Current()
0xe476b  stloc.3
0xe476c  ldarg.0
0xe476d  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Pages.Tools.FormEditor.Dialogs.FieldPropertiesPage::autosuggestion
0xe4772  ldloca.s 3
0xe4774  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0xe4779  ldloca.s 3
0xe477b  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0xe4780  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddItem(string, string)
0xe4785  ldloca.s 2
0xe4787  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::MoveNext()
0xe478c  brtrue.s loc_E4764
0xe478e  leave.s  loc_E479E
0xe4790  ldloca.s 2
0xe4792  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>
0xe4798  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe479d  endfinally
0xe479e  ldc.i4   0x26E1
0xe47a3  call     class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, string>> Microsoft.Crm.Application.Pages.Tools.FormEditor.Dialogs.KMControlHelper::RetrieveAttributeList(int32 entityObjCode)
0xe47a8  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, string>>::GetEnumerator()
  ... truncated ...
```
