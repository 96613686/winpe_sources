# Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::ConfigureForm

- ea: `0x9b80`
- end: `0x9f07`
- name: `Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::ConfigureForm`
- size: `903`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x9b80`
- `0xa550`
- `0xa6e0`

## string_xrefs

- `0x9b81`: `template`
- `0x9cb6`: `templatetypecode`
- `0x9ccd`: `templateTypeCode`
- `0x9d78`: `template_activity_mime_attachments`
- `0x9eaa`: `EmptyGridMessageBoundSubgridCreate`
- `0x9ec5`: `EmailTemplateEditor.Title`

## pseudocode

```c

```

## disassembly

```asm
0x9b80  ldarg.0
0x9b81  ldstr    aTemplate// "template"
0x9b86  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9b8b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9b90  newobj   instance void [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.Template::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x9b95  stfld    class [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.Template Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::_template
0x9b9a  ldarg.0
0x9b9b  ldarg.0
0x9b9c  ldfld    class [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.Template Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::_template
0x9ba1  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x9ba6  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::set_CurrentType(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x9bab  ldarg.0
0x9bac  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x9bb1  ldc.i4.0
0x9bb2  ldarg.0
0x9bb3  ldftn    instance void Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::OnNew(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs e)
0x9bb9  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler::.ctor(object, native int)
0x9bbe  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::RegisterDataEvent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler)
0x9bc3  ldarg.0
0x9bc4  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x9bc9  ldc.i4.1
0x9bca  ldarg.0
0x9bcb  ldftn    instance void Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::Save(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs e)
0x9bd1  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler::.ctor(object, native int)
0x9bd6  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::RegisterDataEvent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler)
0x9bdb  ldarg.0
0x9bdc  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x9be1  ldc.i4.2
0x9be2  ldarg.0
0x9be3  ldftn    instance void Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::Save(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs e)
0x9be9  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler::.ctor(object, native int)
0x9bee  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::RegisterDataEvent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler)
0x9bf3  ldarg.0
0x9bf4  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x9bf9  ldc.i4.s 0x2D
0x9bfb  ldarg.0
0x9bfc  ldftn    instance void Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::MakeOrgAvailable(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs e)
0x9c02  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler::.ctor(object, native int)
0x9c07  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::RegisterDataEvent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler)
0x9c0c  ldarg.0
0x9c0d  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x9c12  ldc.i4.s 0x2E
0x9c14  ldarg.0
0x9c15  ldftn    instance void Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::MakeOrgUnavailable(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs e)
0x9c1b  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler::.ctor(object, native int)
0x9c20  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::RegisterDataEvent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler)
0x9c25  ldarg.0
0x9c26  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x9c2b  ldc.i4.4
0x9c2c  ldarg.0
0x9c2d  ldftn    instance void Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::AfterLoad(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs e)
0x9c33  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler::.ctor(object, native int)
0x9c38  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::RegisterAfterDataEvent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler)
0x9c3d  ldarg.0
0x9c3e  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x9c43  ldc.i4.1
0x9c44  ldarg.0
0x9c45  ldftn    instance void Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::AfterLoad(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs e)
0x9c4b  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler::.ctor(object, native int)
0x9c50  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::RegisterAfterDataEvent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler)
0x9c55  ldarg.0
0x9c56  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x9c5b  ldc.i4.s 0x2D
0x9c5d  ldarg.0
0x9c5e  ldftn    instance void Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::AfterLoad(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs e)
0x9c64  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler::.ctor(object, native int)
0x9c69  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::RegisterAfterDataEvent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler)
0x9c6e  ldarg.0
0x9c6f  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x9c74  ldc.i4.s 0x2E
0x9c76  ldarg.0
0x9c77  ldftn    instance void Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::AfterLoad(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs e)
0x9c7d  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler::.ctor(object, native int)
0x9c82  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::RegisterAfterDataEvent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler)
0x9c87  ldarg.0
0x9c88  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x9c8d  ldarg.0
0x9c8e  ldfld    class [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.Template Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::_template
0x9c93  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::Execute(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity)
0x9c98  ldarg.0
0x9c99  ldarg.0
0x9c9a  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x9c9f  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x9ca4  ldstr    aId// "id"
0x9ca9  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x9cae  brfalse.s loc_9CC2
0x9cb0  ldarg.0
0x9cb1  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x9cb6  ldstr    aTemplatetypeco_0// "templatetypecode"
0x9cbb  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::GetDataValue(string)
0x9cc0  br.s     loc_9CD7
0x9cc2  ldarg.0
0x9cc3  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x9cc8  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x9ccd  ldstr    aTemplatetypeco_1// "templateTypeCode"
0x9cd2  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x9cd7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9cdc  call     int16 [mscorlib]System.Int16::Parse(string, class [mscorlib]System.IFormatProvider)
0x9ce1  stfld    int32 Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::_templateTypeCode
0x9ce6  ldarg.0
0x9ce7  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TextAreaControl Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::description
0x9cec  ldarg.0
0x9ced  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TextBoxControl Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::title
0x9cf2  ldarg.0
0x9cf3  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x9cf8  callvirt instance bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_ReadOnly()
0x9cfd  brtrue.s loc_9D0C
0x9cff  ldarg.0
0x9d00  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x9d05  callvirt instance bool [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x9d0a  br.s     loc_9D0D
0x9d0c  ldc.i4.1
0x9d0d  dup
0x9d0e  stloc.0
0x9d0f  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::set_ReadOnly(bool)
0x9d14  ldloc.0
0x9d15  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::set_ReadOnly(bool)
0x9d1a  ldarg.0
0x9d1b  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppTabBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmTabBar
0x9d20  ldarg.0
0x9d21  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9d26  ldstr    aTabLabelDetail// "Tab_Label_Details"
0x9d2b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9d30  ldstr    aTab0// "tab0"
0x9d35  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TabBar::AddTab(string, string)
0x9d3a  ldarg.0
0x9d3b  call     instance void Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::BuildTemplateType()
0x9d40  ldarg.0
0x9d41  call     instance void Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::BuildObjectsXml()
0x9d46  ldarg.0
0x9d47  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.HiddenInputControl Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::templatetypecode
0x9d4c  ldarg.0
0x9d4d  ldfld    int32 Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::_templateTypeCode
0x9d52  box      [mscorlib]System.Int32
0x9d57  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object)
0x9d5c  ldarg.0
0x9d5d  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x9d62  callvirt instance valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormState [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_State()
0x9d67  ldc.i4.1
0x9d68  beq      loc_9E3F
0x9d6d  ldarg.0
0x9d6e  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::attachmentGrid
0x9d73  ldstr    aRelname// "relName"
0x9d78  ldstr    aTemplateActivi// "template_activity_mime_attachments"
0x9d7d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::AddParameter(string, string)
0x9d82  ldarg.0
0x9d83  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::attachmentGrid
0x9d88  ldstr    aOtype// "oType"
0x9d8d  ldc.i4   0x7DA
0x9d92  stloc.1
0x9d93  ldloca.s 1
0x9d95  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9d9a  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x9d9f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::AddParameter(string, string)
0x9da4  ldarg.0
0x9da5  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::attachmentGrid
0x9daa  ldstr    aOid// "oId"
0x9daf  ldarg.0
0x9db0  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x9db5  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x9dba  ldstr    aId// "id"
0x9dbf  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x9dc4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::AddParameter(string, string)
0x9dc9  ldarg.0
0x9dca  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::attachmentGrid
0x9dcf  ldc.i4.1
0x9dd0  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid::set_ShowJumpBar(bool)
0x9dd5  ldarg.0
0x9dd6  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::attachmentGrid
0x9ddb  ldc.i4.1
0x9ddc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::set_EnablePaging(bool)
0x9de1  ldarg.0
0x9de2  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::attachmentGrid
0x9de7  ldc.i4.1
0x9de8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::set_EnableColumnSorting(bool)
0x9ded  ldarg.0
0x9dee  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x9df3  callvirt instance bool [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x9df8  brtrue.s loc_9E31
0x9dfa  ldarg.0
0x9dfb  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppGridMenuBar Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::crmMenuBarAttachments
0x9e00  ldc.i4.1
0x9e01  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppGridMenuBar::set_GridType(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.GridTypeCode)
0x9e06  ldarg.0
0x9e07  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppGridMenuBar Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::crmMenuBarAttachments
0x9e0c  ldarg.0
0x9e0d  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::attachmentGrid
0x9e12  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppGridMenuBar::Execute(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid)
0x9e17  ldarg.0
0x9e18  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppGridMenuBar Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::crmMenuBarAttachments
0x9e1d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppMenuBar::get_MenuBar()
0x9e22  ldstr    aMnubar3// "mnuBar3"
0x9e27  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x9e2c  br       loc_9EB9
0x9e31  ldarg.0
0x9e32  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppGridMenuBar Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::crmMenuBarAttachments
0x9e37  ldc.i4.0
0x9e38  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppMenuBar::set_ShowToolBar(bool)
0x9e3d  br.s     loc_9EB9
0x9e3f  ldarg.0
0x9e40  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::attachmentGrid
0x9e45  ldstr    aIsgridhidden// "isGridHidden"
0x9e4a  ldstr    aTrue// "true"
0x9e4f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::AddParameter(string, string)
0x9e54  ldarg.0
0x9e55  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppGridMenuBar Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::crmMenuBarAttachments
0x9e5a  ldc.i4.0
0x9e5b  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppMenuBar::set_ShowToolBar(bool)
0x9e60  ldarg.0
0x9e61  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppGridMenuBar Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::crmMenuBarAttachments
0x9e66  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0x9e6b  ldstr    aDisplay// "display"
0x9e70  ldstr    aNone// "none"
0x9e75  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::Add(string, string)
0x9e7a  ldarg.0
0x9e7b  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::attachmentGrid
0x9e80  ldc.i4.0
0x9e81  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid::set_ShowJumpBar(bool)
0x9e86  ldarg.0
0x9e87  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::attachmentGrid
0x9e8c  ldc.i4.0
0x9e8d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::set_EnablePaging(bool)
0x9e92  ldarg.0
0x9e93  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::attachmentGrid
0x9e98  ldc.i4.0
0x9e99  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::set_EnableColumnSorting(bool)
0x9e9e  ldarg.0
0x9e9f  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::attachmentGrid
0x9ea4  ldarg.0
0x9ea5  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9eaa  ldstr    aEmptygridmessa// "EmptyGridMessageBoundSubgridCreate"
0x9eaf  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9eb4  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid::set_EmptyGridMessage(string)
0x9eb9  ldarg.0
0x9eba  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.PowerAppsNavBar Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::_powerAppsNavBar
0x9ebf  ldarg.0
0x9ec0  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9ec5  ldstr    aEmailtemplatee_0// "EmailTemplateEditor.Title"
0x9eca  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9ecf  stfld    string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.PowerAppsNavBar::DesignerName
0x9ed4  ldarg.0
0x9ed5  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x9eda  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x9edf  ldstr    aId// "id"
0x9ee4  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x9ee9  brtrue.s loc_9F06
0x9eeb  ldarg.0
0x9eec  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.PowerAppsNavBar Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::_powerAppsNavBar
0x9ef1  ldarg.0
0x9ef2  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9ef7  ldstr    aFormTitleNew// "Form_Title_New"
0x9efc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9f01  stfld    string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.PowerAppsNavBar::ComponentName
0x9f06  ret
```
