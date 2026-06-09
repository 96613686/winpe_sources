# Microsoft.Crm.Controls.PageResourceManager::AddWrpcUrls

- ea: `0x4c80`
- end: `0x4f15`
- name: `Microsoft.Crm.Controls.PageResourceManager::AddWrpcUrls`
- size: `661`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x79c0`
- `0x7a90`

## callees

- `0x35b0`
- `0x4c60`
- `0x4c80`

## string_xrefs

- `0x4d0b`: `/_common/styles/select.css.aspx`
- `0x4cc8`: `ActivitiesWebService`
- `0x4dbc`: `ActivitiesWebService`
- `0x4dd4`: `ActivitiesWebService`
- `0x4dec`: `ActivitiesWebService`
- `0x4e4c`: `ActivitiesWebService`
- `0x4e6f`: `ActivitiesWebService`
- `0x4cfb`: `LookupService`
- `0x4d74`: `SavedQuerySelectorWebService`
- `0x4d8c`: `AppGridWebService`
- `0x4df7`: `/_static/advancedfind/cachemanager.js`
- `0x4e34`: `Service`
- `0x4e64`: `GanttControlWebService`
- `0x4ecd`: `/_static/tools/solution/scripts/solutioncomponentlist.js`
- `0x4f0a`: `SocialInsightsWebService`

## pseudocode

```c

