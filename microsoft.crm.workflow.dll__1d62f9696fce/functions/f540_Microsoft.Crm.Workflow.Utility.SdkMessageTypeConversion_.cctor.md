# Microsoft.Crm.Workflow.Utility.SdkMessageTypeConversion::.cctor

- ea: `0xf540`
- end: `0xf996`
- name: `Microsoft.Crm.Workflow.Utility.SdkMessageTypeConversion::.cctor`
- size: `1110`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xf9a0`

## string_xrefs

- `0xf621`: `documenttemplate`
- `0xf633`: `competitor`
- `0xf68d`: `teamtemplate`
- `0xf866`: `CLOSEOPPORTUNITY_CompetitorId`
- `0xf8f5`: `SETWORDTEMPLATE_Target`
- `0xf905`: `SETWORDTEMPLATE_SelectedTemplate`
- `0xf92c`: `ADDUSERTORECORDTEAM_TeamTemplateId`
- `0xf958`: `REMOVEUSERFROMRECORDTEAM_SystemUserId`
- `0xf96e`: `REMOVEUSERFROMRECORDTEAM_TeamTemplateId`
- `0xf984`: `REMOVEUSERFROMRECORDTEAM_Record`

## pseudocode

```c

```

## disassembly

```asm
0xf540  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>>::.ctor()
0xf545  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>> Microsoft.Crm.Workflow.Utility.SdkMessageTypeConversion::_typeConversionDictionary
0xf54a  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::.ctor()
0xf54f  dup
0xf550  ldstr    aQueue// "queue"
0xf555  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::Add(var<u1>)
0xf55a  stloc.0
0xf55b  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::.ctor()
0xf560  dup
0xf561  ldstr    aQueue// "queue"
0xf566  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::Add(var<u1>)
0xf56b  stloc.1
0xf56c  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::.ctor()
0xf571  dup
0xf572  ldstr    aIncident// "incident"
0xf577  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::Add(var<u1>)
0xf57c  dup
0xf57d  ldstr    aEmail// "email"
0xf582  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::Add(var<u1>)
0xf587  dup
0xf588  ldstr    aAppointment// "appointment"
0xf58d  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::Add(var<u1>)
0xf592  stloc.2
0xf593  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::.ctor()
0xf598  dup
0xf599  ldstr    aOpportunity_0// "opportunity"
0xf59e  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::Add(var<u1>)
0xf5a3  stloc.3
0xf5a4  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::.ctor()
0xf5a9  dup
0xf5aa  ldstr    aQueue// "queue"
0xf5af  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::Add(var<u1>)
0xf5b4  stloc.s  4
0xf5b6  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::.ctor()
0xf5bb  dup
0xf5bc  ldstr    aSystemuser// "systemuser"
0xf5c1  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::Add(var<u1>)
0xf5c6  stloc.s  5
0xf5c8  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::.ctor()
0xf5cd  dup
0xf5ce  ldstr    aTransactioncur// "transactioncurrency"
0xf5d3  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::Add(var<u1>)
0xf5d8  stloc.s  6
0xf5da  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::.ctor()
0xf5df  dup
0xf5e0  ldstr    aCampaign_0// "campaign"
0xf5e5  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::Add(var<u1>)
0xf5ea  stloc.s  7
0xf5ec  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::.ctor()
0xf5f1  dup
0xf5f2  ldstr    aContact// "contact"
0xf5f7  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::Add(var<u1>)
0xf5fc  dup
0xf5fd  ldstr    aAccount// "account"
0xf602  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::Add(var<u1>)
0xf607  stloc.s  8
0xf609  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::.ctor()
0xf60e  dup
0xf60f  ldstr    aWorkflow// "workflow"
0xf614  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::Add(var<u1>)
0xf619  stloc.s  9
0xf61b  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::.ctor()
0xf620  dup
0xf621  ldstr    aDocumenttempla// "documenttemplate"
0xf626  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::Add(var<u1>)
0xf62b  stloc.s  0xA
0xf62d  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::.ctor()
0xf632  dup
0xf633  ldstr    aCompetitor// "competitor"
0xf638  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::Add(var<u1>)
0xf63d  stloc.s  0xB
0xf63f  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::.ctor()
0xf644  dup
0xf645  ldstr    aIncident// "incident"
0xf64a  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::Add(var<u1>)
0xf64f  stloc.s  0xC
0xf651  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::.ctor()
0xf656  dup
0xf657  ldstr    aQuote// "quote"
0xf65c  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::Add(var<u1>)
0xf661  stloc.s  0xD
0xf663  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::.ctor()
0xf668  dup
0xf669  ldstr    aSystemuser// "systemuser"
0xf66e  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::Add(var<u1>)
0xf673  stloc.s  0xE
0xf675  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::.ctor()
0xf67a  dup
0xf67b  ldstr    aInvoice// "invoice"
0xf680  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::Add(var<u1>)
0xf685  stloc.s  0xF
0xf687  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::.ctor()
0xf68c  dup
0xf68d  ldstr    aTeamtemplate// "teamtemplate"
0xf692  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::Add(var<u1>)
0xf697  stloc.s  0x10
0xf699  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::.ctor()
0xf69e  dup
0xf69f  ldstr    aOpportunity_0// "opportunity"
0xf6a4  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::Add(var<u1>)
0xf6a9  stloc.s  0x11
0xf6ab  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::.ctor()
0xf6b0  dup
0xf6b1  ldstr    aSystemuser// "systemuser"
0xf6b6  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::Add(var<u1>)
0xf6bb  stloc.s  0x12
0xf6bd  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::.ctor()
0xf6c2  dup
0xf6c3  ldstr    aNotificationch// "notificationchannel"
0xf6c8  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::Add(var<u1>)
0xf6cd  stloc.s  0x13
0xf6cf  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>> Microsoft.Crm.Workflow.Utility.SdkMessageTypeConversion::get_TypeConversionDictionary()
0xf6d4  ldstr    aSendnotificati// "SENDNOTIFICATION_To"
0xf6d9  ldloc.s  0x12
0xf6db  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IList`1<var<u1>>)
0xf6e0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>>::set_Item(var<u1>, !!T0)
0xf6e5  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>> Microsoft.Crm.Workflow.Utility.SdkMessageTypeConversion::get_TypeConversionDictionary()
0xf6ea  ldstr    aSendnotificati_0// "SENDNOTIFICATION_ChannelId"
0xf6ef  ldloc.s  0x13
0xf6f1  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IList`1<var<u1>>)
0xf6f6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>>::set_Item(var<u1>, !!T0)
0xf6fb  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>> Microsoft.Crm.Workflow.Utility.SdkMessageTypeConversion::get_TypeConversionDictionary()
0xf700  ldstr    aSendnotificati_1// "SENDNOTIFICATION_RegardingObjectId"
0xf705  ldnull
0xf706  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>>::set_Item(var<u1>, !!T0)
0xf70b  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>> Microsoft.Crm.Workflow.Utility.SdkMessageTypeConversion::get_TypeConversionDictionary()
0xf710  ldstr    aAddtoqueueSour// "ADDTOQUEUE_SourceQueueId"
0xf715  ldloc.0
0xf716  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IList`1<var<u1>>)
0xf71b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>>::set_Item(var<u1>, !!T0)
0xf720  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>> Microsoft.Crm.Workflow.Utility.SdkMessageTypeConversion::get_TypeConversionDictionary()
0xf725  ldstr    aAddtoqueueDest// "ADDTOQUEUE_DestinationQueueId"
0xf72a  ldloc.1
0xf72b  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IList`1<var<u1>>)
0xf730  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>>::set_Item(var<u1>, !!T0)
0xf735  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>> Microsoft.Crm.Workflow.Utility.SdkMessageTypeConversion::get_TypeConversionDictionary()
0xf73a  ldstr    aAddtoqueueTarg// "ADDTOQUEUE_Target"
0xf73f  ldloc.2
0xf740  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IList`1<var<u1>>)
0xf745  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>>::set_Item(var<u1>, !!T0)
0xf74a  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>> Microsoft.Crm.Workflow.Utility.SdkMessageTypeConversion::get_TypeConversionDictionary()
0xf74f  ldstr    aGetinvoiceprod// "GETINVOICEPRODUCTSFROMOPPORTUNITY_Oppor"...
0xf754  ldloc.3
0xf755  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IList`1<var<u1>>)
0xf75a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>>::set_Item(var<u1>, !!T0)
0xf75f  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>> Microsoft.Crm.Workflow.Utility.SdkMessageTypeConversion::get_TypeConversionDictionary()
0xf764  ldstr    aGetquoteproduc// "GETQUOTEPRODUCTSFROMOPPORTUNITY_Opportu"...
0xf769  ldloc.3
0xf76a  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IList`1<var<u1>>)
0xf76f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>>::set_Item(var<u1>, !!T0)
0xf774  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>> Microsoft.Crm.Workflow.Utility.SdkMessageTypeConversion::get_TypeConversionDictionary()
0xf779  ldstr    aGetsalesorderp// "GETSALESORDERPRODUCTSFROMOPPORTUNITY_Op"...
0xf77e  ldloc.3
0xf77f  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IList`1<var<u1>>)
0xf784  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>>::set_Item(var<u1>, !!T0)
0xf789  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>> Microsoft.Crm.Workflow.Utility.SdkMessageTypeConversion::get_TypeConversionDictionary()
0xf78e  ldstr    aConvertsalesor// "CONVERTSALESORDERTOINVOICE_InvoiceId"
0xf793  ldloc.s  0xF
0xf795  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IList`1<var<u1>>)
0xf79a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>>::set_Item(var<u1>, !!T0)
0xf79f  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>> Microsoft.Crm.Workflow.Utility.SdkMessageTypeConversion::get_TypeConversionDictionary()
0xf7a4  ldstr    aGenerateinvoic// "GENERATEINVOICEFROMOPPORTUNITY_Opportun"...
0xf7a9  ldloc.3
0xf7aa  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IList`1<var<u1>>)
0xf7af  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>>::set_Item(var<u1>, !!T0)
0xf7b4  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>> Microsoft.Crm.Workflow.Utility.SdkMessageTypeConversion::get_TypeConversionDictionary()
0xf7b9  ldstr    aGeneratequotef// "GENERATEQUOTEFROMOPPORTUNITY_Opportunit"...
0xf7be  ldloc.3
0xf7bf  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IList`1<var<u1>>)
0xf7c4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>>::set_Item(var<u1>, !!T0)
0xf7c9  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>> Microsoft.Crm.Workflow.Utility.SdkMessageTypeConversion::get_TypeConversionDictionary()
0xf7ce  ldstr    aGeneratesaleso// "GENERATESALESORDERFROMOPPORTUNITY_Oppor"...
0xf7d3  ldloc.3
0xf7d4  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IList`1<var<u1>>)
0xf7d9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>>::set_Item(var<u1>, !!T0)
0xf7de  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>> Microsoft.Crm.Workflow.Utility.SdkMessageTypeConversion::get_TypeConversionDictionary()
0xf7e3  ldstr    aRoutetoTarget// "ROUTETO_Target"
0xf7e8  ldloc.s  4
0xf7ea  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IList`1<var<u1>>)
0xf7ef  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>>::set_Item(var<u1>, !!T0)
0xf7f4  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>> Microsoft.Crm.Workflow.Utility.SdkMessageTypeConversion::get_TypeConversionDictionary()
0xf7f9  ldstr    aPickfromqueueW// "PICKFROMQUEUE_WorkerId"
0xf7fe  ldloc.s  5
0xf800  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IList`1<var<u1>>)
0xf805  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>>::set_Item(var<u1>, !!T0)
0xf80a  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>> Microsoft.Crm.Workflow.Utility.SdkMessageTypeConversion::get_TypeConversionDictionary()
0xf80f  ldstr    aQualifyleadOpp// "QUALIFYLEAD_OpportunityCurrencyId"
0xf814  ldloc.s  6
0xf816  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IList`1<var<u1>>)
0xf81b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>>::set_Item(var<u1>, !!T0)
0xf820  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>> Microsoft.Crm.Workflow.Utility.SdkMessageTypeConversion::get_TypeConversionDictionary()
0xf825  ldstr    aQualifyleadSou// "QUALIFYLEAD_SourceCampaignId"
0xf82a  ldloc.s  7
0xf82c  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IList`1<var<u1>>)
0xf831  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>>::set_Item(var<u1>, !!T0)
0xf836  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>> Microsoft.Crm.Workflow.Utility.SdkMessageTypeConversion::get_TypeConversionDictionary()
0xf83b  ldstr    aQualifyleadOpp_0// "QUALIFYLEAD_OpportunityCustomerId"
0xf840  ldloc.s  8
0xf842  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IList`1<var<u1>>)
0xf847  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>>::set_Item(var<u1>, !!T0)
0xf84c  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>> Microsoft.Crm.Workflow.Utility.SdkMessageTypeConversion::get_TypeConversionDictionary()
0xf851  ldstr    aCloseopportuni// "CLOSEOPPORTUNITY_OpportunityId"
0xf856  ldloc.3
0xf857  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IList`1<var<u1>>)
0xf85c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>>::set_Item(var<u1>, !!T0)
0xf861  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>> Microsoft.Crm.Workflow.Utility.SdkMessageTypeConversion::get_TypeConversionDictionary()
0xf866  ldstr    aCloseopportuni_0// "CLOSEOPPORTUNITY_CompetitorId"
0xf86b  ldloc.s  0xB
0xf86d  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IList`1<var<u1>>)
0xf872  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>>::set_Item(var<u1>, !!T0)
0xf877  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>> Microsoft.Crm.Workflow.Utility.SdkMessageTypeConversion::get_TypeConversionDictionary()
0xf87c  ldstr    aResolvequoteQu// "RESOLVEQUOTE_QuoteId"
0xf881  ldloc.s  0xD
0xf883  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IList`1<var<u1>>)
0xf888  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>>::set_Item(var<u1>, !!T0)
0xf88d  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>> Microsoft.Crm.Workflow.Utility.SdkMessageTypeConversion::get_TypeConversionDictionary()
0xf892  ldstr    aResolveinciden// "RESOLVEINCIDENT_IncidentId"
0xf897  ldloc.s  0xC
0xf899  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IList`1<var<u1>>)
0xf89e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>>::set_Item(var<u1>, !!T0)
0xf8a3  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>> Microsoft.Crm.Workflow.Utility.SdkMessageTypeConversion::get_TypeConversionDictionary()
0xf8a8  ldstr    aConvertquoteto// "CONVERTQUOTETOSALESORDER_QuoteId"
0xf8ad  ldloc.s  0xD
0xf8af  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IList`1<var<u1>>)
0xf8b4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>>::set_Item(var<u1>, !!T0)
0xf8b9  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>> Microsoft.Crm.Workflow.Utility.SdkMessageTypeConversion::get_TypeConversionDictionary()
0xf8be  ldstr    aRevisequoteQuo// "REVISEQUOTE_QuoteId"
0xf8c3  ldloc.s  0xD
0xf8c5  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IList`1<var<u1>>)
0xf8ca  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>>::set_Item(var<u1>, !!T0)
0xf8cf  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>> Microsoft.Crm.Workflow.Utility.SdkMessageTypeConversion::get_TypeConversionDictionary()
0xf8d4  ldstr    aSetprocessTarg// "SETPROCESS_Target"
0xf8d9  ldnull
0xf8da  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>>::set_Item(var<u1>, !!T0)
0xf8df  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>> Microsoft.Crm.Workflow.Utility.SdkMessageTypeConversion::get_TypeConversionDictionary()
0xf8e4  ldstr    aSetprocessNewp// "SETPROCESS_NewProcess"
0xf8e9  ldloc.s  9
0xf8eb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>>::set_Item(var<u1>, !!T0)
0xf8f0  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>> Microsoft.Crm.Workflow.Utility.SdkMessageTypeConversion::get_TypeConversionDictionary()
0xf8f5  ldstr    aSetwordtemplat// "SETWORDTEMPLATE_Target"
0xf8fa  ldnull
0xf8fb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>>::set_Item(var<u1>, !!T0)
0xf900  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>> Microsoft.Crm.Workflow.Utility.SdkMessageTypeConversion::get_TypeConversionDictionary()
0xf905  ldstr    aSetwordtemplat_0// "SETWORDTEMPLATE_SelectedTemplate"
0xf90a  ldloc.s  0xA
0xf90c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>>::set_Item(var<u1>, !!T0)
0xf911  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>> Microsoft.Crm.Workflow.Utility.SdkMessageTypeConversion::get_TypeConversionDictionary()
0xf916  ldstr    aAddusertorecor// "ADDUSERTORECORDTEAM_SystemUserId"
0xf91b  ldloc.s  0xE
0xf91d  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IList`1<var<u1>>)
0xf922  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>>::set_Item(var<u1>, !!T0)
0xf927  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>> Microsoft.Crm.Workflow.Utility.SdkMessageTypeConversion::get_TypeConversionDictionary()
0xf92c  ldstr    aAddusertorecor_0// "ADDUSERTORECORDTEAM_TeamTemplateId"
0xf931  ldloc.s  0x10
0xf933  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IList`1<var<u1>>)
0xf938  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>>::set_Item(var<u1>, !!T0)
0xf93d  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>> Microsoft.Crm.Workflow.Utility.SdkMessageTypeConversion::get_TypeConversionDictionary()
0xf942  ldstr    aAddusertorecor_1// "ADDUSERTORECORDTEAM_Record"
0xf947  ldloc.s  0x11
0xf949  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IList`1<var<u1>>)
0xf94e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>>::set_Item(var<u1>, !!T0)
0xf953  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>> Microsoft.Crm.Workflow.Utility.SdkMessageTypeConversion::get_TypeConversionDictionary()
0xf958  ldstr    aRemoveuserfrom// "REMOVEUSERFROMRECORDTEAM_SystemUserId"
0xf95d  ldloc.s  0xE
0xf95f  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IList`1<var<u1>>)
0xf964  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>>::set_Item(var<u1>, !!T0)
0xf969  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>> Microsoft.Crm.Workflow.Utility.SdkMessageTypeConversion::get_TypeConversionDictionary()
0xf96e  ldstr    aRemoveuserfrom_0// "REMOVEUSERFROMRECORDTEAM_TeamTemplateId"
0xf973  ldloc.s  0x10
0xf975  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IList`1<var<u1>>)
0xf97a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>>::set_Item(var<u1>, !!T0)
0xf97f  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>> Microsoft.Crm.Workflow.Utility.SdkMessageTypeConversion::get_TypeConversionDictionary()
0xf984  ldstr    aRemoveuserfrom_1// "REMOVEUSERFROMRECORDTEAM_Record"
0xf989  ldloc.s  0x11
0xf98b  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IList`1<var<u1>>)
0xf990  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>>::set_Item(var<u1>, !!T0)
0xf995  ret
```
