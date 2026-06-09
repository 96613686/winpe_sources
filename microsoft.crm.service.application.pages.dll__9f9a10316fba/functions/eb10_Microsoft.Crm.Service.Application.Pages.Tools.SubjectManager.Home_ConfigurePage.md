# Microsoft.Crm.Service.Application.Pages.Tools.SubjectManager.Home::ConfigurePage

- ea: `0xeb10`
- end: `0xed8c`
- name: `Microsoft.Crm.Service.Application.Pages.Tools.SubjectManager.Home::ConfigurePage`
- size: `636`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xeb10`

## string_xrefs

- `0xeb16`: `/_nav/taskbox.css.aspx`
- `0xeb46`: `XML_LANGUAGE_NAME`
- `0xeb65`: `LOCID_SUBJED_CONFIRMDELETE`
- `0xec6a`: `TaskBox_MenuItem_Label_AddSubject`
- `0xecd4`: `TaskBox_MenuItem_Label_EditSubject`
- `0xed3e`: `TaskBox_MenuItem_Label_RemoveSubject`
- `0xed53`: `ToolTip_RemoveSubject`
- `0xed77`: `ToolTip_RemoveSubject`
- `0xed62`: `" src="/_imgs/ico/16_l_remove.gif">`
- `0xed6c`: `DeleteSubject();`

## pseudocode

```c

```

## disassembly

