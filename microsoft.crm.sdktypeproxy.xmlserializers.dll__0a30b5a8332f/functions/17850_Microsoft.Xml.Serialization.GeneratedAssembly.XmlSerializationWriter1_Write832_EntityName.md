# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write832_EntityName

- ea: `0x17850`
- end: `0x18098`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write832_EntityName`
- size: `2120`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1940`
- `0x6ac0`
- `0x47040`
- `0x47150`
- `0x5a650`
- `0x5a740`

## callees

- `0x17850`

## string_xrefs

- `0x17b01`: `bulkdeletefailure`
- `0x17b0c`: `bulkdeleteoperation`
- `0x17b2d`: `businesstask`
- `0x17ba6`: `competitor`
- `0x17bdd`: `contracttemplate`
- `0x17cf0`: `isvconfig`
- `0x17d06`: `kbarticlecomment`
- `0x17d11`: `kbarticletemplate`
- `0x17d5e`: `mailmergetemplate`
- `0x17de2`: `pluginassembly`
- `0x17ded`: `plugintype`
- `0x17e03`: `privilege`
- `0x17e9d`: `reportlink`
- `0x17f42`: `sdkmessageprocessingstepsecureconfig`
- `0x17f58`: `service`
- `0x17f63`: `serviceappointment`
- `0x17fc6`: `template`
- `0x18053`: `wizardaccessprivilege`

## pseudocode

```c

```

## disassembly

