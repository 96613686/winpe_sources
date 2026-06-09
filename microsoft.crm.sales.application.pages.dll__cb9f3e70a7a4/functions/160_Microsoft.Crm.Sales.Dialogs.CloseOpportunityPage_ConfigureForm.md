# Microsoft.Crm.Sales.Dialogs.CloseOpportunityPage::ConfigureForm

- ea: `0x160`
- end: `0x582`
- name: `Microsoft.Crm.Sales.Dialogs.CloseOpportunityPage::ConfigureForm`
- size: `1058`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x10`
- `0x160`

## pseudocode

```c

```

## disassembly

```asm
0x160  ldarg.0
0x161  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0x166  ldstr    aOpportunity// "opportunity"
0x16b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x170  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x175  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x17a  stloc.0
0x17b  ldarg.0
0x17c  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x181  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x186  ldstr    aPid// "pId"
0x18b  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x190  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetGuid(string)
0x195  stloc.1
0x196  ldarg.0
0x197  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Sales.Dialogs.CloseOpportunityPage::crmLookup
0x19c  ldc.i4.1
0x19d  newarr   [mscorlib]System.Int32
0x1a2  dup
0x1a3  ldc.i4.0
0x1a4  ldc.i4.s 0x7B
0x1a6  stelem.i4
0x1a7  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupTypes(int32[])
0x1ac  ldarg.0
0x1ad  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Sales.Dialogs.CloseOpportunityPage::crmLookup
0x1b2  ldc.i4.1
0x1b3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0x1b8  ldarg.0
0x1b9  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1be  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1c3  ldstr    aPtype// "pType"
0x1c8  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1cd  ldc.i4   0x43C
0x1d2  stloc.s  6
0x1d4  ldloca.s 6
0x1d6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1db  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1e0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1e5  brfalse.s loc_21D
0x1e7  ldstr    aQuote// "quote"
0x1ec  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1f1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1f6  newobj   instance void [Microsoft.Crm.Sales.Application.Platform]Microsoft.Crm.Sales.Application.Platform.Quote::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x1fb  dup
0x1fc  ldloc.1
0x1fd  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Id(string)
0x202  dup
0x203  ldstr    aColumnsetColum// "<columnset><column>opportunityid</colum"...
0x208  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Retrieve(string)
0x20d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_Data()
0x212  ldstr    aOpportunityid// "opportunityid"
0x217  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetNodeValue(string, string)
0x21c  stloc.1
0x21d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x222  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x227  ldc.i4.3
0x228  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x22d  stloc.2
0x22e  ldloc.2
0x22f  ldstr    aStatuscode// "statuscode"
0x234  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x239  stloc.3
0x23a  ldarg.0
0x23b  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl Microsoft.Crm.Sales.Dialogs.CloseOpportunityPage::selWinStatus
0x240  ldloc.3
0x241  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Metadata(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata)
0x246  ldarg.0
0x247  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl Microsoft.Crm.Sales.Dialogs.CloseOpportunityPage::selWinStatus
0x24c  ldc.i4.1
0x24d  newarr   [mscorlib]System.Int32
0x252  dup
0x253  ldc.i4.0
0x254  ldstr    aOpportunity// "opportunity"
0x259  ldc.i4.1
0x25a  stloc.s  7
0x25c  ldloca.s 7
0x25e  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.OpportunityState
0x264  callvirt instance string [mscorlib]System.Object::ToString()
0x269  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::ConvertStateToNumber(string, string)
0x26e  stelem.i4
0x26f  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl::set_States(int32[])
0x274  ldarg.0
0x275  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl Microsoft.Crm.Sales.Dialogs.CloseOpportunityPage::selLoseStatus
0x27a  ldloc.3
0x27b  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Metadata(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata)
0x280  ldarg.0
0x281  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl Microsoft.Crm.Sales.Dialogs.CloseOpportunityPage::selLoseStatus
0x286  ldc.i4.1
0x287  newarr   [mscorlib]System.Int32
0x28c  dup
0x28d  ldc.i4.0
0x28e  ldstr    aOpportunity// "opportunity"
0x293  ldc.i4.2
0x294  stloc.s  7
0x296  ldloca.s 7
0x298  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.OpportunityState
0x29e  callvirt instance string [mscorlib]System.Object::ToString()
0x2a3  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::ConvertStateToNumber(string, string)
0x2a8  stelem.i4
0x2a9  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl::set_States(int32[])
0x2ae  ldarg.0
0x2af  ldloc.1
0x2b0  stfld    string Microsoft.Crm.Sales.Dialogs.CloseOpportunityPage::OpportunityId
0x2b5  ldnull
0x2b6  stloc.s  4
0x2b8  ldarg.0
0x2b9  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x2be  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x2c3  ldstr    aPtype// "pType"
0x2c8  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x2cd  ldc.i4   0x43C
0x2d2  stloc.s  6
0x2d4  ldloca.s 6
0x2d6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2db  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x2e0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2e5  brfalse.s loc_2FE
0x2e7  ldarg.0
0x2e8  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x2ed  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x2f2  ldstr    aPid// "pId"
0x2f7  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x2fc  stloc.s  4
0x2fe  ldloc.1
0x2ff  ldloc.s  4
0x301  ldc.i4.1
0x302  call     bool Microsoft.Crm.Web.Sfa.SfaUtility::CanCloseOpportunity(string opportunityId, string quoteId, valuetype [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.OpportunityState newState)
0x307  brfalse  loc_4C9
0x30c  ldloc.0
0x30d  ldloc.1
0x30e  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Id(string)
0x313  ldloc.0
0x314  ldstr    aColumnsetColum_0// "<columnset><column>name</column><column"...
0x319  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Retrieve(string)
0x31e  ldarg.0
0x31f  ldarg.0
0x320  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x325  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x32a  ldstr    aEstimatedval// "estimatedVal"
0x32f  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x334  stfld    string Microsoft.Crm.Sales.Dialogs.CloseOpportunityPage::EstimatedRevenue
0x339  ldarg.0
0x33a  ldfld    string Microsoft.Crm.Sales.Dialogs.CloseOpportunityPage::EstimatedRevenue
0x33f  brfalse.s loc_34E
0x341  ldarg.0
0x342  ldfld    string Microsoft.Crm.Sales.Dialogs.CloseOpportunityPage::EstimatedRevenue
0x347  callvirt instance int32 [mscorlib]System.String::get_Length()
0x34c  brtrue.s loc_38C
0x34e  ldloc.0
0x34f  ldstr    aEstimatedvalue// "estimatedvalue"
0x354  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x359  brfalse.s loc_381
0x35b  ldloc.0
0x35c  ldstr    aEstimatedvalue// "estimatedvalue"
0x361  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x366  unbox.any [mscorlib]System.Decimal
0x36b  stloc.s  0xB
0x36d  ldarg.0
0x36e  ldloca.s 0xB
0x370  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x375  call     instance string [mscorlib]System.Decimal::ToString(class [mscorlib]System.IFormatProvider)
0x37a  stfld    string Microsoft.Crm.Sales.Dialogs.CloseOpportunityPage::EstimatedRevenue
0x37f  br.s     loc_38C
0x381  ldarg.0
0x382  ldstr    a0// "0"
0x387  stfld    string Microsoft.Crm.Sales.Dialogs.CloseOpportunityPage::EstimatedRevenue
0x38c  ldarg.0
0x38d  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.DateTimeControl Microsoft.Crm.Sales.Dialogs.CloseOpportunityPage::actualend
0x392  call     valuetype [mscorlib]System.DateTime [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_LocalDateTime()
0x397  stloc.s  0xC
0x399  ldloca.s 0xC
0x39b  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x3a0  box      [mscorlib]System.DateTime
0x3a5  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object)
0x3aa  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x3af  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3b4  ldc.i4   0x1070
0x3b9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x3be  ldstr    aSubject// "subject"
0x3c3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x3c8  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StringAttributeMetadata
0x3cd  stloc.s  8
0x3cf  ldloc.0
0x3d0  ldstr    aName// "name"
0x3d5  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x3da  castclass [mscorlib]System.String
0x3df  stloc.s  9
0x3e1  ldloc.s  9
0x3e3  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3e8  brtrue.s loc_40B
0x3ea  ldloc.s  9
0x3ec  callvirt instance int32 [mscorlib]System.String::get_Length()
0x3f1  ldloc.s  8
0x3f3  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.TextAttributeMetadata::get_MaxLength()
0x3f8  ble.s    loc_40B
0x3fa  ldloc.s  9
0x3fc  ldc.i4.0
0x3fd  ldloc.s  8
0x3ff  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.TextAttributeMetadata::get_MaxLength()
0x404  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x409  stloc.s  9
0x40b  ldarg.0
0x40c  ldarg.0
0x40d  ldfld    string Microsoft.Crm.Sales.Dialogs.CloseOpportunityPage::JScriptHeader
0x412  ldstr    aSubject_0// "_subject=\""
0x417  ldloc.s  9
0x419  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncodeNoQuotes(string)
0x41e  ldstr    asc_24F4// "\";"
0x423  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x428  stfld    string Microsoft.Crm.Sales.Dialogs.CloseOpportunityPage::JScriptHeader
0x42d  ldarg.0
0x42e  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.MoneyControl Microsoft.Crm.Sales.Dialogs.CloseOpportunityPage::actualrevenue
0x433  ldloc.2
0x434  ldstr    aEstimatedvalue// "estimatedvalue"
0x439  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x43e  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Metadata(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata)
0x443  ldarg.0
0x444  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.MoneyControl Microsoft.Crm.Sales.Dialogs.CloseOpportunityPage::actualrevenue
0x449  ldloc.0
0x44a  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::set_DataSource(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity)
0x44f  ldtoken  [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.OpportunityState
0x454  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x459  ldloc.0
0x45a  ldstr    aStatecode// "statecode"
0x45f  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x464  castclass [mscorlib]System.String
0x469  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string)
0x46e  unbox.any [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.OpportunityState
0x473  stloc.s  0xA
0x475  ldloc.s  0xA
0x477  ldc.i4.2
0x478  beq.s    loc_47F
0x47a  ldloc.s  0xA
0x47c  ldc.i4.1
0x47d  bne.un.s loc_4F9
0x47f  ldarg.0
0x480  ldarg.0
0x481  ldfld    string Microsoft.Crm.Sales.Dialogs.CloseOpportunityPage::JScriptHeader
0x486  ldstr    aAlert// "alert(\""
0x48b  ldarg.0
0x48c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x491  ldc.i4   0x80040515
0x496  stloc.s  6
0x498  ldloca.s 6
0x49a  ldstr    aX// "x"
0x49f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4a4  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x4a9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x4ae  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetErrorMessageWithoutEncoding(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4b3  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncodeNoQuotes(string)
0x4b8  ldstr    aClosewindow// "\");closeWindow();"
0x4bd  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x4c2  stfld    string Microsoft.Crm.Sales.Dialogs.CloseOpportunityPage::JScriptHeader
0x4c7  br.s     loc_4F9
0x4c9  ldarg.0
0x4ca  ldarg.0
0x4cb  ldfld    string Microsoft.Crm.Sales.Dialogs.CloseOpportunityPage::JScriptHeader
0x4d0  ldstr    aAlert// "alert(\""
0x4d5  ldarg.0
0x4d6  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x4db  ldstr    aCloseOppConfir// "Close_Opp_Confirm_Quote"
0x4e0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4e5  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncodeNoQuotes(string)
0x4ea  ldstr    aClosewindow// "\");closeWindow();"
0x4ef  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x4f4  stfld    string Microsoft.Crm.Sales.Dialogs.CloseOpportunityPage::JScriptHeader
0x4f9  ldarg.0
0x4fa  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x4ff  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x504  ldstr    aWon// "won"
0x509  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x50e  stloc.s  5
0x510  ldloc.s  5
0x512  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x517  brtrue.s loc_537
0x519  ldloc.s  5
0x51b  ldstr    aTrue// "true"
0x520  ldc.i4.5
0x521  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x526  brtrue.s loc_537
0x528  ldloc.s  5
0x52a  ldstr    a1// "1"
0x52f  ldc.i4.4
0x530  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x535  br.s     loc_538
0x537  ldc.i4.1
0x538  brfalse.s loc_560
0x53a  ldarg.0
0x53b  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Sales.Dialogs.CloseOpportunityPage::divLost
0x540  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0x545  ldstr    aDisplay// "display"
0x54a  ldstr    aNone// "none"
0x54f  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::Add(string, string)
0x554  ldarg.0
0x555  ldstr    aTrue_0// "True"
0x55a  stfld    string Microsoft.Crm.Sales.Dialogs.CloseOpportunityPage::OpportunityIsWon
0x55f  ret
0x560  ldarg.0
0x561  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Sales.Dialogs.CloseOpportunityPage::divWon
0x566  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
  ... truncated ...
```
