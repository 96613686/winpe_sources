# Microsoft.Crm.CrmLive.Provisioning.SandboxInstanceCopyMassageDataExecutor::GetEntitiesToTruncate

- ea: `0x27720`
- end: `0x28426`
- name: `Microsoft.Crm.CrmLive.Provisioning.SandboxInstanceCopyMassageDataExecutor::GetEntitiesToTruncate`
- size: `3334`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## string_xrefs

- `0x27d36`: `PluginTraceLog`
- `0x277c6`: `AzureServiceConnection`
- `0x277d6`: `BulkDeleteFailure`
- `0x27876`: `Competitor`
- `0x27886`: `ChannelAccessProfile`
- `0x27896`: `CompetitorAddress`
- `0x278a6`: `CompetitorProduct`
- `0x278b6`: `CompetitorSalesLiterature`
- `0x27a56`: `EntitlementTemplate`
- `0x27a66`: `EntitlementTemplateChannel`
- `0x27a76`: `EntitlementTemplateProducts`
- `0x27bd6`: `KbArticleComment`
- `0x27c16`: `LeadCompetitors`
- `0x27cc6`: `OpportunityCompetitors`
- `0x27d26`: `PluginTypeStatistic`
- `0x27d56`: `PostComment`
- `0x27db6`: `PrincipalObjectAccess`
- `0x27dc6`: `PrincipalObjectAttributeAccess`
- `0x27f46`: `SdkMessageProcessingStepSecureConfig`
- `0x27f66`: `Service`
- `0x27f76`: `ServiceAppointment`
- `0x27f86`: `ServiceContractContacts`
- `0x27fe6`: `SocialInsightsConfiguration`
- `0x280f6`: `TopicModelConfiguration`
- `0x28156`: `TopicModelConfiguration`
- `0x28226`: `WizardAccessPrivilege`
- `0x283e6`: `RecommendedDocument`
- `0x28416`: `GlobalSearchConfiguration`

## pseudocode

```c

```

## disassembly

