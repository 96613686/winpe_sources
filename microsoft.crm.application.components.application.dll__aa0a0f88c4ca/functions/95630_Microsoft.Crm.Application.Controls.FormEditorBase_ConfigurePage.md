# Microsoft.Crm.Application.Controls.FormEditorBase::ConfigurePage

- ea: `0x95630`
- end: `0x95ac6`
- name: `Microsoft.Crm.Application.Controls.FormEditorBase::ConfigurePage`
- size: `1174`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x8d1e0`
- `0x8d7b0`
- `0x8d7d0`
- `0x8d800`
- `0x97d00`
- `0xab8c0`

## string_xrefs

- `0x9566c`: `/_common/styles/dialogs.css.aspx`
- `0x95a23`: `/_static/_common/scripts/CrmServiceProxyFramework.js`
- `0x9567c`: `/_common/styles/select.css.aspx`
- `0x9563c`: `/_nav/taskbox.css.aspx`
- `0x956bd`: `/_static/_common/scripts/PreviewScript.js`
- `0x956cd`: `/_static/_common/scripts/PreviewDragDrop.js`
- `0x95768`: `SystemCustomization.EntityUtil.Messages.CannotUpdateSystemEntityIcons`
- `0x95789`: `SystemCustomization.EntityUtil.Messages.CannotDeleteSystemEntity`
- `0x957cb`: `SystemCustomization.EntityUtil.Messages.ConfirmEntityDelete`
- `0x95915`: `SystemCustomization.AttributeListPage.Buttons.Create.Tooltip`
- `0x959f3`: `/_static/tools/formeditor/scripts/move.js`
- `0x95a43`: `/_static/_common/scripts/InlineEditCommon.js`

## pseudocode

```c