```

## disassembly

```asm
0x4c80  ldarg.0
0x4c81  ldstr    aStaticControls_6// "/_static/_controls/attachment/attachmen"...
0x4c86  call     instance bool Microsoft.Crm.Controls.PageResourceManager::IsScriptFileLoaded(string scriptFilePath)
0x4c8b  brfalse.s loc_4C98
0x4c8d  ldarg.0
0x4c8e  ldstr    aAnnotation// "Annotation"
0x4c93  call     instance void Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string webServiceName)
0x4c98  ldarg.0
0x4c99  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri> Microsoft.Crm.Controls.PageResourceManager::_styles
0x4c9e  ldstr    aControlsNotesN// "/_controls/notes/notes.css.aspx"
0x4ca3  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri>::ContainsKey(var<u1>)
0x4ca8  brfalse.s loc_4CB5
0x4caa  ldarg.0
0x4cab  ldstr    aAnnotation// "Annotation"
0x4cb0  call     instance void Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string webServiceName)
0x4cb5  ldarg.0
0x4cb6  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri> Microsoft.Crm.Controls.PageResourceManager::_styles
0x4cbb  ldstr    aControlsRelate// "/_controls/relatedinformation/relatedin"...
0x4cc0  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri>::ContainsKey(var<u1>)
0x4cc5  brfalse.s loc_4CE8
0x4cc7  ldarg.0
0x4cc8  ldstr    aActivitieswebs// "ActivitiesWebService"
0x4ccd  call     instance void Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string webServiceName)
0x4cd2  ldarg.0
0x4cd3  ldstr    aRelatedinforma_5// "RelatedInformation"
0x4cd8  call     instance void Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string webServiceName)
0x4cdd  ldarg.0
0x4cde  ldstr    aSubjectmanager// "SubjectManager"
0x4ce3  call     instance void Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string webServiceName)
0x4ce8  ldarg.0
0x4ce9  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri> Microsoft.Crm.Controls.PageResourceManager::_styles
0x4cee  ldstr    aFormsControlsC// "/_forms/controls/controls.css.aspx"
0x4cf3  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri>::ContainsKey(var<u1>)
0x4cf8  brfalse.s loc_4D05
0x4cfa  ldarg.0
0x4cfb  ldstr    aLookupservice// "LookupService"
0x4d00  call     instance void Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string webServiceName)
0x4d05  ldarg.0
0x4d06  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri> Microsoft.Crm.Controls.PageResourceManager::_styles
0x4d0b  ldstr    aCommonStylesSe// "/_common/styles/select.css.aspx"
0x4d10  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri>::ContainsKey(var<u1>)
0x4d15  brfalse.s loc_4D22
0x4d17  ldarg.0
0x4d18  ldstr    aRelationshipro// "RelationshipRolePicklist"
0x4d1d  call     instance void Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string webServiceName)
0x4d22  ldarg.0
0x4d23  ldstr    aStaticGridActi// "/_static/_grid/action.js"
0x4d28  call     instance bool Microsoft.Crm.Controls.PageResourceManager::IsScriptFileLoaded(string scriptFilePath)
0x4d2d  brfalse.s loc_4D5B
0x4d2f  ldarg.0
0x4d30  ldstr    aUserquery// "UserQuery"
0x4d35  call     instance void Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string webServiceName)
0x4d3a  ldarg.0
0x4d3b  ldstr    aMarketingautom// "MarketingAutomation"
0x4d40  call     instance void Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string webServiceName)
0x4d45  ldarg.0
0x4d46  ldstr    aDuplicatedetec// "DuplicateDetection"
0x4d4b  call     instance void Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string webServiceName)
0x4d50  ldarg.0
0x4d51  ldstr    aAssociaterecor// "AssociateRecords"
0x4d56  call     instance void Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string webServiceName)
0x4d5b  ldarg.0
0x4d5c  ldstr    aStaticControls_7// "/_static/_controls/gridfilters/gridfilt"...
0x4d61  call     instance bool Microsoft.Crm.Controls.PageResourceManager::IsScriptFileLoaded(string scriptFilePath)
0x4d66  brfalse.s loc_4D7E
0x4d68  ldarg.0
0x4d69  ldstr    aAdvancedfind// "AdvancedFind"
0x4d6e  call     instance void Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string webServiceName)
0x4d73  ldarg.0
0x4d74  ldstr    aSavedquerysele// "SavedQuerySelectorWebService"
0x4d79  call     instance void Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string webServiceName)
0x4d7e  ldarg.0
0x4d7f  ldstr    aGridAppgridCss// "/_grid/appgrid.css.aspx"
0x4d84  call     instance bool Microsoft.Crm.Controls.PageResourceManager::IsScriptFileLoaded(string scriptFilePath)
0x4d89  brfalse.s loc_4D96
0x4d8b  ldarg.0
0x4d8c  ldstr    aAppgridwebserv// "AppGridWebService"
0x4d91  call     instance void Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string webServiceName)
0x4d96  ldarg.0
0x4d97  ldstr    aTreeFulltreeCs// "/_tree/fulltree.css.aspx"
0x4d9c  call     instance bool Microsoft.Crm.Controls.PageResourceManager::IsScriptFileLoaded(string scriptFilePath)
0x4da1  brfalse.s loc_4DAE
0x4da3  ldarg.0
0x4da4  ldstr    aSubjectmanager// "SubjectManager"
0x4da9  call     instance void Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string webServiceName)
0x4dae  ldarg.0
0x4daf  ldstr    aStaticActiviti// "/_static/activities/activity.js"
0x4db4  call     instance bool Microsoft.Crm.Controls.PageResourceManager::IsScriptFileLoaded(string scriptFilePath)
0x4db9  brfalse.s loc_4DC6
0x4dbb  ldarg.0
0x4dbc  ldstr    aActivitieswebs// "ActivitiesWebService"
0x4dc1  call     instance void Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string webServiceName)
0x4dc6  ldarg.0
0x4dc7  ldstr    aStaticSfaSales// "/_static/sfa/saleslit/saleslit.js"
0x4dcc  call     instance bool Microsoft.Crm.Controls.PageResourceManager::IsScriptFileLoaded(string scriptFilePath)
0x4dd1  brfalse.s loc_4DDE
0x4dd3  ldarg.0
0x4dd4  ldstr    aActivitieswebs// "ActivitiesWebService"
0x4dd9  call     instance void Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string webServiceName)
0x4dde  ldarg.0
0x4ddf  ldstr    aStaticActiviti_0// "/_static/activities/activityscheduling."...
0x4de4  call     instance bool Microsoft.Crm.Controls.PageResourceManager::IsScriptFileLoaded(string scriptFilePath)
0x4de9  brfalse.s loc_4DF6
0x4deb  ldarg.0
0x4dec  ldstr    aActivitieswebs// "ActivitiesWebService"
0x4df1  call     instance void Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string webServiceName)
0x4df6  ldarg.0
0x4df7  ldstr    aStaticAdvanced// "/_static/advancedfind/cachemanager.js"
0x4dfc  call     instance bool Microsoft.Crm.Controls.PageResourceManager::IsScriptFileLoaded(string scriptFilePath)
0x4e01  brfalse.s loc_4E0E
0x4e03  ldarg.0
0x4e04  ldstr    aAdvancedfind// "AdvancedFind"
0x4e09  call     instance void Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string webServiceName)
0x4e0e  ldarg.0
0x4e0f  ldstr    aStaticMaListsL// "/_static/ma/lists/listqualificationdlg/"...
0x4e14  call     instance bool Microsoft.Crm.Controls.PageResourceManager::IsScriptFileLoaded(string scriptFilePath)
0x4e19  brfalse.s loc_4E26
0x4e1b  ldarg.0
0x4e1c  ldstr    aMarketingautom// "MarketingAutomation"
0x4e21  call     instance void Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string webServiceName)
0x4e26  ldarg.0
0x4e27  ldstr    aStaticSmActivi// "/_static/sm/activityscheduling/scheduli"...
0x4e2c  call     instance bool Microsoft.Crm.Controls.PageResourceManager::IsScriptFileLoaded(string scriptFilePath)
0x4e31  brfalse.s loc_4E3E
0x4e33  ldarg.0
0x4e34  ldstr    aService// "Service"
0x4e39  call     instance void Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string webServiceName)
0x4e3e  ldarg.0
0x4e3f  ldstr    aStaticSmApptbo// "/_static/sm/apptbook/apptbook.js"
0x4e44  call     instance bool Microsoft.Crm.Controls.PageResourceManager::IsScriptFileLoaded(string scriptFilePath)
0x4e49  brfalse.s loc_4E56
0x4e4b  ldarg.0
0x4e4c  ldstr    aActivitieswebs// "ActivitiesWebService"
0x4e51  call     instance void Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string webServiceName)
0x4e56  ldarg.0
0x4e57  ldstr    aStaticSmApptbo_0// "/_static/sm/apptbook/gantt.js"
0x4e5c  call     instance bool Microsoft.Crm.Controls.PageResourceManager::IsScriptFileLoaded(string scriptFilePath)
0x4e61  brfalse.s loc_4E79
0x4e63  ldarg.0
0x4e64  ldstr    aGanttcontrolwe// "GanttControlWebService"
0x4e69  call     instance void Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string webServiceName)
0x4e6e  ldarg.0
0x4e6f  ldstr    aActivitieswebs// "ActivitiesWebService"
0x4e74  call     instance void Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string webServiceName)
0x4e79  ldarg.0
0x4e7a  ldstr    aStaticSmResour_0// "/_static/sm/resourcegroups/items.js"
0x4e7f  call     instance bool Microsoft.Crm.Controls.PageResourceManager::IsScriptFileLoaded(string scriptFilePath)
0x4e84  brfalse.s loc_4E91
0x4e86  ldarg.0
0x4e87  ldstr    aResourcegroupu// "ResourceGroupUI"
0x4e8c  call     instance void Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string webServiceName)
0x4e91  ldarg.0
0x4e92  ldstr    aStaticSmResour_1// "/_static/sm/resourcegroups/resourcegrou"...
0x4e97  call     instance bool Microsoft.Crm.Controls.PageResourceManager::IsScriptFileLoaded(string scriptFilePath)
0x4e9c  brfalse.s loc_4EB4
0x4e9e  ldarg.0
0x4e9f  ldstr    aResourcegroupu// "ResourceGroupUI"
0x4ea4  call     instance void Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string webServiceName)
0x4ea9  ldarg.0
0x4eaa  ldstr    aResourcespectr// "ResourceSpecTree"
0x4eaf  call     instance void Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string webServiceName)
0x4eb4  ldarg.0
0x4eb5  ldstr    aStaticSmResour// "/_static/sm/resourcespecs/resourcespecu"...
0x4eba  call     instance bool Microsoft.Crm.Controls.PageResourceManager::IsScriptFileLoaded(string scriptFilePath)
0x4ebf  brfalse.s loc_4ECC
0x4ec1  ldarg.0
0x4ec2  ldstr    aResourcespectr// "ResourceSpecTree"
0x4ec7  call     instance void Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string webServiceName)
0x4ecc  ldarg.0
0x4ecd  ldstr    aStaticToolsSol// "/_static/tools/solution/scripts/solutio"...
0x4ed2  call     instance bool Microsoft.Crm.Controls.PageResourceManager::IsScriptFileLoaded(string scriptFilePath)
0x4ed7  brfalse.s loc_4EE4
0x4ed9  ldarg.0
0x4eda  ldstr    aSolution// "Solution"
0x4edf  call     instance void Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string webServiceName)
0x4ee4  ldarg.0
0x4ee5  ldstr    aStaticToolsPer// "/_static/tools/personalsettings/scripts"...
0x4eea  call     instance bool Microsoft.Crm.Controls.PageResourceManager::IsScriptFileLoaded(string scriptFilePath)
0x4eef  brfalse.s loc_4EFC
0x4ef1  ldarg.0
0x4ef2  ldstr    aUserentityuise// "UserEntityUISettings"
0x4ef7  call     instance void Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string webServiceName)
0x4efc  ldarg.0
0x4efd  ldstr    aStaticControls_8// "/_static/_controls/socialinsights/socia"...
0x4f02  call     instance bool Microsoft.Crm.Controls.PageResourceManager::IsScriptFileLoaded(string scriptFilePath)
0x4f07  brfalse.s loc_4F14
0x4f09  ldarg.0
0x4f0a  ldstr    aSocialinsights// "SocialInsightsWebService"
0x4f0f  call     instance void Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string webServiceName)
0x4f14  ret
```
