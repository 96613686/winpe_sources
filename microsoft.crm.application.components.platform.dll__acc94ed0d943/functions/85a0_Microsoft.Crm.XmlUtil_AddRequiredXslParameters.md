# Microsoft.Crm.XmlUtil::AddRequiredXslParameters

- ea: `0x85a0`
- end: `0x8d37`
- name: `Microsoft.Crm.XmlUtil::AddRequiredXslParameters`
- size: `1943`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x8590`

## callees

- `0x85a0`
- `0x11760`
- `0x30260`
- `0x3aa00`
- `0x44f40`
- `0x6a120`
- `0x6a360`
- `0x9ca50`

## string_xrefs

- `0x867b`: `articlesLookupTemplate.xsl`
- `0x868c`: `articlesViewerComments.xsl`
- `0x86d0`: `kbTemplateEditor.xsl`
- `0x86f2`: `Web._grid.cmds.bulkemail.xsl_ServiceActivity`
- `0x86fd`: `Web._grid.cmds.bulkemail.xsl_ServiceActivity`
- `0x8887`: `Web._grid.cmds.bulkemail.xsl_TemplateAnalyticsNotAvailable`
- `0x8892`: `Web._grid.cmds.bulkemail.xsl_TemplateAnalyticsNotAvailable`
- `0x88a2`: `Web._grid.cmds.bulkemail.xsl_ReplyAndOpenRateMeasure`
- `0x88ad`: `Web._grid.cmds.bulkemail.xsl_ReplyAndOpenRateMeasure`
- `0x88bd`: `RecommendedTemplateIconTitle`
- `0x88c8`: `RecommendedTemplateIconTitle`
- `0x899b`: `internalTemplates`
- `0x89b7`: `CS.articles.Viewer.comments.xsl_1`
- `0x89c2`: `CS.articles.Viewer.comments.xsl_1`
- `0x89ee`: `ServiceActivitySingular`
- `0x8afe`: `TaskSingular`
- `0x8cc1`: `Tools.KBTemplateEditor.kbtemplateeditor.xsl_3`
- `0x8ccc`: `Tools.KBTemplateEditor.kbtemplateeditor.xsl_3`
- `0x8cdc`: `Tools.KBTemplateEditor.kbtemplateeditor.xsl_2`
- `0x8ce7`: `Tools.KBTemplateEditor.kbtemplateeditor.xsl_2`
- `0x8cf7`: `Tools.KBTemplateEditor.kbtemplateeditor.xsl_1`
- `0x8d02`: `Tools.KBTemplateEditor.kbtemplateeditor.xsl_1`

## pseudocode

```c

