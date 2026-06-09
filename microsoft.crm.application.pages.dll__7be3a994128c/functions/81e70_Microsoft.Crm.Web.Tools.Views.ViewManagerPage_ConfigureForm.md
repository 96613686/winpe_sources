# Microsoft.Crm.Web.Tools.Views.ViewManagerPage::ConfigureForm

- ea: `0x81e70`
- end: `0x8266a`
- name: `Microsoft.Crm.Web.Tools.Views.ViewManagerPage::ConfigureForm`
- size: `2042`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x81e70`

## string_xrefs

- `0x81e87`: `FetchXml`
- `0x82353`: `<u><a id='RelevanceSearchClickHere' target='_blank' href='/Tools/SystemSettings/Dialogs/RelevanceSearchConfiguration.aspx' onclick='onLinkClicked("`
- `0x8244f`: `<u><a id='RelevanceSearchLearnMore' target='_blank' href='http://go.microsoft.com/fwlink/p/?LinkID=624377'>`
- `0x82514`: `cancreateviews`

## pseudocode

```c

```

## disassembly

```asm
0x81e70  ldarg.0
0x81e71  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x81e76  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.HardCodedForm
0x81e7b  ldarg.0
0x81e7c  ldarg.0
0x81e7d  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x81e82  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x81e87  ldstr    aFetchxml_1// "FetchXml"
0x81e8c  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x81e91  stfld    string Microsoft.Crm.Web.Tools.Views.ViewManagerPage::_fetchXml
0x81e96  ldarg.0
0x81e97  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x81e9c  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x81ea1  ldstr    aViewtype_1// "viewType"
0x81ea6  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x81eab  stloc.0
0x81eac  ldloc.0
0x81ead  brfalse.s loc_81ECB
0x81eaf  ldloc.0
0x81eb0  callvirt instance int32 [mscorlib]System.String::get_Length()
0x81eb5  ldc.i4.0
0x81eb6  ble.s    loc_81ECB
0x81eb8  ldarg.0
0x81eb9  ldloc.0
0x81eba  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x81ebf  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x81ec4  stfld    valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ViewType Microsoft.Crm.Web.Tools.Views.ViewManagerPage::_viewType
0x81ec9  br.s     loc_81ED6
0x81ecb  ldarg.0
0x81ecc  ldc.i4   0x40F
0x81ed1  stfld    valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ViewType Microsoft.Crm.Web.Tools.Views.ViewManagerPage::_viewType
0x81ed6  ldarg.0
0x81ed7  ldarg.0
0x81ed8  ldfld    valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ViewType Microsoft.Crm.Web.Tools.Views.ViewManagerPage::_viewType
0x81edd  ldc.i4   0x40F
0x81ee2  ceq
0x81ee4  stfld    bool Microsoft.Crm.Web.Tools.Views.ViewManagerPage::_isSystemView
0x81ee9  ldarg.0
0x81eea  ldfld    valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ViewType Microsoft.Crm.Web.Tools.Views.ViewManagerPage::_viewType
0x81eef  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x81ef4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x81ef9  stloc.1
0x81efa  ldarg.0
0x81efb  ldloc.1
0x81efc  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x81f01  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::set_CurrentType(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x81f06  ldarg.0
0x81f07  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x81f0c  ldc.i4.0
0x81f0d  ldarg.0
0x81f0e  ldftn    instance void Microsoft.Crm.Web.Tools.Views.ViewManagerPage::New(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs e)
0x81f14  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler::.ctor(object, native int)
0x81f19  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::RegisterDataEvent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler)
0x81f1e  ldarg.0
0x81f1f  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x81f24  ldc.i4.4
0x81f25  ldarg.0
0x81f26  ldftn    instance void Microsoft.Crm.Web.Tools.Views.ViewManagerPage::Setup(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs e)
0x81f2c  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler::.ctor(object, native int)
0x81f31  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::RegisterDataEvent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler)
0x81f36  ldarg.0
0x81f37  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x81f3c  ldc.i4.1
0x81f3d  ldarg.0
0x81f3e  ldftn    instance void Microsoft.Crm.Web.Tools.Views.ViewManagerPage::Save(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs e)
0x81f44  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler::.ctor(object, native int)
0x81f49  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::RegisterDataEvent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler)
0x81f4e  ldarg.0
0x81f4f  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x81f54  ldc.i4.2
0x81f55  ldarg.0
0x81f56  ldftn    instance void Microsoft.Crm.Web.Tools.Views.ViewManagerPage::Save(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs e)
0x81f5c  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler::.ctor(object, native int)
0x81f61  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::RegisterDataEvent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler)
0x81f66  dup
0x81f67  ldc.i4.0
0x81f68  ldarg.0
0x81f69  ldftn    instance void Microsoft.Crm.Web.Tools.Views.ViewManagerPage::AddSubmitFields(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs e)
0x81f6f  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler::.ctor(object, native int)
0x81f74  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.HardCodedForm::RegisterRenderSubmitFieldsDataEvent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler)
0x81f79  dup
0x81f7a  ldc.i4.1
0x81f7b  ldarg.0
0x81f7c  ldftn    instance void Microsoft.Crm.Web.Tools.Views.ViewManagerPage::AddSubmitFields(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs e)
0x81f82  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler::.ctor(object, native int)
0x81f87  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.HardCodedForm::RegisterRenderSubmitFieldsDataEvent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler)
0x81f8c  dup
0x81f8d  ldc.i4.2
0x81f8e  ldarg.0
0x81f8f  ldftn    instance void Microsoft.Crm.Web.Tools.Views.ViewManagerPage::AddSubmitFields(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs e)
0x81f95  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler::.ctor(object, native int)
0x81f9a  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.HardCodedForm::RegisterRenderSubmitFieldsDataEvent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler)
0x81f9f  ldc.i4.4
0x81fa0  ldarg.0
0x81fa1  ldftn    instance void Microsoft.Crm.Web.Tools.Views.ViewManagerPage::AddSubmitFields(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs e)
0x81fa7  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler::.ctor(object, native int)
0x81fac  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.HardCodedForm::RegisterRenderSubmitFieldsDataEvent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler)
0x81fb1  ldarg.0
0x81fb2  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x81fb7  ldc.i4.4
0x81fb8  ldarg.0
0x81fb9  ldftn    instance void Microsoft.Crm.Web.Tools.Views.ViewManagerPage::AfterLoad(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs e)
0x81fbf  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler::.ctor(object, native int)
0x81fc4  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::RegisterAfterDataEvent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler)
0x81fc9  ldarg.0
0x81fca  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x81fcf  ldc.i4.1
0x81fd0  ldarg.0
0x81fd1  ldftn    instance void Microsoft.Crm.Web.Tools.Views.ViewManagerPage::AfterLoad(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs e)
0x81fd7  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler::.ctor(object, native int)
0x81fdc  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::RegisterAfterDataEvent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler)
0x81fe1  ldarg.0
0x81fe2  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x81fe7  ldc.i4.2
0x81fe8  ldarg.0
0x81fe9  ldftn    instance void Microsoft.Crm.Web.Tools.Views.ViewManagerPage::AfterLoad(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs e)
0x81fef  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler::.ctor(object, native int)
0x81ff4  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::RegisterAfterDataEvent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler)
0x81ff9  ldarg.0
0x81ffa  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x81fff  ldloc.1
0x82000  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::Execute(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity)
0x82005  ldarg.0
0x82006  ldarg.0
0x82007  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x8200c  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_Entity()
0x82011  ldstr    aQueryapi// "queryapi"
0x82016  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x8201b  isinst   [mscorlib]System.String
0x82020  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x82025  ldc.i4.0
0x82026  ceq
0x82028  stfld    bool Microsoft.Crm.Web.Tools.Views.ViewManagerPage::_isQueryApiView
0x8202d  ldarg.0
0x8202e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x82033  ldstr    aBqueryapibased// "bQueryAPIBasedView"
0x82038  ldarg.0
0x82039  ldfld    bool Microsoft.Crm.Web.Tools.Views.ViewManagerPage::_isQueryApiView
0x8203e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x82043  ldarg.0
0x82044  ldfld    bool Microsoft.Crm.Web.Tools.Views.ViewManagerPage::_isSystemView
0x82049  brfalse.s loc_82067
0x8204b  ldarg.0
0x8204c  ldarg.0
0x8204d  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x82052  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_Entity()
0x82057  ldstr    aQuerytype_0// "querytype"
0x8205c  ldc.i4.0
0x8205d  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::GetAttributeValueAsNumber(string, int32)
0x82062  stfld    int32 Microsoft.Crm.Web.Tools.Views.ViewManagerPage::_queryType
0x82067  ldarg.0
0x82068  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x8206d  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x82072  ldstr    aQuickfind_0// "quickfind"
0x82077  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x8207c  stloc.2
0x8207d  ldarg.0
0x8207e  ldarg.0
0x8207f  ldfld    int32 Microsoft.Crm.Web.Tools.Views.ViewManagerPage::_queryType
0x82084  ldc.i4.4
0x82085  beq.s    loc_8209A
0x82087  ldloc.2
0x82088  brfalse.s loc_82097
0x8208a  ldloc.2
0x8208b  ldstr    a1// "1"
0x82090  call     bool [mscorlib]System.String::op_Equality(string, string)
0x82095  br.s     loc_8209B
0x82097  ldc.i4.0
0x82098  br.s     loc_8209B
0x8209a  ldc.i4.1
0x8209b  stfld    bool Microsoft.Crm.Web.Tools.Views.ViewManagerPage::_isQuickFindView
0x820a0  ldarg.0
0x820a1  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x820a6  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x820ab  ldstr    aDefault// "default"
0x820b0  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x820b5  ldstr    a1// "1"
0x820ba  call     bool [mscorlib]System.String::op_Equality(string, string)
0x820bf  brfalse.s loc_820C8
0x820c1  ldarg.0
0x820c2  ldc.i4.1
0x820c3  stfld    bool Microsoft.Crm.Web.Tools.Views.ViewManagerPage::_isDefaultView
0x820c8  ldarg.0
0x820c9  ldfld    int32 Microsoft.Crm.Web.Tools.Views.ViewManagerPage::_queryType
0x820ce  stloc.s  7
0x820d0  ldloc.s  7
0x820d2  switch   loc_820FA, loc_820F1, loc_820F1, loc_8211B, loc_820F1
0x820eb  ldloc.s  7
0x820ed  ldc.i4.s 0x40
0x820ef  bne.un.s loc_8211B
0x820f1  ldarg.0
0x820f2  ldc.i4.0
0x820f3  stfld    bool Microsoft.Crm.Web.Tools.Views.ViewManagerPage::_isSharableView
0x820f8  br.s     loc_82122
0x820fa  ldarg.0
0x820fb  ldarg.0
0x820fc  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x82101  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_Entity()
0x82106  ldstr    aIsdefault// "isdefault"
0x8210b  ldc.i4.0
0x8210c  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::GetAttributeValueAsBoolean(string, bool)
0x82111  ldc.i4.0
0x82112  ceq
0x82114  stfld    bool Microsoft.Crm.Web.Tools.Views.ViewManagerPage::_isSharableView
0x82119  br.s     loc_82122
0x8211b  ldarg.0
0x8211c  ldc.i4.1
0x8211d  stfld    bool Microsoft.Crm.Web.Tools.Views.ViewManagerPage::_isSharableView
0x82122  ldarg.0
0x82123  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x82128  callvirt instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_EventId()
0x8212d  brfalse.s loc_82137
0x8212f  ldarg.0
0x82130  ldfld    bool Microsoft.Crm.Web.Tools.Views.ViewManagerPage::_isSystemView
0x82135  brtrue.s loc_82140
0x82137  ldarg.0
0x82138  ldc.i4.1
0x82139  stfld    bool Microsoft.Crm.Web.Tools.Views.ViewManagerPage::_isCustomizable
0x8213e  br.s     loc_82156
0x82140  ldarg.0
0x82141  ldarg.0
0x82142  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x82147  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_CurrentEntity()
0x8214c  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_IsInstanceCustomizable()
0x82151  stfld    bool Microsoft.Crm.Web.Tools.Views.ViewManagerPage::_isCustomizable
0x82156  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8215b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x82160  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x82165  stloc.3
0x82166  ldarg.0
0x82167  ldfld    bool Microsoft.Crm.Web.Tools.Views.ViewManagerPage::_isCustomizable
0x8216c  brtrue   loc_82313
0x82171  ldstr    aB_0// "<b>"
0x82176  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string)
0x8217b  stloc.s  4
0x8217d  ldloc.s  4
0x8217f  ldarg.0
0x82180  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x82185  ldstr    aWebToolsViewed_19// "Web.Tools.ViewEditor.viewmanager.aspx_1"...
0x8218a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8218f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x82194  pop
0x82195  ldloc.s  4
0x82197  ldstr    aB_3// "</b> "
0x8219c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x821a1  pop
0x821a2  ldarg.0
0x821a3  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x821a8  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_Entity()
0x821ad  ldstr    aReturnedtypeco// "returnedtypecode"
0x821b2  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x821b7  castclass [mscorlib]System.String
0x821bc  stloc.s  8
0x821be  ldloc.3
0x821bf  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x821c4  ldloc.s  8
0x821c6  ldc.i4.1
0x821c7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x821cc  stloc.s  9
0x821ce  ldarg.0
0x821cf  ldfld    int32 Microsoft.Crm.Web.Tools.Views.ViewManagerPage::_queryType
0x821d4  stloc.s  7
0x821d6  ldloc.s  7
0x821d8  ldc.i4.1
0x821d9  sub
0x821da  switch   loc_821F4, loc_82247, loc_822E7, loc_82297
0x821ef  br       loc_822E7
0x821f4  ldarg.0
0x821f5  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x821fa  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x821ff  ldarg.0
0x82200  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x82205  ldstr    aVieweditorTitl// "ViewEditor_Title_AdvancedFind"
0x8220a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8220f  ldc.i4.1
0x82210  newarr   [mscorlib]System.Object
0x82215  dup
0x82216  ldc.i4.0
0x82217  ldloc.s  9
0x82219  ldc.i4.2
0x8221a  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x8221f  stelem.ref
0x82220  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x82225  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_Title(string)
0x8222a  ldloc.s  4
0x8222c  ldarg.0
0x8222d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x82232  ldstr    aWebToolsViewed_20// "Web.Tools.ViewEditor.viewmanager.aspx_1"...
0x82237  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8223c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x82241  pop
0x82242  br       loc_822FF
0x82247  ldarg.0
0x82248  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8224d  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x82252  ldarg.0
0x82253  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x82258  ldstr    aVieweditorTitl_0// "ViewEditor_Title_Associated"
0x8225d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x82262  ldc.i4.1
  ... truncated ...
```
