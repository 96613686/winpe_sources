# Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::.cctor

- ea: `0x49f50`
- end: `0x4ac9c`
- name: `Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::.cctor`
- size: `3404`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callees

- `0x349c0`
- `0x34a90`
- `0x34ab0`
- `0x34ad0`
- `0x34af0`
- `0x34c00`
- `0x34c20`
- `0x34c40`
- `0x34ca0`
- `0x472b0`
- `0x47350`
- `0x49f50`
- `0x4aca0`
- `0x827c0`
- `0x97bc0`

## string_xrefs

- `0x4a02a`: `/_imgs/ico_18_camptask.gif`
- `0x4a02f`: `Tab_Label_PlanningTasks`
- `0x4a3dc`: `navComp`
- `0x4a506`: `navFieldSecurityProfiles`
- `0x4a639`: `navFieldSecurityProfiles`
- `0x4a532`: `navServices`
- `0x4a53d`: `Tab_Label_Services`
- `0x4a929`: `navComps`

## pseudocode

```c

```

## disassembly

```asm
0x49f50  ldc.i4.0
0x49f51  newobj   instance void [mscorlib]System.Threading.Mutex::.ctor(bool)
0x49f56  stsfld   class [mscorlib]System.Threading.Mutex Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_hardcodedRelationInfoListMutex
0x49f5b  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo>>::.ctor()
0x49f60  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo>> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_relationshipListDictionary
0x49f65  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo>>::.ctor()
0x49f6a  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo>> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_relationshipListNonRefreshDictionary
0x49f6f  ldnull
0x49f70  stsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_account
0x49f75  ldnull
0x49f76  stsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_bookableresource
0x49f7b  ldnull
0x49f7c  stsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_campaign
0x49f81  ldnull
0x49f82  stsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_competitor
0x49f87  ldnull
0x49f88  stsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_contact
0x49f8d  ldnull
0x49f8e  stsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_contractDetails
0x49f93  ldnull
0x49f94  stsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_contract
0x49f99  ldnull
0x49f9a  stsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_lead
0x49f9f  ldnull
0x49fa0  stsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_list
0x49fa5  ldnull
0x49fa6  stsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_salesLitrature
0x49fab  ldnull
0x49fac  stsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_site
0x49fb1  ldnull
0x49fb2  stsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_systemUser
0x49fb7  ldnull
0x49fb8  stsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_team
0x49fbd  ldnull
0x49fbe  stsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_territory
0x49fc3  ldnull
0x49fc4  stsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_importFile
0x49fc9  ldnull
0x49fca  stsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_campaignActivity
0x49fcf  ldnull
0x49fd0  stsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_discountType
0x49fd5  ldnull
0x49fd6  stsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_priceLevel
0x49fdb  ldnull
0x49fdc  stsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_product
0x49fe1  ldnull
0x49fe2  stsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_uomSchedule
0x49fe7  ldnull
0x49fe8  stsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_invoice
0x49fed  ldnull
0x49fee  stsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_quote
0x49ff3  ldnull
0x49ff4  stsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_quoteRefresh
0x49ff9  ldnull
0x49ffa  stsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_salesOrder
0x49fff  ldnull
0x4a000  stsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_salesOrderRefresh
0x4a005  ldnull
0x4a006  stsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_userDefined
0x4a00b  ldsfld   class [mscorlib]System.Threading.Mutex Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_hardcodedRelationInfoListMutex
0x4a010  ldc.i4.m1
0x4a011  ldc.i4.0
0x4a012  callvirt instance bool [mscorlib]System.Threading.WaitHandle::WaitOne(int32, bool)
0x4a017  pop
0x4a018  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo>::.ctor()
0x4a01d  stsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_campaign
0x4a022  ldc.i4.0
0x4a023  ldstr    aNavactivities// "navActivities"
0x4a028  ldc.i4.0
0x4a029  ldc.i4.0
0x4a02a  ldstr    aImgsIco18Campt// "/_imgs/ico_18_camptask.gif"
0x4a02f  ldstr    aTabLabelPlanni// "Tab_Label_PlanningTasks"
0x4a034  ldc.i4   0x1068
0x4a039  newobj   instance void Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo::.ctor(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NavPaneArea area, string id, int32 objectTypeCode, int32 sequence, string iconPath, string displayNameResource, int32 entityImageId)
0x4a03e  stloc.0
0x4a03f  ldloc.0
0x4a040  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_ReadActivity()
0x4a045  callvirt instance void Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo::set_Privileges(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition value)
0x4a04a  ldloc.0
0x4a04b  ldstr    aLoadareaThisAr// "loadArea(this, 'areaActivities');"
0x4a050  callvirt instance void Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo::set_Action(string value)
0x4a055  ldsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_campaign
0x4a05a  ldloc.0
0x4a05b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo>::Add(var<u1>)
0x4a060  ldsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_campaign
0x4a065  ldc.i4.0
0x4a066  ldstr    aNavcampaignact// "navCampaignActivities"
0x4a06b  ldc.i4   0x1132
0x4a070  ldc.i4.0
0x4a071  ldnull
0x4a072  newobj   instance void Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo::.ctor(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NavPaneArea area, string id, int32 objectTypeCode, [opt] int32 sequence, [opt] class Microsoft.Crm.Application.Utility.ITitleConstructor titleConstructor)
0x4a077  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo>::Add(var<u1>)
0x4a07c  ldc.i4.0
0x4a07d  ldstr    aNavcampaignres// "navCampaignResponses"
0x4a082  ldc.i4   0x1131
0x4a087  ldc.i4.0
0x4a088  ldnull
0x4a089  newobj   instance void Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo::.ctor(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NavPaneArea area, string id, int32 objectTypeCode, [opt] int32 sequence, [opt] class Microsoft.Crm.Application.Utility.ITitleConstructor titleConstructor)
0x4a08e  stloc.1
0x4a08f  ldloc.1
0x4a090  ldc.i4.6
0x4a091  callvirt instance void Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo::set_CustomLinkType(valuetype Microsoft.Crm.Application.Utility.CustomNavBarLinkType value)
0x4a096  ldsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_campaign
0x4a09b  ldloc.1
0x4a09c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo>::Add(var<u1>)
0x4a0a1  ldsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_campaign
0x4a0a6  ldc.i4.3
0x4a0a7  ldstr    aNavtargetlists// "navTargetLists"
0x4a0ac  ldc.i4   0x10CC
0x4a0b1  ldc.i4.0
0x4a0b2  ldstr    aTabLabelTarget// "Tab_Label_TargetLists"
0x4a0b7  ldnull
0x4a0b8  newobj   instance void Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo::.ctor(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NavPaneArea area, string id, int32 objectTypeCode, int32 sequence, string displayNameResource, [opt] class Microsoft.Crm.Application.Utility.ITitleConstructor titleConstructor)
0x4a0bd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo>::Add(var<u1>)
0x4a0c2  ldc.i4.3
0x4a0c3  ldstr    aNavcampaigns// "navCampaigns"
0x4a0c8  ldc.i4.0
0x4a0c9  ldc.i4.0
0x4a0ca  ldstr    aImgsIco18CampG// "/_imgs/ico_18_camp.gif"
0x4a0cf  ldstr    aTabLabelRelate// "Tab_Label_RelatedCampaigns"
0x4a0d4  ldc.i4   0x1130
0x4a0d9  newobj   instance void Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo::.ctor(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NavPaneArea area, string id, int32 objectTypeCode, int32 sequence, string iconPath, string displayNameResource, int32 entityImageId)
0x4a0de  stloc.2
0x4a0df  ldloc.2
0x4a0e0  ldstr    aLoadareaThisAr_0// "loadArea(this, 'areaRelatedCampaigns');"
0x4a0e5  callvirt instance void Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo::set_Action(string value)
0x4a0ea  ldsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_campaign
0x4a0ef  ldloc.2
0x4a0f0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo>::Add(var<u1>)
0x4a0f5  ldsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_campaign
0x4a0fa  ldc.i4.1
0x4a0fb  ldstr    aNavtargetprodu// "navTargetProducts"
0x4a100  ldc.i4   0x400
0x4a105  ldc.i4.0
0x4a106  ldstr    aTabLabelTarget_0// "Tab_Label_TargetProducts"
0x4a10b  ldnull
0x4a10c  newobj   instance void Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo::.ctor(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NavPaneArea area, string id, int32 objectTypeCode, int32 sequence, string displayNameResource, [opt] class Microsoft.Crm.Application.Utility.ITitleConstructor titleConstructor)
0x4a111  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo>::Add(var<u1>)
0x4a116  ldsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_campaign
0x4a11b  ldc.i4.1
0x4a11c  ldstr    aNavcollaterals// "navCollaterals"
0x4a121  ldc.i4   0x40E
0x4a126  ldc.i4.0
0x4a127  ldnull
0x4a128  newobj   instance void Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo::.ctor(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NavPaneArea area, string id, int32 objectTypeCode, [opt] int32 sequence, [opt] class Microsoft.Crm.Application.Utility.ITitleConstructor titleConstructor)
0x4a12d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo>::Add(var<u1>)
0x4a132  ldc.i4.4
0x4a133  ldstr    aNavwebleads// "navWebLeads"
0x4a138  ldc.i4.0
0x4a139  ldc.i4.0
0x4a13a  ldstr    aTabLabelWeblea// "Tab_Label_WebLeads"
0x4a13f  ldnull
0x4a140  newobj   instance void Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo::.ctor(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NavPaneArea area, string id, int32 objectTypeCode, int32 sequence, string displayNameResource, [opt] class Microsoft.Crm.Application.Utility.ITitleConstructor titleConstructor)
0x4a145  stloc.3
0x4a146  ldloc.3
0x4a147  ldc.i4.7
0x4a148  callvirt instance void Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo::set_CustomLinkType(valuetype Microsoft.Crm.Application.Utility.CustomNavBarLinkType value)
0x4a14d  ldsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_campaign
0x4a152  ldloc.3
0x4a153  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo>::Add(var<u1>)
0x4a158  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo>> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_relationshipListDictionary
0x4a15d  ldc.i4   0x1130
0x4a162  ldsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_campaign
0x4a167  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo>>::Add(var<u1>, !!T0)
0x4a16c  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo>::.ctor()
0x4a171  stsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_competitor
0x4a176  ldsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_competitor
0x4a17b  ldc.i4.1
0x4a17c  ldstr    aNavopportuniti// "navOpportunities"
0x4a181  ldc.i4.3
0x4a182  ldc.i4.0
0x4a183  ldnull
0x4a184  newobj   instance void Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo::.ctor(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NavPaneArea area, string id, int32 objectTypeCode, [opt] int32 sequence, [opt] class Microsoft.Crm.Application.Utility.ITitleConstructor titleConstructor)
0x4a189  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo>::Add(var<u1>)
0x4a18e  ldsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_competitor
0x4a193  ldc.i4.0
0x4a194  ldstr    aNavproducts// "navProducts"
0x4a199  ldc.i4   0x400
0x4a19e  ldc.i4.0
0x4a19f  ldnull
0x4a1a0  newobj   instance void Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo::.ctor(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NavPaneArea area, string id, int32 objectTypeCode, [opt] int32 sequence, [opt] class Microsoft.Crm.Application.Utility.ITitleConstructor titleConstructor)
0x4a1a5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo>::Add(var<u1>)
0x4a1aa  ldsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_competitor
0x4a1af  ldc.i4.1
0x4a1b0  ldstr    aNavsaleslit// "navSalesLit"
0x4a1b5  ldc.i4   0x40E
0x4a1ba  ldc.i4.0
0x4a1bb  ldnull
0x4a1bc  newobj   instance void Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo::.ctor(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NavPaneArea area, string id, int32 objectTypeCode, [opt] int32 sequence, [opt] class Microsoft.Crm.Application.Utility.ITitleConstructor titleConstructor)
0x4a1c1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo>::Add(var<u1>)
0x4a1c6  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo>> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_relationshipListDictionary
0x4a1cb  ldc.i4.s 0x7B
0x4a1cd  ldsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_competitor
0x4a1d2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo>>::Add(var<u1>, !!T0)
0x4a1d7  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo>::.ctor()
0x4a1dc  stsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_contractDetails
0x4a1e1  ldc.i4.2
0x4a1e2  ldstr    aNavcases// "navCases"
0x4a1e7  ldc.i4.s 0x70
0x4a1e9  ldstr    aImgsIco18112Gi// "/_imgs/ico_18_112.gif"
0x4a1ee  ldc.i4.0
0x4a1ef  newobj   instance void Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo::.ctor(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NavPaneArea area, string id, int32 objectTypeCode, string icon, int32 sequence)
0x4a1f4  stloc.s  4
0x4a1f6  ldloc.s  4
0x4a1f8  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_ReadContract()
0x4a1fd  callvirt instance void Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo::set_Privileges(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition value)
0x4a202  ldsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_contractDetails
0x4a207  ldloc.s  4
0x4a209  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo>::Add(var<u1>)
0x4a20e  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo>> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_relationshipListDictionary
0x4a213  ldc.i4   0x3F3
0x4a218  ldsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_contractDetails
0x4a21d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo>>::Add(var<u1>, !!T0)
0x4a222  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo>::.ctor()
0x4a227  stsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_contract
0x4a22c  ldsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_contract
0x4a231  ldc.i4.0
0x4a232  ldstr    aNavcontractlin// "navContractLines"
0x4a237  ldc.i4   0x3F3
0x4a23c  ldstr    aImgsIco181011G// "/_imgs/ico_18_1011.gif"
0x4a241  ldc.i4.0
0x4a242  newobj   instance void Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo::.ctor(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NavPaneArea area, string id, int32 objectTypeCode, string icon, int32 sequence)
0x4a247  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo>::Add(var<u1>)
0x4a24c  ldc.i4.2
0x4a24d  ldstr    aNavcases// "navCases"
0x4a252  ldc.i4.s 0x70
0x4a254  ldstr    aImgsIco18112Gi// "/_imgs/ico_18_112.gif"
0x4a259  ldc.i4.0
0x4a25a  newobj   instance void Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo::.ctor(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NavPaneArea area, string id, int32 objectTypeCode, string icon, int32 sequence)
0x4a25f  stloc.s  5
0x4a261  ldloc.s  5
0x4a263  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_ReadContract()
0x4a268  callvirt instance void Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo::set_Privileges(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition value)
0x4a26d  ldsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_contract
0x4a272  ldloc.s  5
0x4a274  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo>::Add(var<u1>)
0x4a279  ldc.i4.0
0x4a27a  ldstr    aNavactivities// "navActivities"
0x4a27f  ldc.i4   0x1068
0x4a284  ldstr    aImgsIco18ActGi// "/_imgs/ico_18_act.gif"
0x4a289  ldc.i4.0
0x4a28a  newobj   instance void Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo::.ctor(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NavPaneArea area, string id, int32 objectTypeCode, string icon, int32 sequence)
0x4a28f  stloc.s  6
0x4a291  ldloc.s  6
0x4a293  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_ReadActivity()
0x4a298  callvirt instance void Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo::set_Privileges(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition value)
0x4a29d  ldsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_contract
0x4a2a2  ldloc.s  6
0x4a2a4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo>::Add(var<u1>)
0x4a2a9  ldsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_contract
0x4a2ae  ldc.i4.0
0x4a2af  newobj   instance void Microsoft.Crm.Application.Components.Platform.ActivityHistoryNavArea::.ctor(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NavPaneArea areaId)
0x4a2b4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo>::Add(var<u1>)
0x4a2b9  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo>> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_relationshipListDictionary
0x4a2be  ldc.i4   0x3F2
0x4a2c3  ldsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_contract
0x4a2c8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo>>::Add(var<u1>, !!T0)
0x4a2cd  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo>::.ctor()
0x4a2d2  stsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_lead
0x4a2d7  ldsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_lead
0x4a2dc  ldc.i4.3
0x4a2dd  ldstr    aNavcampaignsin// "navCampaignsInSFA"
0x4a2e2  ldc.i4   0x1130
0x4a2e7  ldc.i4.s 0x14
0x4a2e9  ldnull
0x4a2ea  newobj   instance void Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo::.ctor(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NavPaneArea area, string id, int32 objectTypeCode, [opt] int32 sequence, [opt] class Microsoft.Crm.Application.Utility.ITitleConstructor titleConstructor)
0x4a2ef  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo>::Add(var<u1>)
0x4a2f4  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo>> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_relationshipListDictionary
0x4a2f9  ldc.i4.4
0x4a2fa  ldsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_lead
0x4a2ff  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo>>::Add(var<u1>, !!T0)
0x4a304  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo>::.ctor()
0x4a309  stsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_list
0x4a30e  ldc.i4.0
0x4a30f  ldstr    aNavlistmember// "navListMember"
0x4a314  ldc.i4.0
0x4a315  ldc.i4.0
0x4a316  ldstr    aImgsIco184301G// "/_imgs/ico_18_4301.gif"
0x4a31b  ldstr    aMaListListmemb// "MA.List.ListMember.Details.MarketingLis"...
0x4a320  ldc.i4   0x2657
0x4a325  newobj   instance void Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo::.ctor(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NavPaneArea area, string id, int32 objectTypeCode, int32 sequence, string iconPath, string displayNameResource, int32 entityImageId)
0x4a32a  stloc.s  7
0x4a32c  ldloc.s  7
0x4a32e  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_ReadList()
0x4a333  callvirt instance void Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo::set_Privileges(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition value)
0x4a338  ldloc.s  7
0x4a33a  ldstr    aLoadareaThisAr_1// "loadArea(this, 'areaListMember');"
0x4a33f  callvirt instance void Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo::set_Action(string value)
0x4a344  ldsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_list
0x4a349  ldloc.s  7
0x4a34b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo>::Add(var<u1>)
0x4a350  ldsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo> Microsoft.Crm.Application.Utility.EntitySpecificHardcodedRelationships::_list
0x4a355  ldc.i4.3
0x4a356  ldstr    aNavcampaignsin_0// "navCampaignsInList"
0x4a35b  ldc.i4   0x1130
0x4a360  ldc.i4.0
0x4a361  ldnull
0x4a362  newobj   instance void Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo::.ctor(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NavPaneArea area, string id, int32 objectTypeCode, [opt] int32 sequence, [opt] class Microsoft.Crm.Application.Utility.ITitleConstructor titleConstructor)
0x4a367  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.HardcodedNavRelationInfo>::Add(var<u1>)
0x4a36c  ldc.i4.3
  ... truncated ...
```
