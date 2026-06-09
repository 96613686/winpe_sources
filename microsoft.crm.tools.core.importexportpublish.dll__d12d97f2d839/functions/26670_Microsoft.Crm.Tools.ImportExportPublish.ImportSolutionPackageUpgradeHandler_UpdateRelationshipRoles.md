# Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdateRelationshipRoles

- ea: `0x26670`
- end: `0x2707f`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdateRelationshipRoles`
- size: `2575`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x25f70`

## callees

- `0x24120`

## string_xrefs

- `0x266c4`: `competitor`
- `0x266de`: `competitor`
- `0x266f8`: `competitor`
- `0x26712`: `competitor`
- `0x26794`: `competitor`
- `0x267ae`: `competitor`
- `0x267c8`: `competitor`
- `0x26b56`: `opportunitycompetitors`
- `0x26b70`: `opportunitycompetitors`
- `0x26b8a`: `opportunitycompetitors`
- `0x266bf`: `competitorproduct_association`
- `0x266d9`: `competitorproduct_association`
- `0x266f3`: `competitorproduct_association`
- `0x2670d`: `competitorproduct_association`
- `0x26727`: `competitorproduct_association`
- `0x26741`: `competitorproduct_association`
- `0x2675b`: `competitorproduct_association`
- `0x26775`: `competitorproduct_association`
- `0x266ce`: `crmcompetitor.retrievebyobject`
- `0x2679e`: `crmcompetitor.retrievebyobject`
- `0x26702`: `navcomps`
- `0x2678f`: `competitorsalesliterature_association`
- `0x267a9`: `competitorsalesliterature_association`
- `0x267c3`: `competitorsalesliterature_association`
- `0x267dd`: `competitorsalesliterature_association`
- `0x267f7`: `competitorsalesliterature_association`
- `0x26811`: `competitorsalesliterature_association`
- `0x2682b`: `competitorsalesliterature_association`
- `0x267d2`: `navcomp`
- `0x26b03`: `opportunitycompetitors_association`
- `0x26b1d`: `opportunitycompetitors_association`
- `0x26b37`: `opportunitycompetitors_association`
- `0x26b51`: `opportunitycompetitors_association`
- `0x26b6b`: `opportunitycompetitors_association`
- `0x26b85`: `opportunitycompetitors_association`
- `0x26fd8`: `smsite.retrievemembers`

## pseudocode

```c

```

## disassembly

