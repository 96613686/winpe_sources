# Microsoft.Crm.Sales.Web.Commands.LookupAddressPage::ConfigureForm

- ea: `0xd00`
- end: `0xec9`
- name: `Microsoft.Crm.Sales.Web.Commands.LookupAddressPage::ConfigureForm`
- size: `457`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0xd00`

## pseudocode

```c

```

## disassembly

```asm
0xd00  ldarg.0
0xd01  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0xd06  ldarg.0
0xd07  ldarg.0
0xd08  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xd0d  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xd12  ldstr    aHeaderform// "headerForm"
0xd17  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xd1c  ldstr    a1// "1"
0xd21  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd26  stfld    bool Microsoft.Crm.Sales.Web.Commands.LookupAddressPage::_headerForm
0xd2b  ldarg.0
0xd2c  ldarg.0
0xd2d  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xd32  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xd37  ldstr    aWillcall// "willCall"
0xd3c  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xd41  ldstr    a1// "1"
0xd46  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd4b  stfld    bool Microsoft.Crm.Sales.Web.Commands.LookupAddressPage::_willCall
0xd50  ldarg.0
0xd51  ldfld    bool Microsoft.Crm.Sales.Web.Commands.LookupAddressPage::_headerForm
0xd56  brtrue   loc_E0E
0xd5b  ldarg.0
0xd5c  ldarg.0
0xd5d  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xd62  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xd67  ldstr    aHeadertype// "headerType"
0xd6c  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xd71  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xd76  call     int16 [mscorlib]System.Int16::Parse(string, class [mscorlib]System.IFormatProvider)
0xd7b  stfld    int32 Microsoft.Crm.Sales.Web.Commands.LookupAddressPage::_headerType
0xd80  ldarg.0
0xd81  ldarg.0
0xd82  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xd87  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xd8c  ldstr    aHeaderid// "headerId"
0xd91  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xd96  stfld    string Microsoft.Crm.Sales.Web.Commands.LookupAddressPage::_headerId
0xd9b  ldarg.0
0xd9c  ldfld    int32 Microsoft.Crm.Sales.Web.Commands.LookupAddressPage::_headerType
0xda1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xda6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Sales.Application.Platform]Microsoft.Crm.Sales.Application.Platform.SalesEntityFactory::CreateEntity(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xdab  stloc.0
0xdac  ldloc.0
0xdad  ldarg.0
0xdae  ldfld    string Microsoft.Crm.Sales.Web.Commands.LookupAddressPage::_headerId
0xdb3  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Id(string)
0xdb8  ldloc.0
0xdb9  ldstr    aColumnsetColum_1// "<columnset><column>customerid</column><"...
0xdbe  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Retrieve(string)
0xdc3  ldarg.0
0xdc4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xdc9  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xdce  ldloc.0
0xdcf  ldstr    aCustomeridtype// "customeridtype"
0xdd4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::GetPropertyValue(string)
0xdd9  ldc.i4.1
0xdda  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0xddf  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0xde4  stloc.1
0xde5  ldloca.s 1
0xde7  ldstr    aD// "D"
0xdec  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xdf1  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0xdf6  stfld    string Microsoft.Crm.Sales.Web.Commands.LookupAddressPage::_parentType
0xdfb  ldarg.0
0xdfc  ldloc.0
0xdfd  ldstr    aCustomerid// "customerid"
0xe02  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::GetPropertyValue(string)
0xe07  stfld    string Microsoft.Crm.Sales.Web.Commands.LookupAddressPage::_parentId
0xe0c  br.s     loc_E44
0xe0e  ldarg.0
0xe0f  ldarg.0
0xe10  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xe15  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xe1a  ldstr    aParenttype// "parentType"
0xe1f  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xe24  stfld    string Microsoft.Crm.Sales.Web.Commands.LookupAddressPage::_parentType
0xe29  ldarg.0
0xe2a  ldarg.0
0xe2b  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xe30  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xe35  ldstr    aParentid// "parentId"
0xe3a  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xe3f  stfld    string Microsoft.Crm.Sales.Web.Commands.LookupAddressPage::_parentId
0xe44  ldarg.0
0xe45  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0xe4a  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0xe4f  dup
0xe50  ldarg.0
0xe51  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe56  ldstr    aWebSfaQuotesDl// "Web.SFA.quotes.dlg_lookupaddress.aspx_1"...
0xe5b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe60  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0xe65  dup
0xe66  ldarg.0
0xe67  ldfld    bool Microsoft.Crm.Sales.Web.Commands.LookupAddressPage::_headerForm
0xe6c  brtrue.s loc_E80
0xe6e  ldarg.0
0xe6f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe74  ldstr    aWebSfaQuotesDl_0// "Web.SFA.quotes.dlg_lookupaddress.aspx_1"...
0xe79  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe7e  br.s     loc_E90
0xe80  ldarg.0
0xe81  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe86  ldstr    aWebSfaQuotesDl_1// "Web.SFA.quotes.dlg_lookupaddress.aspx_1"...
0xe8b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe90  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0xe95  dup
0xe96  ldc.i4.0
0xe97  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ButtonStyle(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0xe9c  dup
0xe9d  ldstr    aButbegin// "butBegin"
0xea2  ldstr    aButtonLabelOk// "Button_Label_OK"
0xea7  ldstr    aIfMscrmUtiliti// "if(!Mscrm.Utilities.resetValidationFail"...
0xeac  ldc.i4.1
0xead  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(string, string, string, bool)
0xeb2  ldstr    aCmddialogcance// "cmdDialogCancel"
0xeb7  ldstr    aButtonLabelCan// "Button_Label_Cancel"
0xebc  ldstr    aCancel// "cancel();"
0xec1  ldc.i4.0
0xec2  ldc.i4.2
0xec3  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(string, string, string, bool, valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0xec8  ret
```
