# Microsoft.Crm.Application.Controls.ROCommandBarControlsContainer::.ctor_0

- ea: `0x94240`
- end: `0x94341`
- name: `Microsoft.Crm.Application.Controls.ROCommandBarControlsContainer::.ctor_0`
- size: `257`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x92db0`
- `0x94230`

## callees

- `0x92550`
- `0x92b10`
- `0x92c90`
- `0x92d80`
- `0x94240`

## string_xrefs

- `0x94270`: `/_imgs/refreshcommandbar/openlegacyform_16.png`
- `0x94290`: `ms-crm-Menu-ReadForm`
- `0x9430e`: `ms-crm-Menu-ReadForm`
- `0x942c9`: `RefreshCommandBar.Close`
- `0x942d8`: `RefreshCommandBar.Close`
- `0x9424b`: `RefreshCommandBar.Edit`
- `0x9425a`: `RefreshCommandBar.Edit`
- `0x942ee`: `/_imgs/refreshcommandbar/close_16.png`

## pseudocode

```c

```

## disassembly

```asm
0x94240  ldarg.0
0x94241  call     instance void Microsoft.Crm.Application.Controls.CommandBarControlsContainerBase::.ctor()
0x94246  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x9424b  ldstr    aRefreshcommand_24// "RefreshCommandBar.Edit"
0x94250  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x94255  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x9425a  ldstr    aRefreshcommand_24// "RefreshCommandBar.Edit"
0x9425f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x94264  ldstr    aEditbutton// "editButton"
0x94269  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::.ctor(string, string, string)
0x9426e  stloc.0
0x9426f  ldloc.0
0x94270  ldstr    aImgsRefreshcom_1// "/_imgs/refreshcommandbar/openlegacyform"...
0x94275  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9427a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9427f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Icon(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x94284  ldloc.0
0x94285  ldc.i4   0xC9
0x9428a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::set_ActionId(int32)
0x9428f  ldloc.0
0x94290  ldstr    aMsCrmMenuReadf// "ms-crm-Menu-ReadForm"
0x94295  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::set_CssClass(string)
0x9429a  ldarg.0
0x9429b  call     instance class Microsoft.Crm.Application.Controls.CommandBarControlsCollection Microsoft.Crm.Application.Controls.CommandBarControlsContainerBase::get_CommandBarControls()
0x942a0  ldloc.0
0x942a1  ldarg.1
0x942a2  ldc.i4.1
0x942a3  newarr   Microsoft.Crm.Application.Controls.RefreshCommandBarTrimRule
0x942a8  dup
0x942a9  ldc.i4.0
0x942aa  ldc.i4.s 0x1E
0x942ac  stelem.i4
0x942ad  ldloc.0
0x942ae  callvirt instance int32[] [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::get_VisibilityRules()
0x942b3  callvirt instance void Microsoft.Crm.Application.Controls.CommandBarControlsCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl commandBarControl, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity currentEntity, valuetype Microsoft.Crm.Application.Controls.RefreshCommandBarTrimRule[] trimRules, int32[] visibilityRules)
0x942b8  leave.s  loc_942C4
0x942ba  ldloc.0
0x942bb  brfalse.s loc_942C3
0x942bd  ldloc.0
0x942be  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x942c3  endfinally
0x942c4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x942c9  ldstr    aRefreshcommand_11// "RefreshCommandBar.Close"
0x942ce  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x942d3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x942d8  ldstr    aRefreshcommand_11// "RefreshCommandBar.Close"
0x942dd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x942e2  ldstr    aCloseform// "closeForm"
0x942e7  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::.ctor(string, string, string)
0x942ec  stloc.1
0x942ed  ldloc.1
0x942ee  ldstr    aImgsRefreshcom_21// "/_imgs/refreshcommandbar/close_16.png"
0x942f3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x942f8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x942fd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Icon(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x94302  ldloc.1
0x94303  ldstr    aClosewindow// "closeWindow();"
0x94308  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x9430d  ldloc.1
0x9430e  ldstr    aMsCrmMenuReadf// "ms-crm-Menu-ReadForm"
0x94313  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::set_CssClass(string)
0x94318  ldarg.0
0x94319  call     instance class Microsoft.Crm.Application.Controls.CommandBarControlsCollection Microsoft.Crm.Application.Controls.CommandBarControlsContainerBase::get_CommandBarControls()
0x9431e  ldloc.1
0x9431f  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl>::Add(var<u1>)
0x94324  leave.s  loc_94330
0x94326  ldloc.1
0x94327  brfalse.s loc_9432F
0x94329  ldloc.1
0x9432a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9432f  endfinally
0x94330  ldarg.0
0x94331  call     instance class Microsoft.Crm.Application.Controls.CommandBarControlsCollection Microsoft.Crm.Application.Controls.CommandBarControlsContainerBase::get_CommandBarControls()
0x94336  call     class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton Microsoft.Crm.Application.Controls.CommandBarControlsContainerBase::get_HelpButton()
0x9433b  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl>::Add(var<u1>)
0x94340  ret
```
