# Microsoft.Crm.Workflow.Utility.SdkMessageRequestSuffixHelper::.cctor

- ea: `0xf3b0`
- end: `0xf48b`
- name: `Microsoft.Crm.Workflow.Utility.SdkMessageRequestSuffixHelper::.cctor`
- size: `219`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xf490`

## string_xrefs

- `0xf41a`: `RemoveItem_campaign`
- `0xf42a`: `RemoveItem_campaignactivity`
- `0xf44b`: `Copy_campaign`
- `0xf46d`: `CopyMembers_list`

## pseudocode

```c

```

## disassembly

```asm
0xf3b0  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0xf3b5  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Workflow.Utility.SdkMessageRequestSuffixHelper::_requestSuffixDictionary
0xf3ba  ldstr    aCampaign// "Campaign"
0xf3bf  stloc.0
0xf3c0  ldstr    aCampaignactivi// "CampaignActivity"
0xf3c5  stloc.1
0xf3c6  ldstr    aCampaign// "Campaign"
0xf3cb  stloc.2
0xf3cc  ldstr    aCampaignactivi// "CampaignActivity"
0xf3d1  stloc.3
0xf3d2  ldstr    aContract// "Contract"
0xf3d7  stloc.s  4
0xf3d9  ldstr    aCampaign// "Campaign"
0xf3de  stloc.s  5
0xf3e0  ldstr    aContract// "Contract"
0xf3e5  stloc.s  6
0xf3e7  ldstr    aList// "List"
0xf3ec  stloc.s  7
0xf3ee  ldstr    aOpportunity// "Opportunity"
0xf3f3  stloc.s  8
0xf3f5  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Workflow.Utility.SdkMessageRequestSuffixHelper::get_RequestSuffixDictionary()
0xf3fa  ldstr    aAdditemCampaig// "AddItem_campaign"
0xf3ff  ldloc.0
0xf400  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xf405  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Workflow.Utility.SdkMessageRequestSuffixHelper::get_RequestSuffixDictionary()
0xf40a  ldstr    aAdditemCampaig_0// "AddItem_campaignactivity"
0xf40f  ldloc.1
0xf410  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xf415  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Workflow.Utility.SdkMessageRequestSuffixHelper::get_RequestSuffixDictionary()
0xf41a  ldstr    aRemoveitemCamp// "RemoveItem_campaign"
0xf41f  ldloc.2
0xf420  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xf425  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Workflow.Utility.SdkMessageRequestSuffixHelper::get_RequestSuffixDictionary()
0xf42a  ldstr    aRemoveitemCamp_0// "RemoveItem_campaignactivity"
0xf42f  ldloc.3
0xf430  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xf435  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Workflow.Utility.SdkMessageRequestSuffixHelper::get_RequestSuffixDictionary()
0xf43a  ldstr    aRenewContract// "Renew_contract"
0xf43f  ldloc.s  4
0xf441  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xf446  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Workflow.Utility.SdkMessageRequestSuffixHelper::get_RequestSuffixDictionary()
0xf44b  ldstr    aCopyCampaign// "Copy_campaign"
0xf450  ldloc.s  5
0xf452  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xf457  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Workflow.Utility.SdkMessageRequestSuffixHelper::get_RequestSuffixDictionary()
0xf45c  ldstr    aCloneContract// "Clone_contract"
0xf461  ldloc.s  6
0xf463  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xf468  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Workflow.Utility.SdkMessageRequestSuffixHelper::get_RequestSuffixDictionary()
0xf46d  ldstr    aCopymembersLis// "CopyMembers_list"
0xf472  ldloc.s  7
0xf474  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xf479  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Workflow.Utility.SdkMessageRequestSuffixHelper::get_RequestSuffixDictionary()
0xf47e  ldstr    aCalculateactua// "CalculateActualValue_opportunity"
0xf483  ldloc.s  8
0xf485  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xf48a  ret
```
