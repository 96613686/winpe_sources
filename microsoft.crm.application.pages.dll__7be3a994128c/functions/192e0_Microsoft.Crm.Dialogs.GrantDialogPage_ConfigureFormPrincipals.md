# Microsoft.Crm.Dialogs.GrantDialogPage::ConfigureFormPrincipals

- ea: `0x192e0`
- end: `0x194f9`
- name: `Microsoft.Crm.Dialogs.GrantDialogPage::ConfigureFormPrincipals`
- size: `537`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x191e0`

## callees

- `0x192e0`

## string_xrefs

- `0x193a6`: `principalobjectattributeaccess`
- `0x1931b`: `Mscrm.PrincipalObjectAttributeAccess.addPrincipal();`
- `0x1935c`: `MenuItem_Label_Remove`
- `0x19366`: `Mscrm.PrincipalObjectAttributeAccess.removePrincipal();`
- `0x19380`: `/_imgs/ico_16_removeteam.png`
- `0x19390`: `Menu_Label_Tooltip_RemoveUserOrTeamFromGrantDialog`

## pseudocode

```c

```

## disassembly

```asm
0x192e0  ldarg.0
0x192e1  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppGridMenuBar Microsoft.Crm.Dialogs.GrantDialogPage::principalsMenuBar
0x192e6  ldc.i4.1
0x192e7  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppGridMenuBar::set_GridType(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.GridTypeCode)
0x192ec  ldarg.0
0x192ed  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppGridMenuBar Microsoft.Crm.Dialogs.GrantDialogPage::principalsMenuBar
0x192f2  ldarg.0
0x192f3  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Dialogs.GrantDialogPage::principalsGrid
0x192f8  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppGridMenuBar::Execute(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid)
0x192fd  ldarg.1
0x192fe  brfalse.s loc_19348
0x19300  ldarg.0
0x19301  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppGridMenuBar Microsoft.Crm.Dialogs.GrantDialogPage::principalsMenuBar
0x19306  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppMenuBar::get_MenuBar()
0x1930b  ldarg.0
0x1930c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x19311  ldstr    aMenuLabelAddus// "Menu_Label_AddUsersOrTeamsFromGrantDial"...
0x19316  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1931b  ldstr    aMscrmPrincipal// "Mscrm.PrincipalObjectAttributeAccess.ad"...
0x19320  ldc.i4.s 9
0x19322  ldc.i4.0
0x19323  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x19328  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconUtil::GetIconPath(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1932d  callvirt instance string [mscorlib]System.Object::ToString()
0x19332  ldarg.0
0x19333  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x19338  ldstr    aMenuLabelToolt// "Menu_Label_Tooltip_AddUsersOrTeamsFromG"...
0x1933d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x19342  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string)
0x19347  pop
0x19348  ldarg.2
0x19349  brfalse.s loc_193A0
0x1934b  ldarg.0
0x1934c  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppGridMenuBar Microsoft.Crm.Dialogs.GrantDialogPage::principalsMenuBar
0x19351  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppMenuBar::get_MenuBar()
0x19356  ldarg.0
0x19357  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1935c  ldstr    aMenuitemLabelR// "MenuItem_Label_Remove"
0x19361  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x19366  ldstr    aMscrmPrincipal_0// "Mscrm.PrincipalObjectAttributeAccess.re"...
0x1936b  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x19370  ldc.i4.1
0x19371  newarr   [mscorlib]System.Char
0x19376  dup
0x19377  ldc.i4.0
0x19378  ldc.i4.s 0x2F
0x1937a  stelem.i2
0x1937b  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x19380  ldstr    aImgsIco16Remov// "/_imgs/ico_16_removeteam.png"
0x19385  call     string [mscorlib]System.String::Concat(string, string)
0x1938a  ldarg.0
0x1938b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x19390  ldstr    aMenuLabelToolt_0// "Menu_Label_Tooltip_RemoveUserOrTeamFrom"...
0x19395  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1939a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string)
0x1939f  pop
0x193a0  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x193a5  stloc.0
0x193a6  ldstr    aPrincipalobjec// "principalobjectattributeaccess"
0x193ab  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::.ctor(string)
0x193b0  stloc.1
0x193b1  ldloc.1
0x193b2  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x193b7  ldc.i4.1
0x193b8  newarr   [mscorlib]System.String
0x193bd  dup
0x193be  ldc.i4.0
0x193bf  ldstr    aPrincipalid_0// "principalid"
0x193c4  stelem.ref
0x193c5  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumns(string[])
0x193ca  ldloc.1
0x193cb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x193d0  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::get_Conditions()
0x193d5  ldstr    aObjecttypecode// "objecttypecode"
0x193da  ldc.i4.0
0x193db  ldarg.0
0x193dc  ldfld    int32 Microsoft.Crm.Dialogs.GrantDialogPage::ObjType
0x193e1  box      [mscorlib]System.Int32
0x193e6  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x193eb  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x193f0  pop
0x193f1  ldloc.1
0x193f2  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x193f7  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::get_Conditions()
0x193fc  ldstr    aObjectid_0// "objectid"
0x19401  ldc.i4.0
0x19402  ldarg.0
0x19403  ldfld    string Microsoft.Crm.Dialogs.GrantDialogPage::id
0x19408  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x1940d  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x19412  pop
0x19413  ldloc.1
0x19414  ldc.i4.1
0x19415  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::set_Distinct(bool)
0x1941a  ldloc.1
0x1941b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x19420  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x19425  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::GetEnumerator()
0x1942a  stloc.2
0x1942b  br.s     loc_19498
0x1942d  ldloc.2
0x1942e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Current()
0x19433  ldstr    aPrincipalid_0// "principalid"
0x19438  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x1943d  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0x19442  stloc.3
0x19443  ldloc.0
0x19444  ldloc.3
0x19445  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_Name()
0x1944a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1944f  pop
0x19450  ldloc.0
0x19451  ldstr    asc_113A60// ";"
0x19456  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1945b  pop
0x1945c  ldloc.0
0x1945d  ldloc.3
0x1945e  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_Type()
0x19463  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x19468  call     string [mscorlib]System.Convert::ToString(int32, class [mscorlib]System.IFormatProvider)
0x1946d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x19472  pop
0x19473  ldloc.0
0x19474  ldstr    asc_113A60// ";"
0x19479  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1947e  pop
0x1947f  ldloc.0
0x19480  ldloc.3
0x19481  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_ID()
0x19486  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1948b  pop
0x1948c  ldloc.0
0x1948d  ldstr    asc_113A60// ";"
0x19492  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x19497  pop
0x19498  ldloc.2
0x19499  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1949e  brtrue.s loc_1942D
0x194a0  leave.s  loc_194AC
0x194a2  ldloc.2
0x194a3  brfalse.s loc_194AB
0x194a5  ldloc.2
0x194a6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x194ab  endfinally
0x194ac  ldarg.0
0x194ad  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Dialogs.GrantDialogPage::principalsGrid
0x194b2  ldstr    aPrincipalslist// "principalslist"
0x194b7  ldloc.0
0x194b8  callvirt instance string [mscorlib]System.Object::ToString()
0x194bd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::AddParameter(string, string)
0x194c2  ldarg.0
0x194c3  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Dialogs.GrantDialogPage::principalsGrid
0x194c8  ldstr    aObjectid_0// "objectid"
0x194cd  ldarg.0
0x194ce  ldfld    string Microsoft.Crm.Dialogs.GrantDialogPage::id
0x194d3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::AddParameter(string, string)
0x194d8  ldarg.0
0x194d9  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Dialogs.GrantDialogPage::principalsGrid
0x194de  ldstr    aObjecttype// "objecttype"
0x194e3  ldarg.0
0x194e4  ldflda   int32 Microsoft.Crm.Dialogs.GrantDialogPage::ObjType
0x194e9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x194ee  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x194f3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::AddParameter(string, string)
0x194f8  ret
```
