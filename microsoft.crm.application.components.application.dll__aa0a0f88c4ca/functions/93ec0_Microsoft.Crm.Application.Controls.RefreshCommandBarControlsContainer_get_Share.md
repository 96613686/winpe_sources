# Microsoft.Crm.Application.Controls.RefreshCommandBarControlsContainer::get_Share

- ea: `0x93ec0`
- end: `0x93f24`
- name: `Microsoft.Crm.Application.Controls.RefreshCommandBarControlsContainer::get_Share`
- size: `100`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x92e20`
- `0x93070`
- `0x932c0`
- `0x936a0`

## callees

- `0x93ec0`

## string_xrefs

- `0x93f0a`: `ms-crm-Menu-ReadForm`
- `0x93ec5`: `RefreshCommandBar.Share`
- `0x93ed4`: `RefreshCommandBar.Share`
- `0x93eea`: `/_imgs/RefreshCommandbar/Sharing_16.png`

## pseudocode

```c

```

## disassembly

```asm
0x93ec0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x93ec5  ldstr    aRefreshcommand_15// "RefreshCommandBar.Share"
0x93eca  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x93ecf  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x93ed4  ldstr    aRefreshcommand_15// "RefreshCommandBar.Share"
0x93ed9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x93ede  ldstr    aSharebutton// "shareButton"
0x93ee3  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::.ctor(string, string, string)
0x93ee8  stloc.0
0x93ee9  ldloc.0
0x93eea  ldstr    aImgsRefreshcom_16// "/_imgs/RefreshCommandbar/Sharing_16.png"
0x93eef  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x93ef4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x93ef9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Icon(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x93efe  ldloc.0
0x93eff  ldc.i4   0xCC
0x93f04  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::set_ActionId(int32)
0x93f09  ldloc.0
0x93f0a  ldstr    aMsCrmMenuReadf// "ms-crm-Menu-ReadForm"
0x93f0f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::set_CssClass(string)
0x93f14  ldloc.0
0x93f15  stloc.1
0x93f16  leave.s  loc_93F22
0x93f18  ldloc.0
0x93f19  brfalse.s loc_93F21
0x93f1b  ldloc.0
0x93f1c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x93f21  endfinally
0x93f22  ldloc.1
0x93f23  ret
```