```

## disassembly

```asm
0x85a0  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x85a5  stloc.0
0x85a6  ldarg.1
0x85a7  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x85ac  stloc.1
0x85ad  ldloc.1
0x85ae  ldc.i4   0x4DD456A1
0x85b3  bgt.un.s loc_85F0
0x85b5  ldloc.1
0x85b6  ldc.i4   0x1A84014F
0x85bb  bgt.un.s loc_85D4
0x85bd  ldloc.1
0x85be  ldc.i4   0x1802D029
0x85c3  beq      loc_869C
0x85c8  ldloc.1
0x85c9  ldc.i4   0x1A84014F
0x85ce  beq      loc_868B
0x85d3  ret
0x85d4  ldloc.1
0x85d5  ldc.i4   0x2A0CEC1F
0x85da  beq.s    loc_8647
0x85dc  ldloc.1
0x85dd  ldc.i4   0x2EC84B5A
0x85e2  beq      loc_8669
0x85e7  ldloc.1
0x85e8  ldc.i4   0x4DD456A1
0x85ed  beq.s    loc_8636
0x85ef  ret
0x85f0  ldloc.1
0x85f1  ldc.i4   0x7AF6D24C
0x85f6  bgt.un.s loc_8617
0x85f8  ldloc.1
0x85f9  ldc.i4   0x6B3FB3F4
0x85fe  beq      loc_86AD
0x8603  ldloc.1
0x8604  ldc.i4   0x79CD2B13
0x8609  beq      loc_86BE
0x860e  ldloc.1
0x860f  ldc.i4   0x7AF6D24C
0x8614  beq.s    loc_8658
0x8616  ret
0x8617  ldloc.1
0x8618  ldc.i4   0xA49DD50E
0x861d  beq      loc_86E0
0x8622  ldloc.1
0x8623  ldc.i4   0xACBA2E73
0x8628  beq.s    loc_867A
0x862a  ldloc.1
0x862b  ldc.i4   0xB43FD542
0x8630  beq      loc_86CF
0x8635  ret
0x8636  ldarg.1
0x8637  ldstr    aGridcmdsbulkem// "gridCmdsBulkEmail.xsl"
0x863c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8641  brtrue   loc_86F1
0x8646  ret
0x8647  ldarg.1
0x8648  ldstr    aGridcmdsemails// "gridCmdsEmailSignature.xsl"
0x864d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8652  brtrue   loc_88F5
0x8657  ret
0x8658  ldarg.1
0x8659  ldstr    aControlsnaviga// "controlsNavigationMap.xsl"
0x865e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8663  brtrue   loc_8911
0x8668  ret
0x8669  ldarg.1
0x866a  ldstr    aArticleseditco// "articlesEditContent.xsl"
0x866f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8674  brtrue   loc_8963
0x8679  ret
0x867a  ldarg.1
0x867b  ldstr    aArticleslookup// "articlesLookupTemplate.xsl"
0x8680  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8685  brtrue   loc_899A
0x868a  ret
0x868b  ldarg.1
0x868c  ldstr    aArticlesviewer// "articlesViewerComments.xsl"
0x8691  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8696  brtrue   loc_89B6
0x869b  ret
0x869c  ldarg.1
0x869d  ldstr    aHomepagecrmtod// "homepageCrmToday.xsl"
0x86a2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x86a7  brtrue   loc_89D2
0x86ac  ret
0x86ad  ldarg.1
0x86ae  ldstr    aHomepagenewsar// "homepageNewsArticles.xsl"
0x86b3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x86b8  brtrue   loc_8C13
0x86bd  ret
0x86be  ldarg.1
0x86bf  ldstr    aFormeditorXsl// "formEditor.xsl"
0x86c4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x86c9  brtrue   loc_8C65
0x86ce  ret
0x86cf  ldarg.1
0x86d0  ldstr    aKbtemplateedit// "kbTemplateEditor.xsl"
0x86d5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x86da  brtrue   loc_8CC0
0x86df  ret
0x86e0  ldarg.1
0x86e1  ldstr    aTreesubjectXsl// "treeSubject.xsl"
0x86e6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x86eb  brtrue   loc_8D12
0x86f0  ret
0x86f1  ldarg.0
0x86f2  ldstr    aWebGridCmdsBul// "Web._grid.cmds.bulkemail.xsl_ServiceAct"...
0x86f7  ldstr    asc_A9652// ""
0x86fc  ldloc.0
0x86fd  ldstr    aWebGridCmdsBul// "Web._grid.cmds.bulkemail.xsl_ServiceAct"...
0x8702  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x8707  callvirt instance void [System.Xml]System.Xml.Xsl.XsltArgumentList::AddParam(string, string, object)
0x870c  ldarg.0
0x870d  ldstr    aWebGridCmdsBul_0// "Web._grid.cmds.bulkemail.xsl_CampaignAc"...
0x8712  ldstr    asc_A9652// ""
0x8717  ldloc.0
0x8718  ldstr    aWebGridCmdsBul_0// "Web._grid.cmds.bulkemail.xsl_CampaignAc"...
0x871d  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x8722  callvirt instance void [System.Xml]System.Xml.Xsl.XsltArgumentList::AddParam(string, string, object)
0x8727  ldarg.0
0x8728  ldstr    aWebGridCmdsBul_1// "Web._grid.cmds.bulkemail.xsl_106"
0x872d  ldstr    asc_A9652// ""
0x8732  ldloc.0
0x8733  ldstr    aWebGridCmdsBul_1// "Web._grid.cmds.bulkemail.xsl_106"
0x8738  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x873d  callvirt instance void [System.Xml]System.Xml.Xsl.XsltArgumentList::AddParam(string, string, object)
0x8742  ldarg.0
0x8743  ldstr    aWebGridCmdsBul_2// "Web._grid.cmds.bulkemail.xsl_96"
0x8748  ldstr    asc_A9652// ""
0x874d  ldloc.0
0x874e  ldstr    aWebGridCmdsBul_2// "Web._grid.cmds.bulkemail.xsl_96"
0x8753  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x8758  callvirt instance void [System.Xml]System.Xml.Xsl.XsltArgumentList::AddParam(string, string, object)
0x875d  ldarg.0
0x875e  ldstr    aWebGridCmdsBul_3// "Web._grid.cmds.bulkemail.xsl_86"
0x8763  ldstr    asc_A9652// ""
0x8768  ldloc.0
0x8769  ldstr    aWebGridCmdsBul_3// "Web._grid.cmds.bulkemail.xsl_86"
0x876e  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x8773  callvirt instance void [System.Xml]System.Xml.Xsl.XsltArgumentList::AddParam(string, string, object)
0x8778  ldarg.0
0x8779  ldstr    aWebGridCmdsBul_4// "Web._grid.cmds.bulkemail.xsl_76"
0x877e  ldstr    asc_A9652// ""
0x8783  ldloc.0
0x8784  ldstr    aWebGridCmdsBul_4// "Web._grid.cmds.bulkemail.xsl_76"
0x8789  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x878e  callvirt instance void [System.Xml]System.Xml.Xsl.XsltArgumentList::AddParam(string, string, object)
0x8793  ldarg.0
0x8794  ldstr    aWebGridCmdsBul_5// "Web._grid.cmds.bulkemail.xsl_66"
0x8799  ldstr    asc_A9652// ""
0x879e  ldloc.0
0x879f  ldstr    aWebGridCmdsBul_5// "Web._grid.cmds.bulkemail.xsl_66"
0x87a4  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x87a9  callvirt instance void [System.Xml]System.Xml.Xsl.XsltArgumentList::AddParam(string, string, object)
0x87ae  ldarg.0
0x87af  ldstr    aWebGridCmdsBul_6// "Web._grid.cmds.bulkemail.xsl_56"
0x87b4  ldstr    asc_A9652// ""
0x87b9  ldloc.0
0x87ba  ldstr    aWebGridCmdsBul_6// "Web._grid.cmds.bulkemail.xsl_56"
0x87bf  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x87c4  callvirt instance void [System.Xml]System.Xml.Xsl.XsltArgumentList::AddParam(string, string, object)
0x87c9  ldarg.0
0x87ca  ldstr    aWebGridCmdsBul_7// "Web._grid.cmds.bulkemail.xsl_46"
0x87cf  ldstr    asc_A9652// ""
0x87d4  ldloc.0
0x87d5  ldstr    aWebGridCmdsBul_7// "Web._grid.cmds.bulkemail.xsl_46"
0x87da  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x87df  callvirt instance void [System.Xml]System.Xml.Xsl.XsltArgumentList::AddParam(string, string, object)
0x87e4  ldarg.0
0x87e5  ldstr    aWebGridCmdsBul_8// "Web._grid.cmds.bulkemail.xsl_36"
0x87ea  ldstr    asc_A9652// ""
0x87ef  ldloc.0
0x87f0  ldstr    aWebGridCmdsBul_8// "Web._grid.cmds.bulkemail.xsl_36"
0x87f5  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x87fa  callvirt instance void [System.Xml]System.Xml.Xsl.XsltArgumentList::AddParam(string, string, object)
0x87ff  ldarg.0
0x8800  ldstr    aWebGridCmdsBul_9// "Web._grid.cmds.bulkemail.xsl_18"
0x8805  ldstr    asc_A9652// ""
0x880a  ldloc.0
0x880b  ldstr    aWebGridCmdsBul_9// "Web._grid.cmds.bulkemail.xsl_18"
0x8810  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x8815  callvirt instance void [System.Xml]System.Xml.Xsl.XsltArgumentList::AddParam(string, string, object)
0x881a  ldarg.0
0x881b  ldstr    aWebGridCmdsBul_10// "Web._grid.cmds.bulkemail.xsl_12"
0x8820  ldstr    asc_A9652// ""
0x8825  ldloc.0
0x8826  ldstr    aWebGridCmdsBul_10// "Web._grid.cmds.bulkemail.xsl_12"
0x882b  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x8830  callvirt instance void [System.Xml]System.Xml.Xsl.XsltArgumentList::AddParam(string, string, object)
0x8835  ldarg.0
0x8836  ldstr    aWebGridCmdsBul_11// "Web._grid.cmds.bulkemail.xsl_06"
0x883b  ldstr    asc_A9652// ""
0x8840  ldloc.0
0x8841  ldstr    aWebGridCmdsBul_11// "Web._grid.cmds.bulkemail.xsl_06"
0x8846  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x884b  callvirt instance void [System.Xml]System.Xml.Xsl.XsltArgumentList::AddParam(string, string, object)
0x8850  ldarg.0
0x8851  ldstr    aWebGridCmdsBul_12// "Web._grid.cmds.bulkemail.xsl_08"
0x8856  ldstr    asc_A9652// ""
0x885b  ldloc.0
0x885c  ldstr    aWebGridCmdsBul_12// "Web._grid.cmds.bulkemail.xsl_08"
0x8861  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x8866  callvirt instance void [System.Xml]System.Xml.Xsl.XsltArgumentList::AddParam(string, string, object)
0x886b  ldarg.0
0x886c  ldstr    aWebGridCmdsBul_13// "Web._grid.cmds.bulkemail.xsl_AsyncEmail"
0x8871  ldstr    asc_A9652// ""
0x8876  ldloc.0
0x8877  ldstr    aWebGridCmdsBul_13// "Web._grid.cmds.bulkemail.xsl_AsyncEmail"
0x887c  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x8881  callvirt instance void [System.Xml]System.Xml.Xsl.XsltArgumentList::AddParam(string, string, object)
0x8886  ldarg.0
0x8887  ldstr    aWebGridCmdsBul_14// "Web._grid.cmds.bulkemail.xsl_TemplateAn"...
0x888c  ldstr    asc_A9652// ""
0x8891  ldloc.0
0x8892  ldstr    aWebGridCmdsBul_14// "Web._grid.cmds.bulkemail.xsl_TemplateAn"...
0x8897  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x889c  callvirt instance void [System.Xml]System.Xml.Xsl.XsltArgumentList::AddParam(string, string, object)
0x88a1  ldarg.0
0x88a2  ldstr    aWebGridCmdsBul_15// "Web._grid.cmds.bulkemail.xsl_ReplyAndOp"...
0x88a7  ldstr    asc_A9652// ""
0x88ac  ldloc.0
0x88ad  ldstr    aWebGridCmdsBul_15// "Web._grid.cmds.bulkemail.xsl_ReplyAndOp"...
0x88b2  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x88b7  callvirt instance void [System.Xml]System.Xml.Xsl.XsltArgumentList::AddParam(string, string, object)
0x88bc  ldarg.0
0x88bd  ldstr    aRecommendedtem// "RecommendedTemplateIconTitle"
0x88c2  ldstr    asc_A9652// ""
0x88c7  ldloc.0
0x88c8  ldstr    aRecommendedtem// "RecommendedTemplateIconTitle"
0x88cd  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x88d2  callvirt instance void [System.Xml]System.Xml.Xsl.XsltArgumentList::AddParam(string, string, object)
0x88d7  ldarg.2
0x88d8  call     bool Microsoft.Crm.Application.Utility.Util::IsEmailEngagementFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x88dd  stloc.2
0x88de  ldarg.0
0x88df  ldstr    aIsemailengagem// "IsEmailEngagementFeatureEnabled"
0x88e4  ldstr    asc_A9652// ""
0x88e9  ldloc.2
0x88ea  box      [mscorlib]System.Boolean
0x88ef  callvirt instance void [System.Xml]System.Xml.Xsl.XsltArgumentList::AddParam(string, string, object)
0x88f4  ret
0x88f5  ldarg.0
0x88f6  ldstr    aWebGridCmdsEma// "Web._grid.cmds.emailsignature.xsl_01"
0x88fb  ldstr    asc_A9652// ""
0x8900  ldloc.0
0x8901  ldstr    aWebGridCmdsEma// "Web._grid.cmds.emailsignature.xsl_01"
0x8906  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x890b  callvirt instance void [System.Xml]System.Xml.Xsl.XsltArgumentList::AddParam(string, string, object)
0x8910  ret
0x8911  ldarg.0
0x8912  ldstr    aWebControlsNav// "Web._controls.navigation.map.xsl_155"
0x8917  ldstr    asc_A9652// ""
0x891c  ldloc.0
0x891d  ldstr    aWebControlsNav// "Web._controls.navigation.map.xsl_155"
0x8922  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x8927  callvirt instance void [System.Xml]System.Xml.Xsl.XsltArgumentList::AddParam(string, string, object)
0x892c  ldarg.0
0x892d  ldstr    aWebControlsNav_0// "Web._controls.navigation.map.xsl_98"
0x8932  ldstr    asc_A9652// ""
0x8937  ldloc.0
0x8938  ldstr    aWebControlsNav_0// "Web._controls.navigation.map.xsl_98"
0x893d  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x8942  callvirt instance void [System.Xml]System.Xml.Xsl.XsltArgumentList::AddParam(string, string, object)
0x8947  ldarg.0
0x8948  ldstr    aWebControlsNav_1// "Web.Controls.Navigation.Map.xsl_1"
0x894d  ldstr    asc_A9652// ""
0x8952  ldloc.0
0x8953  ldstr    aWebControlsNav_1// "Web.Controls.Navigation.Map.xsl_1"
0x8958  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x895d  callvirt instance void [System.Xml]System.Xml.Xsl.XsltArgumentList::AddParam(string, string, object)
0x8962  ret
0x8963  ldarg.0
0x8964  ldstr    aCsArticlesEdit// "CS.articles.edit_content.xsl_2"
0x8969  ldstr    asc_A9652// ""
0x896e  ldloc.0
0x896f  ldstr    aCsArticlesEdit// "CS.articles.edit_content.xsl_2"
0x8974  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x8979  callvirt instance void [System.Xml]System.Xml.Xsl.XsltArgumentList::AddParam(string, string, object)
0x897e  ldarg.0
0x897f  ldstr    aCsArticlesEdit_0// "CS.articles.edit_content.xsl_1"
0x8984  ldstr    asc_A9652// ""
0x8989  ldloc.0
0x898a  ldstr    aCsArticlesEdit_0// "CS.articles.edit_content.xsl_1"
0x898f  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x8994  callvirt instance void [System.Xml]System.Xml.Xsl.XsltArgumentList::AddParam(string, string, object)
0x8999  ret
0x899a  ldarg.0
0x899b  ldstr    aInternaltempla// "internalTemplates"
0x89a0  ldstr    asc_A9652// ""
0x89a5  ldloc.0
0x89a6  ldstr    a627e093bB79e42// "627E093B-B79E-4269-BA54-475C298484D2"
0x89ab  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x89b0  callvirt instance void [System.Xml]System.Xml.Xsl.XsltArgumentList::AddParam(string, string, object)
0x89b5  ret
0x89b6  ldarg.0
0x89b7  ldstr    aCsArticlesView// "CS.articles.Viewer.comments.xsl_1"
0x89bc  ldstr    asc_A9652// ""
0x89c1  ldloc.0
0x89c2  ldstr    aCsArticlesView// "CS.articles.Viewer.comments.xsl_1"
  ... truncated ...
```
