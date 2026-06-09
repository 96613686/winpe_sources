# Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::.cctor

- ea: `0x22710`
- end: `0x2283d`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::.cctor`
- size: `301`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## string_xrefs

- `0x2272e`: `ExchangeWebLink`
- `0x22742`: `DeliveryLastAttemptedOn`
- `0x22756`: `Community`
- `0x2277e`: `<Type>datetime</Type><Name>deliverylastattemptedon</Name><LogicalName>deliverylastattemptedon</LogicalName><RequiredLevel>none</RequiredLevel><DisplayMask>ValidForAdvancedFind|ValidForForm|ValidForGrid</DisplayMask><ImeMode>inactive</ImeMode><ValidForReadApi>1</ValidForReadApi><IsCustomField>0</IsCustomField><IsAuditEnabled>1</IsAuditEnabled><IsSecured>0</IsSecured><IntroducedVersion>6.0.0.0</IntroducedVersion><IsCustomizable>1</IsCustomizable><IsRenameable>1</IsRenameable><CanModifySearchSettin`
- `0x22788`: `<Type>picklist</Type><Name>deliveryprioritycode</Name><LogicalName>deliveryprioritycode</LogicalName><RequiredLevel>none</RequiredLevel><DisplayMask>ValidForAdvancedFind|ValidForForm|ValidForGrid</DisplayMask><ImeMode>auto</ImeMode><ValidForReadApi>1</ValidForReadApi><ValidForCreateApi>1</ValidForCreateApi><IsCustomField>0</IsCustomField><IsAuditEnabled>1</IsAuditEnabled><IsSecured>0</IsSecured><IntroducedVersion>6.0.0.0</IntroducedVersion><IsCustomizable>1</IsCustomizable><IsRenameable>1</IsRen`
- `0x22792`: `<Type>picklist</Type><Name>community</Name><LogicalName>community</LogicalName><RequiredLevel>none</RequiredLevel><DisplayMask>ValidForAdvancedFind|ValidForGrid</DisplayMask><ImeMode>auto</ImeMode><ValidForUpdateApi>1</ValidForUpdateApi><ValidForReadApi>1</ValidForReadApi><ValidForCreateApi>1</ValidForCreateApi><IsCustomField>0</IsCustomField><IsAuditEnabled>1</IsAuditEnabled><IsSecured>0</IsSecured><IntroducedVersion>6.1.0.0</IntroducedVersion><IsCustomizable>1</IsCustomizable><IsRenameable>1</`
- `0x2279c`: `<Type>datetime</Type><Name>postponeactivityprocessinguntil</Name><LogicalName>postponeactivityprocessinguntil</LogicalName><RequiredLevel>none</RequiredLevel><ImeMode>inactive</ImeMode><ValidForReadApi>1</ValidForReadApi><IsCustomField>0</IsCustomField><IsAuditEnabled>1</IsAuditEnabled><IsSecured>0</IsSecured><IntroducedVersion>6.0.0.0</IntroducedVersion><IsCustomizable>1</IsCustomizable><IsRenameable>1</IsRenameable><CanModifySearchSettings>1</CanModifySearchSettings><CanModifyRequirementLevelS`
- `0x227a6`: `<Type>datetime</Type><Name>senton</Name><LogicalName>senton</LogicalName><RequiredLevel>none</RequiredLevel><DisplayMask>ValidForAdvancedFind|ValidForForm|ValidForGrid</DisplayMask><ImeMode>inactive</ImeMode><ValidForReadApi>1</ValidForReadApi><IsCustomField>0</IsCustomField><IsAuditEnabled>1</IsAuditEnabled><IsSecured>0</IsSecured><IntroducedVersion>6.0.0.0</IntroducedVersion><IsCustomizable>1</IsCustomizable><IsRenameable>1</IsRenameable><CanModifySearchSettings>1</CanModifySearchSettings><Can`
- `0x227b0`: `<Type>ntext</Type><Name>activityadditionalparams</Name><LogicalName>activityadditionalparams</LogicalName><RequiredLevel>none</RequiredLevel><DisplayMask>ValidForAdvancedFind|ValidForForm|ValidForGrid</DisplayMask><ImeMode>auto</ImeMode><ValidForUpdateApi>1</ValidForUpdateApi><ValidForReadApi>1</ValidForReadApi><ValidForCreateApi>1</ValidForCreateApi><IsCustomField>0</IsCustomField><IsAuditEnabled>0</IsAuditEnabled><IsSecured>0</IsSecured><IntroducedVersion>7.1.0.0</IntroducedVersion><IsCustomiz`

## pseudocode

```c