```asm
0x27720  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::.ctor()
0x27725  dup
0x27726  ldstr    aAccount// "Account"
0x2772b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x27730  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x27735  dup
0x27736  ldstr    aAccountleads// "AccountLeads"
0x2773b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x27740  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x27745  dup
0x27746  ldstr    aActivityparty// "ActivityParty"
0x2774b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x27750  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x27755  dup
0x27756  ldstr    aActivitypointe// "ActivityPointer"
0x2775b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x27760  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x27765  dup
0x27766  ldstr    aAdvancedsimila// "AdvancedSimilarityRule"
0x2776b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x27770  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x27775  dup
0x27776  ldstr    aAnnotation// "Annotation"
0x2777b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x27780  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x27785  dup
0x27786  ldstr    aAnnualfiscalca// "AnnualFiscalCalendar"
0x2778b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x27790  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x27795  dup
0x27796  ldstr    aAppointment// "Appointment"
0x2779b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x277a0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x277a5  dup
0x277a6  ldstr    aAttachment// "Attachment"
0x277ab  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x277b0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x277b5  dup
0x277b6  ldstr    aAudit// "Audit"
0x277bb  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x277c0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x277c5  dup
0x277c6  ldstr    aAzureserviceco// "AzureServiceConnection"
0x277cb  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x277d0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x277d5  dup
0x277d6  ldstr    aBulkdeletefail// "BulkDeleteFailure"
0x277db  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x277e0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x277e5  dup
0x277e6  ldstr    aBulkoperation// "BulkOperation"
0x277eb  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x277f0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x277f5  dup
0x277f6  ldstr    aBulkoperationl// "BulkOperationLog"
0x277fb  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x27800  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x27805  dup
0x27806  ldstr    aBusinessproces// "BusinessProcessFlowInstance"
0x2780b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x27810  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x27815  dup
0x27816  ldstr    aBusinessunitne// "BusinessUnitNewsArticle"
0x2781b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x27820  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x27825  dup
0x27826  ldstr    aCampaign// "Campaign"
0x2782b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x27830  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x27835  dup
0x27836  ldstr    aCampaignactivi// "CampaignActivity"
0x2783b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x27840  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x27845  dup
0x27846  ldstr    aCampaignactivi_0// "CampaignActivityItem"
0x2784b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x27850  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x27855  dup
0x27856  ldstr    aCampaignitem// "CampaignItem"
0x2785b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x27860  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x27865  dup
0x27866  ldstr    aCampaignrespon// "CampaignResponse"
0x2786b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x27870  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x27875  dup
0x27876  ldstr    aCompetitor// "Competitor"
0x2787b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x27880  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x27885  dup
0x27886  ldstr    aChannelaccessp// "ChannelAccessProfile"
0x2788b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x27890  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x27895  dup
0x27896  ldstr    aCompetitoraddr// "CompetitorAddress"
0x2789b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x278a0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x278a5  dup
0x278a6  ldstr    aCompetitorprod// "CompetitorProduct"
0x278ab  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x278b0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x278b5  dup
0x278b6  ldstr    aCompetitorsale// "CompetitorSalesLiterature"
0x278bb  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x278c0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x278c5  dup
0x278c6  ldstr    aConnection// "Connection"
0x278cb  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x278d0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x278d5  dup
0x278d6  ldstr    aContact// "Contact"
0x278db  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x278e0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x278e5  dup
0x278e6  ldstr    aContactinvoice// "ContactInvoices"
0x278eb  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x278f0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x278f5  dup
0x278f6  ldstr    aContactleads// "ContactLeads"
0x278fb  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x27900  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x27905  dup
0x27906  ldstr    aContactorders// "ContactOrders"
0x2790b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x27910  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x27915  dup
0x27916  ldstr    aContactquotes// "ContactQuotes"
0x2791b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x27920  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x27925  dup
0x27926  ldstr    aContract// "Contract"
0x2792b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x27930  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x27935  dup
0x27936  ldstr    aContractdetail// "ContractDetail"
0x2793b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x27940  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x27945  dup
0x27946  ldstr    aConvertrule// "ConvertRule"
0x2794b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x27950  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x27955  dup
0x27956  ldstr    aConvertruleite// "ConvertRuleItem"
0x2795b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x27960  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x27965  dup
0x27966  ldstr    aCustomeraddres// "CustomerAddress"
0x2796b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x27970  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x27975  dup
0x27976  ldstr    aCustomeropport// "CustomerOpportunityRole"
0x2797b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x27980  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x27985  dup
0x27986  ldstr    aCustomerrelati// "CustomerRelationship"
0x2798b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x27990  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x27995  dup
0x27996  ldstr    aDelveactionhub// "DelveActionHub"
0x2799b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x279a0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x279a5  dup
0x279a6  ldstr    aDiscount// "Discount"
0x279ab  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x279b0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x279b5  dup
0x279b6  ldstr    aDiscounttype// "DiscountType"
0x279bb  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x279c0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x279c5  dup
0x279c6  ldstr    aDocumentindex// "DocumentIndex"
0x279cb  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x279d0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x279d5  dup
0x279d6  ldstr    aDuplicaterecor// "DuplicateRecord"
0x279db  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x279e0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x279e5  dup
0x279e6  ldstr    aEmail// "Email"
0x279eb  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x279f0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x279f5  dup
0x279f6  ldstr    aEmailhash// "EmailHash"
0x279fb  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x27a00  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x27a05  dup
0x27a06  ldstr    aEmailsearch// "EmailSearch"
0x27a0b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x27a10  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x27a15  dup
0x27a16  ldstr    aEntitlement// "Entitlement"
0x27a1b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x27a20  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x27a25  dup
0x27a26  ldstr    aEntitlementcha// "EntitlementChannel"
0x27a2b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x27a30  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x27a35  dup
0x27a36  ldstr    aEntitlementcon// "EntitlementContacts"
0x27a3b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x27a40  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x27a45  dup
0x27a46  ldstr    aEntitlementpro// "EntitlementProducts"
0x27a4b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x27a50  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x27a55  dup
0x27a56  ldstr    aEntitlementtem// "EntitlementTemplate"
0x27a5b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x27a60  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x27a65  dup
0x27a66  ldstr    aEntitlementtem_0// "EntitlementTemplateChannel"
0x27a6b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x27a70  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x27a75  dup
0x27a76  ldstr    aEntitlementtem_1// "EntitlementTemplateProducts"
0x27a7b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x27a80  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x27a85  dup
0x27a86  ldstr    aExchangesyncid// "ExchangeSyncIdMapping"
0x27a8b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x27a90  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x27a95  dup
0x27a96  ldstr    aBookableresour// "BookableResourceBookingExchangeSyncIdMa"...
0x27a9b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x27aa0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x27aa5  dup
0x27aa6  ldstr    aExternalparty// "ExternalParty"
0x27aab  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x27ab0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x27ab5  dup
0x27ab6  ldstr    aExternalpartyi// "ExternalPartyItem"
0x27abb  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x27ac0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x27ac5  dup
0x27ac6  ldstr    aFax// "Fax"
0x27acb  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x27ad0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x27ad5  dup
0x27ad6  ldstr    aFixedmonthlyfi// "FixedMonthlyFiscalCalendar"
0x27adb  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x27ae0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x27ae5  dup
0x27ae6  ldstr    aGoal// "Goal"
0x27aeb  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x27af0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x27af5  dup
0x27af6  ldstr    aGoalrollupquer// "GoalRollupQuery"
0x27afb  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x27b00  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x27b05  dup
0x27b06  ldstr    aImport// "Import"
0x27b0b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x27b10  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x27b15  dup
0x27b16  ldstr    aImportdata// "ImportData"
0x27b1b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x27b20  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x27b25  dup
0x27b26  ldstr    aImportfile// "ImportFile"
0x27b2b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x27b30  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x27b35  dup
0x27b36  ldstr    aImportlog// "ImportLog"
0x27b3b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x27b40  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x27b45  dup
0x27b46  ldstr    aIncident// "Incident"
0x27b4b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x27b50  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x27b55  dup
0x27b56  ldstr    aIncidentresolu// "IncidentResolution"
0x27b5b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x27b60  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x27b65  dup
0x27b66  ldstr    aIntegrationsta// "IntegrationStatus"
0x27b6b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x27b70  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x27b75  dup
0x27b76  ldstr    aInterprocesslo// "InterProcessLock"
0x27b7b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x27b80  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x27b85  dup
0x27b86  ldstr    aInvoice// "Invoice"
0x27b8b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x27b90  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x27b95  dup
0x27b96  ldstr    aInvoicedetail// "InvoiceDetail"
0x27b9b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x27ba0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x27ba5  dup
0x27ba6  ldstr    aKnowledgeartic// "KnowledgeArticle"
0x27bab  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x27bb0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x27bb5  dup
0x27bb6  ldstr    aKnowledgeartic_0// "KnowledgeArticlesCategories"
0x27bbb  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x27bc0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x27bc5  dup
0x27bc6  ldstr    aKbarticle// "KbArticle"
0x27bcb  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
  ... truncated ...
```
