# Microsoft.Crm.Application.Controls.NavBar::InitializeEntityTypeToEntityImageUrl

- ea: `0xa2a90`
- end: `0xa30f6`
- name: `Microsoft.Crm.Application.Controls.NavBar::InitializeEntityTypeToEntityImageUrl`
- size: `1638`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xa4b70`
- `0xa55f0`
- `0xa58f0`

## callees

- `0xa2a90`

## string_xrefs

- `0xa2c1e`: `Competitors_32.png`
- `0xa2cfa`: `EntitlementTemplates_32.png`
- `0xa2d0a`: `EntitlementTemplateChannel_32.png`
- `0xa2d2a`: `FieldSecurityProfiles_32.png`
- `0xa2eec`: `SecurityRoles_32.png`
- `0xa2f3c`: `Service_32.png`
- `0xa2f4c`: `ServiceAppointment_32.png`
- `0xa2f7c`: `ServiceLevelAgreement_32.png`
- `0xa2f8c`: `ServiceLevelAgreementItem_32.png`
- `0xa2fe9`: `Task_32.png`
- `0xa3006`: `Templates_32.png`

## pseudocode

```c

```

## disassembly

```asm
0xa2a90  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Application.Controls.NavBar::_entityTypeToEntityImageUrl
0xa2a95  brtrue   loc_A30F5
0xa2a9a  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::.ctor()
0xa2a9f  dup
0xa2aa0  ldc.i4.1
0xa2aa1  ldstr    aAccount32Png// "Account_32.png"
0xa2aa6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2aab  dup
0xa2aac  ldc.i4   0x2655
0xa2ab1  ldstr    aActivitiesclos// "ActivitiesClosed_32.png"
0xa2ab6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2abb  dup
0xa2abc  ldc.i4   0x1068
0xa2ac1  ldstr    aActivities32Pn// "Activities_32.png"
0xa2ac6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2acb  dup
0xa2acc  ldc.i4   0x2654
0xa2ad1  ldstr    aAlerts32Png// "Alerts_32.png"
0xa2ad6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2adb  dup
0xa2adc  ldc.i4   0x1069
0xa2ae1  ldstr    aAppointment32P// "Appointment_32.png"
0xa2ae6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2aeb  dup
0xa2aec  ldc.i4   0x232D
0xa2af1  ldstr    aBackgroundproc// "BackgroundProcess_32.png"
0xa2af6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2afb  dup
0xa2afc  ldc.i4   0x125C
0xa2b01  ldstr    aBackgroundproc// "BackgroundProcess_32.png"
0xa2b06  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2b0b  dup
0xa2b0c  ldc.i4   0x11D7
0xa2b11  ldstr    aAuditing32Png// "Auditing_32.png"
0xa2b16  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2b1b  dup
0xa2b1c  ldc.i4   0x47E
0xa2b21  ldstr    aBookableresour// "BookableResource_32.png"
0xa2b26  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2b2b  dup
0xa2b2c  ldc.i4   0x479
0xa2b31  ldstr    aBookableresour_0// "BookableResourceBooking_32.png"
0xa2b36  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2b3b  dup
0xa2b3c  ldc.i4   0x47A
0xa2b41  ldstr    aBookableresour_1// "BookableResourceBookingHeader_32.png"
0xa2b46  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2b4b  dup
0xa2b4c  ldc.i4   0x47B
0xa2b51  ldstr    aBookableresour_2// "BookableResourceCategory_32.png"
0xa2b56  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2b5b  dup
0xa2b5c  ldc.i4   0x47D
0xa2b61  ldstr    aBookableresour_2// "BookableResourceCategory_32.png"
0xa2b66  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2b6b  dup
0xa2b6c  ldc.i4   0x47C
0xa2b71  ldstr    aCharacteristic// "Characteristic_32.png"
0xa2b76  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2b7b  dup
0xa2b7c  ldc.i4   0x47F
0xa2b81  ldstr    aBookableresour// "BookableResource_32.png"
0xa2b86  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2b8b  dup
0xa2b8c  ldc.i4   0x480
0xa2b91  ldstr    aBookingstatus3// "BookingStatus_32.png"
0xa2b96  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2b9b  dup
0xa2b9c  ldc.i4   0x1136
0xa2ba1  ldstr    aQuickcampaign3// "QuickCampaign_32.png"
0xa2ba6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2bab  dup
0xa2bac  ldc.i4   0x84
0xa2bb1  ldstr    aArticles32Png// "Articles_32.png"
0xa2bb6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2bbb  dup
0xa2bbc  ldc.i4   0xFA3
0xa2bc1  ldstr    aCalendar32Png// "Calendar_32.png"
0xa2bc6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2bcb  dup
0xa2bcc  ldc.i4   0x1130
0xa2bd1  ldstr    aCampaign32Png// "Campaign_32.png"
0xa2bd6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2bdb  dup
0xa2bdc  ldc.i4   0x1131
0xa2be1  ldstr    aCampaignrespon_1// "CampaignResponse_32.png"
0xa2be6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2beb  dup
0xa2bec  ldc.i4   0x1132
0xa2bf1  ldstr    aCampaignactivi_2// "CampaignActivity_32.png"
0xa2bf6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2bfb  dup
0xa2bfc  ldc.i4   0x26E7
0xa2c01  ldstr    aHierarchycateg// "HierarchyCategory_32.png"
0xa2c06  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2c0b  dup
0xa2c0c  ldc.i4   0x475
0xa2c11  ldstr    aCharacteristic// "Characteristic_32.png"
0xa2c16  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2c1b  dup
0xa2c1c  ldc.i4.s 0x7B
0xa2c1e  ldstr    aCompetitors32P// "Competitors_32.png"
0xa2c23  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2c28  dup
0xa2c29  ldc.i4   0xCA2
0xa2c2e  ldstr    aConnections32P// "Connections_32.png"
0xa2c33  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2c38  dup
0xa2c39  ldc.i4   0xFA7
0xa2c3e  ldstr    aResourcegroup3// "ResourceGroup_32.png"
0xa2c43  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2c48  dup
0xa2c49  ldc.i4.2
0xa2c4a  ldstr    aContact32Png// "Contact_32.png"
0xa2c4f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2c54  dup
0xa2c55  ldc.i4   0x3F2
0xa2c5a  ldstr    aContract32Png// "Contract_32.png"
0xa2c5f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2c64  dup
0xa2c65  ldc.i4   0x3F3
0xa2c6a  ldstr    aContractlines3// "ContractLines_32.png"
0xa2c6f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2c74  dup
0xa2c75  ldc.i4   0x2454
0xa2c7a  ldstr    aAutomaticcasec// "AutomaticCaseCreationRules_32.png"
0xa2c7f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2c84  dup
0xa2c85  ldc.i4   0x2455
0xa2c8a  ldstr    aAutomaticcasec_0// "AutomaticCaseCreationRulesItem_32.png"
0xa2c8f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2c94  dup
0xa2c95  ldc.i4   0x1197
0xa2c9a  ldstr    aRelationshipsW// "Relationships_White_32.png"
0xa2c9f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2ca4  dup
0xa2ca5  ldc.i4   0x3F5
0xa2caa  ldstr    aDiscount32Png// "Discount_32.png"
0xa2caf  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2cb4  dup
0xa2cb5  ldc.i4   0x106A
0xa2cba  ldstr    aEmail32Png// "Email_32.png"
0xa2cbf  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2cc4  dup
0xa2cc5  ldc.i4   0x25E4
0xa2cca  ldstr    aEntitlement32P// "Entitlement_32.png"
0xa2ccf  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2cd4  dup
0xa2cd5  ldc.i4   0x26E6
0xa2cda  ldstr    aFeedback32Png// "Feedback_32.png"
0xa2cdf  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2ce4  dup
0xa2ce5  ldc.i4   0x25E5
0xa2cea  ldstr    aEntitlementcha// "EntitlementChannel_32.png"
0xa2cef  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2cf4  dup
0xa2cf5  ldc.i4   0x25E6
0xa2cfa  ldstr    aEntitlementtem// "EntitlementTemplates_32.png"
0xa2cff  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2d04  dup
0xa2d05  ldc.i4   0x25E7
0xa2d0a  ldstr    aEntitlementtem_0// "EntitlementTemplateChannel_32.png"
0xa2d0f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2d14  dup
0xa2d15  ldc.i4   0x106C
0xa2d1a  ldstr    aFaxl32Png// "Faxl_32.png"
0xa2d1f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2d24  dup
0xa2d25  ldc.i4   0x4B0
0xa2d2a  ldstr    aFieldsecurityp// "FieldSecurityProfiles_32.png"
0xa2d2f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2d34  dup
0xa2d35  ldc.i4   0x2580
0xa2d3a  ldstr    aGoal32Png// "Goal_32.png"
0xa2d3f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2d44  dup
0xa2d45  ldc.i4   0x2582
0xa2d4a  ldstr    aRollupqueries3// "RollupQueries_32.png"
0xa2d4f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2d54  dup
0xa2d55  ldc.i4.s 0x70
0xa2d57  ldstr    aCases32Png// "Cases_32.png"
0xa2d5c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2d61  dup
0xa2d62  ldc.i4   0x442
0xa2d67  ldstr    aInvoices32Png// "Invoices_32.png"
0xa2d6c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2d71  dup
0xa2d72  ldc.i4.s 0x7F
0xa2d74  ldstr    aArticles32Png// "Articles_32.png"
0xa2d79  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2d7e  dup
0xa2d7f  ldc.i4   0x26E1
0xa2d84  ldstr    aKnowledgeartic// "KnowledgeArticle_32.png"
0xa2d89  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2d8e  dup
0xa2d8f  ldc.i4   0x26CA
0xa2d94  ldstr    aKnowledgebase3// "KnowledgeBase_32.png"
0xa2d99  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2d9e  dup
0xa2d9f  ldc.i4.4
0xa2da0  ldstr    aLead32Png// "Lead_32.png"
0xa2da5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2daa  dup
0xa2dab  ldc.i4   0x106F
0xa2db0  ldstr    aLetter32Png// "Letter_32.png"
0xa2db5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2dba  dup
0xa2dbb  ldc.i4   0x10CC
0xa2dc0  ldstr    aMarketinglist3// "MarketingList_32.png"
0xa2dc5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2dca  dup
0xa2dcb  ldc.i4   0x2657
0xa2dd0  ldstr    aMarketinglistm// "MarketingListMember_32.png"
0xa2dd5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2dda  dup
0xa2ddb  ldc.i4   0x2583
0xa2de0  ldstr    aGoalmetrics32P// "GoalMetrics_32.png"
0xa2de5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2dea  dup
0xa2deb  ldc.i4.3
0xa2dec  ldstr    aOpportunity32P// "Opportunity_32.png"
0xa2df1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2df6  dup
0xa2df7  ldc.i4   0x43B
0xa2dfc  ldstr    aOpportunitypro_0// "OpportunityProduct_32.png"
0xa2e01  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2e06  dup
0xa2e07  ldc.i4   0x443
0xa2e0c  ldstr    aInvoicedetail3// "InvoiceDetail_32.png"
0xa2e11  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2e16  dup
0xa2e17  ldc.i4   0x43D
0xa2e1c  ldstr    aQuotedetail32P// "QuoteDetail_32.png"
0xa2e21  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2e26  dup
0xa2e27  ldc.i4   0x441
0xa2e2c  ldstr    aSalesorderdeta_0// "SalesOrderDetail_32.png"
0xa2e31  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2e36  dup
0xa2e37  ldc.i4   0x1072
0xa2e3c  ldstr    aPhonecall32Png// "PhoneCall_32.png"
0xa2e41  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2e46  dup
0xa2e47  ldc.i4   0x402
0xa2e4c  ldstr    aPricelistitemW// "PriceListItem_White_32.png"
0xa2e51  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2e56  dup
0xa2e57  ldc.i4   0x1266
0xa2e5c  ldstr    aRealtimeproces// "RealTimeProcess_32.png"
0xa2e61  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2e66  dup
0xa2e67  ldc.i4   0x400
0xa2e6c  ldstr    aProducts32Png// "Products_32.png"
0xa2e71  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2e76  dup
0xa2e77  ldc.i4   0x7E4
0xa2e7c  ldstr    aQueues32Png// "Queues_32.png"
0xa2e81  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2e86  dup
0xa2e87  ldc.i4   0x7ED
0xa2e8c  ldstr    aQueues32Png// "Queues_32.png"
0xa2e91  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2e96  dup
0xa2e97  ldc.i4   0x43C
0xa2e9c  ldstr    aQuote32Png// "Quote_32.png"
0xa2ea1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2ea6  dup
0xa2ea7  ldc.i4   0x478
0xa2eac  ldstr    aRating32Png// "Rating_32.png"
0xa2eb1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2eb6  dup
0xa2eb7  ldc.i4   0x476
0xa2ebc  ldstr    aRating32Png// "Rating_32.png"
0xa2ec1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2ec6  dup
0xa2ec7  ldc.i4   0x109B
0xa2ecc  ldstr    aRecurringappoi_0// "RecurringAppointment_32.png"
0xa2ed1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2ed6  dup
0xa2ed7  ldc.i4   0x238C
0xa2edc  ldstr    aReport32Png// "Report_32.png"
0xa2ee1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2ee6  dup
0xa2ee7  ldc.i4   0x40C
0xa2eec  ldstr    aSecurityroles3// "SecurityRoles_32.png"
0xa2ef1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2ef6  dup
0xa2ef7  ldc.i4   0x2584
0xa2efc  ldstr    aRollupqueries3// "RollupQueries_32.png"
0xa2f01  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2f06  dup
0xa2f07  ldc.i4   0x1FF5
0xa2f0c  ldstr    aRoutingrules32// "RoutingRules_32.png"
0xa2f11  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2f16  dup
0xa2f17  ldc.i4   0x40E
0xa2f1c  ldstr    aSalesliteratur_0// "SalesLiterature_32.png"
0xa2f21  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0xa2f26  dup
  ... truncated ...
```