```asm
0xeb10  ldarg.0
0xeb11  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xeb16  ldstr    aNavTaskboxCssA// "/_nav/taskbox.css.aspx"
0xeb1b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xeb20  ldarg.0
0xeb21  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xeb26  ldstr    aControlsNaviga// "/_controls/navigation/map.css.aspx"
0xeb2b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xeb30  ldarg.0
0xeb31  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xeb36  ldstr    aSubjectmanager// "SubjectManager"
0xeb3b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0xeb40  ldarg.0
0xeb41  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xeb46  ldstr    aXmlLanguageNam// "XML_LANGUAGE_NAME"
0xeb4b  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0xeb50  callvirt instance class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_Parent()
0xeb55  callvirt instance string [mscorlib]System.Globalization.CultureInfo::get_TwoLetterISOLanguageName()
0xeb5a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xeb5f  ldarg.0
0xeb60  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xeb65  ldstr    aLocidSubjedCon// "LOCID_SUBJED_CONFIRMDELETE"
0xeb6a  ldarg.0
0xeb6b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xeb70  ldstr    aWebToolsSubjec// "Web.Tools.SubjectEditor.SubjectEditor.a"...
0xeb75  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xeb7a  ldc.i4.0
0xeb7b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xeb80  ldarg.0
0xeb81  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xeb86  ldstr    aLocidSubjedSel// "LOCID_SUBJED_SELECTSUBJ"
0xeb8b  ldarg.0
0xeb8c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xeb91  ldstr    aWebToolsSubjec_0// "Web.Tools.SubjectEditor.SubjectEditor.a"...
0xeb96  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xeb9b  ldc.i4.0
0xeb9c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xeba1  ldarg.0
0xeba2  ldstr    aSubject// "subject"
0xeba7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xebac  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xebb1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::set_CurrentType(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0xebb6  ldc.i4.1
0xebb7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xebbc  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.ServiceDataSource::RetrieveRootSubjects(unsigned int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xebc1  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection::Serialize(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection)
0xebc6  stloc.0
0xebc7  ldarg.0
0xebc8  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppTree Microsoft.Crm.Service.Application.Pages.Tools.SubjectManager.Home::crmTree
0xebcd  ldstr    aTreesubject// "TreeSubject"
0xebd2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Tree::set_ClientId(string)
0xebd7  ldarg.0
0xebd8  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppTree Microsoft.Crm.Service.Application.Pages.Tools.SubjectManager.Home::crmTree
0xebdd  ldstr    aAnswersretrv// "answersRetrv"
0xebe2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Tree::set_ReturnFunction(string)
0xebe7  ldarg.0
0xebe8  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppTree Microsoft.Crm.Service.Application.Pages.Tools.SubjectManager.Home::crmTree
0xebed  ldc.i4.5
0xebee  newarr   [mscorlib]System.String
0xebf3  dup
0xebf4  ldc.i4.0
0xebf5  ldstr    aTree// "<tree>"
0xebfa  stelem.ref
0xebfb  dup
0xebfc  ldc.i4.1
0xebfd  ldloc.0
0xebfe  stelem.ref
0xebff  dup
0xec00  ldc.i4.2
0xec01  ldstr    aRootalttag// "<rootalttag>"
0xec06  stelem.ref
0xec07  dup
0xec08  ldc.i4.3
0xec09  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xec0e  ldstr    aTreeAltExpand// "Tree.Alt.Expand"
0xec13  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xec18  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0xec1d  stelem.ref
0xec1e  dup
0xec1f  ldc.i4.4
0xec20  ldstr    aRootalttagTree// "</rootalttag></tree>"
0xec25  stelem.ref
0xec26  call     string [mscorlib]System.String::Concat(string[])
0xec2b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Tree::set_Data(string)
0xec30  ldarg.0
0xec31  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox Microsoft.Crm.Service.Application.Pages.Tools.SubjectManager.Home::crmTaskBox
0xec36  ldstr    a185px// "185px"
0xec3b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox::set_Width(string)
0xec40  ldarg.0
0xec41  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox Microsoft.Crm.Service.Application.Pages.Tools.SubjectManager.Home::crmTaskBox
0xec46  ldc.i4.s 0x1E
0xec48  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox::set_ColumnWidth(int32)
0xec4d  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_CreateSubject()
0xec52  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xec57  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xec5c  brfalse.s loc_ECB7
0xec5e  ldarg.0
0xec5f  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox Microsoft.Crm.Service.Application.Pages.Tools.SubjectManager.Home::crmTaskBox
0xec64  ldarg.0
0xec65  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xec6a  ldstr    aTaskboxMenuite// "TaskBox_MenuItem_Label_AddSubject"
0xec6f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xec74  ldstr    aImgAlt// "<img alt=\""
0xec79  ldarg.0
0xec7a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xec7f  ldstr    aTooltipAddsubj// "ToolTip_AddSubject"
0xec84  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xec89  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0xec8e  ldstr    aSrcImgsIco18Ad// "\" src=\"/_imgs/ico/18_addView.gif\">"
0xec93  call     string [mscorlib]System.String::Concat(string, string, string)
0xec98  ldstr    aAddsubject// "AddSubject();"
0xec9d  ldarg.0
0xec9e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xeca3  ldstr    aTooltipAddsubj// "ToolTip_AddSubject"
0xeca8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xecad  ldstr    aAddsubj// "_addSubj"
0xecb2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox::AddTopTask(string, string, string, string, string)
0xecb7  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_WriteSubject()
0xecbc  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xecc1  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xecc6  brfalse.s loc_ED21
0xecc8  ldarg.0
0xecc9  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox Microsoft.Crm.Service.Application.Pages.Tools.SubjectManager.Home::crmTaskBox
0xecce  ldarg.0
0xeccf  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xecd4  ldstr    aTaskboxMenuite_0// "TaskBox_MenuItem_Label_EditSubject"
0xecd9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xecde  ldstr    aImgAlt// "<img alt=\""
0xece3  ldarg.0
0xece4  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xece9  ldstr    aTooltipEditsub// "ToolTip_EditSubject"
0xecee  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xecf3  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0xecf8  ldstr    aSrcImgsIco18Ed// "\" src=\"/_imgs/ico/18_editForm.gif\">"
0xecfd  call     string [mscorlib]System.String::Concat(string, string, string)
0xed02  ldstr    aAddsubjectTrue// "AddSubject(true);"
0xed07  ldarg.0
0xed08  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xed0d  ldstr    aTooltipEditsub// "ToolTip_EditSubject"
0xed12  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xed17  ldstr    aEditsubj// "_editSubj"
0xed1c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox::AddTopTask(string, string, string, string, string)
0xed21  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_DeleteSubject()
0xed26  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xed2b  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xed30  brfalse.s loc_ED8B
0xed32  ldarg.0
0xed33  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox Microsoft.Crm.Service.Application.Pages.Tools.SubjectManager.Home::crmTaskBox
0xed38  ldarg.0
0xed39  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xed3e  ldstr    aTaskboxMenuite_1// "TaskBox_MenuItem_Label_RemoveSubject"
0xed43  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xed48  ldstr    aImgAlt// "<img alt=\""
0xed4d  ldarg.0
0xed4e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xed53  ldstr    aTooltipRemoves// "ToolTip_RemoveSubject"
0xed58  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xed5d  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0xed62  ldstr    aSrcImgsIco16LR// "\" src=\"/_imgs/ico/16_l_remove.gif\">"
0xed67  call     string [mscorlib]System.String::Concat(string, string, string)
0xed6c  ldstr    aDeletesubject// "DeleteSubject();"
0xed71  ldarg.0
0xed72  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xed77  ldstr    aTooltipRemoves// "ToolTip_RemoveSubject"
0xed7c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xed81  ldstr    aDelsubj// "_delSubj"
0xed86  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox::AddTopTask(string, string, string, string, string)
0xed8b  ret
```
