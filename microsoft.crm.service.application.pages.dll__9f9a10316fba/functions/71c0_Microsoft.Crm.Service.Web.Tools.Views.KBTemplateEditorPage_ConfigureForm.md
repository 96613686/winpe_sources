# Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::ConfigureForm

- ea: `0x71c0`
- end: `0x7433`
- name: `Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::ConfigureForm`
- size: `627`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x71c0`
- `0x7930`

## string_xrefs

- `0x71c0`: `kbarticletemplate`
- `0x73f1`: `Web.CS.articles.lookup_template.aspx_28`
- `0x730c`: `preStructureXml`
- `0x7327`: `preFormatXml`
- `0x7390`: `kbTemplateStyles.xsl`
- `0x73b6`: `kbTemplateEditor.xsl`

## pseudocode

```c

```

## disassembly

```asm
0x71c0  ldstr    aKbarticletempl// "kbarticletemplate"
0x71c5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x71ca  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x71cf  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x71d4  stloc.0
0x71d5  ldarg.0
0x71d6  ldloc.0
0x71d7  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x71dc  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::set_CurrentType(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x71e1  ldarg.0
0x71e2  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x71e7  ldc.i4.0
0x71e8  ldarg.0
0x71e9  ldftn    instance void Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::New(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs e)
0x71ef  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler::.ctor(object, native int)
0x71f4  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::RegisterDataEvent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler)
0x71f9  ldarg.0
0x71fa  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x71ff  ldc.i4.5
0x7200  ldarg.0
0x7201  ldftn    instance void Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::changeState(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs e)
0x7207  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler::.ctor(object, native int)
0x720c  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::RegisterDataEvent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler)
0x7211  ldarg.0
0x7212  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x7217  ldc.i4.6
0x7218  ldarg.0
0x7219  ldftn    instance void Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::changeState(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs e)
0x721f  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler::.ctor(object, native int)
0x7224  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::RegisterDataEvent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler)
0x7229  ldarg.0
0x722a  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x722f  ldc.i4.4
0x7230  ldarg.0
0x7231  ldftn    instance void Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::AfterLoad(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs e)
0x7237  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler::.ctor(object, native int)
0x723c  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::RegisterAfterDataEvent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler)
0x7241  ldarg.0
0x7242  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x7247  ldc.i4.1
0x7248  ldarg.0
0x7249  ldftn    instance void Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::AfterLoad(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs e)
0x724f  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler::.ctor(object, native int)
0x7254  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::RegisterAfterDataEvent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler)
0x7259  ldarg.0
0x725a  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x725f  ldc.i4.5
0x7260  ldarg.0
0x7261  ldftn    instance void Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::AfterLoad(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs e)
0x7267  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler::.ctor(object, native int)
0x726c  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::RegisterAfterDataEvent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler)
0x7271  ldarg.0
0x7272  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x7277  ldc.i4.6
0x7278  ldarg.0
0x7279  ldftn    instance void Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::AfterLoad(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs e)
0x727f  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler::.ctor(object, native int)
0x7284  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::RegisterAfterDataEvent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler)
0x7289  ldarg.0
0x728a  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x728f  ldloc.0
0x7290  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::Execute(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity)
0x7295  ldarg.0
0x7296  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x729b  callvirt instance valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormState [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_State()
0x72a0  ldc.i4.1
0x72a1  beq.s    loc_72B7
0x72a3  ldarg.0
0x72a4  ldloc.0
0x72a5  ldstr    aIsactive// "isactive"
0x72aa  ldc.i4.0
0x72ab  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::GetAttributeValueAsBoolean(string, bool)
0x72b0  stfld    bool Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::_isActive
0x72b5  br.s     loc_72BE
0x72b7  ldarg.0
0x72b8  ldc.i4.1
0x72b9  stfld    bool Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::_isActive
0x72be  ldarg.0
0x72bf  ldfld    bool Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::_isActive
0x72c4  brtrue.s loc_72D2
0x72c6  ldarg.0
0x72c7  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x72cc  ldc.i4.1
0x72cd  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::set_ReadOnly(bool)
0x72d2  ldarg.0
0x72d3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x72d8  ldstr    aBnewform// "_bNewForm"
0x72dd  ldarg.0
0x72de  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x72e3  callvirt instance valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormState [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_State()
0x72e8  ldc.i4.1
0x72e9  ceq
0x72eb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x72f0  ldarg.0
0x72f1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x72f6  ldstr    aBisactive// "_bIsActive"
0x72fb  ldarg.0
0x72fc  ldfld    bool Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::_isActive
0x7301  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x7306  ldarg.0
0x7307  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x730c  ldstr    aPrestructurexm// "preStructureXml"
0x7311  ldarg.0
0x7312  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::_structureXmlDoc
0x7317  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x731c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x7321  ldarg.0
0x7322  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7327  ldstr    aPreformatxml// "preFormatXml"
0x732c  ldarg.0
0x732d  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::_formatXmlDoc
0x7332  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x7337  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x733c  ldarg.0
0x733d  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.HiddenInputControl Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::structurexml
0x7342  ldarg.0
0x7343  ldarg.0
0x7344  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::_structureXmlDoc
0x7349  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x734e  call     instance string Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::SetInputXml(string xml)
0x7353  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object)
0x7358  ldarg.0
0x7359  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.HiddenInputControl Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::formatxml
0x735e  ldarg.0
0x735f  ldarg.0
0x7360  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::_formatXmlDoc
0x7365  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x736a  call     instance string Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::SetInputXml(string xml)
0x736f  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object)
0x7374  ldarg.0
0x7375  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.XmlRenderer Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::xmlRenderer
0x737a  ldarg.0
0x737b  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::_structureXmlDoc
0x7380  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x7385  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.XmlRenderer::set_XmlData(string)
0x738a  ldarg.0
0x738b  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.XmlRenderer Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::xmlRenderer
0x7390  ldstr    aKbtemplatestyl// "kbTemplateStyles.xsl"
0x7395  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.XmlRenderer::set_XslFileId(string)
0x739a  ldarg.0
0x739b  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.XmlRenderer Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::editorRenderer
0x73a0  ldarg.0
0x73a1  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::_structureXmlDoc
0x73a6  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x73ab  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.XmlRenderer::set_XmlData(string)
0x73b0  ldarg.0
0x73b1  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.XmlRenderer Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::editorRenderer
0x73b6  ldstr    aKbtemplateedit// "kbTemplateEditor.xsl"
0x73bb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.XmlRenderer::set_XslFileId(string)
0x73c0  ldarg.0
0x73c1  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.XmlRenderer Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::editorRenderer
0x73c6  callvirt instance class [System.Xml]System.Xml.Xsl.XsltArgumentList [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.XmlRenderer::get_XsltArguments()
0x73cb  ldstr    aIsactive_0// "isActive"
0x73d0  ldstr    asc_15D82// ""
0x73d5  ldarg.0
0x73d6  ldfld    bool Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::_isActive
0x73db  box      [mscorlib]System.Boolean
0x73e0  callvirt instance void [System.Xml]System.Xml.Xsl.XsltArgumentList::AddParam(string, string, object)
0x73e5  ldarg.0
0x73e6  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.PowerAppsNavBar Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::_powerAppsNavBar
0x73eb  ldarg.0
0x73ec  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x73f1  ldstr    aWebCsArticlesL_0// "Web.CS.articles.lookup_template.aspx_28"
0x73f6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x73fb  stfld    string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.PowerAppsNavBar::DesignerName
0x7400  ldarg.0
0x7401  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x7406  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x740b  ldstr    aId// "id"
0x7410  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x7415  brtrue.s loc_7432
0x7417  ldarg.0
0x7418  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.PowerAppsNavBar Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::_powerAppsNavBar
0x741d  ldarg.0
0x741e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7423  ldstr    aFormTitleNew// "Form_Title_New"
0x7428  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x742d  stfld    string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.PowerAppsNavBar::ComponentName
0x7432  ret
```