```

## disassembly

```asm
0x22710  ldstr    aLeftvoicemail// "LeftVoiceMail"
0x22715  stsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::missingAttributeLeftVoiceMail
0x2271a  ldstr    aIsmapiprivate// "IsMapiPrivate"
0x2271f  stsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::missingAttributeIsMapiPrivate
0x22724  ldstr    aExchangeitemid// "ExchangeItemId"
0x22729  stsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::missingAttributeExchangeItemId
0x2272e  ldstr    aExchangeweblin// "ExchangeWebLink"
0x22733  stsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::missingAttributeExchangeWebLink
0x22738  ldstr    aSortdate// "SortDate"
0x2273d  stsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::missingAttributeSortDate
0x22742  ldstr    aDeliverylastat// "DeliveryLastAttemptedOn"
0x22747  stsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::missingAttributeDeliveryLastAttemptedOn
0x2274c  ldstr    aDeliverypriori// "DeliveryPriorityCode"
0x22751  stsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::missingAttributeDeliveryPriorityCode
0x22756  ldstr    aCommunity// "Community"
0x2275b  stsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::missingAttributeCommunity
0x22760  ldstr    aPostponeactivi// "PostponeActivityProcessingUntil"
0x22765  stsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::missingAttributePostponeActivityProcessingUntil
0x2276a  ldstr    aSenton// "SentOn"
0x2276f  stsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::missingAttributeSentOn
0x22774  ldstr    aActivityadditi// "ActivityAdditionalParams"
0x22779  stsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::missingAttributeActivityAdditionalParams
0x2277e  ldstr    aTypeDatetimeTy// "<Type>datetime</Type><Name>deliverylast"...
0x22783  stsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::deliveryLastAttemptedOnXml
0x22788  ldstr    aTypePicklistTy// "<Type>picklist</Type><Name>deliveryprio"...
0x2278d  stsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::deliveryPriorityCodeXml
0x22792  ldstr    aTypePicklistTy_0// "<Type>picklist</Type><Name>community</N"...
0x22797  stsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::communityXml
0x2279c  ldstr    aTypeDatetimeTy_0// "<Type>datetime</Type><Name>postponeacti"...
0x227a1  stsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::postponeActivityProcessingUntilXml
0x227a6  ldstr    aTypeDatetimeTy_1// "<Type>datetime</Type><Name>senton</Name"...
0x227ab  stsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::sentOnXml
0x227b0  ldstr    aTypeNtextTypeN// "<Type>ntext</Type><Name>activityadditio"...
0x227b5  stsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::activityAdditionalParamsXml
0x227ba  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x227bf  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::attributeNameToAttributeXml
0x227c4  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::attributeNameToAttributeXml
0x227c9  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::missingAttributeDeliveryLastAttemptedOn
0x227ce  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::deliveryLastAttemptedOnXml
0x227d3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x227d8  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::attributeNameToAttributeXml
0x227dd  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::missingAttributeDeliveryPriorityCode
0x227e2  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::deliveryPriorityCodeXml
0x227e7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x227ec  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::attributeNameToAttributeXml
0x227f1  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::missingAttributeCommunity
0x227f6  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::communityXml
0x227fb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x22800  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::attributeNameToAttributeXml
0x22805  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::missingAttributePostponeActivityProcessingUntil
0x2280a  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::postponeActivityProcessingUntilXml
0x2280f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x22814  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::attributeNameToAttributeXml
0x22819  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::missingAttributeSentOn
0x2281e  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::sentOnXml
0x22823  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x22828  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::attributeNameToAttributeXml
0x2282d  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::missingAttributeActivityAdditionalParams
0x22832  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::activityAdditionalParamsXml
0x22837  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x2283c  ret
```
