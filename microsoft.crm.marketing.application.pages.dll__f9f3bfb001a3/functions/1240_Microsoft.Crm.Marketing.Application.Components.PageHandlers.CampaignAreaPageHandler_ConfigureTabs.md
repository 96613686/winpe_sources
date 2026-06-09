# Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignAreaPageHandler::ConfigureTabs

- ea: `0x1240`
- end: `0x157e`
- name: `Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignAreaPageHandler::ConfigureTabs`
- size: `830`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1240`
- `0x4170`

## pseudocode

```c

```

## disassembly

```asm
0x1240  ldarg.0
0x1241  call     instance string [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.AreaPageHandler::get_CurrentTabId()
0x1246  stloc.0
0x1247  ldloc.0
0x1248  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x124d  stloc.1
0x124e  ldloc.1
0x124f  ldc.i4   0x546D426D
0x1254  bgt.un.s loc_129C
0x1256  ldloc.1
0x1257  ldc.i4   0x13C967DB
0x125c  bgt.un.s loc_1279
0x125e  ldloc.1
0x125f  ldc.i4   0xF75E00C
0x1264  beq      loc_1357
0x1269  ldloc.1
0x126a  ldc.i4   0x13C967DB
0x126f  beq      loc_1342
0x1274  br       loc_1577
0x1279  ldloc.1
0x127a  ldc.i4   0x248758AE
0x127f  beq.s    loc_12D9
0x1281  ldloc.1
0x1282  ldc.i4   0x390F1BBE
0x1287  beq      loc_1381
0x128c  ldloc.1
0x128d  ldc.i4   0x546D426D
0x1292  beq      loc_136C
0x1297  br       loc_1577
0x129c  ldloc.1
0x129d  ldc.i4   0x6D8A6DEB
0x12a2  bgt.un.s loc_12B9
0x12a4  ldloc.1
0x12a5  ldc.i4   0x693D63A5
0x12aa  beq.s    loc_1303
0x12ac  ldloc.1
0x12ad  ldc.i4   0x6D8A6DEB
0x12b2  beq.s    loc_132D
0x12b4  br       loc_1577
0x12b9  ldloc.1
0x12ba  ldc.i4   0x700D1335
0x12bf  beq      loc_1396
0x12c4  ldloc.1
0x12c5  ldc.i4   0x8CFFF922
0x12ca  beq.s    loc_1318
0x12cc  ldloc.1
0x12cd  ldc.i4   0xB46D5B36
0x12d2  beq.s    loc_12EE
0x12d4  br       loc_1577
0x12d9  ldloc.0
0x12da  ldstr    aAreatargetlist// "areaTargetLists"
0x12df  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12e4  brtrue   loc_13AB
0x12e9  br       loc_1577
0x12ee  ldloc.0
0x12ef  ldstr    aArearelatedcam// "areaRelatedCampaigns"
0x12f4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12f9  brtrue   loc_13CA
0x12fe  br       loc_1577
0x1303  ldloc.0
0x1304  ldstr    aAreatargetprod// "areaTargetProducts"
0x1309  call     bool [mscorlib]System.String::op_Equality(string, string)
0x130e  brtrue   loc_13E9
0x1313  br       loc_1577
0x1318  ldloc.0
0x1319  ldstr    aAreacollateral// "areaCollaterals"
0x131e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1323  brtrue   loc_1408
0x1328  br       loc_1577
0x132d  ldloc.0
0x132e  ldstr    aAreacampaignac// "areaCampaignActivities"
0x1333  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1338  brtrue   loc_1427
0x133d  br       loc_1577
0x1342  ldloc.0
0x1343  ldstr    aAreaomcampaign// "areaOMCampaignActivities"
0x1348  call     bool [mscorlib]System.String::op_Equality(string, string)
0x134d  brtrue   loc_1444
0x1352  br       loc_1577
0x1357  ldloc.0
0x1358  ldstr    aOmwebleads// "OMWebLeads"
0x135d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1362  brtrue   loc_145C
0x1367  br       loc_1577
0x136c  ldloc.0
0x136d  ldstr    aOmwebleadsinac// "OMWebLeadsInactive"
0x1372  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1377  brtrue   loc_14CC
0x137c  br       loc_1577
0x1381  ldloc.0
0x1382  ldstr    aAreacampaignre// "areaCampaignResponses"
0x1387  call     bool [mscorlib]System.String::op_Equality(string, string)
0x138c  brtrue   loc_153D
0x1391  br       loc_1577
0x1396  ldloc.0
0x1397  ldstr    aAreaactivities// "areaActivities"
0x139c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x13a1  brtrue   loc_155A
0x13a6  br       loc_1577
0x13ab  ldarg.0
0x13ac  ldc.i4   0x10CC
0x13b1  ldstr    aBdd9354753f646// "{BDD93547-53F6-4609-B591-9F48CE86295F}"
0x13b6  ldstr    aCampaignRetrie// "Campaign.RetrieveRelatedEntities"
0x13bb  ldc.i4.2
0x13bc  ldstr    aCampaignlistAs// "campaignlist_association"
0x13c1  ldc.i4.0
0x13c2  ldc.i4.1
0x13c3  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AreaTab [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.AreaPageHandler::ConfigureAreaPage(int32, string, string, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.GridTypeCode, string, bool, int32)
0x13c8  pop
0x13c9  ret
0x13ca  ldarg.0
0x13cb  ldc.i4   0x1130
0x13d0  ldstr    a244af698F75348// "{244AF698-F753-48FD-9803-C1939DCF02D1}"
0x13d5  ldstr    aCampaignRetrie// "Campaign.RetrieveRelatedEntities"
0x13da  ldc.i4.2
0x13db  ldstr    aCampaigncampai// "campaigncampaign_association"
0x13e0  ldc.i4.0
0x13e1  ldc.i4.1
0x13e2  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AreaTab [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.AreaPageHandler::ConfigureAreaPage(int32, string, string, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.GridTypeCode, string, bool, int32)
0x13e7  pop
0x13e8  ret
0x13e9  ldarg.0
0x13ea  ldc.i4   0x400
0x13ef  ldstr    aF8de15f44c764a// "{F8DE15F4-4C76-4A21-94C9-A38FCAFDB73D}"
0x13f4  ldstr    aCampaignRetrie// "Campaign.RetrieveRelatedEntities"
0x13f9  ldc.i4.2
0x13fa  ldstr    aCampaignproduc// "campaignproduct_association"
0x13ff  ldc.i4.0
0x1400  ldc.i4.1
0x1401  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AreaTab [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.AreaPageHandler::ConfigureAreaPage(int32, string, string, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.GridTypeCode, string, bool, int32)
0x1406  pop
0x1407  ret
0x1408  ldarg.0
0x1409  ldc.i4   0x40E
0x140e  ldstr    a00000000000000_0// "{00000000-0000-0000-00aa-000010001113}"
0x1413  ldstr    aCampaignRetrie// "Campaign.RetrieveRelatedEntities"
0x1418  ldc.i4.2
0x1419  ldstr    aCampaignsalesl// "campaignsalesliterature_association"
0x141e  ldc.i4.0
0x141f  ldc.i4.1
0x1420  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AreaTab [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.AreaPageHandler::ConfigureAreaPage(int32, string, string, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.GridTypeCode, string, bool, int32)
0x1425  pop
0x1426  ret
0x1427  ldarg.0
0x1428  ldc.i4   0x1132
0x142d  ldstr    a89d107ab42f541// "{89D107AB-42F5-4164-B7D9-AA83CE170673}"
0x1432  ldstr    aCampaignRetrie_0// "Campaign.RetrieveCampaignActivitiesForC"...
0x1437  ldc.i4.1
0x1438  ldstr    aCampaignCampai// "Campaign_CampaignActivities"
0x143d  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AreaTab [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.AreaPageHandler::ConfigureAreaPage(int32, string, string, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.GridTypeCode, string)
0x1442  pop
0x1443  ret
0x1444  ldarg.0
0x1445  ldc.i4   0x1132
0x144a  ldstr    aCf1057a30e20Dd// "{cf1057a3-0e20-dd11-a897-00155d870408}"
0x144f  ldstr    aCampaignRetrie_0// "Campaign.RetrieveCampaignActivitiesForC"...
0x1454  ldc.i4.1
0x1455  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AreaTab [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.AreaPageHandler::ConfigureAreaPage(int32, string, string, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.GridTypeCode)
0x145a  pop
0x145b  ret
0x145c  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x1461  stloc.2
0x1462  ldloc.2
0x1463  ldstr    aRedirid// "redirId"
0x1468  ldc.i4.4
0x1469  stloc.s  4
0x146b  ldloca.s 4
0x146d  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x1472  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1477  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x147c  ldloc.2
0x147d  ldstr    aName// "name"
0x1482  ldstr    aOlm// "OLM"
0x1487  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x148c  ldloc.2
0x148d  ldstr    aObjecttypecode// "objecttypecode"
0x1492  ldarg.0
0x1493  call     instance string [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.AreaPageHandler::get_CurrentObjectTypeCode()
0x1498  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x149d  ldloc.2
0x149e  ldstr    aObjectid// "objectid"
0x14a3  ldarg.0
0x14a4  call     instance string [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.AreaPageHandler::get_CurrentObjectId()
0x14a9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x14ae  ldarg.0
0x14af  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.PageManager Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignAreaPageHandler::_pageManager
0x14b4  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x14b9  ldstr    aPartnerPartner// "/partner/partnerredir.aspx"
0x14be  ldloc.2
0x14bf  ldc.i4.0
0x14c0  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::AppendParameters(string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>, bool)
0x14c5  ldc.i4.1
0x14c6  callvirt instance void [System.Web]System.Web.HttpResponse::Redirect(string, bool)
0x14cb  ret
0x14cc  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x14d1  stloc.3
0x14d2  ldloc.3
0x14d3  ldstr    aRedirid// "redirId"
0x14d8  ldc.i4.s 0xC
0x14da  stloc.s  4
0x14dc  ldloca.s 4
0x14de  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x14e3  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x14e8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x14ed  ldloc.3
0x14ee  ldstr    aName// "name"
0x14f3  ldstr    aOlm// "OLM"
0x14f8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x14fd  ldloc.3
0x14fe  ldstr    aObjecttypecode// "objecttypecode"
0x1503  ldarg.0
0x1504  call     instance string [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.AreaPageHandler::get_CurrentObjectTypeCode()
0x1509  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x150e  ldloc.3
0x150f  ldstr    aObjectid// "objectid"
0x1514  ldarg.0
0x1515  call     instance string [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.AreaPageHandler::get_CurrentObjectId()
0x151a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x151f  ldarg.0
0x1520  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.PageManager Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignAreaPageHandler::_pageManager
0x1525  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x152a  ldstr    aPartnerPartner// "/partner/partnerredir.aspx"
0x152f  ldloc.3
0x1530  ldc.i4.0
0x1531  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::AppendParameters(string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>, bool)
0x1536  ldc.i4.1
0x1537  callvirt instance void [System.Web]System.Web.HttpResponse::Redirect(string, bool)
0x153c  ret
0x153d  ldarg.0
0x153e  ldc.i4   0x1131
0x1543  ldstr    a83300948D1184c// "{83300948-D118-4c6d-90B8-89F068290830}"
0x1548  ldstr    aCampaignRetrie_1// "Campaign.RetrieveCampaignResponsesForCa"...
0x154d  ldc.i4.1
0x154e  ldstr    aCampaignCampai_0// "Campaign_CampaignResponses"
0x1553  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AreaTab [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.AreaPageHandler::ConfigureAreaPage(int32, string, string, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.GridTypeCode, string)
0x1558  pop
0x1559  ret
0x155a  ldarg.0
0x155b  ldc.i4   0x1068
0x1560  ldstr    aF8d3a0d783ee47// "{F8D3A0D7-83EE-47B7-945C-C9463CBF380D}"
0x1565  ldstr    aCrmactivityRet// "CRMActivity.RetrieveByObject"
0x156a  ldc.i4.1
0x156b  ldstr    aCampaignActivi// "Campaign_ActivityPointers"
0x1570  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AreaTab [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.AreaPageHandler::ConfigureAreaPage(int32, string, string, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.GridTypeCode, string)
0x1575  pop
0x1576  ret
0x1577  ldarg.0
0x1578  call     instance void [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.AreaPageHandler::ConfigureTabs()
0x157d  ret
```
