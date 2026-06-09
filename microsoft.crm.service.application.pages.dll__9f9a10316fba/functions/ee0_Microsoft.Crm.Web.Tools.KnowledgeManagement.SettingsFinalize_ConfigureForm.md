# Microsoft.Crm.Web.Tools.KnowledgeManagement.SettingsFinalize::ConfigureForm

- ea: `0xee0`
- end: `0x100b`
- name: `Microsoft.Crm.Web.Tools.KnowledgeManagement.SettingsFinalize::ConfigureForm`
- size: `299`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0xa70`
- `0xe10`
- `0xee0`

## pseudocode

```c

```

## disassembly

```asm
0xee0  ldarg.0
0xee1  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentForm()
0xee6  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.WizardForm
0xeeb  dup
0xeec  ldarg.0
0xeed  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xef2  ldstr    aWebToolsKnowle_10// "Web.Tools.KnowledgeManagement.SettingsP"...
0xef7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xefc  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.WizardForm::set_PageTitle(string)
0xf01  dup
0xf02  ldsfld   string [mscorlib]System.String::Empty
0xf07  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.WizardForm::set_PageDescription(string)
0xf0c  ldarg.0
0xf0d  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlTable Microsoft.Crm.Web.Tools.KnowledgeManagement.SettingsFinalize::warningMessageTable
0xf12  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0xf17  ldstr    aDisplay// "display"
0xf1c  ldstr    aNone// "none"
0xf21  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::Add(string, string)
0xf26  ldarg.0
0xf27  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xf2c  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0xf31  ldstr    aWizardpagepost// "wizardPagePostData"
0xf36  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xf3b  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0xf40  dup
0xf41  ldstr    aDataValidatere// "//data/validateresult"
0xf46  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xf4b  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0xf50  stloc.0
0xf51  ldstr    aDataSelecteden// "//data/selectedentitycount"
0xf56  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xf5b  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0xf60  ldc.i4.7
0xf61  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf66  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0xf6b  ldc.i4.0
0xf6c  bgt.s    loc_F89
0xf6e  ldarg.0
0xf6f  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LabelUI Microsoft.Crm.Web.Tools.KnowledgeManagement.SettingsFinalize::validateResultLabel
0xf74  ldarg.0
0xf75  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xf7a  ldstr    aWebToolsKnowle_19// "Web.Tools.KnowledgeManagement.SettingsP"...
0xf7f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf84  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LabelUI::set_Text(string)
0xf89  ldarg.0
0xf8a  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LabelUI Microsoft.Crm.Web.Tools.KnowledgeManagement.SettingsFinalize::validateResultLabel
0xf8f  ldarg.0
0xf90  ldloc.0
0xf91  call     instance string Microsoft.Crm.Web.Tools.KnowledgeManagement.SettingsFinalize::ConfigureValidateResultLabel(string validateResult)
0xf96  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LabelUI::set_Text(string)
0xf9b  ldarg.0
0xf9c  ldloc.0
0xf9d  call     instance void Microsoft.Crm.Web.Tools.KnowledgeManagement.SettingsFinalize::ConfigurePrivacyDisclaimerLabel(string validateResult)
0xfa2  ldarg.0
0xfa3  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xfa8  ldstr    aWizardButtonTe// "Wizard_Button_Text_Finish"
0xfad  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xfb2  stloc.1
0xfb3  dup
0xfb4  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.WizardForm::get_NextButton()
0xfb9  ldloc.1
0xfba  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::DecorateAccessKey(string)
0xfbf  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0xfc4  dup
0xfc5  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.WizardForm::get_NextButton()
0xfca  ldloc.1
0xfcb  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetAccessKey(string)
0xfd0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_AccessKey(string)
0xfd5  dup
0xfd6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.WizardForm::get_NextButton()
0xfdb  ldarg.0
0xfdc  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xfe1  ldstr    aWebToolsKnowle_20// "Web.Tools.KnowledgeManagement.SettingsP"...
0xfe6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xfeb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_Title(string)
0xff0  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.WizardForm::get_BackButton()
0xff5  ldarg.0
0xff6  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xffb  ldstr    aKmWizardButton_0// "KM_Wizard_Button_Tooltip_Back"
0x1000  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1005  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_Title(string)
0x100a  ret
```
