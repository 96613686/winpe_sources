# Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::.cctor

- ea: `0xe730`
- end: `0xe9ca`
- name: `Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::.cctor`
- size: `666`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0xe730`: `'activitytypecode','activityadditionalparams','actualdurationminutes','actualend','actualstart','deliverylastattemptedon',\n										'deliveryprioritycode','description','exchangeitemid','exchangeweblink','community','instancetypecode','isbilled','ismapiprivate','isregularactivity',\n										'isworkflowcreated','leftvoicemail','postponeactivityprocessinguntil','prioritycode','regardingobjectid','scheduleddurationminutes','scheduledend',\n										'scheduledstart','sendermailboxid','senton`
- `0xe76e`: `'none_bulkoperation_instancetypecode','none_bulkoperation_ismapiprivate','none_bulkoperation_leftvoicemail','none_bulkoperation_prioritycode'\n										,'none_campaignactivity_instancetypecode','none_campaignactivity_ismapiprivate','none_campaignactivity_leftvoicemail','none_campaignresponse_instancetypecode'\n										,'none_campaignresponse_ismapiprivate','none_campaignresponse_leftvoicemail','none_incidentresolution_instancetypecode','none_incidentresolution_ismapiprivate'\n										,'n`
- `0xe7ac`: `'mobileofflineenabledentities','template_templatetypecode','activitypointer_activitytypecode','mailmergetemplate_templatetypecode','sla_slaenabledentities'`
- `0xe827`: `competitor`
- `0xe832`: `competitoraddress`
- `0xe83d`: `competitorproduct`
- `0xe87f`: `entitlementtemplateproducts`
- `0xe8ab`: `leadcompetitors`
- `0xe8e2`: `opportunitycompetitors`
- `0xe950`: `serviceactivity`
- `0xe97c`: `serviceappointment`
- `0xe98b`: `'commitment_statuscode', 'lead_isautocreate', 'lead_isprivate', 'opportunity_isprivate'`

## pseudocode

```c

```

## disassembly

