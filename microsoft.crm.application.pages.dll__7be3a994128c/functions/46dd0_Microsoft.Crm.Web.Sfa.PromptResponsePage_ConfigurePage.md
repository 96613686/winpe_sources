# Microsoft.Crm.Web.Sfa.PromptResponsePage::ConfigurePage

- ea: `0x46dd0`
- end: `0x471bb`
- name: `Microsoft.Crm.Web.Sfa.PromptResponsePage::ConfigurePage`
- size: `1003`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x46dd0`
- `0x471c0`
- `0x47470`
- `0x47630`
- `0x47720`
- `0x47f70`
- `0x48330`
- `0x48340`

## string_xrefs

- `0x46de6`: `/_static/_common/scripts/stage.js`
- `0x46e7b`: `Web.SFA.Workflow.CreateStep.RequiredFail`
- `0x470f1`: `readonlymode`
- `0x46f63`: `Web._controls.listedit.buttons.MoveUp`
- `0x46f7e`: `Web._controls.listedit.buttons.MoveDown`
- `0x46fcf`: `Web._controls.listedit.buttons.Delete`

## pseudocode

```c

```

## disassembly

```asm
0x46dd0  ldarg.0
0x46dd1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x46dd6  ldstr    aControlsRelate// "/_controls/relatedinformation/relatedin"...
0x46ddb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x46de0  ldarg.0
0x46de1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x46de6  ldstr    aStaticCommonSc_4// "/_static/_common/scripts/stage.js"
0x46deb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x46df0  ldarg.0
0x46df1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x46df6  ldstr    aStaticSfaWorkf// "/_static/SFA/workflow/workflowstep.js"
0x46dfb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x46e00  ldarg.0
0x46e01  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x46e06  ldstr    aFormsControlsF// "/_forms/controls/form.css.aspx"
0x46e0b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x46e10  ldarg.0
0x46e11  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x46e16  ldstr    aSfaWorkflowPro// "/SFA/workflow/promptresponse.css.aspx"
0x46e1b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x46e20  ldarg.0
0x46e21  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x46e26  ldstr    aEntityid_3// "ENTITYID"
0x46e2b  ldarg.0
0x46e2c  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x46e31  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x46e36  ldstr    aEntityid_2// "EntityId"
0x46e3b  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x46e40  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x46e45  ldarg.0
0x46e46  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x46e4b  ldstr    aStepid_2// "STEPID"
0x46e50  ldarg.0
0x46e51  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x46e56  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x46e5b  ldstr    aStepid// "StepId"
0x46e60  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x46e65  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x46e6a  ldarg.0
0x46e6b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x46e70  ldstr    aLocidRequiredF// "LOCID_REQUIRED_FIELD"
0x46e75  ldarg.0
0x46e76  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x46e7b  ldstr    aWebSfaWorkflow_2// "Web.SFA.Workflow.CreateStep.RequiredFai"...
0x46e80  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x46e85  ldc.i4.0
0x46e86  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x46e8b  ldarg.0
0x46e8c  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.MultipleValueFormatAppPicklistEdit Microsoft.Crm.Web.Sfa.PromptResponsePage::responsePicklistValues
0x46e91  ldc.i4.s 0x17
0x46e93  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.MultipleValueFormatAppPicklistEdit::AddFunction(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.OptionSetFunction)
0x46e98  ldarg.0
0x46e99  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.EntityAttributeSelectionControl Microsoft.Crm.Web.Sfa.PromptResponsePage::prEntityAttribute
0x46e9e  ldc.i4.0
0x46e9f  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.EntityAttributeSelectionControl::set_VerticalLayout(bool)
0x46ea4  ldarg.0
0x46ea5  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.EntityAttributeSelectionControl Microsoft.Crm.Web.Sfa.PromptResponsePage::prEntityAttribute
0x46eaa  ldarg.0
0x46eab  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.EntityAttributeSelectionControl Microsoft.Crm.Web.Sfa.PromptResponsePage::prEntityAttribute
0x46eb0  ldarg.0
0x46eb1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x46eb6  ldstr    aWebSfaInteract// "Web.SFA.InteractiveWorkflow.EntityAttri"...
0x46ebb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x46ec0  dup
0x46ec1  stloc.s  4
0x46ec3  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.EntityAttributeSelectionControl::set_EntityLabelAltText(string)
0x46ec8  ldloc.s  4
0x46eca  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.EntityAttributeSelectionControl::set_EntityLabel(string)
0x46ecf  ldarg.0
0x46ed0  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.EntityAttributeSelectionControl Microsoft.Crm.Web.Sfa.PromptResponsePage::prEntityAttribute
0x46ed5  ldarg.0
0x46ed6  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.EntityAttributeSelectionControl Microsoft.Crm.Web.Sfa.PromptResponsePage::prEntityAttribute
0x46edb  ldarg.0
0x46edc  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x46ee1  ldstr    aWebSfaInteract_0// "Web.SFA.InteractiveWorkflow.EntityAttri"...
0x46ee6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x46eeb  dup
0x46eec  stloc.s  4
0x46eee  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.EntityAttributeSelectionControl::set_AttributeLabelAltText(string)
0x46ef3  ldloc.s  4
0x46ef5  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.EntityAttributeSelectionControl::set_AttributeLabel(string)
0x46efa  ldarg.0
0x46efb  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.EntityAttributeSelectionControl Microsoft.Crm.Web.Sfa.PromptResponsePage::prEntityAttribute
0x46f00  ldc.i4.1
0x46f01  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.EntityAttributeSelectionControl::set_StarRequired(bool)
0x46f06  ldarg.0
0x46f07  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.EntityAttributeSelectionControl Microsoft.Crm.Web.Sfa.PromptResponsePage::prEntityAttribute
0x46f0c  ldarg.0
0x46f0d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x46f12  ldstr    aFormsRequiredA// "Forms.Required.AltTag"
0x46f17  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x46f1c  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.EntityAttributeSelectionControl::set_RequiredAltText(string)
0x46f21  ldarg.0
0x46f22  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.MultipleValueFormatAppPicklistEdit Microsoft.Crm.Web.Sfa.PromptResponsePage::responsePicklistValues
0x46f27  ldarg.0
0x46f28  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x46f2d  ldstr    aWebSfaInteract_2// "Web.SFA.InteractiveWorkflow.ResponseOpt"...
0x46f32  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x46f37  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.MultipleValueFormatAppPicklistEdit::set_ItemLabelLabel(string)
0x46f3c  ldarg.0
0x46f3d  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.MultipleValueFormatAppPicklistEdit Microsoft.Crm.Web.Sfa.PromptResponsePage::responsePicklistValues
0x46f42  ldarg.0
0x46f43  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x46f48  ldstr    aWebSfaInteract_3// "Web.SFA.InteractiveWorkflow.ResponseOpt"...
0x46f4d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x46f52  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.MultipleValueFormatAppPicklistEdit::set_ItemValueLabel(string)
0x46f57  ldarg.0
0x46f58  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.MultipleValueFormatAppPicklistEdit Microsoft.Crm.Web.Sfa.PromptResponsePage::responsePicklistValues
0x46f5d  ldarg.0
0x46f5e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x46f63  ldstr    aWebControlsLis// "Web._controls.listedit.buttons.MoveUp"
0x46f68  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x46f6d  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.MultipleValueFormatAppPicklistEdit::set_MoveUpLabel(string)
0x46f72  ldarg.0
0x46f73  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.MultipleValueFormatAppPicklistEdit Microsoft.Crm.Web.Sfa.PromptResponsePage::responsePicklistValues
0x46f78  ldarg.0
0x46f79  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x46f7e  ldstr    aWebControlsLis_0// "Web._controls.listedit.buttons.MoveDown"
0x46f83  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x46f88  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.MultipleValueFormatAppPicklistEdit::set_MoveDownLabel(string)
0x46f8d  ldarg.0
0x46f8e  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.MultipleValueFormatAppPicklistEdit Microsoft.Crm.Web.Sfa.PromptResponsePage::responsePicklistValues
0x46f93  ldarg.0
0x46f94  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x46f99  ldstr    aWebControlsLis_1// "Web._controls.listedit.buttons.Edit"
0x46f9e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x46fa3  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.MultipleValueFormatAppPicklistEdit::set_EditLabel(string)
0x46fa8  ldarg.0
0x46fa9  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.MultipleValueFormatAppPicklistEdit Microsoft.Crm.Web.Sfa.PromptResponsePage::responsePicklistValues
0x46fae  ldarg.0
0x46faf  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x46fb4  ldstr    aWebControlsLis_2// "Web._controls.listedit.buttons.Add"
0x46fb9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x46fbe  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.MultipleValueFormatAppPicklistEdit::set_AddLabel(string)
0x46fc3  ldarg.0
0x46fc4  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.MultipleValueFormatAppPicklistEdit Microsoft.Crm.Web.Sfa.PromptResponsePage::responsePicklistValues
0x46fc9  ldarg.0
0x46fca  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x46fcf  ldstr    aWebControlsLis_3// "Web._controls.listedit.buttons.Delete"
0x46fd4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x46fd9  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.MultipleValueFormatAppPicklistEdit::set_RemoveLabel(string)
0x46fde  ldarg.0
0x46fdf  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.MultipleValueFormatAppPicklistEdit Microsoft.Crm.Web.Sfa.PromptResponsePage::responsePicklistValues
0x46fe4  ldarg.0
0x46fe5  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x46fea  ldstr    aWebControlsLis_4// "Web._controls.listedit.buttons.SortAsc"
0x46fef  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x46ff4  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.MultipleValueFormatAppPicklistEdit::set_SortAscendingLabel(string)
0x46ff9  ldarg.0
0x46ffa  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.MultipleValueFormatAppPicklistEdit Microsoft.Crm.Web.Sfa.PromptResponsePage::responsePicklistValues
0x46fff  ldarg.0
0x47000  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x47005  ldstr    aWebControlsLis_5// "Web._controls.listedit.buttons.SortDesc"
0x4700a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4700f  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.MultipleValueFormatAppPicklistEdit::set_SortDescendingLabel(string)
0x47014  ldarg.0
0x47015  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.MultipleValueFormatAppPicklistEdit Microsoft.Crm.Web.Sfa.PromptResponsePage::responsePicklistValues
0x4701a  ldarg.0
0x4701b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x47020  ldstr    aWebControlsLis_6// "Web._controls.listedit.labels.DefaultVa"...
0x47025  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4702a  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.MultipleValueFormatAppPicklistEdit::set_DefaultValueLabel(string)
0x4702f  ldarg.0
0x47030  call     instance void Microsoft.Crm.Web.Sfa.PromptResponsePage::SetupResponseTypeList()
0x47035  ldarg.0
0x47036  call     instance void Microsoft.Crm.Web.Sfa.PromptResponsePage::SetupDataTypeList()
0x4703b  ldarg.0
0x4703c  call     instance void Microsoft.Crm.Web.Sfa.PromptResponsePage::SetMaximumLengths()
0x47041  ldarg.0
0x47042  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUI Microsoft.Crm.Web.Sfa.PromptResponsePage::responseTextDefault3
0x47047  ldstr    aDatetime// "datetime"
0x4704c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUIBase::set_DisplayFormat(string)
0x47051  ldarg.0
0x47052  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUI Microsoft.Crm.Web.Sfa.PromptResponsePage::responseTextDefault3
0x47057  ldc.i4.1
0x47058  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUIBase::set_ShowTime(bool)
0x4705d  ldarg.0
0x4705e  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Number Microsoft.Crm.Web.Sfa.PromptResponsePage::responseTextDefault0
0x47063  ldstr    aStyle_0// "style"
0x47068  ldstr    aDisplayInlineI// "display: inline; ime-mode:disabled;"
0x4706d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string, string)
0x47072  ldarg.0
0x47073  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Number Microsoft.Crm.Web.Sfa.PromptResponsePage::responseTextDefault1
0x47078  ldstr    aStyle_0// "style"
0x4707d  ldstr    aDisplayNoneIme// "display: none; ime-mode:disabled;"
0x47082  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string, string)
0x47087  ldarg.0
0x47088  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.TextBox Microsoft.Crm.Web.Sfa.PromptResponsePage::responseTextDefault2
0x4708d  ldstr    aStyle_0// "style"
0x47092  ldstr    aDisplayNone// "display: none"
0x47097  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string, string)
0x4709c  ldarg.0
0x4709d  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUI Microsoft.Crm.Web.Sfa.PromptResponsePage::responseTextDefault4
0x470a2  ldstr    aStyle_0// "style"
0x470a7  ldstr    aDisplayNone// "display: none"
0x470ac  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string, string)
0x470b1  ldarg.0
0x470b2  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUI Microsoft.Crm.Web.Sfa.PromptResponsePage::responseTextDefault3
0x470b7  ldstr    aStyle_0// "style"
0x470bc  ldstr    aDisplayNone// "display: none"
0x470c1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string, string)
0x470c6  ldarg.0
0x470c7  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.EntityAttributeSelectionControl Microsoft.Crm.Web.Sfa.PromptResponsePage::prEntityAttribute
0x470cc  ldstr    aStyle_0// "style"
0x470d1  ldstr    aDisplayNone// "display: none"
0x470d6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string, string)
0x470db  ldc.i4.1
0x470dc  stsfld   bool Microsoft.Crm.Web.Sfa.PromptResponsePage::isReadOnlyMode
0x470e1  ldarg.0
0x470e2  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x470e7  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x470ec  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x470f1  ldstr    aReadonlymode// "readonlymode"
0x470f6  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x470fb  stloc.0
0x470fc  ldloc.0
0x470fd  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x47102  brtrue.s loc_47118
0x47104  ldloc.0
0x47105  ldstr    aFalse// "false"
0x4710a  ldc.i4.5
0x4710b  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x47110  brtrue.s loc_47118
0x47112  ldc.i4.0
0x47113  stsfld   bool Microsoft.Crm.Web.Sfa.PromptResponsePage::isReadOnlyMode
0x47118  ldloca.s 1
0x4711a  ldarg.0
0x4711b  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x47120  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x47125  ldstr    aEntityid_2// "EntityId"
0x4712a  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x4712f  call     instance void [mscorlib]System.Guid::.ctor(string)
0x47134  ldarg.0
0x47135  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x4713a  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x4713f  ldstr    aStepid// "StepId"
0x47144  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x47149  stloc.2
0x4714a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x4714f  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x47154  stloc.3
0x47155  ldarg.0
0x47156  ldloc.3
0x47157  ldloc.1
0x47158  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x4715d  stfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Web.Sfa.PromptResponsePage::_workflowStep
0x47162  ldarg.0
0x47163  ldarg.0
0x47164  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Web.Sfa.PromptResponsePage::_workflowStep
0x47169  ldloc.2
0x4716a  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x4716f  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep
0x47174  stfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep Microsoft.Crm.Web.Sfa.PromptResponsePage::_currentStep
0x47179  ldarg.0
0x4717a  ldarg.0
0x4717b  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Web.Sfa.PromptResponsePage::_workflowStep
0x47180  ldarg.0
0x47181  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep Microsoft.Crm.Web.Sfa.PromptResponsePage::_currentStep
0x47186  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.DataSourceCollection [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetDataSourceForStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x4718b  stfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.DataSourceCollection Microsoft.Crm.Web.Sfa.PromptResponsePage::_dataSourcesForCurrentStep
0x47190  ldarg.0
0x47191  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x47196  ldarg.0
0x47197  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x4719c  call     void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Categories.WorkflowRelatedCategory::SetStringResources(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager)
0x471a1  ldarg.0
0x471a2  ldarg.0
0x471a3  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Web.Sfa.PromptResponsePage::get_Workflow()
0x471a8  ldarg.0
0x471a9  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep Microsoft.Crm.Web.Sfa.PromptResponsePage::get_CurrentStep()
0x471ae  call     instance bool Microsoft.Crm.Web.Sfa.PromptResponsePage::PopulateQuerySelectorRecursive(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase current, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase referenceStep)
0x471b3  pop
0x471b4  ldarg.0
0x471b5  call     instance void Microsoft.Crm.Web.Sfa.PromptResponsePage::PrepopulateInteractionForm()
0x471ba  ret
```
