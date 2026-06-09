# Microsoft.Crm.Metadata.AttributeRenameMapper::.cctor

- ea: `0x19e10`
- end: `0x1a1d0`
- name: `Microsoft.Crm.Metadata.AttributeRenameMapper::.cctor`
- size: `960`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, service_task, broker_com_uri`

## string_xrefs

- `0x19e4b`: `amount_Base`
- `0x19e50`: `Amount_Base`
- `0x19e5b`: `baseamount_Base`
- `0x19e60`: `BaseAmount_Base`
- `0x19e6b`: `budgetamount_Base`
- `0x19e70`: `BudgetAmount_Base`
- `0x19ebb`: `discountamount_Base`
- `0x19ec0`: `DiscountAmount_Base`
- `0x19ecb`: `estimatedamount_Base`
- `0x19ed0`: `EstimatedAmount_Base`
- `0x19efb`: `extendedamount_Base`
- `0x19f00`: `ExtendedAmount_Base`
- `0x19f0b`: `freightamount_Base`
- `0x19f10`: `FreightAmount_Base`
- `0x19f1b`: `manualdiscountamount_Base`
- `0x19f20`: `ManualDiscountAmount_Base`
- `0x19fab`: `roundingoptionamount_Base`
- `0x19fb0`: `RoundingOptionAmount_Base`
- `0x19feb`: `totalamount_Base`
- `0x19ff0`: `TotalAmount_Base`
- `0x19ffb`: `totalamountlessfreight_Base`
- `0x1a000`: `TotalAmountLessFreight_Base`
- `0x1a02b`: `totaldiscountamount_Base`
- `0x1a030`: `TotalDiscountAmount_Base`
- `0x1a03b`: `totallineitemamount_Base`
- `0x1a040`: `TotalLineItemAmount_Base`
- `0x1a04b`: `totallineitemdiscountamount_Base`
- `0x1a050`: `TotalLineItemDiscountAmount_Base`
- `0x1a07b`: `volumediscountamount_Base`
- `0x1a080`: `VolumeDiscountAmount_Base`
- `0x1a08b`: `accountleadsid`
- `0x1a09b`: `contactinvoicesid`
- `0x1a0ab`: `contactleadsid`
- `0x1a0bb`: `contactordersid`
- `0x1a0cb`: `contactquotesid`
- `0x1a0db`: `entitlementcontactsid`
- `0x1a0eb`: `entitlementproductsid`
- `0x1a0fb`: `entitlementtemplateproductsid`
- `0x1a100`: `entitlementtemplateproductid`
- `0x1a10b`: `leadcompetitorsid`
- `0x1a110`: `leadcompetitorid`
- `0x1a11b`: `opportunitycompetitorsid`
- `0x1a120`: `opportunitycompetitorid`
- `0x1a12b`: `servicecontractcontactsid`
- `0x1a130`: `servicecontractcontactid`
- `0x1a1bb`: `openrevenue_Base`
- `0x1a1c0`: `OpenRevenue_Base`

## pseudocode

```c

