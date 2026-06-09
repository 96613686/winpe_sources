# Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdateAttributes

- ea: `0x261c0`
- end: `0x265fe`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdateAttributes`
- size: `1086`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x25f70`

## callees

- `0x270a0`

## string_xrefs

- `0x261f0`: `totalamount`
- `0x26319`: `totalamount`
- `0x2637c`: `totalamount`
- `0x263b7`: `createdrecordtypecode`
- `0x263ed`: `ValidForCreateAPI`
- `0x26412`: `ValidForCreateAPI`
- `0x26437`: `ValidForCreateAPI`
- `0x2645c`: `ValidForCreateAPI`
- `0x26481`: `ValidForCreateAPI`
- `0x264a6`: `ValidForCreateAPI`
- `0x264cb`: `ValidForCreateAPI`
- `0x264f0`: `ValidForCreateAPI`
- `0x26535`: `ValidForUpdateAPI`
- `0x2655a`: `ValidForUpdateAPI`
- `0x2657f`: `ValidForUpdateAPI`
- `0x265a4`: `ValidForUpdateAPI`

## pseudocode

```c

```

## disassembly

```asm
0x261c0  ldc.i4.6
0x261c1  newarr   [mscorlib]System.String
0x261c6  dup
0x261c7  ldc.i4.0
0x261c8  ldstr    aCustomerid_0// "customerid"
0x261cd  stelem.ref
0x261ce  dup
0x261cf  ldc.i4.1
0x261d0  ldstr    aDatedelivered// "datedelivered"
0x261d5  stelem.ref
0x261d6  dup
0x261d7  ldc.i4.2
0x261d8  ldstr    aDuedate// "duedate"
0x261dd  stelem.ref
0x261de  dup
0x261df  ldc.i4.3
0x261e0  ldstr    aPaymenttermsco// "paymenttermscode"
0x261e5  stelem.ref
0x261e6  dup
0x261e7  ldc.i4.4
0x261e8  ldstr    aShippingmethod// "shippingmethodcode"
0x261ed  stelem.ref
0x261ee  dup
0x261ef  ldc.i4.5
0x261f0  ldstr    aTotalamount// "totalamount"
0x261f5  stelem.ref
0x261f6  stloc.0
0x261f7  ldarg.0
0x261f8  ldstr    aInvoice// "invoice"
0x261fd  ldloc.0
0x261fe  ldstr    aIssortableenab// "IsSortableEnabled"
0x26203  ldstr    a1// "1"
0x26208  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdateAttributeForEntities(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entity, string[] attrNames, string propertyName, string value)
0x2620d  ldarg.0
0x2620e  ldstr    aInvoice// "invoice"
0x26213  ldloc.0
0x26214  ldstr    aIsglobalfilter_1// "IsglobalfilterEnabled"
0x26219  ldstr    a1// "1"
0x2621e  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdateAttributeForEntities(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entity, string[] attrNames, string propertyName, string value)
0x26223  ldc.i4.4
0x26224  newarr   [mscorlib]System.String
0x26229  dup
0x2622a  ldc.i4.0
0x2622b  ldstr    aIndustrycode// "industrycode"
0x26230  stelem.ref
0x26231  dup
0x26232  ldc.i4.1
0x26233  ldstr    aLeadqualitycod// "leadqualitycode"
0x26238  stelem.ref
0x26239  dup
0x2623a  ldc.i4.2
0x2623b  ldstr    aLeadsourcecode// "leadsourcecode"
0x26240  stelem.ref
0x26241  dup
0x26242  ldc.i4.3
0x26243  ldstr    aPreferredconta// "preferredcontactmethodcode"
0x26248  stelem.ref
0x26249  stloc.0
0x2624a  ldarg.0
0x2624b  ldstr    aLead// "lead"
0x26250  ldloc.0
0x26251  ldstr    aIssortableenab// "IsSortableEnabled"
0x26256  ldstr    a1// "1"
0x2625b  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdateAttributeForEntities(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entity, string[] attrNames, string propertyName, string value)
0x26260  ldarg.0
0x26261  ldstr    aLead// "lead"
0x26266  ldloc.0
0x26267  ldstr    aIsglobalfilter_1// "IsglobalfilterEnabled"
0x2626c  ldstr    a1// "1"
0x26271  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdateAttributeForEntities(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entity, string[] attrNames, string propertyName, string value)
0x26276  ldc.i4.8
0x26277  newarr   [mscorlib]System.String
0x2627c  dup
0x2627d  ldc.i4.0
0x2627e  ldstr    aActualclosedat// "actualclosedate"
0x26283  stelem.ref
0x26284  dup
0x26285  ldc.i4.1
0x26286  ldstr    aActualvalue// "actualvalue"
0x2628b  stelem.ref
0x2628c  dup
0x2628d  ldc.i4.2
0x2628e  ldstr    aBudgetstatus// "budgetstatus"
0x26293  stelem.ref
0x26294  dup
0x26295  ldc.i4.3
0x26296  ldstr    aEstimatedclose// "estimatedclosedate"
0x2629b  stelem.ref
0x2629c  dup
0x2629d  ldc.i4.4
0x2629e  ldstr    aEstimatedvalue// "estimatedvalue"
0x262a3  stelem.ref
0x262a4  dup
0x262a5  ldc.i4.5
0x262a6  ldstr    aParentaccounti// "parentaccountid"
0x262ab  stelem.ref
0x262ac  dup
0x262ad  ldc.i4.6
0x262ae  ldstr    aParentcontacti// "parentcontactid"
0x262b3  stelem.ref
0x262b4  dup
0x262b5  ldc.i4.7
0x262b6  ldstr    aPurchasetimefr// "purchasetimeframe"
0x262bb  stelem.ref
0x262bc  stloc.0
0x262bd  ldarg.0
0x262be  ldstr    aOpportunity// "opportunity"
0x262c3  ldloc.0
0x262c4  ldstr    aIssortableenab// "IsSortableEnabled"
0x262c9  ldstr    a1// "1"
0x262ce  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdateAttributeForEntities(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entity, string[] attrNames, string propertyName, string value)
0x262d3  ldarg.0
0x262d4  ldstr    aOpportunity// "opportunity"
0x262d9  ldloc.0
0x262da  ldstr    aIsglobalfilter_1// "IsglobalfilterEnabled"
0x262df  ldstr    a1// "1"
0x262e4  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdateAttributeForEntities(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entity, string[] attrNames, string propertyName, string value)
0x262e9  ldc.i4.6
0x262ea  newarr   [mscorlib]System.String
0x262ef  dup
0x262f0  ldc.i4.0
0x262f1  ldstr    aCustomerid_0// "customerid"
0x262f6  stelem.ref
0x262f7  dup
0x262f8  ldc.i4.1
0x262f9  ldstr    aEffectivefrom// "effectivefrom"
0x262fe  stelem.ref
0x262ff  dup
0x26300  ldc.i4.2
0x26301  ldstr    aEffectiveto// "effectiveto"
0x26306  stelem.ref
0x26307  dup
0x26308  ldc.i4.3
0x26309  ldstr    aPaymenttermsco// "paymenttermscode"
0x2630e  stelem.ref
0x2630f  dup
0x26310  ldc.i4.4
0x26311  ldstr    aShippingmethod// "shippingmethodcode"
0x26316  stelem.ref
0x26317  dup
0x26318  ldc.i4.5
0x26319  ldstr    aTotalamount// "totalamount"
0x2631e  stelem.ref
0x2631f  stloc.0
0x26320  ldarg.0
0x26321  ldstr    aQuote// "quote"
0x26326  ldloc.0
0x26327  ldstr    aIssortableenab// "IsSortableEnabled"
0x2632c  ldstr    a1// "1"
0x26331  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdateAttributeForEntities(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entity, string[] attrNames, string propertyName, string value)
0x26336  ldarg.0
0x26337  ldstr    aQuote// "quote"
0x2633c  ldloc.0
0x2633d  ldstr    aIsglobalfilter_1// "IsglobalfilterEnabled"
0x26342  ldstr    a1// "1"
0x26347  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdateAttributeForEntities(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entity, string[] attrNames, string propertyName, string value)
0x2634c  ldc.i4.6
0x2634d  newarr   [mscorlib]System.String
0x26352  dup
0x26353  ldc.i4.0
0x26354  ldstr    aCustomerid_0// "customerid"
0x26359  stelem.ref
0x2635a  dup
0x2635b  ldc.i4.1
0x2635c  ldstr    aDatefulfilled// "datefulfilled"
0x26361  stelem.ref
0x26362  dup
0x26363  ldc.i4.2
0x26364  ldstr    aPaymenttermsco// "paymenttermscode"
0x26369  stelem.ref
0x2636a  dup
0x2636b  ldc.i4.3
0x2636c  ldstr    aRequestdeliver// "requestdeliveryby"
0x26371  stelem.ref
0x26372  dup
0x26373  ldc.i4.4
0x26374  ldstr    aShippingmethod// "shippingmethodcode"
0x26379  stelem.ref
0x2637a  dup
0x2637b  ldc.i4.5
0x2637c  ldstr    aTotalamount// "totalamount"
0x26381  stelem.ref
0x26382  stloc.0
0x26383  ldarg.0
0x26384  ldstr    aSalesorder// "salesorder"
0x26389  ldloc.0
0x2638a  ldstr    aIssortableenab// "IsSortableEnabled"
0x2638f  ldstr    a1// "1"
0x26394  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdateAttributeForEntities(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entity, string[] attrNames, string propertyName, string value)
0x26399  ldarg.0
0x2639a  ldstr    aSalesorder// "salesorder"
0x2639f  ldloc.0
0x263a0  ldstr    aIsglobalfilter_1// "IsglobalfilterEnabled"
0x263a5  ldstr    a1// "1"
0x263aa  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdateAttributeForEntities(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entity, string[] attrNames, string propertyName, string value)
0x263af  ldc.i4.6
0x263b0  newarr   [mscorlib]System.String
0x263b5  dup
0x263b6  ldc.i4.0
0x263b7  ldstr    aCreatedrecordt// "createdrecordtypecode"
0x263bc  stelem.ref
0x263bd  dup
0x263be  ldc.i4.1
0x263bf  ldstr    aOperationtypec// "operationtypecode"
0x263c4  stelem.ref
0x263c5  dup
0x263c6  ldc.i4.2
0x263c7  ldstr    aParameters// "parameters"
0x263cc  stelem.ref
0x263cd  dup
0x263ce  ldc.i4.3
0x263cf  ldstr    aSubject// "subject"
0x263d4  stelem.ref
0x263d5  dup
0x263d6  ldc.i4.4
0x263d7  ldstr    aTargetedrecord// "targetedrecordtypecode"
0x263dc  stelem.ref
0x263dd  dup
0x263de  ldc.i4.5
0x263df  ldstr    aTargetmembersc// "targetmemberscount"
0x263e4  stelem.ref
0x263e5  stloc.0
0x263e6  ldarg.0
0x263e7  ldstr    aBulkoperation// "bulkoperation"
0x263ec  ldloc.0
0x263ed  ldstr    aValidforcreate_1// "ValidForCreateAPI"
0x263f2  ldstr    a1// "1"
0x263f7  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdateAttributeForEntities(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entity, string[] attrNames, string propertyName, string value)
0x263fc  ldc.i4.1
0x263fd  newarr   [mscorlib]System.String
0x26402  dup
0x26403  ldc.i4.0
0x26404  ldstr    aTransactioncur// "transactioncurrencyid"
0x26409  stelem.ref
0x2640a  stloc.0
0x2640b  ldarg.0
0x2640c  ldstr    aInvoicedetail_0// "invoicedetail"
0x26411  ldloc.0
0x26412  ldstr    aValidforcreate_1// "ValidForCreateAPI"
0x26417  ldstr    a1// "1"
0x2641c  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdateAttributeForEntities(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entity, string[] attrNames, string propertyName, string value)
0x26421  ldc.i4.1
0x26422  newarr   [mscorlib]System.String
0x26427  dup
0x26428  ldc.i4.0
0x26429  ldstr    aTransactioncur// "transactioncurrencyid"
0x2642e  stelem.ref
0x2642f  stloc.0
0x26430  ldarg.0
0x26431  ldstr    aOpportunitypro// "opportunityproduct"
0x26436  ldloc.0
0x26437  ldstr    aValidforcreate_1// "ValidForCreateAPI"
0x2643c  ldstr    a1// "1"
0x26441  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdateAttributeForEntities(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entity, string[] attrNames, string propertyName, string value)
0x26446  ldc.i4.1
0x26447  newarr   [mscorlib]System.String
0x2644c  dup
0x2644d  ldc.i4.0
0x2644e  ldstr    aStatecode// "statecode"
0x26453  stelem.ref
0x26454  stloc.0
0x26455  ldarg.0
0x26456  ldstr    aProduct// "product"
0x2645b  ldloc.0
0x2645c  ldstr    aValidforcreate_1// "ValidForCreateAPI"
0x26461  ldstr    a1// "1"
0x26466  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdateAttributeForEntities(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entity, string[] attrNames, string propertyName, string value)
0x2646b  ldc.i4.1
0x2646c  newarr   [mscorlib]System.String
0x26471  dup
0x26472  ldc.i4.0
0x26473  ldstr    aTransactioncur// "transactioncurrencyid"
0x26478  stelem.ref
0x26479  stloc.0
0x2647a  ldarg.0
0x2647b  ldstr    aQuotedetail_0// "quotedetail"
0x26480  ldloc.0
0x26481  ldstr    aValidforcreate_1// "ValidForCreateAPI"
0x26486  ldstr    a1// "1"
0x2648b  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdateAttributeForEntities(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entity, string[] attrNames, string propertyName, string value)
0x26490  ldc.i4.1
0x26491  newarr   [mscorlib]System.String
0x26496  dup
0x26497  ldc.i4.0
0x26498  ldstr    aOrganizationid// "organizationid"
0x2649d  stelem.ref
0x2649e  stloc.0
0x2649f  ldarg.0
0x264a0  ldstr    aResource// "resource"
0x264a5  ldloc.0
0x264a6  ldstr    aValidforcreate_1// "ValidForCreateAPI"
0x264ab  ldstr    a1// "1"
0x264b0  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdateAttributeForEntities(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entity, string[] attrNames, string propertyName, string value)
0x264b5  ldc.i4.1
0x264b6  newarr   [mscorlib]System.String
0x264bb  dup
0x264bc  ldc.i4.0
0x264bd  ldstr    aGrouptypecode// "grouptypecode"
0x264c2  stelem.ref
0x264c3  stloc.0
  ... truncated ...
```
