# Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildFieldSecurityProfileMenuBar

- ea: `0x233b0`
- end: `0x2368f`
- name: `Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildFieldSecurityProfileMenuBar`
- size: `735`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1b610`

## callees

- `0x1a490`
- `0x1a510`
- `0x1a5d0`
- `0x1a5f0`
- `0x1b510`
- `0x1c010`
- `0x1c060`
- `0x233b0`
- `0x24210`

## string_xrefs

- `0x23422`: `Menu_Label_AddFieldSecurityProfileFromTeamOrUser`
- `0x23523`: `Menu_Label_AddFieldSecurityProfileFromTeamOrUser`
- `0x23432`: `Menu_Label_Tooltip_AddFieldSecurityProfileFromTeamOrUser`
- `0x23533`: `Menu_Label_Tooltip_AddFieldSecurityProfileFromTeamOrUser`
- `0x2344d`: `Menu_Label_RemoveFieldSecurityProfiles`
- `0x2354e`: `Menu_Label_RemoveFieldSecurityProfiles`
- `0x23457`: `/_imgs/ico_16_removefieldsecurityprofile.png`
- `0x23558`: `/_imgs/ico_16_removefieldsecurityprofile.png`

## pseudocode

```c

```

## disassembly

```asm
0x233b0  ldarg.0
0x233b1  call     instance int32 Microsoft.Crm.Application.Menus.AppGridMenuBar::GetParentEntityType()
0x233b6  stloc.0
0x233b7  ldloc.0
0x233b8  ldc.i4.8
0x233b9  beq      loc_234C7
0x233be  ldloc.0
0x233bf  ldc.i4.s 9
0x233c1  bne.un   loc_235C8
0x233c6  ldarg.0
0x233c7  ldc.i4   0x400
0x233cc  ldc.i4.0
0x233cd  ldc.i4.1
0x233ce  ldc.i4.1
0x233cf  ldc.i4.0
0x233d0  ldc.i4.0
0x233d1  ldc.i4.0
0x233d2  ldc.i4.0
0x233d3  call     instance void Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildStandardActionsMenu(valuetype Microsoft.Crm.Application.Menus.GridActionParameters actionParam, bool buttonNew, bool buttonExport, bool buttonPrint, bool buttonReports, bool actionDeDupe, bool actionConnection, bool actionWorkflow)
0x233d8  ldarg.0
0x233d9  ldc.i4.5
0x233da  newarr   [mscorlib]System.String
0x233df  dup
0x233e0  ldc.i4.0
0x233e1  ldstr    aRunfunctionfro_2// "RunFunctionFromParentOrSelf('locAssocOb"...
0x233e6  stelem.ref
0x233e7  dup
0x233e8  ldc.i4.1
0x233e9  ldarg.0
0x233ea  ldflda   int32 Microsoft.Crm.Application.Menus.AppGridMenuBar::_objectTypeId
0x233ef  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x233f4  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x233f9  stelem.ref
0x233fa  dup
0x233fb  ldc.i4.2
0x233fc  ldstr    asc_117ADC// ",'',"
0x23401  stelem.ref
0x23402  dup
0x23403  ldc.i4.3
0x23404  ldstr    aTeamprofilesAs// "teamprofiles_association"
0x23409  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x2340e  stelem.ref
0x2340f  dup
0x23410  ldc.i4.4
0x23411  ldstr    a2// ", 2);"
0x23416  stelem.ref
0x23417  call     string [mscorlib]System.String::Concat(string[])
0x2341c  ldarg.0
0x2341d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x23422  ldstr    aMenuLabelAddfi// "Menu_Label_AddFieldSecurityProfileFromT"...
0x23427  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2342c  ldarg.0
0x2342d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x23432  ldstr    aMenuLabelToolt_1// "Menu_Label_Tooltip_AddFieldSecurityProf"...
0x23437  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2343c  call     instance void Microsoft.Crm.Application.Menus.AppGridMenuBar::AddNewButton(string onclickScript, string buttonTitle, string buttonTip)
0x23441  ldarg.0
0x23442  ldstr    asc_F537C// ""
0x23447  ldarg.0
0x23448  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x2344d  ldstr    aMenuLabelRemov_1// "Menu_Label_RemoveFieldSecurityProfiles"
0x23452  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x23457  ldstr    aImgsIco16Remov_1// "/_imgs/ico_16_removefieldsecurityprofil"...
0x2345c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x23461  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x23466  ldstr    aDisassociate// "disassociate"
0x2346b  ldstr    aWindowParentGe// "window.parent.$get('crmFormSubmit').crm"...
0x23470  ldstr    aWindowParentGe_0// "window.parent.$get('crmFormSubmit').crm"...
0x23475  ldc.i4.2
0x23476  newarr   [mscorlib]System.String
0x2347b  dup
0x2347c  ldc.i4.0
0x2347d  ldstr    aAssociationnam// "associationName"
0x23482  stelem.ref
0x23483  dup
0x23484  ldc.i4.1
0x23485  ldstr    aRoleord// "roleOrd"
0x2348a  stelem.ref
0x2348b  ldc.i4.2
0x2348c  newarr   [mscorlib]System.String
0x23491  dup
0x23492  ldc.i4.0
0x23493  ldarg.0
0x23494  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Menus.AppGridMenuBar::_grid
0x23499  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x2349e  ldstr    aRelname// "relName"
0x234a3  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x234a8  stelem.ref
0x234a9  dup
0x234aa  ldc.i4.1
0x234ab  ldarg.0
0x234ac  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Menus.AppGridMenuBar::_grid
0x234b1  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x234b6  ldstr    aRoleord// "roleOrd"
0x234bb  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x234c0  stelem.ref
0x234c1  call     instance void Microsoft.Crm.Application.Menus.AppGridMenuBar::AddButtonDoActionEx(string name, string tooltip, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri icon, string action, string parentId, string parentType, string[] queryStringParameters, string[] queryStringValues)
0x234c6  ret
0x234c7  ldarg.0
0x234c8  ldc.i4   0x400
0x234cd  ldc.i4.0
0x234ce  ldc.i4.1
0x234cf  ldc.i4.1
0x234d0  ldc.i4.0
0x234d1  ldc.i4.0
0x234d2  ldc.i4.0
0x234d3  ldc.i4.0
0x234d4  call     instance void Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildStandardActionsMenu(valuetype Microsoft.Crm.Application.Menus.GridActionParameters actionParam, bool buttonNew, bool buttonExport, bool buttonPrint, bool buttonReports, bool actionDeDupe, bool actionConnection, bool actionWorkflow)
0x234d9  ldarg.0
0x234da  ldc.i4.5
0x234db  newarr   [mscorlib]System.String
0x234e0  dup
0x234e1  ldc.i4.0
0x234e2  ldstr    aRunfunctionfro_2// "RunFunctionFromParentOrSelf('locAssocOb"...
0x234e7  stelem.ref
0x234e8  dup
0x234e9  ldc.i4.1
0x234ea  ldarg.0
0x234eb  ldflda   int32 Microsoft.Crm.Application.Menus.AppGridMenuBar::_objectTypeId
0x234f0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x234f5  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x234fa  stelem.ref
0x234fb  dup
0x234fc  ldc.i4.2
0x234fd  ldstr    asc_117ADC// ",'',"
0x23502  stelem.ref
0x23503  dup
0x23504  ldc.i4.3
0x23505  ldstr    aSystemuserprof// "systemuserprofiles_association"
0x2350a  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x2350f  stelem.ref
0x23510  dup
0x23511  ldc.i4.4
0x23512  ldstr    a2// ", 2);"
0x23517  stelem.ref
0x23518  call     string [mscorlib]System.String::Concat(string[])
0x2351d  ldarg.0
0x2351e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x23523  ldstr    aMenuLabelAddfi// "Menu_Label_AddFieldSecurityProfileFromT"...
0x23528  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2352d  ldarg.0
0x2352e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x23533  ldstr    aMenuLabelToolt_1// "Menu_Label_Tooltip_AddFieldSecurityProf"...
0x23538  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2353d  call     instance void Microsoft.Crm.Application.Menus.AppGridMenuBar::AddNewButton(string onclickScript, string buttonTitle, string buttonTip)
0x23542  ldarg.0
0x23543  ldstr    asc_F537C// ""
0x23548  ldarg.0
0x23549  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x2354e  ldstr    aMenuLabelRemov_1// "Menu_Label_RemoveFieldSecurityProfiles"
0x23553  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x23558  ldstr    aImgsIco16Remov_1// "/_imgs/ico_16_removefieldsecurityprofil"...
0x2355d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x23562  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x23567  ldstr    aDisassociate// "disassociate"
0x2356c  ldstr    aWindowParentGe// "window.parent.$get('crmFormSubmit').crm"...
0x23571  ldstr    aWindowParentGe_0// "window.parent.$get('crmFormSubmit').crm"...
0x23576  ldc.i4.2
0x23577  newarr   [mscorlib]System.String
0x2357c  dup
0x2357d  ldc.i4.0
0x2357e  ldstr    aAssociationnam// "associationName"
0x23583  stelem.ref
0x23584  dup
0x23585  ldc.i4.1
0x23586  ldstr    aRoleord// "roleOrd"
0x2358b  stelem.ref
0x2358c  ldc.i4.2
0x2358d  newarr   [mscorlib]System.String
0x23592  dup
0x23593  ldc.i4.0
0x23594  ldarg.0
0x23595  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Menus.AppGridMenuBar::_grid
0x2359a  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x2359f  ldstr    aRelname// "relName"
0x235a4  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x235a9  stelem.ref
0x235aa  dup
0x235ab  ldc.i4.1
0x235ac  ldarg.0
0x235ad  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Menus.AppGridMenuBar::_grid
0x235b2  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x235b7  ldstr    aRoleord// "roleOrd"
0x235bc  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x235c1  stelem.ref
0x235c2  call     instance void Microsoft.Crm.Application.Menus.AppGridMenuBar::AddButtonDoActionEx(string name, string tooltip, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri icon, string action, string parentId, string parentType, string[] queryStringParameters, string[] queryStringValues)
0x235c7  ret
0x235c8  ldarg.0
0x235c9  ldc.i4.7
0x235ca  newarr   [mscorlib]System.String
0x235cf  dup
0x235d0  ldc.i4.0
0x235d1  ldstr    aLocaddrelatedt// "locAddRelatedToNonForm("
0x235d6  stelem.ref
0x235d7  dup
0x235d8  ldc.i4.1
0x235d9  ldc.i4   0x4B0
0x235de  stloc.0
0x235df  ldloca.s 0
0x235e1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x235e6  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x235eb  stelem.ref
0x235ec  dup
0x235ed  ldc.i4.2
0x235ee  ldstr    asc_11387C// ","
0x235f3  stelem.ref
0x235f4  dup
0x235f5  ldc.i4.3
0x235f6  ldc.i4.s 0xA
0x235f8  stloc.0
0x235f9  ldloca.s 0
0x235fb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x23600  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x23605  stelem.ref
0x23606  dup
0x23607  ldc.i4.4
0x23608  ldstr    asc_11AA82// ",'"
0x2360d  stelem.ref
0x2360e  dup
0x2360f  ldc.i4.5
0x23610  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x23615  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_BusinessId()
0x2361a  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GuidToString(valuetype [mscorlib]System.Guid)
0x2361f  stelem.ref
0x23620  dup
0x23621  ldc.i4.6
0x23622  ldstr    asc_11AA88// "', '')"
0x23627  stelem.ref
0x23628  call     string [mscorlib]System.String::Concat(string[])
0x2362d  call     instance void Microsoft.Crm.Application.Menus.AppGridMenuBar::AddNewButton(string onclickScript)
0x23632  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x23637  ldstr    aLocaddrelatedt_0// "locAddRelatedToNonForm({0}, {{0}}, '{{1"...
0x2363c  ldc.i4.1
0x2363d  newarr   [mscorlib]System.Object
0x23642  dup
0x23643  ldc.i4.0
0x23644  ldc.i4   0x4B0
0x23649  box      [mscorlib]System.Int32
0x2364e  stelem.ref
0x2364f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x23654  stloc.1
0x23655  ldarg.0
0x23656  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2365b  ldloc.1
0x2365c  ldc.i4.2
0x2365d  newarr   [mscorlib]System.Object
0x23662  dup
0x23663  ldc.i4.0
0x23664  ldarg.0
0x23665  call     instance int32 Microsoft.Crm.Application.Menus.AppGridMenuBar::GetParentEntityType()
0x2366a  box      [mscorlib]System.Int32
0x2366f  stelem.ref
0x23670  dup
0x23671  ldc.i4.1
0x23672  ldarg.0
0x23673  call     instance string Microsoft.Crm.Application.Menus.AppGridMenuBar::GetParentEntityId()
0x23678  stelem.ref
0x23679  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2367e  call     instance void Microsoft.Crm.Application.Menus.AppGridMenuBar::AddNewButton(string onclickScript)
0x23683  ldc.i4.2
0x23684  stloc.2
0x23685  ldarg.0
0x23686  ldloc.2
0x23687  ldc.i4.0
0x23688  ldc.i4.1
0x23689  call     instance void Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildStandardActionsMenu(valuetype Microsoft.Crm.Application.Menus.GridActionParameters actionParam, bool buttonNew, bool buttonExport)
0x2368e  ret
```
