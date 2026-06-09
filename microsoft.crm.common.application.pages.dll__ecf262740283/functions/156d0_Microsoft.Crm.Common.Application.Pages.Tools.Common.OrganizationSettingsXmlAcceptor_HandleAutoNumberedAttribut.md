# Microsoft.Crm.Common.Application.Pages.Tools.Common.OrganizationSettingsXmlAcceptor::HandleAutoNumberedAttributes

- ea: `0x156d0`
- end: `0x15847`
- name: `Microsoft.Crm.Common.Application.Pages.Tools.Common.OrganizationSettingsXmlAcceptor::HandleAutoNumberedAttributes`
- size: `375`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x15240`

## callees

- `0x15690`
- `0x156d0`
- `0x16250`

## pseudocode

```c

```

## disassembly

```asm
0x156d0  ldarg.1
0x156d1  ldstr    aUniquespecifie// "uniquespecifierlength"
0x156d6  call     string Microsoft.Crm.Common.Application.Pages.Tools.Common.XmlNodeExtensions::GetNodeValue(class [System.Xml]System.Xml.XmlNode node, string childElementName)
0x156db  call     int32 [mscorlib]System.Convert::ToInt32(string)
0x156e0  stloc.0
0x156e1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x156e6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x156eb  ldc.i4.0
0x156ec  ldc.i4.0
0x156ed  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x156f2  dup
0x156f3  stloc.1
0x156f4  stloc.2
0x156f5  ldloc.1
0x156f6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x156fb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_UserId()
0x15700  ldc.i4.0
0x15701  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnBeginRequest(valuetype [mscorlib]System.Guid, bool)
0x15706  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsCRMOrganization()
0x1570b  brfalse  loc_157C4
0x15710  ldarg.0
0x15711  ldstr    aContract// "Contract"
0x15716  ldstr    aContractnumber// "contractnumber"
0x1571b  ldarg.1
0x1571c  ldstr    aContractprefix// "contractprefix"
0x15721  call     string Microsoft.Crm.Common.Application.Pages.Tools.Common.XmlNodeExtensions::GetNodeValue(class [System.Xml]System.Xml.XmlNode node, string childElementName)
0x15726  ldloc.0
0x15727  ldloc.1
0x15728  ldc.i4.1
0x15729  call     instance void Microsoft.Crm.Common.Application.Pages.Tools.Common.OrganizationSettingsXmlAcceptor::UpdateAutoNumberedField(string entityName, string attributeName, string prefix, int32 uniqueSpecifierLength, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, bool hasRandomStringSuffix)
0x1572e  ldarg.0
0x1572f  ldstr    aQuote// "Quote"
0x15734  ldstr    aQuotenumber// "quotenumber"
0x15739  ldarg.1
0x1573a  ldstr    aQuoteprefix// "quoteprefix"
0x1573f  call     string Microsoft.Crm.Common.Application.Pages.Tools.Common.XmlNodeExtensions::GetNodeValue(class [System.Xml]System.Xml.XmlNode node, string childElementName)
0x15744  ldloc.0
0x15745  ldloc.1
0x15746  ldc.i4.1
0x15747  call     instance void Microsoft.Crm.Common.Application.Pages.Tools.Common.OrganizationSettingsXmlAcceptor::UpdateAutoNumberedField(string entityName, string attributeName, string prefix, int32 uniqueSpecifierLength, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, bool hasRandomStringSuffix)
0x1574c  ldarg.0
0x1574d  ldstr    aInvoice// "Invoice"
0x15752  ldstr    aInvoicenumber// "invoicenumber"
0x15757  ldarg.1
0x15758  ldstr    aInvoiceprefix// "invoiceprefix"
0x1575d  call     string Microsoft.Crm.Common.Application.Pages.Tools.Common.XmlNodeExtensions::GetNodeValue(class [System.Xml]System.Xml.XmlNode node, string childElementName)
0x15762  ldloc.0
0x15763  ldloc.1
0x15764  ldc.i4.1
0x15765  call     instance void Microsoft.Crm.Common.Application.Pages.Tools.Common.OrganizationSettingsXmlAcceptor::UpdateAutoNumberedField(string entityName, string attributeName, string prefix, int32 uniqueSpecifierLength, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, bool hasRandomStringSuffix)
0x1576a  ldarg.0
0x1576b  ldstr    aSalesorder// "SalesOrder"
0x15770  ldstr    aOrdernumber// "ordernumber"
0x15775  ldarg.1
0x15776  ldstr    aOrderprefix// "orderprefix"
0x1577b  call     string Microsoft.Crm.Common.Application.Pages.Tools.Common.XmlNodeExtensions::GetNodeValue(class [System.Xml]System.Xml.XmlNode node, string childElementName)
0x15780  ldloc.0
0x15781  ldloc.1
0x15782  ldc.i4.1
0x15783  call     instance void Microsoft.Crm.Common.Application.Pages.Tools.Common.OrganizationSettingsXmlAcceptor::UpdateAutoNumberedField(string entityName, string attributeName, string prefix, int32 uniqueSpecifierLength, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, bool hasRandomStringSuffix)
0x15788  ldarg.0
0x15789  ldstr    aCampaign// "Campaign"
0x1578e  ldstr    aCodename// "codename"
0x15793  ldarg.1
0x15794  ldstr    aCampaignprefix// "campaignprefix"
0x15799  call     string Microsoft.Crm.Common.Application.Pages.Tools.Common.XmlNodeExtensions::GetNodeValue(class [System.Xml]System.Xml.XmlNode node, string childElementName)
0x1579e  ldloc.0
0x1579f  ldloc.1
0x157a0  ldc.i4.1
0x157a1  call     instance void Microsoft.Crm.Common.Application.Pages.Tools.Common.OrganizationSettingsXmlAcceptor::UpdateAutoNumberedField(string entityName, string attributeName, string prefix, int32 uniqueSpecifierLength, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, bool hasRandomStringSuffix)
0x157a6  ldarg.0
0x157a7  ldstr    aIncident_0// "Incident"
0x157ac  ldstr    aTicketnumber// "ticketnumber"
0x157b1  ldarg.1
0x157b2  ldstr    aCaseprefix// "caseprefix"
0x157b7  call     string Microsoft.Crm.Common.Application.Pages.Tools.Common.XmlNodeExtensions::GetNodeValue(class [System.Xml]System.Xml.XmlNode node, string childElementName)
0x157bc  ldloc.0
0x157bd  ldloc.1
0x157be  ldc.i4.1
0x157bf  call     instance void Microsoft.Crm.Common.Application.Pages.Tools.Common.OrganizationSettingsXmlAcceptor::UpdateAutoNumberedField(string entityName, string attributeName, string prefix, int32 uniqueSpecifierLength, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, bool hasRandomStringSuffix)
0x157c4  ldarg.0
0x157c5  ldstr    aKbarticle_0// "KbArticle"
0x157ca  ldstr    aNumber// "number"
0x157cf  ldarg.1
0x157d0  ldstr    aKbprefix// "kbprefix"
0x157d5  call     string Microsoft.Crm.Common.Application.Pages.Tools.Common.XmlNodeExtensions::GetNodeValue(class [System.Xml]System.Xml.XmlNode node, string childElementName)
0x157da  ldloc.0
0x157db  ldloc.1
0x157dc  ldc.i4.0
0x157dd  call     instance void Microsoft.Crm.Common.Application.Pages.Tools.Common.OrganizationSettingsXmlAcceptor::UpdateAutoNumberedField(string entityName, string attributeName, string prefix, int32 uniqueSpecifierLength, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, bool hasRandomStringSuffix)
0x157e2  ldarg.0
0x157e3  ldstr    aKnowledgeartic// "KnowledgeArticle"
0x157e8  ldstr    aArticlepublicn// "articlepublicnumber"
0x157ed  ldarg.1
0x157ee  ldstr    aKaprefix// "kaprefix"
0x157f3  call     string Microsoft.Crm.Common.Application.Pages.Tools.Common.XmlNodeExtensions::GetNodeValue(class [System.Xml]System.Xml.XmlNode node, string childElementName)
0x157f8  ldloc.0
0x157f9  ldloc.1
0x157fa  ldc.i4.0
0x157fb  call     instance void Microsoft.Crm.Common.Application.Pages.Tools.Common.OrganizationSettingsXmlAcceptor::UpdateAutoNumberedField(string entityName, string attributeName, string prefix, int32 uniqueSpecifierLength, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, bool hasRandomStringSuffix)
0x15800  ldarg.0
0x15801  ldstr    aCategory// "Category"
0x15806  ldstr    aCategorynumber// "categorynumber"
0x1580b  ldarg.1
0x1580c  ldstr    aCategoryprefix// "categoryprefix"
0x15811  call     string Microsoft.Crm.Common.Application.Pages.Tools.Common.XmlNodeExtensions::GetNodeValue(class [System.Xml]System.Xml.XmlNode node, string childElementName)
0x15816  ldloc.0
0x15817  ldloc.1
0x15818  ldc.i4.0
0x15819  call     instance void Microsoft.Crm.Common.Application.Pages.Tools.Common.OrganizationSettingsXmlAcceptor::UpdateAutoNumberedField(string entityName, string attributeName, string prefix, int32 uniqueSpecifierLength, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, bool hasRandomStringSuffix)
0x1581e  ldarg.0
0x1581f  ldfld    bool Microsoft.Crm.Common.Application.Pages.Tools.Common.OrganizationSettingsXmlAcceptor::anyFieldChanged
0x15824  brfalse.s loc_1582B
0x15826  call     void [Microsoft.Crm.Application.Components.WebServices.SystemCustomization]Microsoft.Crm.Application.WebServices.SystemCustomization.CustomizationsPublishAll::Execute()
0x1582b  ldloc.1
0x1582c  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnEndRequest()
0x15831  leave.s  loc_15846
0x15833  pop
0x15834  ldloc.1
0x15835  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnErrorRequest()
0x1583a  rethrow
0x1583c  ldloc.2
0x1583d  brfalse.s loc_15845
0x1583f  ldloc.2
0x15840  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x15845  endfinally
0x15846  ret
```
