# Microsoft.Crm.Service.Application.Pages.SM.Resources.DetailPage::ConfigureNav

- ea: `0x12ff0`
- end: `0x13118`
- name: `Microsoft.Crm.Service.Application.Pages.SM.Resources.DetailPage::ConfigureNav`
- size: `296`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x12ff0`

## string_xrefs

- `0x13018`: `Services`
- `0x13023`: `Tab_Label_Services`
- `0x130e3`: `', Mscrm.CrmUri.create('/biz/users/monthlyCalendar.aspx'));`

## pseudocode

```c

```

## disassembly

```asm
0x12ff0  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsOnline()
0x12ff5  brfalse.s loc_1305E
0x12ff7  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_ReadService()
0x12ffc  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x13001  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x13006  brfalse.s loc_13033
0x13008  ldarg.0
0x13009  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppNavigationBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmNavBar
0x1300e  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppNavigationBarArea [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppNavigationBar::get_AreaService()
0x13013  ldc.i4   0xFA1
0x13018  ldstr    aServices// "Services"
0x1301d  ldarg.0
0x1301e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x13023  ldstr    aTabLabelServic_0// "Tab_Label_Services"
0x13028  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1302d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.NavigationBarItem [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppNavigationBarArea::AddObjectArea(int32, string, string)
0x13032  pop
0x13033  ldarg.0
0x13034  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppNavigationBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmNavBar
0x13039  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppNavigationBarArea [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppNavigationBar::get_AreaService()
0x1303e  ldc.i4   0xFA7
0x13043  ldstr    aResourcegroups_0// "ResourceGroups"
0x13048  ldarg.0
0x13049  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1304e  ldstr    aTabLabelResour// "Tab_Label_ResourceGroups"
0x13053  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x13058  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.NavigationBarItem [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppNavigationBarArea::AddObjectArea(int32, string, string)
0x1305d  pop
0x1305e  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsOnline()
0x13063  brfalse  loc_13117
0x13068  ldc.i4.0
0x13069  stloc.0
0x1306a  ldarg.0
0x1306b  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x13070  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_Entity()
0x13075  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0x1307a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1307f  brtrue.s loc_130B5
0x13081  ldarg.0
0x13082  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x13087  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_Entity()
0x1308c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0x13091  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x13096  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1309b  ldc.i4.0
0x1309c  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::FindOrCreateResourceCalendar(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext, int32)
0x130a1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x130a6  call     class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Calendar [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::RetrieveCalendar(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x130ab  pop
0x130ac  ldc.i4.1
0x130ad  stloc.0
0x130ae  leave.s  loc_130B5
0x130b0  pop
0x130b1  ldc.i4.0
0x130b2  stloc.0
0x130b3  leave.s  loc_130B5
0x130b5  ldloc.0
0x130b6  brfalse.s loc_13117
0x130b8  ldarg.0
0x130b9  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppNavigationBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmNavBar
0x130be  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppNavigationBarArea [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppNavigationBar::get_AreaInfo()
0x130c3  ldarg.0
0x130c4  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x130c9  ldstr    aTabLabelWorkin// "Tab_Label_Working_Hours"
0x130ce  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x130d3  ldstr    aImgsArea18Cale// "/_imgs/area/18_calendar.gif"
0x130d8  ldstr    aLoadareaThisAr// "loadArea(this, 'areaMonthlyCalendar', '"...
0x130dd  ldarg.0
0x130de  ldfld    string Microsoft.Crm.Service.Application.Pages.SM.Resources.DetailPage::_equipmentCalendarId
0x130e3  ldstr    aMscrmCrmuriCre// "', Mscrm.CrmUri.create('/biz/users/mont"...
0x130e8  call     string [mscorlib]System.String::Concat(string, string, string)
0x130ed  ldstr    aNavmonthlycale// "navMonthlyCalendar"
0x130f2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.NavigationBarItem [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppNavigationBarArea::AddItem(string, string, string, string)
0x130f7  stloc.1
0x130f8  ldloc.1
0x130f9  ldc.i4   0xFA3
0x130fe  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.NavigationBarItem::set_EntityImageId(int32)
0x13103  ldarg.0
0x13104  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x13109  callvirt instance bool [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x1310e  brfalse.s loc_13117
0x13110  ldloc.1
0x13111  ldc.i4.1
0x13112  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0x13117  ret
```