```asm
0x26670  ldarg.0
0x26671  ldstr    aCampaignlistAs// "campaignlist_association"
0x26676  ldstr    aCampaign_0// "campaign"
0x2667b  ldstr    aNavpanequeryap// "NavPaneQueryApi"
0x26680  ldstr    aCampaignRetrie// "campaign.retrievecampaignsforlist"
0x26685  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntityRelationshipRole(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entityRelationshipName, string entityName, string propertyName, string value)
0x2668a  ldarg.0
0x2668b  ldstr    aCampaignlistAs// "campaignlist_association"
0x26690  ldstr    aCampaign_0// "campaign"
0x26695  ldstr    aNavpaneviewid// "NavPaneViewId"
0x2669a  ldstr    a244af698F75348// "244af698-f753-48fd-9803-c1939dcf02d1"
0x2669f  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntityRelationshipRole(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entityRelationshipName, string entityName, string propertyName, string value)
0x266a4  ldarg.0
0x266a5  ldstr    aCampaignlistAs// "campaignlist_association"
0x266aa  ldstr    aCampaign_0// "campaign"
0x266af  ldstr    aNavpaneid// "NavPaneId"
0x266b4  ldstr    aNavcampaignsin// "navcampaignsinlist"
0x266b9  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntityRelationshipRole(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entityRelationshipName, string entityName, string propertyName, string value)
0x266be  ldarg.0
0x266bf  ldstr    aCompetitorprod_0// "competitorproduct_association"
0x266c4  ldstr    aCompetitor// "competitor"
0x266c9  ldstr    aNavpanequeryap// "NavPaneQueryApi"
0x266ce  ldstr    aCrmcompetitorR// "crmcompetitor.retrievebyobject"
0x266d3  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntityRelationshipRole(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entityRelationshipName, string entityName, string propertyName, string value)
0x266d8  ldarg.0
0x266d9  ldstr    aCompetitorprod_0// "competitorproduct_association"
0x266de  ldstr    aCompetitor// "competitor"
0x266e3  ldstr    aNavpaneviewid// "NavPaneViewId"
0x266e8  ldstr    a00000000000000// "00000000-0000-0000-00aa-000010001206"
0x266ed  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntityRelationshipRole(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entityRelationshipName, string entityName, string propertyName, string value)
0x266f2  ldarg.0
0x266f3  ldstr    aCompetitorprod_0// "competitorproduct_association"
0x266f8  ldstr    aCompetitor// "competitor"
0x266fd  ldstr    aNavpaneid// "NavPaneId"
0x26702  ldstr    aNavcomps// "navcomps"
0x26707  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntityRelationshipRole(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entityRelationshipName, string entityName, string propertyName, string value)
0x2670c  ldarg.0
0x2670d  ldstr    aCompetitorprod_0// "competitorproduct_association"
0x26712  ldstr    aCompetitor// "competitor"
0x26717  ldstr    aNavpaneiscusto// "NavPaneIsCustomizable"
0x2671c  ldstr    a1// "1"
0x26721  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntityRelationshipRole(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entityRelationshipName, string entityName, string propertyName, string value)
0x26726  ldarg.0
0x26727  ldstr    aCompetitorprod_0// "competitorproduct_association"
0x2672c  ldstr    aProduct// "product"
0x26731  ldstr    aNavpanequeryap// "NavPaneQueryApi"
0x26736  ldstr    aCrmproductRetr// "crmproduct.retrievebyobject"
0x2673b  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntityRelationshipRole(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entityRelationshipName, string entityName, string propertyName, string value)
0x26740  ldarg.0
0x26741  ldstr    aCompetitorprod_0// "competitorproduct_association"
0x26746  ldstr    aProduct// "product"
0x2674b  ldstr    aNavpaneviewid// "NavPaneViewId"
0x26750  ldstr    aF8de15f44c764a// "f8de15f4-4c76-4a21-94c9-a38fcafdb73d"
0x26755  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntityRelationshipRole(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entityRelationshipName, string entityName, string propertyName, string value)
0x2675a  ldarg.0
0x2675b  ldstr    aCompetitorprod_0// "competitorproduct_association"
0x26760  ldstr    aProduct// "product"
0x26765  ldstr    aNavpaneid// "NavPaneId"
0x2676a  ldstr    aNavproducts// "navproducts"
0x2676f  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntityRelationshipRole(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entityRelationshipName, string entityName, string propertyName, string value)
0x26774  ldarg.0
0x26775  ldstr    aCompetitorprod_0// "competitorproduct_association"
0x2677a  ldstr    aProduct// "product"
0x2677f  ldstr    aNavpaneiscusto// "NavPaneIsCustomizable"
0x26784  ldstr    a1// "1"
0x26789  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntityRelationshipRole(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entityRelationshipName, string entityName, string propertyName, string value)
0x2678e  ldarg.0
0x2678f  ldstr    aCompetitorsale// "competitorsalesliterature_association"
0x26794  ldstr    aCompetitor// "competitor"
0x26799  ldstr    aNavpanequeryap// "NavPaneQueryApi"
0x2679e  ldstr    aCrmcompetitorR// "crmcompetitor.retrievebyobject"
0x267a3  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntityRelationshipRole(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entityRelationshipName, string entityName, string propertyName, string value)
0x267a8  ldarg.0
0x267a9  ldstr    aCompetitorsale// "competitorsalesliterature_association"
0x267ae  ldstr    aCompetitor// "competitor"
0x267b3  ldstr    aNavpaneviewid// "NavPaneViewId"
0x267b8  ldstr    a00000000000000// "00000000-0000-0000-00aa-000010001206"
0x267bd  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntityRelationshipRole(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entityRelationshipName, string entityName, string propertyName, string value)
0x267c2  ldarg.0
0x267c3  ldstr    aCompetitorsale// "competitorsalesliterature_association"
0x267c8  ldstr    aCompetitor// "competitor"
0x267cd  ldstr    aNavpaneid// "NavPaneId"
0x267d2  ldstr    aNavcomp// "navcomp"
0x267d7  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntityRelationshipRole(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entityRelationshipName, string entityName, string propertyName, string value)
0x267dc  ldarg.0
0x267dd  ldstr    aCompetitorsale// "competitorsalesliterature_association"
0x267e2  ldstr    aSalesliteratur// "salesliterature"
0x267e7  ldstr    aNavpanequeryap// "NavPaneQueryApi"
0x267ec  ldstr    aCrmsaleslitera// "crmsalesliterature.retrievebyobject"
0x267f1  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntityRelationshipRole(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entityRelationshipName, string entityName, string propertyName, string value)
0x267f6  ldarg.0
0x267f7  ldstr    aCompetitorsale// "competitorsalesliterature_association"
0x267fc  ldstr    aSalesliteratur// "salesliterature"
0x26801  ldstr    aNavpaneviewid// "NavPaneViewId"
0x26806  ldstr    a00000000000000_0// "00000000-0000-0000-00aa-000010001113"
0x2680b  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntityRelationshipRole(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entityRelationshipName, string entityName, string propertyName, string value)
0x26810  ldarg.0
0x26811  ldstr    aCompetitorsale// "competitorsalesliterature_association"
0x26816  ldstr    aSalesliteratur// "salesliterature"
0x2681b  ldstr    aNavpaneid// "NavPaneId"
0x26820  ldstr    aNavsaleslit// "navsaleslit"
0x26825  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntityRelationshipRole(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entityRelationshipName, string entityName, string propertyName, string value)
0x2682a  ldarg.0
0x2682b  ldstr    aCompetitorsale// "competitorsalesliterature_association"
0x26830  ldstr    aSalesliteratur// "salesliterature"
0x26835  ldstr    aNavpaneiscusto// "NavPaneIsCustomizable"
0x2683a  ldstr    a1// "1"
0x2683f  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntityRelationshipRole(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entityRelationshipName, string entityName, string propertyName, string value)
0x26844  ldarg.0
0x26845  ldstr    aContactinvoice// "contactinvoices_association"
0x2684a  ldstr    aInvoice// "invoice"
0x2684f  ldstr    aNavpanequeryap// "NavPaneQueryApi"
0x26854  ldstr    aCrminvoiceRetr// "crminvoice.retrievecontacts"
0x26859  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntityRelationshipRole(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entityRelationshipName, string entityName, string propertyName, string value)
0x2685e  ldarg.0
0x2685f  ldstr    aContactinvoice// "contactinvoices_association"
0x26864  ldstr    aInvoice// "invoice"
0x26869  ldstr    aNavpaneviewid// "NavPaneViewId"
0x2686e  ldstr    a00000000000000_1// "00000000-0000-0000-00aa-000010001210"
0x26873  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntityRelationshipRole(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entityRelationshipName, string entityName, string propertyName, string value)
0x26878  ldarg.0
0x26879  ldstr    aContactinvoice// "contactinvoices_association"
0x2687e  ldstr    aInvoice// "invoice"
0x26883  ldstr    aNavpaneid// "NavPaneId"
0x26888  ldstr    aNavcontacts// "navcontacts"
0x2688d  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntityRelationshipRole(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entityRelationshipName, string entityName, string propertyName, string value)
0x26892  ldarg.0
0x26893  ldstr    aContactinvoice// "contactinvoices_association"
0x26898  ldstr    aInvoice// "invoice"
0x2689d  ldstr    aNavpaneiscusto// "NavPaneIsCustomizable"
0x268a2  ldstr    a1// "1"
0x268a7  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntityRelationshipRole(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entityRelationshipName, string entityName, string propertyName, string value)
0x268ac  ldarg.0
0x268ad  ldstr    aContractCases// "contract_cases"
0x268b2  ldstr    aIncident// "incident"
0x268b7  ldstr    aNavpanequeryap// "NavPaneQueryApi"
0x268bc  ldstr    aCrmincidentRet// "crmincident.retrievebyobject"
0x268c1  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntityRelationshipRole(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entityRelationshipName, string entityName, string propertyName, string value)
0x268c6  ldarg.0
0x268c7  ldstr    aContractCases// "contract_cases"
0x268cc  ldstr    aIncident// "incident"
0x268d1  ldstr    aNavpaneviewid// "NavPaneViewId"
0x268d6  ldstr    a00000000000000_2// "00000000-0000-0000-00aa-000010003501"
0x268db  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntityRelationshipRole(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entityRelationshipName, string entityName, string propertyName, string value)
0x268e0  ldarg.0
0x268e1  ldstr    aContractCases// "contract_cases"
0x268e6  ldstr    aIncident// "incident"
0x268eb  ldstr    aNavpaneid// "NavPaneId"
0x268f0  ldstr    aNavcases// "navcases"
0x268f5  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntityRelationshipRole(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entityRelationshipName, string entityName, string propertyName, string value)
0x268fa  ldarg.0
0x268fb  ldstr    aContractCases// "contract_cases"
0x26900  ldstr    aIncident// "incident"
0x26905  ldstr    aNavpaneiscusto// "NavPaneIsCustomizable"
0x2690a  ldstr    a1// "1"
0x2690f  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntityRelationshipRole(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entityRelationshipName, string entityName, string propertyName, string value)
0x26914  ldarg.0
0x26915  ldstr    aContractDetail// "contract_detail_cases"
0x2691a  ldstr    aIncident// "incident"
0x2691f  ldstr    aNavpanequeryap// "NavPaneQueryApi"
0x26924  ldstr    aCrmincidentRet// "crmincident.retrievebyobject"
0x26929  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntityRelationshipRole(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entityRelationshipName, string entityName, string propertyName, string value)
0x2692e  ldarg.0
0x2692f  ldstr    aContractDetail// "contract_detail_cases"
0x26934  ldstr    aIncident// "incident"
0x26939  ldstr    aNavpaneviewid// "NavPaneViewId"
0x2693e  ldstr    a00000000000000_2// "00000000-0000-0000-00aa-000010003501"
0x26943  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntityRelationshipRole(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entityRelationshipName, string entityName, string propertyName, string value)
0x26948  ldarg.0
0x26949  ldstr    aContractDetail// "contract_detail_cases"
0x2694e  ldstr    aIncident// "incident"
0x26953  ldstr    aNavpaneid// "NavPaneId"
0x26958  ldstr    aNavcases// "navcases"
0x2695d  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntityRelationshipRole(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entityRelationshipName, string entityName, string propertyName, string value)
0x26962  ldarg.0
0x26963  ldstr    aContractDetail// "contract_detail_cases"
0x26968  ldstr    aIncident// "incident"
0x2696d  ldstr    aNavpaneiscusto// "NavPaneIsCustomizable"
0x26972  ldstr    a1// "1"
0x26977  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntityRelationshipRole(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entityRelationshipName, string entityName, string propertyName, string value)
0x2697c  ldarg.0
0x2697d  ldstr    aContractLineIt// "contract_line_items"
0x26982  ldstr    aContractdetail_0// "contractdetail"
0x26987  ldstr    aNavpanequeryap// "NavPaneQueryApi"
0x2698c  ldstr    aCrmcontractdet// "crmcontractdetail.retrievebycontract"
0x26991  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntityRelationshipRole(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entityRelationshipName, string entityName, string propertyName, string value)
0x26996  ldarg.0
0x26997  ldstr    aContractLineIt// "contract_line_items"
0x2699c  ldstr    aContractdetail_0// "contractdetail"
0x269a1  ldstr    aNavpaneviewid// "NavPaneViewId"
0x269a6  ldstr    a2922b6fe757840// "2922b6fe-7578-4002-b4e1-b5189c28a37a"
0x269ab  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntityRelationshipRole(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entityRelationshipName, string entityName, string propertyName, string value)
0x269b0  ldarg.0
0x269b1  ldstr    aContractLineIt// "contract_line_items"
0x269b6  ldstr    aContractdetail_0// "contractdetail"
0x269bb  ldstr    aNavpaneid// "NavPaneId"
0x269c0  ldstr    aNavcontractlin// "navcontractlines"
0x269c5  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntityRelationshipRole(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entityRelationshipName, string entityName, string propertyName, string value)
0x269ca  ldarg.0
0x269cb  ldstr    aContractLineIt// "contract_line_items"
0x269d0  ldstr    aContractdetail_0// "contractdetail"
0x269d5  ldstr    aNavpaneiscusto// "NavPaneIsCustomizable"
0x269da  ldstr    a1// "1"
0x269df  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntityRelationshipRole(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entityRelationshipName, string entityName, string propertyName, string value)
0x269e4  ldarg.0
0x269e5  ldstr    aDiscountTypeDi// "discount_type_discounts"
0x269ea  ldstr    aDiscount// "discount"
0x269ef  ldstr    aNavpanequeryap// "NavPaneQueryApi"
0x269f4  ldstr    aCrmdiscountRet// "crmdiscount.retrievebyobject"
0x269f9  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntityRelationshipRole(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entityRelationshipName, string entityName, string propertyName, string value)
0x269fe  ldarg.0
0x269ff  ldstr    aDiscountTypeDi// "discount_type_discounts"
0x26a04  ldstr    aDiscount// "discount"
0x26a09  ldstr    aNavpaneviewid// "NavPaneViewId"
0x26a0e  ldstr    a00000000000000_3// "00000000-0000-0000-00aa-000010016000"
0x26a13  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntityRelationshipRole(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entityRelationshipName, string entityName, string propertyName, string value)
0x26a18  ldarg.0
0x26a19  ldstr    aDiscountTypeDi// "discount_type_discounts"
0x26a1e  ldstr    aDiscount// "discount"
0x26a23  ldstr    aNavpaneid// "NavPaneId"
0x26a28  ldstr    aNavdiscounts// "navdiscounts"
0x26a2d  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntityRelationshipRole(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entityRelationshipName, string entityName, string propertyName, string value)
0x26a32  ldarg.0
0x26a33  ldstr    aDiscountTypeDi// "discount_type_discounts"
0x26a38  ldstr    aDiscount// "discount"
0x26a3d  ldstr    aNavpaneiscusto// "NavPaneIsCustomizable"
0x26a42  ldstr    a1// "1"
0x26a47  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntityRelationshipRole(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entityRelationshipName, string entityName, string propertyName, string value)
0x26a4c  ldarg.0
0x26a4d  ldstr    aInvoiceDetails// "invoice_details"
0x26a52  ldstr    aInvoicedetail_0// "invoicedetail"
0x26a57  ldstr    aNavpanequeryap// "NavPaneQueryApi"
0x26a5c  ldstr    aCrminvoicedeta// "crminvoicedetail.retrievebyobject"
0x26a61  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntityRelationshipRole(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entityRelationshipName, string entityName, string propertyName, string value)
0x26a66  ldarg.0
0x26a67  ldstr    aInvoiceDetails// "invoice_details"
0x26a6c  ldstr    aInvoicedetail_0// "invoicedetail"
0x26a71  ldstr    aNavpaneviewid// "NavPaneViewId"
0x26a76  ldstr    a966f79a852004d// "966f79a8-5200-4dab-bafd-6de1947ee181"
0x26a7b  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntityRelationshipRole(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entityRelationshipName, string entityName, string propertyName, string value)
0x26a80  ldarg.0
0x26a81  ldstr    aInvoiceDetails// "invoice_details"
0x26a86  ldstr    aInvoicedetail_0// "invoicedetail"
0x26a8b  ldstr    aNavpaneid// "NavPaneId"
0x26a90  ldstr    aNavproducts// "navproducts"
0x26a95  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntityRelationshipRole(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entityRelationshipName, string entityName, string propertyName, string value)
0x26a9a  ldarg.0
0x26a9b  ldstr    aInvoiceDetails// "invoice_details"
0x26aa0  ldstr    aInvoicedetail_0// "invoicedetail"
0x26aa5  ldstr    aNavpaneiscusto// "NavPaneIsCustomizable"
0x26aaa  ldstr    a1// "1"
0x26aaf  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntityRelationshipRole(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entityRelationshipName, string entityName, string propertyName, string value)
0x26ab4  ldarg.0
0x26ab5  ldstr    aListBulkoperat// "list_bulkoperations"
0x26aba  ldstr    aBulkoperation// "bulkoperation"
0x26abf  ldstr    aNavpanequeryap// "NavPaneQueryApi"
0x26ac4  ldstr    aBulkoperationR// "bulkoperation.retrieveminicampaignsforl"...
0x26ac9  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntityRelationshipRole(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entityRelationshipName, string entityName, string propertyName, string value)
0x26ace  ldarg.0
0x26acf  ldstr    aListBulkoperat// "list_bulkoperations"
0x26ad4  ldstr    aBulkoperation// "bulkoperation"
0x26ad9  ldstr    aNavpaneviewid// "NavPaneViewId"
0x26ade  ldstr    a83dc23890a4c42// "83dc2389-0a4c-4249-a5d3-ba1ab401ff1c"
0x26ae3  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntityRelationshipRole(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entityRelationshipName, string entityName, string propertyName, string value)
0x26ae8  ldarg.0
0x26ae9  ldstr    aListBulkoperat// "list_bulkoperations"
0x26aee  ldstr    aBulkoperation// "bulkoperation"
0x26af3  ldstr    aNavpaneid// "NavPaneId"
0x26af8  ldstr    aNavminicampaig// "navminicampaignsforlist"
0x26afd  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntityRelationshipRole(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entityRelationshipName, string entityName, string propertyName, string value)
0x26b02  ldarg.0
0x26b03  ldstr    aOpportunitycom_0// "opportunitycompetitors_association"
0x26b08  ldstr    aOpportunity// "opportunity"
0x26b0d  ldstr    aNavpanequeryap// "NavPaneQueryApi"
0x26b12  ldstr    aCrmopportunity// "crmopportunity.retrievebyobject"
0x26b17  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntityRelationshipRole(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entityRelationshipName, string entityName, string propertyName, string value)
0x26b1c  ldarg.0
0x26b1d  ldstr    aOpportunitycom_0// "opportunitycompetitors_association"
0x26b22  ldstr    aOpportunity// "opportunity"
0x26b27  ldstr    aNavpaneviewid// "NavPaneViewId"
0x26b2c  ldstr    a00000000000000_4// "00000000-0000-0000-00aa-000010001203"
0x26b31  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntityRelationshipRole(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entityRelationshipName, string entityName, string propertyName, string value)
0x26b36  ldarg.0
0x26b37  ldstr    aOpportunitycom_0// "opportunitycompetitors_association"
0x26b3c  ldstr    aOpportunity// "opportunity"
0x26b41  ldstr    aNavpaneid// "NavPaneId"
0x26b46  ldstr    aNavopportuniti// "navopportunities"
0x26b4b  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntityRelationshipRole(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entityRelationshipName, string entityName, string propertyName, string value)
0x26b50  ldarg.0
0x26b51  ldstr    aOpportunitycom_0// "opportunitycompetitors_association"
0x26b56  ldstr    aOpportunitycom// "opportunitycompetitors"
0x26b5b  ldstr    aNavpanequeryap// "NavPaneQueryApi"
0x26b60  ldstr    aCrmopportunity// "crmopportunity.retrievebyobject"
0x26b65  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntityRelationshipRole(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entityRelationshipName, string entityName, string propertyName, string value)
0x26b6a  ldarg.0
0x26b6b  ldstr    aOpportunitycom_0// "opportunitycompetitors_association"
0x26b70  ldstr    aOpportunitycom// "opportunitycompetitors"
0x26b75  ldstr    aNavpaneviewid// "NavPaneViewId"
0x26b7a  ldstr    a00000000000000_4// "00000000-0000-0000-00aa-000010001203"
0x26b7f  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntityRelationshipRole(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entityRelationshipName, string entityName, string propertyName, string value)
  ... truncated ...
```