```asm
0xe730  ldstr    aActivitytypeco// "'activitytypecode','activityadditionalp"...
0xe735  stsfld   string Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::AcitivityPointerAttributesForSql
0xe73a  ldsfld   string Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::AcitivityPointerAttributesForSql
0xe73f  ldc.i4.1
0xe740  newarr   [mscorlib]System.Char
0xe745  dup
0xe746  ldc.i4.0
0xe747  ldc.i4.s 0x2C
0xe749  stelem.i2
0xe74a  callvirt instance string[] [mscorlib]System.String::Split(char[])
0xe74f  ldsfld   class <>c <>c::<>9
0xe754  ldftn    instance string <>c::<.cctor>b__121_0(string op)
0xe75a  newobj   instance void class [mscorlib]System.Func`2<string, string>::.ctor(object, native int)
0xe75f  call     T0x2B00000D
0xe764  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0xe769  stsfld   class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::AcitivityPointerAttributes
0xe76e  ldstr    aNoneBulkoperat// "'none_bulkoperation_instancetypecode','"...
0xe773  stsfld   string Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::ActivityPointerOptionSetNamesForSql
0xe778  ldsfld   string Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::ActivityPointerOptionSetNamesForSql
0xe77d  ldc.i4.1
0xe77e  newarr   [mscorlib]System.Char
0xe783  dup
0xe784  ldc.i4.0
0xe785  ldc.i4.s 0x2C
0xe787  stelem.i2
0xe788  callvirt instance string[] [mscorlib]System.String::Split(char[])
0xe78d  ldsfld   class <>c <>c::<>9
0xe792  ldftn    instance string <>c::<.cctor>b__121_1(string op)
0xe798  newobj   instance void class [mscorlib]System.Func`2<string, string>::.ctor(object, native int)
0xe79d  call     T0x2B00000D
0xe7a2  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0xe7a7  stsfld   class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::ActivityPointerOptionSetNames
0xe7ac  ldstr    aMobileofflinee// "'mobileofflineenabledentities','templat"...
0xe7b1  stsfld   string Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::AutoCreatedEntityOTCOptionSetNamesForSql
0xe7b6  ldsfld   string Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::AutoCreatedEntityOTCOptionSetNamesForSql
0xe7bb  ldc.i4.1
0xe7bc  newarr   [mscorlib]System.Char
0xe7c1  dup
0xe7c2  ldc.i4.0
0xe7c3  ldc.i4.s 0x2C
0xe7c5  stelem.i2
0xe7c6  callvirt instance string[] [mscorlib]System.String::Split(char[])
0xe7cb  ldsfld   class <>c <>c::<>9
0xe7d0  ldftn    instance string <>c::<.cctor>b__121_2(string op)
0xe7d6  newobj   instance void class [mscorlib]System.Func`2<string, string>::.ctor(object, native int)
0xe7db  call     T0x2B00000D
0xe7e0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0xe7e5  stsfld   class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::AutoCreatedEntityOTCOptionSetNames
0xe7ea  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0xe7ef  dup
0xe7f0  ldstr    aAccountleads// "accountleads"
0xe7f5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xe7fa  dup
0xe7fb  ldstr    aCampaignactivi// "campaignactivity"
0xe800  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xe805  dup
0xe806  ldstr    aCampaignrespon// "campaignresponse"
0xe80b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xe810  dup
0xe811  ldstr    aIncident// "incident"
0xe816  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xe81b  dup
0xe81c  ldstr    aCaseresolution// "caseresolution"
0xe821  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xe826  dup
0xe827  ldstr    aCompetitor// "competitor"
0xe82c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xe831  dup
0xe832  ldstr    aCompetitoraddr// "competitoraddress"
0xe837  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xe83c  dup
0xe83d  ldstr    aCompetitorprod// "competitorproduct"
0xe842  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xe847  dup
0xe848  ldstr    aContactleads// "contactleads"
0xe84d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xe852  dup
0xe853  ldstr    aContract// "contract"
0xe858  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xe85d  dup
0xe85e  ldstr    aEntitlement// "entitlement"
0xe863  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xe868  dup
0xe869  ldstr    aEntitlementcon// "entitlementcontacts"
0xe86e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xe873  dup
0xe874  ldstr    aEntitlementpro// "entitlementproducts"
0xe879  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xe87e  dup
0xe87f  ldstr    aEntitlementtem// "entitlementtemplateproducts"
0xe884  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xe889  dup
0xe88a  ldstr    aIncidentknowle// "incidentknowledgebaserecord"
0xe88f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xe894  dup
0xe895  ldstr    aInvoice// "invoice"
0xe89a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xe89f  dup
0xe8a0  ldstr    aLead// "lead"
0xe8a5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xe8aa  dup
0xe8ab  ldstr    aLeadcompetitor// "leadcompetitors"
0xe8b0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xe8b5  dup
0xe8b6  ldstr    aLeadproduct// "leadproduct"
0xe8bb  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xe8c0  dup
0xe8c1  ldstr    aLeadtoopportun// "leadtoopportunitysalesprocess"
0xe8c6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xe8cb  dup
0xe8cc  ldstr    aOpportunity// "opportunity"
0xe8d1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xe8d6  dup
0xe8d7  ldstr    aOpportunityclo// "opportunityclose"
0xe8dc  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xe8e1  dup
0xe8e2  ldstr    aOpportunitycom// "opportunitycompetitors"
0xe8e7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xe8ec  dup
0xe8ed  ldstr    aOpportunitypro// "opportunityproduct"
0xe8f2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xe8f7  dup
0xe8f8  ldstr    aOpportunitysal// "opportunitysalesprocess"
0xe8fd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xe902  dup
0xe903  ldstr    aOrder// "order"
0xe908  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xe90d  dup
0xe90e  ldstr    aOrderclose// "orderclose"
0xe913  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xe918  dup
0xe919  ldstr    aPhonetocasepro// "phonetocaseprocess"
0xe91e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xe923  dup
0xe924  ldstr    aProduct// "product"
0xe929  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xe92e  dup
0xe92f  ldstr    aQuickcampaign// "quickcampaign"
0xe934  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xe939  dup
0xe93a  ldstr    aQuote// "quote"
0xe93f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xe944  dup
0xe945  ldstr    aQuoteclose// "quoteclose"
0xe94a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xe94f  dup
0xe950  ldstr    aServiceactivit// "serviceactivity"
0xe955  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xe95a  dup
0xe95b  ldstr    aIncidentresolu// "incidentresolution"
0xe960  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xe965  dup
0xe966  ldstr    aSalesorder// "salesorder"
0xe96b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xe970  dup
0xe971  ldstr    aBulkoperation// "bulkoperation"
0xe976  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xe97b  dup
0xe97c  ldstr    aServiceappoint// "serviceappointment"
0xe981  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xe986  stsfld   class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::AttributePicklistValueEntityNames
0xe98b  ldstr    aCommitmentStat// "'commitment_statuscode', 'lead_isautocr"...
0xe990  stsfld   string Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::AutoCreatedOptionSetNamesForSql
0xe995  ldsfld   string Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::AutoCreatedOptionSetNamesForSql
0xe99a  ldc.i4.1
0xe99b  newarr   [mscorlib]System.Char
0xe9a0  dup
0xe9a1  ldc.i4.0
0xe9a2  ldc.i4.s 0x2C
0xe9a4  stelem.i2
0xe9a5  callvirt instance string[] [mscorlib]System.String::Split(char[])
0xe9aa  ldsfld   class <>c <>c::<>9
0xe9af  ldftn    instance string <>c::<.cctor>b__121_3(string op)
0xe9b5  newobj   instance void class [mscorlib]System.Func`2<string, string>::.ctor(object, native int)
0xe9ba  call     T0x2B00000D
0xe9bf  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0xe9c4  stsfld   class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::AutoCreatedOptionSetNames
0xe9c9  ret
```