```

## disassembly

```asm
0x19e10  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x19e15  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x19e1a  dup
0x19e1b  ldstr    aActualcostBase// "actualcost_Base"
0x19e20  ldstr    aActualcostBase_0// "ActualCost_Base"
0x19e25  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x19e2a  dup
0x19e2b  ldstr    aActualrevenueB// "actualrevenue_Base"
0x19e30  ldstr    aActualrevenueB_0// "ActualRevenue_Base"
0x19e35  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x19e3a  dup
0x19e3b  ldstr    aActualvalueBas// "actualvalue_Base"
0x19e40  ldstr    aActualvalueBas_0// "ActualValue_Base"
0x19e45  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x19e4a  dup
0x19e4b  ldstr    aAmountBase// "amount_Base"
0x19e50  ldstr    aAmountBase_0// "Amount_Base"
0x19e55  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x19e5a  dup
0x19e5b  ldstr    aBaseamountBase// "baseamount_Base"
0x19e60  ldstr    aBaseamountBase_0// "BaseAmount_Base"
0x19e65  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x19e6a  dup
0x19e6b  ldstr    aBudgetamountBa// "budgetamount_Base"
0x19e70  ldstr    aBudgetamountBa_0// "BudgetAmount_Base"
0x19e75  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x19e7a  dup
0x19e7b  ldstr    aBudgetedcostBa// "budgetedcost_Base"
0x19e80  ldstr    aBudgetedcostBa_0// "BudgetedCost_Base"
0x19e85  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x19e8a  dup
0x19e8b  ldstr    aCostBase// "cost_Base"
0x19e90  ldstr    aCostBase_0// "Cost_Base"
0x19e95  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x19e9a  dup
0x19e9b  ldstr    aCurrentcostBas// "currentcost_Base"
0x19ea0  ldstr    aCurrentcostBas_0// "CurrentCost_Base"
0x19ea5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x19eaa  dup
0x19eab  ldstr    aDiscountBase// "discount_Base"
0x19eb0  ldstr    aDiscountBase_0// "Discount_Base"
0x19eb5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x19eba  dup
0x19ebb  ldstr    aDiscountamount// "discountamount_Base"
0x19ec0  ldstr    aDiscountamount_0// "DiscountAmount_Base"
0x19ec5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x19eca  dup
0x19ecb  ldstr    aEstimatedamoun// "estimatedamount_Base"
0x19ed0  ldstr    aEstimatedamoun_0// "EstimatedAmount_Base"
0x19ed5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x19eda  dup
0x19edb  ldstr    aEstimatedvalue// "estimatedvalue_Base"
0x19ee0  ldstr    aEstimatedvalue_0// "EstimatedValue_Base"
0x19ee5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x19eea  dup
0x19eeb  ldstr    aExpectedrevenu// "expectedrevenue_Base"
0x19ef0  ldstr    aExpectedrevenu_0// "ExpectedRevenue_Base"
0x19ef5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x19efa  dup
0x19efb  ldstr    aExtendedamount// "extendedamount_Base"
0x19f00  ldstr    aExtendedamount_0// "ExtendedAmount_Base"
0x19f05  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x19f0a  dup
0x19f0b  ldstr    aFreightamountB// "freightamount_Base"
0x19f10  ldstr    aFreightamountB_0// "FreightAmount_Base"
0x19f15  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x19f1a  dup
0x19f1b  ldstr    aManualdiscount// "manualdiscountamount_Base"
0x19f20  ldstr    aManualdiscount_0// "ManualDiscountAmount_Base"
0x19f25  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x19f2a  dup
0x19f2b  ldstr    aNetBase// "net_Base"
0x19f30  ldstr    aNetBase_0// "Net_Base"
0x19f35  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x19f3a  dup
0x19f3b  ldstr    aNetpriceBase// "netprice_Base"
0x19f40  ldstr    aNetpriceBase_0// "NetPrice_Base"
0x19f45  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x19f4a  dup
0x19f4b  ldstr    aOthercostBase// "othercost_Base"
0x19f50  ldstr    aOthercostBase_0// "OtherCost_Base"
0x19f55  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x19f5a  dup
0x19f5b  ldstr    aPriceBase// "price_Base"
0x19f60  ldstr    aPriceBase_0// "Price_Base"
0x19f65  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x19f6a  dup
0x19f6b  ldstr    aPriceperunitBa// "priceperunit_Base"
0x19f70  ldstr    aPriceperunitBa_0// "PricePerUnit_Base"
0x19f75  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x19f7a  dup
0x19f7b  ldstr    aRateBase// "rate_Base"
0x19f80  ldstr    aRateBase_0// "Rate_Base"
0x19f85  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x19f8a  dup
0x19f8b  ldstr    aReportedrevenu// "reportedrevenue_Base"
0x19f90  ldstr    aReportedrevenu_0// "ReportedRevenue_Base"
0x19f95  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x19f9a  dup
0x19f9b  ldstr    aRevenueBase// "revenue_Base"
0x19fa0  ldstr    aRevenueBase_0// "Revenue_Base"
0x19fa5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x19faa  dup
0x19fab  ldstr    aRoundingoption// "roundingoptionamount_Base"
0x19fb0  ldstr    aRoundingoption_0// "RoundingOptionAmount_Base"
0x19fb5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x19fba  dup
0x19fbb  ldstr    aStandardcostBa// "standardcost_Base"
0x19fc0  ldstr    aStandardcostBa_0// "StandardCost_Base"
0x19fc5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x19fca  dup
0x19fcb  ldstr    aTaxBase// "tax_Base"
0x19fd0  ldstr    aTaxBase_0// "Tax_Base"
0x19fd5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x19fda  dup
0x19fdb  ldstr    aTotalactualcos// "totalactualcost_Base"
0x19fe0  ldstr    aTotalactualcos_0// "TotalActualCost_Base"
0x19fe5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x19fea  dup
0x19feb  ldstr    aTotalamountBas// "totalamount_Base"
0x19ff0  ldstr    aTotalamountBas_0// "TotalAmount_Base"
0x19ff5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x19ffa  dup
0x19ffb  ldstr    aTotalamountles// "totalamountlessfreight_Base"
0x1a000  ldstr    aTotalamountles_0// "TotalAmountLessFreight_Base"
0x1a005  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x1a00a  dup
0x1a00b  ldstr    aTotalcampaigna// "totalcampaignactivityactualcost_Base"
0x1a010  ldstr    aTotalcampaigna_0// "TotalCampaignActivityActualCost_Base"
0x1a015  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x1a01a  dup
0x1a01b  ldstr    aTotaldiscountB// "totaldiscount_Base"
0x1a020  ldstr    aTotaldiscountB_0// "TotalDiscount_Base"
0x1a025  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x1a02a  dup
0x1a02b  ldstr    aTotaldiscounta// "totaldiscountamount_Base"
0x1a030  ldstr    aTotaldiscounta_0// "TotalDiscountAmount_Base"
0x1a035  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x1a03a  dup
0x1a03b  ldstr    aTotallineitema// "totallineitemamount_Base"
0x1a040  ldstr    aTotallineitema_0// "TotalLineItemAmount_Base"
0x1a045  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x1a04a  dup
0x1a04b  ldstr    aTotallineitemd// "totallineitemdiscountamount_Base"
0x1a050  ldstr    aTotallineitemd_0// "TotalLineItemDiscountAmount_Base"
0x1a055  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x1a05a  dup
0x1a05b  ldstr    aTotalpriceBase// "totalprice_Base"
0x1a060  ldstr    aTotalpriceBase_0// "TotalPrice_Base"
0x1a065  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x1a06a  dup
0x1a06b  ldstr    aTotaltaxBase// "totaltax_Base"
0x1a070  ldstr    aTotaltaxBase_0// "TotalTax_Base"
0x1a075  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x1a07a  dup
0x1a07b  ldstr    aVolumediscount// "volumediscountamount_Base"
0x1a080  ldstr    aVolumediscount_0// "VolumeDiscountAmount_Base"
0x1a085  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x1a08a  dup
0x1a08b  ldstr    aAccountleadsid// "accountleadsid"
0x1a090  ldstr    aAccountleadid// "accountleadid"
0x1a095  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x1a09a  dup
0x1a09b  ldstr    aContactinvoice// "contactinvoicesid"
0x1a0a0  ldstr    aContactinvoice_0// "contactinvoiceid"
0x1a0a5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x1a0aa  dup
0x1a0ab  ldstr    aContactleadsid// "contactleadsid"
0x1a0b0  ldstr    aContactleadid// "contactleadid"
0x1a0b5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x1a0ba  dup
0x1a0bb  ldstr    aContactordersi// "contactordersid"
0x1a0c0  ldstr    aContactorderid// "contactorderid"
0x1a0c5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x1a0ca  dup
0x1a0cb  ldstr    aContactquotesi// "contactquotesid"
0x1a0d0  ldstr    aContactquoteid// "contactquoteid"
0x1a0d5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x1a0da  dup
0x1a0db  ldstr    aEntitlementcon// "entitlementcontactsid"
0x1a0e0  ldstr    aEntitlementcon_0// "entitlementcontactid"
0x1a0e5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x1a0ea  dup
0x1a0eb  ldstr    aEntitlementpro// "entitlementproductsid"
0x1a0f0  ldstr    aEntitlementpro_0// "entitlementproductid"
0x1a0f5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x1a0fa  dup
0x1a0fb  ldstr    aEntitlementtem// "entitlementtemplateproductsid"
0x1a100  ldstr    aEntitlementtem_0// "entitlementtemplateproductid"
0x1a105  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x1a10a  dup
0x1a10b  ldstr    aLeadcompetitor// "leadcompetitorsid"
0x1a110  ldstr    aLeadcompetitor_0// "leadcompetitorid"
0x1a115  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x1a11a  dup
0x1a11b  ldstr    aOpportunitycom// "opportunitycompetitorsid"
0x1a120  ldstr    aOpportunitycom_0// "opportunitycompetitorid"
0x1a125  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x1a12a  dup
0x1a12b  ldstr    aServicecontrac// "servicecontractcontactsid"
0x1a130  ldstr    aServicecontrac_0// "servicecontractcontactid"
0x1a135  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x1a13a  dup
0x1a13b  ldstr    aPricelistidnam// "pricelistidname"
0x1a140  ldstr    aPricelistname// "pricelistname"
0x1a145  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x1a14a  dup
0x1a14b  ldstr    aAssociatedprod// "associatedproductname"
0x1a150  ldstr    aAssociatedprod_0// "associatedproductidname"
0x1a155  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x1a15a  dup
0x1a15b  ldstr    aMasteridyomina// "masteridyominame"
0x1a160  ldstr    aMasterleadidyo// "masterleadidyominame"
0x1a165  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x1a16a  dup
0x1a16b  ldstr    aDonotsendonopt// "donotsendonoptoutname"
0x1a170  ldstr    aCheckfordonots// "checkfordonotsendmmonlistmembersname"
0x1a175  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x1a17a  dup
0x1a17b  ldstr    aDonotsendmmnam// "donotsendmmname"
0x1a180  ldstr    aDonotsendmarke// "donotsendmarketingmaterialname"
0x1a185  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x1a18a  dup
0x1a18b  ldstr    aBudgetstatusna// "budgetstatusname"
0x1a190  ldstr    aBudgettypename// "BudgetTypeName"
0x1a195  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x1a19a  dup
0x1a19b  ldstr    aSetproductasso// "setproductassociationsname"
0x1a1a0  ldstr    aIsproductassoc// "isproductassociations"
0x1a1a5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x1a1aa  dup
0x1a1ab  ldstr    aSlaname// "slaname"
0x1a1b0  ldstr    aSlaidname// "slaidname"
0x1a1b5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x1a1ba  dup
0x1a1bb  ldstr    aOpenrevenueBas// "openrevenue_Base"
0x1a1c0  ldstr    aOpenrevenueBas_0// "OpenRevenue_Base"
0x1a1c5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x1a1ca  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Metadata.AttributeRenameMapper::renameAttributeDictionary
0x1a1cf  ret
```
