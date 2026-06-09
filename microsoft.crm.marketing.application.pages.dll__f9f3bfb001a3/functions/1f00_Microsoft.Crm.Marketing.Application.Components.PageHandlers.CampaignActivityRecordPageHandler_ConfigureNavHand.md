# Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignActivityRecordPageHandler::ConfigureNavHandler

- ea: `0x1f00`
- end: `0x20db`
- name: `Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignActivityRecordPageHandler::ConfigureNavHandler`
- size: `475`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1f00`

## string_xrefs

- `0x1f6b`: `Configuring Nav for channel type = {0}`

## pseudocode

```c

```

## disassembly

```asm
0x1f00  ldarg.0
0x1f01  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentForm()
0x1f06  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.NavPaneItems [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_NavPaneItems()
0x1f0b  stloc.0
0x1f0c  ldarg.0
0x1f0d  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppNavigationBar [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmNavBar()
0x1f12  stloc.1
0x1f13  ldsfld   string [mscorlib]System.String::Empty
0x1f18  stloc.2
0x1f19  ldarg.0
0x1f1a  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableForm Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignActivityRecordPageHandler::crmCustomizableForm
0x1f1f  ldstr    aChanneltypecod// "channeltypecode"
0x1f24  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0x1f29  brfalse  loc_20AC
0x1f2e  ldarg.0
0x1f2f  call     instance class [System.Web]System.Web.HttpRequest [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_Request()
0x1f34  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1f39  ldstr    aId// "id"
0x1f3e  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1f43  brfalse  loc_20AC
0x1f48  ldarg.0
0x1f49  ldfld    bool Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignActivityRecordPageHandler::propFlag
0x1f4e  brfalse  loc_20AC
0x1f53  ldsfld   string [mscorlib]System.String::Empty
0x1f58  stloc.3
0x1f59  ldc.i4.0
0x1f5a  stloc.s  4
0x1f5c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1f61  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x1f66  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x1f6b  ldstr    aConfiguringNav// "Configuring Nav for channel type = {0}"
0x1f70  ldc.i4.1
0x1f71  newarr   [mscorlib]System.Object
0x1f76  dup
0x1f77  ldc.i4.0
0x1f78  ldarg.0
0x1f79  ldfld    int32 Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignActivityRecordPageHandler::channelType
0x1f7e  box      [mscorlib]System.Int32
0x1f83  stelem.ref
0x1f84  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1f89  ldarg.0
0x1f8a  ldfld    int32 Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignActivityRecordPageHandler::channelType
0x1f8f  stloc.s  5
0x1f91  ldloc.s  5
0x1f93  ldc.i4.1
0x1f94  sub
0x1f95  switch   loc_1FE6, loc_2010, loc_1FBC, loc_1FBC, loc_1FFB, loc_1FFB, loc_1FD1, loc_1FD1
0x1fba  br.s     loc_2025
0x1fbc  ldc.i4   0x106F
0x1fc1  ldc.i4.2
0x1fc2  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x1fc7  stloc.3
0x1fc8  ldc.i4   0x106F
0x1fcd  stloc.s  4
0x1fcf  br.s     loc_202B
0x1fd1  ldc.i4   0x106A
0x1fd6  ldc.i4.2
0x1fd7  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x1fdc  stloc.3
0x1fdd  ldc.i4   0x106A
0x1fe2  stloc.s  4
0x1fe4  br.s     loc_202B
0x1fe6  ldc.i4   0x1072
0x1feb  ldc.i4.2
0x1fec  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x1ff1  stloc.3
0x1ff2  ldc.i4   0x1072
0x1ff7  stloc.s  4
0x1ff9  br.s     loc_202B
0x1ffb  ldc.i4   0x106C
0x2000  ldc.i4.2
0x2001  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x2006  stloc.3
0x2007  ldc.i4   0x106C
0x200c  stloc.s  4
0x200e  br.s     loc_202B
0x2010  ldc.i4   0x1069
0x2015  ldc.i4.2
0x2016  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x201b  stloc.3
0x201c  ldc.i4   0x1069
0x2021  stloc.s  4
0x2023  br.s     loc_202B
0x2025  ldsfld   string [mscorlib]System.String::Empty
0x202a  stloc.3
0x202b  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsOnline()
0x2030  brfalse.s loc_20AC
0x2032  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x2037  ldarg.0
0x2038  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentResourceManager()
0x203d  ldstr    aBulkoperations// "BulkOperationSuccesses_View"
0x2042  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2047  ldc.i4.1
0x2048  newarr   [mscorlib]System.Object
0x204d  dup
0x204e  ldc.i4.0
0x204f  ldloc.3
0x2050  stelem.ref
0x2051  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2056  stloc.2
0x2057  ldloc.1
0x2058  ldloc.0
0x2059  ldstr    aNavbulkoperati// "navBulkOperationSuccesses"
0x205e  ldc.i4.0
0x205f  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppNavigationBarArea [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppNavigationBar::GetNavigationBarArea(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.NavPaneItems, string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NavPaneArea)
0x2064  ldloc.0
0x2065  ldloc.s  4
0x2067  ldstr    aBulkoperations_0// "BulkOperationSuccesses"
0x206c  ldloc.2
0x206d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.NavigationBarItem [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppNavigationBarArea::AddObjectArea(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.NavPaneItems, int32, string, string)
0x2072  pop
0x2073  ldsfld   string [mscorlib]System.String::Empty
0x2078  stloc.s  6
0x207a  ldarg.0
0x207b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentResourceManager()
0x2080  ldstr    aBulkoperationf// "BulkOperationFailures_View"
0x2085  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x208a  stloc.s  6
0x208c  ldloc.1
0x208d  ldloc.0
0x208e  ldstr    aNavbulkoperati_0// "navBulkOperationFailures"
0x2093  ldc.i4.0
0x2094  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppNavigationBarArea [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppNavigationBar::GetNavigationBarArea(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.NavPaneItems, string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NavPaneArea)
0x2099  ldloc.0
0x209a  ldc.i4   0x1135
0x209f  ldstr    aBulkoperationf_0// "BulkOperationFailures"
0x20a4  ldloc.s  6
0x20a6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.NavigationBarItem [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppNavigationBarArea::AddObjectArea(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.NavPaneItems, int32, string, string)
0x20ab  pop
0x20ac  ldloc.1
0x20ad  ldloc.0
0x20ae  ldstr    aNavtargetlists// "navTargetLists"
0x20b3  ldc.i4.0
0x20b4  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppNavigationBarArea [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppNavigationBar::GetNavigationBarArea(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.NavPaneItems, string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NavPaneArea)
0x20b9  ldloc.0
0x20ba  ldc.i4   0x10CC
0x20bf  ldstr    aTargetlists// "TargetLists"
0x20c4  ldarg.0
0x20c5  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentResourceManager()
0x20ca  ldstr    aTabLabelTarget// "Tab_Label_TargetLists"
0x20cf  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x20d4  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.NavigationBarItem [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppNavigationBarArea::AddObjectArea(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.NavPaneItems, int32, string, string)
0x20d9  pop
0x20da  ret
```
