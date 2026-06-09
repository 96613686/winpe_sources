# Microsoft.Crm.Application.Controls.RefreshCommandBarControlsContainer::get_Activate

- ea: `0x93da0`
- end: `0x93e00`
- name: `Microsoft.Crm.Application.Controls.RefreshCommandBarControlsContainer::get_Activate`
- size: `96`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x92e20`
- `0x93070`

## callees

- `0x93da0`

## string_xrefs

- `0x93de6`: `ms-crm-Menu-ReadForm`
- `0x93da5`: `RefreshCommandBar.Activate`
- `0x93db4`: `RefreshCommandBar.Activate`
- `0x93dca`: `/_imgs/RefreshCommandbar/ReactivateCase_16.png`

## pseudocode

```c

```

## disassembly

```asm
0x93da0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x93da5  ldstr    aRefreshcommand_12// "RefreshCommandBar.Activate"
0x93daa  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x93daf  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x93db4  ldstr    aRefreshcommand_12// "RefreshCommandBar.Activate"
0x93db9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x93dbe  ldstr    aActivatebutton// "activateButton"
0x93dc3  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::.ctor(string, string, string)
0x93dc8  stloc.0
0x93dc9  ldloc.0
0x93dca  ldstr    aImgsRefreshcom_13// "/_imgs/RefreshCommandbar/ReactivateCase"...
0x93dcf  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x93dd4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x93dd9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Icon(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x93dde  ldloc.0
0x93ddf  ldc.i4.6
0x93de0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::set_ActionId(int32)
0x93de5  ldloc.0
0x93de6  ldstr    aMsCrmMenuReadf// "ms-crm-Menu-ReadForm"
0x93deb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::set_CssClass(string)
0x93df0  ldloc.0
0x93df1  stloc.1
0x93df2  leave.s  loc_93DFE
0x93df4  ldloc.0
0x93df5  brfalse.s loc_93DFD
0x93df7  ldloc.0
0x93df8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x93dfd  endfinally
0x93dfe  ldloc.1
0x93dff  ret
```
