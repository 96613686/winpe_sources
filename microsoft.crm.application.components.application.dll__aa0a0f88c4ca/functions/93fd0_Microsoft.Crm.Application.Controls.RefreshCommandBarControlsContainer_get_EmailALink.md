# Microsoft.Crm.Application.Controls.RefreshCommandBarControlsContainer::get_EmailALink

- ea: `0x93fd0`
- end: `0x94034`
- name: `Microsoft.Crm.Application.Controls.RefreshCommandBarControlsContainer::get_EmailALink`
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

- `0x93fd0`

## string_xrefs

- `0x9401a`: `ms-crm-Menu-ReadForm`
- `0x93fd5`: `RefreshCommandBar.EmailLink`
- `0x93fe4`: `RefreshCommandBar.EmailLink`
- `0x93fee`: `emailLinkButton`
- `0x93ffa`: `/_imgs/RefreshCommandbar/EmailLink_16.png`

## pseudocode

```c

```

## disassembly

```asm
0x93fd0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x93fd5  ldstr    aRefreshcommand_20// "RefreshCommandBar.EmailLink"
0x93fda  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x93fdf  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x93fe4  ldstr    aRefreshcommand_20// "RefreshCommandBar.EmailLink"
0x93fe9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x93fee  ldstr    aEmaillinkbutto// "emailLinkButton"
0x93ff3  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::.ctor(string, string, string)
0x93ff8  stloc.0
0x93ff9  ldloc.0
0x93ffa  ldstr    aImgsRefreshcom_18// "/_imgs/RefreshCommandbar/EmailLink_16.p"...
0x93fff  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x94004  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x94009  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Icon(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x9400e  ldloc.0
0x9400f  ldc.i4   0xD4
0x94014  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::set_ActionId(int32)
0x94019  ldloc.0
0x9401a  ldstr    aMsCrmMenuReadf// "ms-crm-Menu-ReadForm"
0x9401f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::set_CssClass(string)
0x94024  ldloc.0
0x94025  stloc.1
0x94026  leave.s  loc_94032
0x94028  ldloc.0
0x94029  brfalse.s loc_94031
0x9402b  ldloc.0
0x9402c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x94031  endfinally
0x94032  ldloc.1
0x94033  ret
```
