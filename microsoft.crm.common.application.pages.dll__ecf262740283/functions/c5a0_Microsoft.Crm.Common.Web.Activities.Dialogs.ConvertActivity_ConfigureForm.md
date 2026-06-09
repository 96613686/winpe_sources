# Microsoft.Crm.Common.Web.Activities.Dialogs.ConvertActivity::ConfigureForm

- ea: `0xc5a0`
- end: `0xc945`
- name: `Microsoft.Crm.Common.Web.Activities.Dialogs.ConvertActivity::ConfigureForm`
- size: `933`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0xc3a0`
- `0xc3c0`
- `0xc3e0`
- `0xc400`
- `0xc5a0`

## pseudocode

```c

```

## disassembly

```asm
0xc5a0  ldarg.0
0xc5a1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0xc5a6  ldarg.0
0xc5a7  call     instance class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Common.Web.Activities.Dialogs.ConvertActivity::get_CampaignLookup()
0xc5ac  ldstr    aSingle// "single"
0xc5b1  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupStyle(string)
0xc5b6  ldarg.0
0xc5b7  call     instance class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Common.Web.Activities.Dialogs.ConvertActivity::get_CampaignLookup()
0xc5bc  ldc.i4.2
0xc5bd  newarr   [mscorlib]System.Int32
0xc5c2  dup
0xc5c3  ldc.i4.0
0xc5c4  ldc.i4   0x1130
0xc5c9  stelem.i4
0xc5ca  dup
0xc5cb  ldc.i4.1
0xc5cc  ldc.i4   0x1136
0xc5d1  stelem.i4
0xc5d2  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupTypes(int32[])
0xc5d7  ldarg.0
0xc5d8  call     instance class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Common.Web.Activities.Dialogs.ConvertActivity::get_CustomerLookup()
0xc5dd  ldstr    aSingle// "single"
0xc5e2  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupStyle(string)
0xc5e7  ldarg.0
0xc5e8  call     instance class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Common.Web.Activities.Dialogs.ConvertActivity::get_CustomerLookup()
0xc5ed  ldc.i4.2
0xc5ee  newarr   [mscorlib]System.Int32
0xc5f3  dup
0xc5f4  ldc.i4.0
0xc5f5  ldc.i4.1
0xc5f6  stelem.i4
0xc5f7  dup
0xc5f8  ldc.i4.1
0xc5f9  ldc.i4.2
0xc5fa  stelem.i4
0xc5fb  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupTypes(int32[])
0xc600  ldarg.0
0xc601  call     instance class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Common.Web.Activities.Dialogs.ConvertActivity::get_CurrencyLookup()
0xc606  ldstr    aSingle// "single"
0xc60b  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupStyle(string)
0xc610  ldarg.0
0xc611  call     instance class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Common.Web.Activities.Dialogs.ConvertActivity::get_CurrencyLookup()
0xc616  ldc.i4.1
0xc617  newarr   [mscorlib]System.Int32
0xc61c  dup
0xc61d  ldc.i4.0
0xc61e  ldc.i4   0x2391
0xc623  stelem.i4
0xc624  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupTypes(int32[])
0xc629  ldarg.0
0xc62a  call     instance class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Common.Web.Activities.Dialogs.ConvertActivity::get_CurrencyLookup()
0xc62f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xc634  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::ObtainDefaultCurrency(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xc639  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object)
0xc63e  ldarg.0
0xc63f  call     instance class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Common.Web.Activities.Dialogs.ConvertActivity::get_LeadLookup()
0xc644  ldstr    aSingle// "single"
0xc649  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupStyle(string)
0xc64e  ldarg.0
0xc64f  call     instance class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Common.Web.Activities.Dialogs.ConvertActivity::get_LeadLookup()
0xc654  ldc.i4.1
0xc655  newarr   [mscorlib]System.Int32
0xc65a  dup
0xc65b  ldc.i4.0
0xc65c  ldc.i4.4
0xc65d  stelem.i4
0xc65e  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupTypes(int32[])
0xc663  ldarg.0
0xc664  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xc669  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xc66e  ldstr    aCustomertype// "customerType"
0xc673  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xc678  stloc.0
0xc679  ldarg.0
0xc67a  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xc67f  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xc684  ldstr    aCustomerid_0// "customerId"
0xc689  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xc68e  stloc.1
0xc68f  ldarg.0
0xc690  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xc695  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xc69a  ldstr    aCustomername// "customerName"
0xc69f  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xc6a4  stloc.2
0xc6a5  ldc.i4.0
0xc6a6  stloc.3
0xc6a7  ldloc.0
0xc6a8  brfalse.s loc_C6D8
0xc6aa  ldloc.0
0xc6ab  callvirt instance int32 [mscorlib]System.String::get_Length()
0xc6b0  brfalse.s loc_C6D8
0xc6b2  ldloc.0
0xc6b3  ldc.i4.7
0xc6b4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc6b9  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0xc6be  stloc.3
0xc6bf  ldloc.1
0xc6c0  brfalse.s loc_C6D8
0xc6c2  ldloc.1
0xc6c3  callvirt instance int32 [mscorlib]System.String::get_Length()
0xc6c8  brfalse.s loc_C6D8
0xc6ca  ldarg.0
0xc6cb  call     instance class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Common.Web.Activities.Dialogs.ConvertActivity::get_CustomerLookup()
0xc6d0  ldloc.1
0xc6d1  ldloc.3
0xc6d2  ldloc.2
0xc6d3  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::AddItem(string, int32, string)
0xc6d8  ldarg.0
0xc6d9  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xc6de  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xc6e3  ldstr    aLeadid// "leadId"
0xc6e8  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xc6ed  stloc.s  4
0xc6ef  ldarg.0
0xc6f0  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xc6f5  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xc6fa  ldstr    aLeadname// "leadName"
0xc6ff  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xc704  stloc.s  5
0xc706  ldloc.s  4
0xc708  brfalse.s loc_C72A
0xc70a  ldloc.s  4
0xc70c  callvirt instance int32 [mscorlib]System.String::get_Length()
0xc711  brfalse.s loc_C72A
0xc713  ldarg.0
0xc714  call     instance class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Common.Web.Activities.Dialogs.ConvertActivity::get_LeadLookup()
0xc719  ldloc.s  4
0xc71b  ldc.i4.4
0xc71c  ldloc.s  5
0xc71e  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::AddItem(string, int32, string)
0xc723  ldarg.0
0xc724  ldc.i4.1
0xc725  stfld    bool Microsoft.Crm.Common.Web.Activities.Dialogs.ConvertActivity::isForLead
0xc72a  ldarg.0
0xc72b  ldfld    bool Microsoft.Crm.Common.Web.Activities.Dialogs.ConvertActivity::isForLead
0xc730  brtrue.s loc_C73E
0xc732  ldarg.0
0xc733  call     instance class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Common.Web.Activities.Dialogs.ConvertActivity::get_LeadLookup()
0xc738  ldc.i4.0
0xc739  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_AutoRegisterClientComponent(bool)
0xc73e  ldarg.0
0xc73f  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xc744  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xc749  ldstr    aCampaigntype// "campaignType"
0xc74e  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xc753  stloc.s  6
0xc755  ldarg.0
0xc756  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xc75b  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xc760  ldstr    aCampaignid// "campaignId"
0xc765  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xc76a  stloc.s  7
0xc76c  ldarg.0
0xc76d  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xc772  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xc777  ldstr    aCampaignname// "campaignName"
0xc77c  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xc781  stloc.s  8
0xc783  ldc.i4.0
0xc784  stloc.s  9
0xc786  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xc78b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0xc790  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0xc795  stloc.s  0xA
0xc797  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0xc79c  ldloc.s  0xA
0xc79e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xc7a3  ldloc.s  0xA
0xc7a5  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0xc7aa  stloc.s  0xB
0xc7ac  ldarg.0
0xc7ad  ldloc.s  0xB
0xc7af  ldstr    aActivityconver// "ActivityConvertDlgCampaignUnchecked"
0xc7b4  ldc.i4.1
0xc7b5  box      [mscorlib]System.Boolean
0xc7ba  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::GetOrgDBOrgSetting(string, object)
0xc7bf  unbox.any [mscorlib]System.Boolean
0xc7c4  stfld    bool Microsoft.Crm.Common.Web.Activities.Dialogs.ConvertActivity::defaultCampaignUnchecked
0xc7c9  ldloc.s  6
0xc7cb  brfalse  loc_C883
0xc7d0  ldloc.s  6
0xc7d2  callvirt instance int32 [mscorlib]System.String::get_Length()
0xc7d7  brfalse  loc_C883
0xc7dc  ldloc.s  6
0xc7de  ldc.i4.7
0xc7df  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc7e4  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0xc7e9  stloc.s  9
0xc7eb  ldloc.s  9
0xc7ed  ldc.i4   0x1132
0xc7f2  bne.un.s loc_C865
0xc7f4  ldc.i4.1
0xc7f5  newarr   [mscorlib]System.String
0xc7fa  dup
0xc7fb  ldc.i4.0
0xc7fc  ldstr    aRegardingobjec_0// "regardingobjectid"
0xc801  stelem.ref
0xc802  stloc.s  0xF
0xc804  ldloca.s 0x10
0xc806  ldloc.s  7
0xc808  call     instance void [mscorlib]System.Guid::.ctor(string)
0xc80d  ldstr    aCampaignactivi// "campaignactivity"
0xc812  ldloc.s  0x10
0xc814  ldloc.s  0xF
0xc816  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xc81b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xc820  dup
0xc821  ldstr    aRegardingobjec_0// "regardingobjectid"
0xc826  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xc82b  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0xc830  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_ID()
0xc835  stloc.s  7
0xc837  ldloc.s  0xA
0xc839  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xc83e  ldstr    aCampaign// "Campaign"
0xc843  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string)
0xc848  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0xc84d  stloc.s  9
0xc84f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_Data()
0xc854  ldstr    aRegardingobjec_0// "regardingobjectid"
0xc859  ldstr    aName// "name"
0xc85e  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetAttrValue(string, string, string)
0xc863  stloc.s  8
0xc865  ldloc.s  7
0xc867  brfalse.s loc_C883
0xc869  ldloc.s  7
0xc86b  callvirt instance int32 [mscorlib]System.String::get_Length()
0xc870  brfalse.s loc_C883
0xc872  ldarg.0
0xc873  call     instance class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Common.Web.Activities.Dialogs.ConvertActivity::get_CampaignLookup()
0xc878  ldloc.s  7
0xc87a  ldloc.s  9
0xc87c  ldloc.s  8
0xc87e  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::AddItem(string, int32, string)
0xc883  ldloc.s  0xA
0xc885  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xc88a  ldarg.0
0xc88b  ldfld    int32 Microsoft.Crm.Common.Web.Activities.Dialogs.ConvertActivity::activityType
0xc890  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0xc895  stloc.s  0xC
0xc897  ldarg.0
0xc898  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xc89d  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xc8a2  ldstr    aSubject// "subject"
0xc8a7  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xc8ac  stloc.s  0xD
0xc8ae  ldarg.0
0xc8af  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.HiddenInputControl Microsoft.Crm.Common.Web.Activities.Dialogs.ConvertActivity::subject
0xc8b4  ldloc.s  0xD
0xc8b6  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object)
0xc8bb  ldarg.0
0xc8bc  ldarg.0
0xc8bd  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xc8c2  ldstr    aConvertActivit// "Convert_Activity_To_Oppo_InlineDlg_Titl"...
0xc8c7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc8cc  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogTitle(string)
0xc8d1  ldarg.0
0xc8d2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc8d7  ldarg.0
0xc8d8  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xc8dd  ldstr    aConvertActivit_0// "Convert_Activity_To_Oppo_Dlg_Desc"
0xc8e2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc8e7  ldc.i4.1
0xc8e8  newarr   [mscorlib]System.Object
0xc8ed  dup
0xc8ee  ldc.i4.0
0xc8ef  ldloc.s  0xC
0xc8f1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LocalizedName()
0xc8f6  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0xc8fb  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0xc900  ldloc.s  0xA
0xc902  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::TryGetDescription(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xc907  stelem.ref
0xc908  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xc90d  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogDescription(string)
0xc912  ldarg.0
0xc913  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0xc918  ldc.i4.1
0xc919  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::AddStandardButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.StandardDialogButtons)
0xc91e  stloc.s  0xE
0xc920  ldarg.0
0xc921  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0xc926  ldloc.s  0xE
0xc928  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButton [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::get_Item(int32)
0xc92d  ldstr    aConvertActivit_1// "Convert_Activity_To_Oppo_Dlg_ConvertBut"...
0xc932  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_ResourceId(string)
0xc937  ldarg.0
0xc938  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0xc93d  ldc.i4.2
0xc93e  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::AddStandardButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.StandardDialogButtons)
0xc943  pop
0xc944  ret
```
