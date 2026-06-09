# Microsoft.Crm.Common.Application.Pages.Dialogs.ListBasicActivityPage::ConfigureForm

- ea: `0x18ec0`
- end: `0x1931a`
- name: `Microsoft.Crm.Common.Application.Pages.Dialogs.ListBasicActivityPage::ConfigureForm`
- size: `1114`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18dc0`
- `0x18dd0`
- `0x18ec0`
- `0x19320`
- `0x19350`
- `0x193f0`
- `0x19450`
- `0x19490`

## string_xrefs

- `0x19042`: `templateId`
- `0x1905b`: `templateId`
- `0x1911b`: `Activities can be created only for List or CampaignActivity entity not for {0}`
- `0x1919e`: `Button_Label_ListActivityCreate`
- `0x191db`: `Button_Label_ListActivityCreate`

## pseudocode

```c

```

## disassembly

```asm
0x18ec0  ldarg.0
0x18ec1  call     instance string Microsoft.Crm.Common.Application.Pages.Dialogs.ListBasicActivityPage::GetResourceId()
0x18ec6  stloc.0
0x18ec7  ldarg.0
0x18ec8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x18ecd  ldarg.0
0x18ece  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x18ed3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18ed8  ldstr    aDialogList0Tit// "Dialog_List{0}_Title"
0x18edd  ldc.i4.1
0x18ede  newarr   [mscorlib]System.Object
0x18ee3  dup
0x18ee4  ldc.i4.0
0x18ee5  ldloc.0
0x18ee6  stelem.ref
0x18ee7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x18eec  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x18ef1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_Title(string)
0x18ef6  ldarg.0
0x18ef7  ldarg.0
0x18ef8  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x18efd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18f02  ldstr    aDialogList0Hea// "Dialog_List{0}_Header"
0x18f07  ldc.i4.1
0x18f08  newarr   [mscorlib]System.Object
0x18f0d  dup
0x18f0e  ldc.i4.0
0x18f0f  ldloc.0
0x18f10  stelem.ref
0x18f11  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x18f16  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x18f1b  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogTitle(string)
0x18f20  ldarg.0
0x18f21  ldarg.0
0x18f22  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x18f27  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18f2c  ldstr    aDialogList0Des// "Dialog_List{0}_Description"
0x18f31  ldc.i4.1
0x18f32  newarr   [mscorlib]System.Object
0x18f37  dup
0x18f38  ldc.i4.0
0x18f39  ldloc.0
0x18f3a  stelem.ref
0x18f3b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x18f40  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x18f45  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogDescription(string)
0x18f4a  ldarg.0
0x18f4b  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x18f50  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpRequest::get_InputStream()
0x18f55  newobj   instance void [mscorlib]System.IO.StreamReader::.ctor(class [mscorlib]System.IO.Stream)
0x18f5a  callvirt instance string [mscorlib]System.IO.TextReader::ReadToEnd()
0x18f5f  stloc.1
0x18f60  ldloc.1
0x18f61  callvirt instance int32 [mscorlib]System.String::get_Length()
0x18f66  ldc.i4.0
0x18f67  ble      loc_1914A
0x18f6c  ldarg.0
0x18f6d  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x18f72  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x18f77  ldstr    aIobjtype// "iObjType"
0x18f7c  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x18f81  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18f86  call     int16 [mscorlib]System.Int16::Parse(string, class [mscorlib]System.IFormatProvider)
0x18f8b  stloc.2
0x18f8c  ldarg.0
0x18f8d  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x18f92  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x18f97  ldstr    aIid// "iId"
0x18f9c  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x18fa1  stloc.3
0x18fa2  ldarg.0
0x18fa3  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x18fa8  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x18fad  ldstr    aOwneroption// "OwnerOption"
0x18fb2  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x18fb7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18fbc  call     int16 [mscorlib]System.Int16::Parse(string, class [mscorlib]System.IFormatProvider)
0x18fc1  call     valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropagationOwnershipOptions Microsoft.Crm.Common.Application.Pages.Dialogs.ListBasicActivityPage::ConvertToOwnershipOptions(int32 ownerOptionValue)
0x18fc6  stloc.s  4
0x18fc8  ldarg.0
0x18fc9  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x18fce  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x18fd3  ldstr    aOwnerid_1// "OwnerId"
0x18fd8  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x18fdd  stloc.s  5
0x18fdf  ldarg.0
0x18fe0  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x18fe5  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x18fea  ldstr    aOwnertype// "OwnerType"
0x18fef  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x18ff4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18ff9  call     int16 [mscorlib]System.Int16::Parse(string, class [mscorlib]System.IFormatProvider)
0x18ffe  stloc.s  6
0x19000  ldarg.0
0x19001  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x19006  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1900b  ldstr    aSendemail// "SendEmail"
0x19010  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x19015  call     bool [mscorlib]System.Boolean::Parse(string)
0x1901a  stloc.s  7
0x1901c  ldloc.s  5
0x1901e  brfalse.s loc_19029
0x19020  ldloc.s  5
0x19022  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x19027  br.s     loc_1902E
0x19029  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1902e  stloc.s  8
0x19030  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x19035  stloc.s  9
0x19037  ldarg.0
0x19038  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1903d  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x19042  ldstr    aTemplateid// "templateId"
0x19047  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1904c  brfalse.s loc_1906A
0x1904e  ldloca.s 9
0x19050  ldarg.0
0x19051  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x19056  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1905b  ldstr    aTemplateid// "templateId"
0x19060  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x19065  call     instance void [mscorlib]System.Guid::.ctor(string)
0x1906a  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1906f  stloc.s  0xA
0x19071  ldarg.0
0x19072  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x19077  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1907c  ldstr    aQueueid_1// "QueueId"
0x19081  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x19086  stloc.s  0xB
0x19088  ldloc.s  0xB
0x1908a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1908f  brtrue.s loc_1909A
0x19091  ldloca.s 0xA
0x19093  ldloc.s  0xB
0x19095  call     instance void [mscorlib]System.Guid::.ctor(string)
0x1909a  ldarg.0
0x1909b  ldloc.1
0x1909c  callvirt instance string Microsoft.Crm.Common.Application.Pages.Dialogs.ListBasicActivityPage::FixStateCode(string formXml)
0x190a1  stloc.1
0x190a2  ldloc.2
0x190a3  ldc.i4   0x10CC
0x190a8  beq.s    loc_190B4
0x190aa  ldloc.2
0x190ab  ldc.i4   0x1132
0x190b0  beq.s    loc_190E3
0x190b2  br.s     loc_1911A
0x190b4  ldstr    aList// "list"
0x190b9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x190be  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x190c3  newobj   instance void [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.List::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x190c8  stloc.s  0xC
0x190ca  ldarg.0
0x190cb  ldloc.s  0xC
0x190cd  ldloc.3
0x190ce  ldloc.1
0x190cf  ldloc.s  4
0x190d1  ldloc.s  5
0x190d3  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x190d8  ldloc.s  6
0x190da  ldloc.s  0xA
0x190dc  call     instance void Microsoft.Crm.Common.Application.Pages.Dialogs.ListBasicActivityPage::CreateListActivity(class [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.List list, string id, string formXml, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropagationOwnershipOptions ownerOption, valuetype [mscorlib]System.Guid ownerId, int32 ownerType, valuetype [mscorlib]System.Guid queueId)
0x190e1  br.s     loc_19134
0x190e3  ldloc.1
0x190e4  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::GetEntityName(string)
0x190e9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x190ee  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x190f3  dup
0x190f4  ldloc.1
0x190f5  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::set_Data(string)
0x190fa  ldloc.3
0x190fb  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x19100  ldloc.s  4
0x19102  ldloc.s  9
0x19104  ldloc.s  8
0x19106  ldloc.s  6
0x19108  ldloc.s  7
0x1910a  ldloc.s  0xA
0x1910c  ldc.i4.1
0x1910d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x19112  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Marketing.Application.Platform]Microsoft.Crm.Marketing.Application.Platform.MarketingDataSource::ExecuteCampaignActivity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropagationOwnershipOptions, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, int32, bool, valuetype [mscorlib]System.Guid, bool, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x19117  pop
0x19118  br.s     loc_19134
0x1911a  ldc.i4.0
0x1911b  ldstr    aActivitiesCanB// "Activities can be created only for List"...
0x19120  ldc.i4.1
0x19121  newarr   [mscorlib]System.Object
0x19126  dup
0x19127  ldc.i4.0
0x19128  ldloc.2
0x19129  box      [mscorlib]System.Int32
0x1912e  stelem.ref
0x1912f  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string, object[])
0x19134  ldarg.0
0x19135  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x1913a  call     void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::RaiseXMLSuccess(class [System.Web]System.Web.UI.Page)
0x1913f  leave    loc_19319
0x19144  call     class [mscorlib]System.Exception [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::CreateXmlException(class [mscorlib]System.Exception)
0x19149  throw
0x1914a  ldarg.0
0x1914b  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x19150  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableForm
0x19155  stloc.s  0xD
0x19157  ldloc.s  0xD
0x19159  ldarg.0
0x1915a  dup
0x1915b  ldvirtftn instance void Microsoft.Crm.Common.Application.Pages.Dialogs.ListBasicActivityPage::Item_DataBoundReady(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CrmFormEventArgs e)
0x19161  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm/DataBoundEventHandler::.ctor(object, native int)
0x19166  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::add_DataBound(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm/DataBoundEventHandler)
0x1916b  ldarg.0
0x1916c  ldc.i4   0x2BC
0x19171  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_Width(int32)
0x19176  ldarg.0
0x19177  ldc.i4   0x1F4
0x1917c  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_Height(int32)
0x19181  ldarg.0
0x19182  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentType()
0x19187  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_TypeCode()
0x1918c  ldc.i4   0x106A
0x19191  bne.un.s loc_191D0
0x19193  ldarg.0
0x19194  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0x19199  ldstr    aButbegin// "butBegin"
0x1919e  ldstr    aButtonLabelLis// "Button_Label_ListActivityCreate"
0x191a3  ldstr    aApplychangeson// "applyChangesOnDistribute("
0x191a8  ldarg.0
0x191a9  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentType()
0x191ae  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_TypeCode()
0x191b3  box      [mscorlib]System.Int32
0x191b8  ldstr    asc_31980// ");"
0x191bd  call     string [mscorlib]System.String::Concat(object, object, object)
0x191c2  ldc.i4.0
0x191c3  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButton::.ctor(string, string, string, bool)
0x191c8  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::Add(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButton)
0x191cd  pop
0x191ce  br.s     loc_1920B
0x191d0  ldarg.0
0x191d1  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0x191d6  ldstr    aButbegin// "butBegin"
0x191db  ldstr    aButtonLabelLis// "Button_Label_ListActivityCreate"
0x191e0  ldstr    aApplychanges_1// "applychanges("
0x191e5  ldarg.0
0x191e6  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentType()
0x191eb  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_TypeCode()
0x191f0  box      [mscorlib]System.Int32
0x191f5  ldstr    asc_31980// ");"
0x191fa  call     string [mscorlib]System.String::Concat(object, object, object)
0x191ff  ldc.i4.0
0x19200  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButton::.ctor(string, string, string, bool)
0x19205  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::Add(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButton)
0x1920a  pop
0x1920b  ldarg.0
0x1920c  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0x19211  ldc.i4.2
0x19212  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::AddStandardButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.StandardDialogButtons)
0x19217  pop
0x19218  ldarg.0
0x19219  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0x1921e  ldc.i4.s 0x10
0x19220  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::AddStandardButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.StandardDialogButtons)
0x19225  pop
0x19226  ldc.i4.1
0x19227  stloc.s  0xE
0x19229  ldarg.0
0x1922a  callvirt instance string Microsoft.Crm.Common.Application.Pages.Dialogs.ListBasicActivityPage::get_WizardFormGuid()
0x1922f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x19234  brtrue.s loc_1928B
0x19236  ldarg.0
0x19237  callvirt instance string Microsoft.Crm.Common.Application.Pages.Dialogs.ListBasicActivityPage::get_WizardFormGuid()
0x1923c  ldloca.s 0xF
0x1923e  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x19243  brfalse.s loc_1928B
0x19245  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.AppFormFilter::.ctor()
0x1924a  ldloc.s  0xF
0x1924c  ldarg.0
0x1924d  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Common.Application.Pages.Dialogs.ListBasicActivityPage::get_CurrentActivity()
0x19252  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x19257  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_TypeCode()
0x1925c  ldc.i4.2
0x1925d  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.AppFormFilter::IsValidForm(valuetype [mscorlib]System.Guid, int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormType)
0x19262  brfalse.s loc_1928B
0x19264  ldloc.s  0xF
0x19266  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Forms.FormDescriptorCache::GetFormDescriptor(valuetype [mscorlib]System.Guid)
0x1926b  stloc.s  0x10
0x1926d  ldloc.s  0x10
0x1926f  brfalse.s loc_1928B
0x19271  ldloc.s  0xD
0x19273  ldc.i4.0
0x19274  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableForm::set_SetLastViewedXml(bool)
0x19279  ldloc.s  0xD
0x1927b  ldarg.0
0x1927c  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Common.Application.Pages.Dialogs.ListBasicActivityPage::get_CurrentActivity()
0x19281  ldloc.s  0x10
0x19283  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableForm::ExecuteForFormDescriptor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor)
0x19288  ldc.i4.0
0x19289  stloc.s  0xE
0x1928b  ldloc.s  0xE
0x1928d  brfalse.s loc_1929C
0x1928f  ldloc.s  0xD
0x19291  ldarg.0
  ... truncated ...
```