```asm
0x17850  ldnull
0x17851  stloc.0
0x17852  ldarg.1
0x17853  stloc.1
0x17854  ldloc.1
0x17855  switch   loc_17A93, loc_17A9E, loc_17AA9, loc_17AB4, loc_17ABF, loc_17ACA, loc_17AD5, loc_17AE0, loc_17AEB, loc_17AF6, loc_17B01, loc_17B0C, loc_17B17, loc_17B22, loc_17B2D, loc_17B38, loc_17B43, loc_17B4E, loc_17B59, loc_17B64, loc_17B6F, loc_17B7A, loc_17B85, loc_17B90, loc_17B9B, loc_17BA6, loc_17BB1, loc_17BBC, loc_17BC7, loc_17BD2, loc_17BDD, loc_17BE8, loc_17BF3, loc_17BFE, loc_17C09, loc_17C14, loc_17C1F, loc_17C2A, loc_17C35, loc_17C40, loc_17C4B, loc_17C56, loc_17C61, loc_17C6C, loc_17C77, loc_17C82, loc_17C8D, loc_17C98, loc_17CA3, loc_17CAE, loc_17CB9, loc_17CC4, loc_17CCF, loc_17CDA, loc_17CE5 \
0x17a8e  br       loc_1807B
0x17a93  ldstr    aNone_0// "none"
0x17a98  stloc.0
0x17a99  br       loc_18096
0x17a9e  ldstr    aAccount// "account"
0x17aa3  stloc.0
0x17aa4  br       loc_18096
0x17aa9  ldstr    aActivitymimeat// "activitymimeattachment"
0x17aae  stloc.0
0x17aaf  br       loc_18096
0x17ab4  ldstr    aActivityparty// "activityparty"
0x17ab9  stloc.0
0x17aba  br       loc_18096
0x17abf  ldstr    aActivitypointe// "activitypointer"
0x17ac4  stloc.0
0x17ac5  br       loc_18096
0x17aca  ldstr    aAnnotation// "annotation"
0x17acf  stloc.0
0x17ad0  br       loc_18096
0x17ad5  ldstr    aAnnualfiscalca// "annualfiscalcalendar"
0x17ada  stloc.0
0x17adb  br       loc_18096
0x17ae0  ldstr    aAppointment_0// "appointment"
0x17ae5  stloc.0
0x17ae6  br       loc_18096
0x17aeb  ldstr    aAsyncoperation_0// "asyncoperation"
0x17af0  stloc.0
0x17af1  br       loc_18096
0x17af6  ldstr    aAttributemap// "attributemap"
0x17afb  stloc.0
0x17afc  br       loc_18096
0x17b01  ldstr    aBulkdeletefail// "bulkdeletefailure"
0x17b06  stloc.0
0x17b07  br       loc_18096
0x17b0c  ldstr    aBulkdeleteoper// "bulkdeleteoperation"
0x17b11  stloc.0
0x17b12  br       loc_18096
0x17b17  ldstr    aBulkoperation// "bulkoperation"
0x17b1c  stloc.0
0x17b1d  br       loc_18096
0x17b22  ldstr    aBulkoperationl// "bulkoperationlog"
0x17b27  stloc.0
0x17b28  br       loc_18096
0x17b2d  ldstr    aBusinesstask// "businesstask"
0x17b32  stloc.0
0x17b33  br       loc_18096
0x17b38  ldstr    aBusinessunit// "businessunit"
0x17b3d  stloc.0
0x17b3e  br       loc_18096
0x17b43  ldstr    aBusinessunitne// "businessunitnewsarticle"
0x17b48  stloc.0
0x17b49  br       loc_18096
0x17b4e  ldstr    aCalendar// "calendar"
0x17b53  stloc.0
0x17b54  br       loc_18096
0x17b59  ldstr    aCalendarrule// "calendarrule"
0x17b5e  stloc.0
0x17b5f  br       loc_18096
0x17b64  ldstr    aCampaign// "campaign"
0x17b69  stloc.0
0x17b6a  br       loc_18096
0x17b6f  ldstr    aCampaignactivi_0// "campaignactivity"
0x17b74  stloc.0
0x17b75  br       loc_18096
0x17b7a  ldstr    aCampaignactivi_1// "campaignactivityitem"
0x17b7f  stloc.0
0x17b80  br       loc_18096
0x17b85  ldstr    aCampaignitem// "campaignitem"
0x17b8a  stloc.0
0x17b8b  br       loc_18096
0x17b90  ldstr    aCampaignrespon_0// "campaignresponse"
0x17b95  stloc.0
0x17b96  br       loc_18096
0x17b9b  ldstr    aColumnmapping// "columnmapping"
0x17ba0  stloc.0
0x17ba1  br       loc_18096
0x17ba6  ldstr    aCompetitor// "competitor"
0x17bab  stloc.0
0x17bac  br       loc_18096
0x17bb1  ldstr    aConstraintbase// "constraintbasedgroup"
0x17bb6  stloc.0
0x17bb7  br       loc_18096
0x17bbc  ldstr    aContact// "contact"
0x17bc1  stloc.0
0x17bc2  br       loc_18096
0x17bc7  ldstr    aContract// "contract"
0x17bcc  stloc.0
0x17bcd  br       loc_18096
0x17bd2  ldstr    aContractdetail_0// "contractdetail"
0x17bd7  stloc.0
0x17bd8  br       loc_18096
0x17bdd  ldstr    aContracttempla// "contracttemplate"
0x17be2  stloc.0
0x17be3  br       loc_18096
0x17be8  ldstr    aCustomeraddres// "customeraddress"
0x17bed  stloc.0
0x17bee  br       loc_18096
0x17bf3  ldstr    aCustomeropport// "customeropportunityrole"
0x17bf8  stloc.0
0x17bf9  br       loc_18096
0x17bfe  ldstr    aCustomerrelati// "customerrelationship"
0x17c03  stloc.0
0x17c04  br       loc_18096
0x17c09  ldstr    aDiscount// "discount"
0x17c0e  stloc.0
0x17c0f  br       loc_18096
0x17c14  ldstr    aDiscounttype// "discounttype"
0x17c19  stloc.0
0x17c1a  br       loc_18096
0x17c1f  ldstr    aDisplaystring// "displaystring"
0x17c24  stloc.0
0x17c25  br       loc_18096
0x17c2a  ldstr    aDuplicaterecor// "duplicaterecord"
0x17c2f  stloc.0
0x17c30  br       loc_18096
0x17c35  ldstr    aDuplicaterule// "duplicaterule"
0x17c3a  stloc.0
0x17c3b  br       loc_18096
0x17c40  ldstr    aDuplicaterulec// "duplicaterulecondition"
0x17c45  stloc.0
0x17c46  br       loc_18096
0x17c4b  ldstr    aEmail_0// "email"
0x17c50  stloc.0
0x17c51  br       loc_18096
0x17c56  ldstr    aEntitymap// "entitymap"
0x17c5b  stloc.0
0x17c5c  br       loc_18096
0x17c61  ldstr    aEquipment// "equipment"
0x17c66  stloc.0
0x17c67  br       loc_18096
0x17c6c  ldstr    aFax// "fax"
0x17c71  stloc.0
0x17c72  br       loc_18096
0x17c77  ldstr    aFixedmonthlyfi// "fixedmonthlyfiscalcalendar"
0x17c7c  stloc.0
0x17c7d  br       loc_18096
0x17c82  ldstr    aImport// "import"
0x17c87  stloc.0
0x17c88  br       loc_18096
0x17c8d  ldstr    aImportdata// "importdata"
0x17c92  stloc.0
0x17c93  br       loc_18096
0x17c98  ldstr    aImportfile// "importfile"
0x17c9d  stloc.0
0x17c9e  br       loc_18096
0x17ca3  ldstr    aImportjob// "importjob"
0x17ca8  stloc.0
0x17ca9  br       loc_18096
0x17cae  ldstr    aImportlog// "importlog"
0x17cb3  stloc.0
0x17cb4  br       loc_18096
0x17cb9  ldstr    aImportmap// "importmap"
0x17cbe  stloc.0
0x17cbf  br       loc_18096
0x17cc4  ldstr    aIncident// "incident"
0x17cc9  stloc.0
0x17cca  br       loc_18096
0x17ccf  ldstr    aIncidentresolu_0// "incidentresolution"
0x17cd4  stloc.0
0x17cd5  br       loc_18096
0x17cda  ldstr    aInvoice// "invoice"
0x17cdf  stloc.0
0x17ce0  br       loc_18096
0x17ce5  ldstr    aInvoicedetail// "invoicedetail"
0x17cea  stloc.0
0x17ceb  br       loc_18096
0x17cf0  ldstr    aIsvconfig// "isvconfig"
0x17cf5  stloc.0
0x17cf6  br       loc_18096
0x17cfb  ldstr    aKbarticle// "kbarticle"
0x17d00  stloc.0
0x17d01  br       loc_18096
0x17d06  ldstr    aKbarticlecomme// "kbarticlecomment"
0x17d0b  stloc.0
0x17d0c  br       loc_18096
0x17d11  ldstr    aKbarticletempl// "kbarticletemplate"
0x17d16  stloc.0
0x17d17  br       loc_18096
0x17d1c  ldstr    aLead// "lead"
0x17d21  stloc.0
0x17d22  br       loc_18096
0x17d27  ldstr    aLetter// "letter"
0x17d2c  stloc.0
0x17d2d  br       loc_18096
0x17d32  ldstr    aLicense// "license"
0x17d37  stloc.0
0x17d38  br       loc_18096
0x17d3d  ldstr    aList// "list"
0x17d42  stloc.0
0x17d43  br       loc_18096
0x17d48  ldstr    aListmember// "listmember"
0x17d4d  stloc.0
0x17d4e  br       loc_18096
0x17d53  ldstr    aLookupmapping// "lookupmapping"
0x17d58  stloc.0
0x17d59  br       loc_18096
0x17d5e  ldstr    aMailmergetempl_0// "mailmergetemplate"
0x17d63  stloc.0
0x17d64  br       loc_18096
0x17d69  ldstr    aMonthlyfiscalc// "monthlyfiscalcalendar"
0x17d6e  stloc.0
0x17d6f  br       loc_18096
0x17d74  ldstr    aNotification// "notification"
0x17d79  stloc.0
0x17d7a  br       loc_18096
0x17d7f  ldstr    aOpportunity// "opportunity"
0x17d84  stloc.0
0x17d85  br       loc_18096
0x17d8a  ldstr    aOpportunityclo_0// "opportunityclose"
0x17d8f  stloc.0
0x17d90  br       loc_18096
0x17d95  ldstr    aOpportunitypro// "opportunityproduct"
0x17d9a  stloc.0
0x17d9b  br       loc_18096
0x17da0  ldstr    aOrderclose// "orderclose"
0x17da5  stloc.0
0x17da6  br       loc_18096
0x17dab  ldstr    aOrganization// "organization"
0x17db0  stloc.0
0x17db1  br       loc_18096
0x17db6  ldstr    aOrganizationui// "organizationui"
0x17dbb  stloc.0
0x17dbc  br       loc_18096
0x17dc1  ldstr    aOwnermapping// "ownermapping"
0x17dc6  stloc.0
0x17dc7  br       loc_18096
0x17dcc  ldstr    aPhonecall// "phonecall"
0x17dd1  stloc.0
0x17dd2  br       loc_18096
0x17dd7  ldstr    aPicklistmappin_0// "picklistmapping"
0x17ddc  stloc.0
0x17ddd  br       loc_18096
0x17de2  ldstr    aPluginassembly// "pluginassembly"
0x17de7  stloc.0
0x17de8  br       loc_18096
0x17ded  ldstr    aPlugintype// "plugintype"
0x17df2  stloc.0
0x17df3  br       loc_18096
0x17df8  ldstr    aPricelevel// "pricelevel"
0x17dfd  stloc.0
0x17dfe  br       loc_18096
0x17e03  ldstr    aPrivilege_0// "privilege"
0x17e08  stloc.0
0x17e09  br       loc_18096
0x17e0e  ldstr    aProduct// "product"
0x17e13  stloc.0
0x17e14  br       loc_18096
0x17e19  ldstr    aProductpricele// "productpricelevel"
0x17e1e  stloc.0
0x17e1f  br       loc_18096
0x17e24  ldstr    aQuarterlyfisca// "quarterlyfiscalcalendar"
0x17e29  stloc.0
0x17e2a  br       loc_18096
0x17e2f  ldstr    aQueue// "queue"
0x17e34  stloc.0
0x17e35  br       loc_18096
0x17e3a  ldstr    aQueueitem// "queueitem"
0x17e3f  stloc.0
0x17e40  br       loc_18096
0x17e45  ldstr    aQuote// "quote"
0x17e4a  stloc.0
0x17e4b  br       loc_18096
0x17e50  ldstr    aQuoteclose// "quoteclose"
0x17e55  stloc.0
0x17e56  br       loc_18096
0x17e5b  ldstr    aQuotedetail// "quotedetail"
0x17e60  stloc.0
0x17e61  br       loc_18096
0x17e66  ldstr    aRelationshipro_0// "relationshiprole"
0x17e6b  stloc.0
0x17e6c  br       loc_18096
0x17e71  ldstr    aRelationshipro_1// "relationshiprolemap"
0x17e76  stloc.0
0x17e77  br       loc_18096
0x17e7c  ldstr    aReport// "report"
0x17e81  stloc.0
0x17e82  br       loc_18096
0x17e87  ldstr    aReportcategory// "reportcategory"
0x17e8c  stloc.0
0x17e8d  br       loc_18096
0x17e92  ldstr    aReportentity// "reportentity"
0x17e97  stloc.0
0x17e98  br       loc_18096
0x17e9d  ldstr    aReportlink// "reportlink"
0x17ea2  stloc.0
0x17ea3  br       loc_18096
0x17ea8  ldstr    aReportvisibili// "reportvisibility"
0x17ead  stloc.0
0x17eae  br       loc_18096
0x17eb3  ldstr    aResource// "resource"
0x17eb8  stloc.0
0x17eb9  br       loc_18096
0x17ebe  ldstr    aResourcegroup// "resourcegroup"
0x17ec3  stloc.0
  ... truncated ...
```
