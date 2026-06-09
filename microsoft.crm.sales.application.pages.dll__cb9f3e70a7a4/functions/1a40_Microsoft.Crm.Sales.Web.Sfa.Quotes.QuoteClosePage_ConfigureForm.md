# Microsoft.Crm.Sales.Web.Sfa.Quotes.QuoteClosePage::ConfigureForm

- ea: `0x1a40`
- end: `0x1b16`
- name: `Microsoft.Crm.Sales.Web.Sfa.Quotes.QuoteClosePage::ConfigureForm`
- size: `214`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x10`

## pseudocode

```c

```

## disassembly

```asm
0x1a40  ldarg.0
0x1a41  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0x1a46  ldarg.0
0x1a47  ldarg.0
0x1a48  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1a4d  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1a52  ldstr    aQuoteid_0// "quoteid"
0x1a57  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1a5c  stfld    string Microsoft.Crm.Sales.Web.Sfa.Quotes.QuoteClosePage::_quoteId
0x1a61  ldarg.0
0x1a62  ldarg.0
0x1a63  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1a68  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1a6d  ldstr    aOpportunityid// "opportunityid"
0x1a72  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1a77  stfld    string Microsoft.Crm.Sales.Web.Sfa.Quotes.QuoteClosePage::_opportunityId
0x1a7c  ldarg.0
0x1a7d  ldarg.0
0x1a7e  ldfld    string Microsoft.Crm.Sales.Web.Sfa.Quotes.QuoteClosePage::_opportunityId
0x1a83  ldarg.0
0x1a84  ldfld    string Microsoft.Crm.Sales.Web.Sfa.Quotes.QuoteClosePage::_quoteId
0x1a89  ldc.i4.2
0x1a8a  call     bool Microsoft.Crm.Web.Sfa.SfaUtility::CanCloseOpportunity(string opportunityId, string quoteId, valuetype [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.OpportunityState newState)
0x1a8f  stfld    bool Microsoft.Crm.Sales.Web.Sfa.Quotes.QuoteClosePage::_canCloseOpportunity
0x1a94  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1a99  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1a9e  ldc.i4   0x43C
0x1aa3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x1aa8  stloc.0
0x1aa9  ldarg.0
0x1aaa  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl Microsoft.Crm.Sales.Web.Sfa.Quotes.QuoteClosePage::selStatus
0x1aaf  ldloc.0
0x1ab0  ldstr    aStatuscode// "statuscode"
0x1ab5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x1aba  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Metadata(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata)
0x1abf  ldarg.0
0x1ac0  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl Microsoft.Crm.Sales.Web.Sfa.Quotes.QuoteClosePage::selStatus
0x1ac5  ldc.i4.1
0x1ac6  newarr   [mscorlib]System.Int32
0x1acb  dup
0x1acc  ldc.i4.0
0x1acd  ldstr    aQuote// "quote"
0x1ad2  ldc.i4.3
0x1ad3  stloc.1
0x1ad4  ldloca.s 1
0x1ad6  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.QuoteState
0x1adc  callvirt instance string [mscorlib]System.Object::ToString()
0x1ae1  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::ConvertStateToNumber(string, string)
0x1ae6  stelem.i4
0x1ae7  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl::set_States(int32[])
0x1aec  ldarg.0
0x1aed  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.DateTimeControl Microsoft.Crm.Sales.Web.Sfa.Quotes.QuoteClosePage::closeDate
0x1af2  ldc.i4.0
0x1af3  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.DateTimeControl::set_AllowBlankDate(bool)
0x1af8  ldarg.0
0x1af9  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.DateTimeControl Microsoft.Crm.Sales.Web.Sfa.Quotes.QuoteClosePage::closeDate
0x1afe  call     valuetype [mscorlib]System.DateTime [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_LocalDateTime()
0x1b03  stloc.2
0x1b04  ldloca.s 2
0x1b06  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x1b0b  box      [mscorlib]System.DateTime
0x1b10  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object)
0x1b15  ret
```
