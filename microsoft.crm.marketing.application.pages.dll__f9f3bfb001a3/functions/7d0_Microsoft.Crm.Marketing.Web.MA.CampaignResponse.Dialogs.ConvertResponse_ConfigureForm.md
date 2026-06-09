# Microsoft.Crm.Marketing.Web.MA.CampaignResponse.Dialogs.ConvertResponse::ConfigureForm

- ea: `0x7d0`
- end: `0xbd6`
- name: `Microsoft.Crm.Marketing.Web.MA.CampaignResponse.Dialogs.ConvertResponse::ConfigureForm`
- size: `1030`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x6c0`
- `0x6e0`
- `0x700`
- `0x720`
- `0x740`
- `0x770`
- `0x7d0`

## pseudocode

```c

```

## disassembly

```asm
0x7d0  ldarg.0
0x7d1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0x7d6  ldarg.0
0x7d7  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x7dc  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x7e1  ldstr    aCustomertype// "customerType"
0x7e6  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x7eb  stloc.0
0x7ec  ldarg.0
0x7ed  ldarg.0
0x7ee  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x7f3  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x7f8  ldstr    aCustomerid// "customerId"
0x7fd  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x802  stfld    string Microsoft.Crm.Marketing.Web.MA.CampaignResponse.Dialogs.ConvertResponse::_customerId
0x807  ldarg.0
0x808  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x80d  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x812  ldstr    aCustomername// "customerName"
0x817  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x81c  stloc.1
0x81d  ldarg.0
0x81e  ldc.i4.0
0x81f  stfld    int32 Microsoft.Crm.Marketing.Web.MA.CampaignResponse.Dialogs.ConvertResponse::_customerType
0x824  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x829  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x82e  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x833  ldstr    aConvertRespons// "Convert Response for customer with Name"...
0x838  ldc.i4.3
0x839  newarr   [mscorlib]System.Object
0x83e  dup
0x83f  ldc.i4.0
0x840  ldloc.1
0x841  stelem.ref
0x842  dup
0x843  ldc.i4.1
0x844  ldarg.0
0x845  ldfld    string Microsoft.Crm.Marketing.Web.MA.CampaignResponse.Dialogs.ConvertResponse::_customerId
0x84a  stelem.ref
0x84b  dup
0x84c  ldc.i4.2
0x84d  ldarg.0
0x84e  ldfld    int32 Microsoft.Crm.Marketing.Web.MA.CampaignResponse.Dialogs.ConvertResponse::_customerType
0x853  box      [mscorlib]System.Int32
0x858  stelem.ref
0x859  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x85e  ldloc.0
0x85f  brfalse.s loc_87B
0x861  ldloc.0
0x862  callvirt instance int32 [mscorlib]System.String::get_Length()
0x867  brfalse.s loc_87B
0x869  ldarg.0
0x86a  ldloc.0
0x86b  ldc.i4.7
0x86c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x871  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x876  stfld    int32 Microsoft.Crm.Marketing.Web.MA.CampaignResponse.Dialogs.ConvertResponse::_customerType
0x87b  ldarg.0
0x87c  ldfld    string Microsoft.Crm.Marketing.Web.MA.CampaignResponse.Dialogs.ConvertResponse::_customerId
0x881  brfalse.s loc_890
0x883  ldarg.0
0x884  ldfld    string Microsoft.Crm.Marketing.Web.MA.CampaignResponse.Dialogs.ConvertResponse::_customerId
0x889  callvirt instance int32 [mscorlib]System.String::get_Length()
0x88e  brtrue.s loc_89B
0x890  ldarg.0
0x891  ldsfld   string [mscorlib]System.String::Empty
0x896  stfld    string Microsoft.Crm.Marketing.Web.MA.CampaignResponse.Dialogs.ConvertResponse::_customerId
0x89b  ldloc.1
0x89c  brfalse.s loc_8A6
0x89e  ldloc.1
0x89f  callvirt instance int32 [mscorlib]System.String::get_Length()
0x8a4  brtrue.s loc_8AC
0x8a6  ldsfld   string [mscorlib]System.String::Empty
0x8ab  stloc.1
0x8ac  ldarg.0
0x8ad  call     instance class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Marketing.Web.MA.CampaignResponse.Dialogs.ConvertResponse::get_CrmCurrencyLookup()
0x8b2  ldc.i4.1
0x8b3  newarr   [mscorlib]System.Int32
0x8b8  dup
0x8b9  ldc.i4.0
0x8ba  ldc.i4   0x2391
0x8bf  stelem.i4
0x8c0  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupTypes(int32[])
0x8c5  ldarg.0
0x8c6  call     instance class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Marketing.Web.MA.CampaignResponse.Dialogs.ConvertResponse::get_CrmCurrencyLookup()
0x8cb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8d0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::ObtainDefaultCurrency(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8d5  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object)
0x8da  ldarg.0
0x8db  call     instance class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Marketing.Web.MA.CampaignResponse.Dialogs.ConvertResponse::get_LeadLookup()
0x8e0  ldstr    aSingle// "single"
0x8e5  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupStyle(string)
0x8ea  ldarg.0
0x8eb  call     instance class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Marketing.Web.MA.CampaignResponse.Dialogs.ConvertResponse::get_LeadLookup()
0x8f0  ldc.i4.1
0x8f1  newarr   [mscorlib]System.Int32
0x8f6  dup
0x8f7  ldc.i4.0
0x8f8  ldc.i4.4
0x8f9  stelem.i4
0x8fa  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupTypes(int32[])
0x8ff  ldarg.0
0x900  call     instance class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Marketing.Web.MA.CampaignResponse.Dialogs.ConvertResponse::get_LeadLookup()
0x905  ldstr    a00000000000000// "00000000-0000-0000-00AA-000010001006"
0x90a  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x90f  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_DefaultViewId(valuetype [mscorlib]System.Guid)
0x914  ldarg.0
0x915  call     instance class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Marketing.Web.MA.CampaignResponse.Dialogs.ConvertResponse::get_AcctContLookup()
0x91a  ldstr    aSingle// "single"
0x91f  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupStyle(string)
0x924  ldarg.0
0x925  call     instance class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Marketing.Web.MA.CampaignResponse.Dialogs.ConvertResponse::get_AcctContLookup()
0x92a  ldc.i4.2
0x92b  newarr   [mscorlib]System.Int32
0x930  dup
0x931  ldc.i4.0
0x932  ldc.i4.1
0x933  stelem.i4
0x934  dup
0x935  ldc.i4.1
0x936  ldc.i4.2
0x937  stelem.i4
0x938  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupTypes(int32[])
0x93d  ldarg.0
0x93e  ldfld    string Microsoft.Crm.Marketing.Web.MA.CampaignResponse.Dialogs.ConvertResponse::_customerId
0x943  callvirt instance int32 [mscorlib]System.String::get_Length()
0x948  brfalse.s loc_997
0x94a  ldarg.0
0x94b  ldfld    int32 Microsoft.Crm.Marketing.Web.MA.CampaignResponse.Dialogs.ConvertResponse::_customerType
0x950  ldc.i4.1
0x951  beq.s    loc_95C
0x953  ldarg.0
0x954  ldfld    int32 Microsoft.Crm.Marketing.Web.MA.CampaignResponse.Dialogs.ConvertResponse::_customerType
0x959  ldc.i4.2
0x95a  bne.un.s loc_976
0x95c  ldarg.0
0x95d  call     instance class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Marketing.Web.MA.CampaignResponse.Dialogs.ConvertResponse::get_AcctContLookup()
0x962  ldarg.0
0x963  ldfld    string Microsoft.Crm.Marketing.Web.MA.CampaignResponse.Dialogs.ConvertResponse::_customerId
0x968  ldarg.0
0x969  ldfld    int32 Microsoft.Crm.Marketing.Web.MA.CampaignResponse.Dialogs.ConvertResponse::_customerType
0x96e  ldloc.1
0x96f  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::AddItem(string, int32, string)
0x974  br.s     loc_997
0x976  ldarg.0
0x977  ldfld    int32 Microsoft.Crm.Marketing.Web.MA.CampaignResponse.Dialogs.ConvertResponse::_customerType
0x97c  ldc.i4.4
0x97d  bne.un.s loc_997
0x97f  ldarg.0
0x980  call     instance class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Marketing.Web.MA.CampaignResponse.Dialogs.ConvertResponse::get_LeadLookup()
0x985  ldarg.0
0x986  ldfld    string Microsoft.Crm.Marketing.Web.MA.CampaignResponse.Dialogs.ConvertResponse::_customerId
0x98b  ldarg.0
0x98c  ldfld    int32 Microsoft.Crm.Marketing.Web.MA.CampaignResponse.Dialogs.ConvertResponse::_customerType
0x991  ldloc.1
0x992  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::AddItem(string, int32, string)
0x997  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x99c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x9a1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x9a6  stloc.2
0x9a7  ldloc.2
0x9a8  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9ad  ldc.i4   0x1131
0x9b2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x9b7  ldstr    aStatecode// "statecode"
0x9bc  ldc.i4.1
0x9bd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x9c2  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StateAttributeMetadata
0x9c7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IStateOptionsByValueCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StateAttributeMetadata::get_StateOptions()
0x9cc  stloc.3
0x9cd  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x9d2  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x9d7  stloc.s  4
0x9d9  ldstr    aActivitypointe// "activitypointer"
0x9de  ldc.i4.1
0x9df  stloc.s  7
0x9e1  ldloca.s 7
0x9e3  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.ActivityPointerState
0x9e9  callvirt instance string [mscorlib]System.Object::ToString()
0x9ee  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::ConvertStateToNumber(string, string)
0x9f3  stloc.s  5
0x9f5  ldstr    aActivitypointe// "activitypointer"
0x9fa  ldc.i4.2
0x9fb  stloc.s  7
0x9fd  ldloca.s 7
0x9ff  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.ActivityPointerState
0xa05  callvirt instance string [mscorlib]System.Object::ToString()
0xa0a  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::ConvertStateToNumber(string, string)
0xa0f  stloc.s  6
0xa11  ldc.i4.2
0xa12  newarr   [mscorlib]System.Int32
0xa17  dup
0xa18  ldc.i4.0
0xa19  ldloc.s  5
0xa1b  stelem.i4
0xa1c  dup
0xa1d  ldc.i4.1
0xa1e  ldloc.s  6
0xa20  stelem.i4
0xa21  stloc.s  8
0xa23  ldc.i4.0
0xa24  stloc.s  9
0xa26  br.s     loc_A6B
0xa28  ldloc.s  8
0xa2a  ldloc.s  9
0xa2c  ldelem.i4
0xa2d  stloc.s  0xA
0xa2f  ldarg.0
0xa30  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Marketing.Web.MA.CampaignResponse.Dialogs.ConvertResponse::get_ResponseStatePicklist()
0xa35  ldloc.3
0xa36  ldloc.s  0xA
0xa38  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEnumOptionsByValueCollection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StateOption>::get_Item(!!T0)
0xa3d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Labels()
0xa42  ldloc.s  4
0xa44  ldloc.2
0xa45  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa4a  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0xa4f  ldloca.s 0xA
0xa51  ldstr    aD// "D"
0xa56  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa5b  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0xa60  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddItem(string, string)
0xa65  ldloc.s  9
0xa67  ldc.i4.1
0xa68  add
0xa69  stloc.s  9
0xa6b  ldloc.s  9
0xa6d  ldloc.s  8
0xa6f  ldlen
0xa70  conv.i4
0xa71  blt.s    loc_A28
0xa73  ldarg.0
0xa74  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Marketing.Web.MA.CampaignResponse.Dialogs.ConvertResponse::get_ResponseStatePicklist()
0xa79  ldstr    a1// "1"
0xa7e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::set_Selected(string)
0xa83  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_CreateOpportunity()
0xa88  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa8d  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa92  brfalse.s loc_AB4
0xa94  ldarg.0
0xa95  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Marketing.Web.MA.CampaignResponse.Dialogs.ConvertResponse::get_CreateNewRecordPicklist()
0xa9a  ldarg.0
0xa9b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xaa0  ldstr    aMaCampaignresp// "MA.CampaignResponse.Dialogs.conv_respon"...
0xaa5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xaaa  ldstr    a1// "1"
0xaaf  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddItem(string, string)
0xab4  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_CreateOrder()
0xab9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xabe  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xac3  brfalse.s loc_AE5
0xac5  ldarg.0
0xac6  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Marketing.Web.MA.CampaignResponse.Dialogs.ConvertResponse::get_CreateNewRecordPicklist()
0xacb  ldarg.0
0xacc  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xad1  ldstr    aMaCampaignresp_0// "MA.CampaignResponse.Dialogs.conv_respon"...
0xad6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xadb  ldstr    a2// "2"
0xae0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddItem(string, string)
0xae5  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_CreateQuote()
0xaea  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xaef  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xaf4  brfalse.s loc_B16
0xaf6  ldarg.0
0xaf7  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Marketing.Web.MA.CampaignResponse.Dialogs.ConvertResponse::get_CreateNewRecordPicklist()
0xafc  ldarg.0
0xafd  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xb02  ldstr    aMaCampaignresp_1// "MA.CampaignResponse.Dialogs.conv_respon"...
0xb07  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xb0c  ldstr    a3// "3"
0xb11  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddItem(string, string)
0xb16  ldarg.0
0xb17  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Marketing.Web.MA.CampaignResponse.Dialogs.ConvertResponse::get_CreateNewRecordPicklist()
0xb1c  ldstr    a1// "1"
0xb21  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::set_Selected(string)
0xb26  ldarg.0
0xb27  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_CreateLead()
0xb2c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xb31  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xb36  brtrue.s loc_B7C
0xb38  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_ReadLead()
0xb3d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xb42  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xb47  brtrue.s loc_B7C
0xb49  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_CreateQuote()
0xb4e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xb53  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xb58  brtrue.s loc_B7C
0xb5a  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_CreateOrder()
0xb5f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xb64  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xb69  brtrue.s loc_B7C
0xb6b  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_CreateOpportunity()
0xb70  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xb75  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xb7a  br.s     loc_B7D
0xb7c  ldc.i4.1
0xb7d  call     instance void Microsoft.Crm.Marketing.Web.MA.CampaignResponse.Dialogs.ConvertResponse::set_CanConvertResponse(bool value)
0xb82  ldarg.0
0xb83  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
  ... truncated ...
```