```

## disassembly

```asm
0x95630  ldarg.0
0x95631  call     instance void Microsoft.Crm.Application.Controls.PageManager::ConfigurePage()
0x95636  ldarg.0
0x95637  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9563c  ldstr    aNavTaskboxCssA// "/_nav/taskbox.css.aspx"
0x95641  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x95646  ldarg.0
0x95647  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9564c  ldstr    aNavTabsCssAspx// "/_nav/tabs.css.aspx"
0x95651  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x95656  ldarg.0
0x95657  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9565c  ldstr    aNavNavCssAspx// "/_nav/nav.css.aspx"
0x95661  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x95666  ldarg.0
0x95667  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9566c  ldstr    aCommonStylesDi// "/_common/styles/dialogs.css.aspx"
0x95671  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x95676  ldarg.0
0x95677  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9567c  ldstr    aCommonStylesSe// "/_common/styles/select.css.aspx"
0x95681  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x95686  ldarg.0
0x95687  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9568c  ldstr    aAppnavAppnavba// "/appnav/appnavbar.css.aspx"
0x95691  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x95696  ldarg.0
0x95697  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9569c  ldstr    aMscrmDialogsco// "Mscrm.DialogsControl"
0x956a1  ldnull
0x956a2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0x956a7  ldarg.0
0x956a8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x956ad  ldstr    aStaticToolsFor// "/_static/tools/formeditor/scripts/FormE"...
0x956b2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x956b7  ldarg.0
0x956b8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x956bd  ldstr    aStaticCommonSc_22// "/_static/_common/scripts/PreviewScript."...
0x956c2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x956c7  ldarg.0
0x956c8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x956cd  ldstr    aStaticCommonSc_23// "/_static/_common/scripts/PreviewDragDro"...
0x956d2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x956d7  ldarg.0
0x956d8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x956dd  ldstr    aStaticToolsFor_0// "/_static/tools/formeditor/scripts/dragd"...
0x956e2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x956e7  ldarg.0
0x956e8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x956ed  ldstr    aStaticToolsDep// "/_static/tools/dependency/scripts/depen"...
0x956f2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x956f7  ldarg.0
0x956f8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x956fd  ldstr    aStaticToolsSol// "/_static/tools/solution/scripts/Managed"...
0x95702  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x95707  ldarg.0
0x95708  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9570d  ldstr    aStaticToolsSol_0// "/_static/tools/solution/scripts/StatusR"...
0x95712  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x95717  ldarg.0
0x95718  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9571d  ldstr    aToolsFormedito_0// "/tools/formeditor/styles/formeditor.css"...
0x95722  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x95727  ldarg.0
0x95728  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9572d  ldstr    aStaticToolsSys// "/_static/tools/systemcustomization/scri"...
0x95732  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x95737  ldarg.0
0x95738  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9573d  ldstr    aStaticToolsSys_0// "/_static/tools/systemcustomization/enti"...
0x95742  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x95747  ldarg.0
0x95748  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9574d  ldstr    aStaticToolsSys_1// "/_static/tools/systemcustomization/scri"...
0x95752  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x95757  ldarg.0
0x95758  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9575d  ldstr    aLocidEntutlCan// "LOCID_ENTUTL_CANTUPDSYSENTICN"
0x95762  ldarg.0
0x95763  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x95768  ldstr    aSystemcustomiz_6// "SystemCustomization.EntityUtil.Messages"...
0x9576d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x95772  ldc.i4.0
0x95773  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x95778  ldarg.0
0x95779  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9577e  ldstr    aLocidEntutlCan_0// "LOCID_ENTUTL_CANTDELSYSENT"
0x95783  ldarg.0
0x95784  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x95789  ldstr    aSystemcustomiz_7// "SystemCustomization.EntityUtil.Messages"...
0x9578e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x95793  ldc.i4.0
0x95794  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x95799  ldarg.0
0x9579a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9579f  ldstr    aLocidEntutlCan_1// "LOCID_ENTUTL_CANTPUBLISHENT"
0x957a4  ldarg.0
0x957a5  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x957aa  ldstr    aSystemcustomiz_8// "SystemCustomization.EntityUtil.Messages"...
0x957af  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x957b4  ldc.i4.0
0x957b5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x957ba  ldarg.0
0x957bb  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x957c0  ldstr    aLocidEntutlCon// "LOCID_ENTUTL_CONFIRMDEL"
0x957c5  ldarg.0
0x957c6  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x957cb  ldstr    aSystemcustomiz_9// "SystemCustomization.EntityUtil.Messages"...
0x957d0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x957d5  ldc.i4.0
0x957d6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x957db  ldarg.0
0x957dc  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x957e1  ldstr    aLocidEntutlCre// "LOCID_ENTUTL_CREATINGENT"
0x957e6  ldarg.0
0x957e7  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x957ec  ldstr    aSystemcustomiz_10// "SystemCustomization.EntityUtil.Messages"...
0x957f1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x957f6  ldc.i4.0
0x957f7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x957fc  ldarg.0
0x957fd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x95802  ldstr    aLocidEntutlUpd// "LOCID_ENTUTL_UPDATINGENT"
0x95807  ldarg.0
0x95808  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9580d  ldstr    aSystemcustomiz_11// "SystemCustomization.EntityUtil.Messages"...
0x95812  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x95817  ldc.i4.0
0x95818  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9581d  ldarg.0
0x9581e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x95823  ldstr    aLocidEntutlDel// "LOCID_ENTUTL_DELETINGENT"
0x95828  ldarg.0
0x95829  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9582e  ldstr    aSystemcustomiz_12// "SystemCustomization.EntityUtil.Messages"...
0x95833  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x95838  ldc.i4.0
0x95839  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9583e  ldarg.0
0x9583f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x95844  ldstr    aLocidEntutlPub// "LOCID_ENTUTL_PUBLISHINGENT"
0x95849  ldarg.0
0x9584a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9584f  ldstr    aSystemcustomiz_13// "SystemCustomization.EntityUtil.Messages"...
0x95854  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x95859  ldc.i4.0
0x9585a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9585f  ldarg.0
0x95860  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x95865  ldstr    aLocidSyscustCa// "LOCID_SYSCUST_CANTBEBLANK"
0x9586a  ldarg.0
0x9586b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x95870  ldstr    aSystemcustomiz_14// "SystemCustomization.Validation.Errors.C"...
0x95875  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9587a  ldc.i4.0
0x9587b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x95880  ldarg.0
0x95881  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x95886  ldstr    aLocidSyscustIn// "LOCID_SYSCUST_INVALCHARS"
0x9588b  ldarg.0
0x9588c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x95891  ldstr    aSystemcustomiz_15// "SystemCustomization.Validation.Errors.C"...
0x95896  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9589b  ldc.i4.0
0x9589c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x958a1  ldarg.0
0x958a2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x958a7  ldstr    aLocidSyscustAl// "LOCID_SYSCUST_ALPHANUMSONLY"
0x958ac  ldarg.0
0x958ad  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x958b2  ldstr    aSystemcustomiz_16// "SystemCustomization.Validation.Errors.C"...
0x958b7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x958bc  ldc.i4.0
0x958bd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x958c2  ldarg.0
0x958c3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x958c8  ldstr    aLocidFormedCan// "LOCID_FORMED_CANNOTPUBLISH"
0x958cd  ldarg.0
0x958ce  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x958d3  ldstr    aWebToolsFormed_0// "Web.Tools.FormEditor.CanNotPublish.Mess"...
0x958d8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x958dd  ldc.i4.0
0x958de  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x958e3  ldarg.0
0x958e4  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x958e9  ldstr    aLocidAnotherEx// "LOCID_ANOTHER_EXPANDING_TAB"
0x958ee  ldarg.0
0x958ef  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x958f4  ldstr    aWebToolsFormed_1// "Web.Tools.FormEditor.scripts.Fielddialo"...
0x958f9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x958fe  ldc.i4.0
0x958ff  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x95904  ldarg.0
0x95905  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9590a  ldstr    aLocidNewButton// "LOCID_NEW_BUTTON_TOOL_TIP"
0x9590f  ldarg.0
0x95910  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x95915  ldstr    aSystemcustomiz_17// "SystemCustomization.AttributeListPage.B"...
0x9591a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9591f  ldc.i4.0
0x95920  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x95925  ldarg.0
0x95926  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9592b  ldstr    aLocidFormLabel// "LOCID_FORM_LABEL_PREFIX"
0x95930  ldarg.0
0x95931  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x95936  ldstr    aFormEditorForm// "Form_Editor_Form_Label_Prefix"
0x9593b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x95940  ldc.i4.0
0x95941  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x95946  ldarg.0
0x95947  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9594c  ldstr    aLocidSolutionL// "LOCID_SOLUTION_LABEL"
0x95951  ldarg.0
0x95952  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x95957  ldstr    aFormEditorSolu// "Form_Editor_Solution_Label_Prefix"
0x9595c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x95961  ldstr    asc_F74F4// " "
0x95966  ldarg.0
0x95967  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext Microsoft.Crm.Application.Controls.AppPage::get_CurrentSolutionContext()
0x9596c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext::get_SolutionName()
0x95971  call     string [mscorlib]System.String::Concat(string, string, string)
0x95976  ldc.i4.0
0x95977  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9597c  ldarg.0
0x9597d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x95982  ldstr    aLocidMaxRefpan// "LOCID_MAX_REFPANEL_LIMIT_REACHED"
0x95987  ldarg.0
0x95988  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9598d  ldstr    aFormeditorDial// "Formeditor_Dialogs_Refpanel_Max_Limit_M"...
0x95992  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x95997  ldc.i4.0
0x95998  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9599d  ldarg.0
0x9599e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x959a3  ldstr    aStaticToolsFor_1// "/_static/tools/formeditor/scripts/util."...
0x959a8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x959ad  ldarg.0
0x959ae  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x959b3  ldstr    aStaticToolsFor_2// "/_static/tools/formeditor/scripts/objec"...
0x959b8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x959bd  ldarg.0
0x959be  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x959c3  ldstr    aStaticToolsFor_3// "/_static/tools/formeditor/scripts/tabs."...
0x959c8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x959cd  ldarg.0
0x959ce  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x959d3  ldstr    aStaticToolsFor_4// "/_static/tools/formeditor/scripts/secti"...
0x959d8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x959dd  ldarg.0
0x959de  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x959e3  ldstr    aStaticToolsFor_5// "/_static/tools/formeditor/scripts/field"...
0x959e8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x959ed  ldarg.0
0x959ee  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x959f3  ldstr    aStaticToolsFor_6// "/_static/tools/formeditor/scripts/move."...
0x959f8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x959fd  ldarg.0
0x959fe  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x95a03  ldstr    aStaticToolsVie// "/_static/tools/vieweditor/scripts/field"...
0x95a08  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x95a0d  ldarg.0
0x95a0e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x95a13  ldstr    aStaticToolsFor// "/_static/tools/formeditor/scripts/FormE"...
0x95a18  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x95a1d  ldarg.0
0x95a1e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x95a23  ldstr    aStaticCommonSc_6// "/_static/_common/scripts/CrmServiceProx"...
0x95a28  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x95a2d  ldarg.0
0x95a2e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x95a33  ldstr    aStaticControls_22// "/_static/_controls/ProcessControl/Proce"...
0x95a38  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x95a3d  ldarg.0
0x95a3e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x95a43  ldstr    aStaticCommonSc_24// "/_static/_common/scripts/InlineEditComm"...
0x95a48  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x95a4d  ldarg.0
0x95a4e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x95a53  ldstr    aStaticToolsSys_2// "/_static/tools/systemcustomization/busi"...
0x95a58  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x95a5d  ldarg.0
0x95a5e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x95a63  ldstr    aStaticFormsSel// "/_static/_forms/select.js"
0x95a68  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x95a6d  ldarg.0
0x95a6e  callvirt instance class Microsoft.Crm.Application.Controls.AppHeader Microsoft.Crm.Application.Controls.AppPage::get_CurrentAppHeader()
0x95a73  ldarg.0
0x95a74  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x95a79  ldc.i4.4
0x95a7a  newarr   [mscorlib]System.String
0x95a7f  dup
0x95a80  ldc.i4.0
0x95a81  ldstr    aUtilJs// "util.js"
0x95a86  stelem.ref
0x95a87  dup
0x95a88  ldc.i4.1
0x95a89  ldstr    aTabsJs// "tabs.js"
0x95a8e  stelem.ref
0x95a8f  dup
  ... truncated ...
```
