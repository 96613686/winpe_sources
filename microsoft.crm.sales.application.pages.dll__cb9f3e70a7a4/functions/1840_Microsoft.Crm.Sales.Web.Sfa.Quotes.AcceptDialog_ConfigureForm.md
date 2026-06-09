# Microsoft.Crm.Sales.Web.Sfa.Quotes.AcceptDialog::ConfigureForm

- ea: `0x1840`
- end: `0x1993`
- name: `Microsoft.Crm.Sales.Web.Sfa.Quotes.AcceptDialog::ConfigureForm`
- size: `339`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x10`
- `0x1840`

## pseudocode

```c

```

## disassembly

```asm
0x1840  ldarg.0
0x1841  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0x1846  ldarg.0
0x1847  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.DateTimeControl Microsoft.Crm.Sales.Web.Sfa.Quotes.AcceptDialog::closeDate
0x184c  ldc.i4.0
0x184d  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.DateTimeControl::set_AllowBlankDate(bool)
0x1852  ldarg.0
0x1853  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.DateTimeControl Microsoft.Crm.Sales.Web.Sfa.Quotes.AcceptDialog::closeDate
0x1858  call     valuetype [mscorlib]System.DateTime [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_LocalDateTime()
0x185d  stloc.2
0x185e  ldloca.s 2
0x1860  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x1865  box      [mscorlib]System.DateTime
0x186a  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object)
0x186f  ldarg.0
0x1870  ldstr    aQuote// "quote"
0x1875  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x187a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x187f  newobj   instance void [Microsoft.Crm.Sales.Application.Platform]Microsoft.Crm.Sales.Application.Platform.Quote::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x1884  stfld    class [Microsoft.Crm.Sales.Application.Platform]Microsoft.Crm.Sales.Application.Platform.Quote Microsoft.Crm.Sales.Web.Sfa.Quotes.AcceptDialog::_quote
0x1889  ldarg.0
0x188a  ldfld    class [Microsoft.Crm.Sales.Application.Platform]Microsoft.Crm.Sales.Application.Platform.Quote Microsoft.Crm.Sales.Web.Sfa.Quotes.AcceptDialog::_quote
0x188f  ldarg.0
0x1890  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1895  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x189a  ldstr    aQuoteid// "QuoteId"
0x189f  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x18a4  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Id(string)
0x18a9  ldarg.0
0x18aa  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x18af  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x18b4  ldstr    aOpportunityid// "opportunityid"
0x18b9  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x18be  stloc.0
0x18bf  ldarg.0
0x18c0  ldloc.0
0x18c1  ldarg.0
0x18c2  ldfld    class [Microsoft.Crm.Sales.Application.Platform]Microsoft.Crm.Sales.Application.Platform.Quote Microsoft.Crm.Sales.Web.Sfa.Quotes.AcceptDialog::_quote
0x18c7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0x18cc  ldc.i4.1
0x18cd  call     bool Microsoft.Crm.Web.Sfa.SfaUtility::CanCloseOpportunity(string opportunityId, string quoteId, valuetype [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.OpportunityState newState)
0x18d2  stfld    bool Microsoft.Crm.Sales.Web.Sfa.Quotes.AcceptDialog::canCloseOpportunity
0x18d7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x18dc  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x18e1  ldc.i4.3
0x18e2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x18e7  stloc.1
0x18e8  ldarg.0
0x18e9  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.MoneyControl Microsoft.Crm.Sales.Web.Sfa.Quotes.AcceptDialog::actualRevenue
0x18ee  ldloc.1
0x18ef  ldstr    aEstimatedvalue// "estimatedvalue"
0x18f4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x18f9  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Metadata(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata)
0x18fe  ldarg.0
0x18ff  ldfld    bool Microsoft.Crm.Sales.Web.Sfa.Quotes.AcceptDialog::canCloseOpportunity
0x1904  brfalse.s loc_1939
0x1906  ldstr    aOpportunity// "opportunity"
0x190b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1910  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1915  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x191a  stloc.3
0x191b  ldloc.3
0x191c  ldloc.0
0x191d  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Id(string)
0x1922  ldloc.3
0x1923  ldstr    aColumnsetColum_2// "<columnset><column>transactioncurrencyi"...
0x1928  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Retrieve(string)
0x192d  ldarg.0
0x192e  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.MoneyControl Microsoft.Crm.Sales.Web.Sfa.Quotes.AcceptDialog::actualRevenue
0x1933  ldloc.3
0x1934  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::set_DataSource(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity)
0x1939  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x193e  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1943  ldc.i4   0x43C
0x1948  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x194d  stloc.1
0x194e  ldarg.0
0x194f  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl Microsoft.Crm.Sales.Web.Sfa.Quotes.AcceptDialog::selStatus
0x1954  ldloc.1
0x1955  ldstr    aStatuscode// "statuscode"
0x195a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x195f  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Metadata(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata)
0x1964  ldarg.0
0x1965  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl Microsoft.Crm.Sales.Web.Sfa.Quotes.AcceptDialog::selStatus
0x196a  ldc.i4.1
0x196b  newarr   [mscorlib]System.Int32
0x1970  dup
0x1971  ldc.i4.0
0x1972  ldstr    aQuote// "quote"
0x1977  ldc.i4.2
0x1978  stloc.s  4
0x197a  ldloca.s 4
0x197c  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.QuoteState
0x1982  callvirt instance string [mscorlib]System.Object::ToString()
0x1987  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::ConvertStateToNumber(string, string)
0x198c  stelem.i4
0x198d  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl::set_States(int32[])
0x1992  ret
```
