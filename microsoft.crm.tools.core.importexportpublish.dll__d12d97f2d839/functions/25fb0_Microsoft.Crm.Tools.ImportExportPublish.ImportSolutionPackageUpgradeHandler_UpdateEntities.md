# Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdateEntities

- ea: `0x25fb0`
- end: `0x261b1`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdateEntities`
- size: `513`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x25f70`

## callees

- `0x27080`

## string_xrefs

- `0x26149`: `IsQuickCreateEnabled`
- `0x26061`: `CanModifyMobileClientReadOnly`
- `0x26019`: `CanCreateViews`
- `0x260d8`: `contracttemplate`
- `0x260f8`: `service`
- `0x26119`: `IsAIRUpdated`

## pseudocode

```c

```

## disassembly

```asm
0x25fb0  ldc.i4.8
0x25fb1  newarr   [mscorlib]System.String
0x25fb6  dup
0x25fb7  ldc.i4.0
0x25fb8  ldstr    aBulkoperationl// "BulkOperationLog"
0x25fbd  stelem.ref
0x25fbe  dup
0x25fbf  ldc.i4.1
0x25fc0  ldstr    aContractdetail// "ContractDetail"
0x25fc5  stelem.ref
0x25fc6  dup
0x25fc7  ldc.i4.2
0x25fc8  ldstr    aEntitlementcha// "EntitlementChannel"
0x25fcd  stelem.ref
0x25fce  dup
0x25fcf  ldc.i4.3
0x25fd0  ldstr    aInvoicedetail// "InvoiceDetail"
0x25fd5  stelem.ref
0x25fd6  dup
0x25fd7  ldc.i4.4
0x25fd8  ldstr    aKnowledgeartic_0// "KnowledgeArticleIncident"
0x25fdd  stelem.ref
0x25fde  dup
0x25fdf  ldc.i4.5
0x25fe0  ldstr    aOpportunitypro_0// "OpportunityProduct"
0x25fe5  stelem.ref
0x25fe6  dup
0x25fe7  ldc.i4.6
0x25fe8  ldstr    aQuotedetail// "QuoteDetail"
0x25fed  stelem.ref
0x25fee  dup
0x25fef  ldc.i4.7
0x25ff0  ldstr    aSalesorderdeta// "SalesOrderDetail"
0x25ff5  stelem.ref
0x25ff6  stloc.0
0x25ff7  ldarg.0
0x25ff8  ldloc.0
0x25ff9  ldstr    aOwnershiptypem// "OwnershipTypeMask"
0x25ffe  ldstr    a1// "1"
0x26003  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntities(class [System.Xml]System.Xml.XmlDocument customizationDoc, string[] entityNames, string propertyName, string value)
0x26008  ldc.i4.1
0x26009  newarr   [mscorlib]System.String
0x2600e  dup
0x2600f  ldc.i4.0
0x26010  ldstr    aProductpricele_0// "productpricelevel"
0x26015  stelem.ref
0x26016  stloc.0
0x26017  ldarg.0
0x26018  ldloc.0
0x26019  ldstr    aCancreateviews// "CanCreateViews"
0x2601e  ldstr    a1// "1"
0x26023  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntities(class [System.Xml]System.Xml.XmlDocument customizationDoc, string[] entityNames, string propertyName, string value)
0x26028  ldc.i4.6
0x26029  newarr   [mscorlib]System.String
0x2602e  dup
0x2602f  ldc.i4.0
0x26030  ldstr    aPricelevel_0// "pricelevel"
0x26035  stelem.ref
0x26036  dup
0x26037  ldc.i4.1
0x26038  ldstr    aProduct// "product"
0x2603d  stelem.ref
0x2603e  dup
0x2603f  ldc.i4.2
0x26040  ldstr    aProductpricele_0// "productpricelevel"
0x26045  stelem.ref
0x26046  dup
0x26047  ldc.i4.3
0x26048  ldstr    aTerritory// "territory"
0x2604d  stelem.ref
0x2604e  dup
0x2604f  ldc.i4.4
0x26050  ldstr    aUom// "uom"
0x26055  stelem.ref
0x26056  dup
0x26057  ldc.i4.5
0x26058  ldstr    aUomschedule// "uomschedule"
0x2605d  stelem.ref
0x2605e  stloc.0
0x2605f  ldarg.0
0x26060  ldloc.0
0x26061  ldstr    aCanmodifymobil_3// "CanModifyMobileClientReadOnly"
0x26066  ldstr    a1// "1"
0x2606b  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntities(class [System.Xml]System.Xml.XmlDocument customizationDoc, string[] entityNames, string propertyName, string value)
0x26070  ldc.i4.1
0x26071  newarr   [mscorlib]System.String
0x26076  dup
0x26077  ldc.i4.0
0x26078  ldstr    aDynamicpropert// "dynamicproperty"
0x2607d  stelem.ref
0x2607e  stloc.0
0x2607f  ldarg.0
0x26080  ldloc.0
0x26081  ldstr    aCanmodifymobil_1// "CanModifyMobileClientVisibility"
0x26086  ldstr    a0_1// "0"
0x2608b  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntities(class [System.Xml]System.Xml.XmlDocument customizationDoc, string[] entityNames, string propertyName, string value)
0x26090  ldc.i4.5
0x26091  newarr   [mscorlib]System.String
0x26096  dup
0x26097  ldc.i4.0
0x26098  ldstr    aPricelevel_0// "pricelevel"
0x2609d  stelem.ref
0x2609e  dup
0x2609f  ldc.i4.1
0x260a0  ldstr    aProductpricele_0// "productpricelevel"
0x260a5  stelem.ref
0x260a6  dup
0x260a7  ldc.i4.2
0x260a8  ldstr    aTerritory// "territory"
0x260ad  stelem.ref
0x260ae  dup
0x260af  ldc.i4.3
0x260b0  ldstr    aUom// "uom"
0x260b5  stelem.ref
0x260b6  dup
0x260b7  ldc.i4.4
0x260b8  ldstr    aUomschedule// "uomschedule"
0x260bd  stelem.ref
0x260be  stloc.0
0x260bf  ldarg.0
0x260c0  ldloc.0
0x260c1  ldstr    aCanmodifymobil_1// "CanModifyMobileClientVisibility"
0x260c6  ldstr    a1// "1"
0x260cb  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntities(class [System.Xml]System.Xml.XmlDocument customizationDoc, string[] entityNames, string propertyName, string value)
0x260d0  ldc.i4.8
0x260d1  newarr   [mscorlib]System.String
0x260d6  dup
0x260d7  ldc.i4.0
0x260d8  ldstr    aContracttempla_3// "contracttemplate"
0x260dd  stelem.ref
0x260de  dup
0x260df  ldc.i4.1
0x260e0  ldstr    aEquipment_0// "equipment"
0x260e5  stelem.ref
0x260e6  dup
0x260e7  ldc.i4.2
0x260e8  ldstr    aIncidentresolu// "incidentresolution"
0x260ed  stelem.ref
0x260ee  dup
0x260ef  ldc.i4.3
0x260f0  ldstr    aResource// "resource"
0x260f5  stelem.ref
0x260f6  dup
0x260f7  ldc.i4.4
0x260f8  ldstr    aService_0// "service"
0x260fd  stelem.ref
0x260fe  dup
0x260ff  ldc.i4.5
0x26100  ldstr    aSite// "site"
0x26105  stelem.ref
0x26106  dup
0x26107  ldc.i4.6
0x26108  ldstr    aUom// "uom"
0x2610d  stelem.ref
0x2610e  dup
0x2610f  ldc.i4.7
0x26110  ldstr    aUomschedule// "uomschedule"
0x26115  stelem.ref
0x26116  stloc.0
0x26117  ldarg.0
0x26118  ldloc.0
0x26119  ldstr    aIsairupdated// "IsAIRUpdated"
0x2611e  ldstr    a1// "1"
0x26123  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntities(class [System.Xml]System.Xml.XmlDocument customizationDoc, string[] entityNames, string propertyName, string value)
0x26128  ldc.i4.3
0x26129  newarr   [mscorlib]System.String
0x2612e  dup
0x2612f  ldc.i4.0
0x26130  ldstr    aInvoicedetail_0// "invoicedetail"
0x26135  stelem.ref
0x26136  dup
0x26137  ldc.i4.1
0x26138  ldstr    aQuotedetail_0// "quotedetail"
0x2613d  stelem.ref
0x2613e  dup
0x2613f  ldc.i4.2
0x26140  ldstr    aSalesorderdeta_0// "salesorderdetail"
0x26145  stelem.ref
0x26146  stloc.0
0x26147  ldarg.0
0x26148  ldloc.0
0x26149  ldstr    aIsquickcreatee// "IsQuickCreateEnabled"
0x2614e  ldstr    a1// "1"
0x26153  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntities(class [System.Xml]System.Xml.XmlDocument customizationDoc, string[] entityNames, string propertyName, string value)
0x26158  ldc.i4.4
0x26159  newarr   [mscorlib]System.String
0x2615e  dup
0x2615f  ldc.i4.0
0x26160  ldstr    aUom// "uom"
0x26165  stelem.ref
0x26166  dup
0x26167  ldc.i4.1
0x26168  ldstr    aUomschedule// "uomschedule"
0x2616d  stelem.ref
0x2616e  dup
0x2616f  ldc.i4.2
0x26170  ldstr    aWorkflow_1// "workflow"
0x26175  stelem.ref
0x26176  dup
0x26177  ldc.i4.3
0x26178  ldstr    aSavedquery_1// "savedquery"
0x2617d  stelem.ref
0x2617e  stloc.0
0x2617f  ldarg.0
0x26180  ldloc.0
0x26181  ldstr    aIsvisibleinmob_1// "IsVisibleInMobileClient"
0x26186  ldstr    a1// "1"
0x2618b  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntities(class [System.Xml]System.Xml.XmlDocument customizationDoc, string[] entityNames, string propertyName, string value)
0x26190  ldc.i4.1
0x26191  newarr   [mscorlib]System.String
0x26196  dup
0x26197  ldc.i4.0
0x26198  ldstr    aResourcegroupe// "ResourceGroupExpansion"
0x2619d  stelem.ref
0x2619e  stloc.0
0x2619f  ldarg.0
0x261a0  ldloc.0
0x261a1  ldstr    aIsaudited// "IsAudited"
0x261a6  ldstr    a0_1// "0"
0x261ab  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntities(class [System.Xml]System.Xml.XmlDocument customizationDoc, string[] entityNames, string propertyName, string value)
0x261b0  ret
```
