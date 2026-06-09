# Microsoft.Crm.Application.Controls.CommandBarControlsContainerBase::get_SwitchToClassic

- ea: `0x92c20`
- end: `0x92c84`
- name: `Microsoft.Crm.Application.Controls.CommandBarControlsContainerBase::get_SwitchToClassic`
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

- `0x92c20`

## string_xrefs

- `0x92c25`: `RefreshCommandBar.SwitchToClassic`
- `0x92c34`: `RefreshCommandBar.SwitchToClassic`
- `0x92c4a`: `/_imgs/refreshcommandbar/openlegacyform_16.png`
- `0x92c6a`: `ms-crm-Menu-ReadForm`

## pseudocode

```c

```

## disassembly

```asm
0x92c20  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x92c25  ldstr    aRefreshcommand_2// "RefreshCommandBar.SwitchToClassic"
0x92c2a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x92c2f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x92c34  ldstr    aRefreshcommand_2// "RefreshCommandBar.SwitchToClassic"
0x92c39  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x92c3e  ldstr    aSwitchtoclassi// "switchToClassicButton"
0x92c43  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::.ctor(string, string, string)
0x92c48  stloc.0
0x92c49  ldloc.0
0x92c4a  ldstr    aImgsRefreshcom_1// "/_imgs/refreshcommandbar/openlegacyform"...
0x92c4f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x92c54  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x92c59  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Icon(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x92c5e  ldloc.0
0x92c5f  ldc.i4   0xC9
0x92c64  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::set_ActionId(int32)
0x92c69  ldloc.0
0x92c6a  ldstr    aMsCrmMenuReadf// "ms-crm-Menu-ReadForm"
0x92c6f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::set_CssClass(string)
0x92c74  ldloc.0
0x92c75  stloc.1
0x92c76  leave.s  loc_92C82
0x92c78  ldloc.0
0x92c79  brfalse.s loc_92C81
0x92c7b  ldloc.0
0x92c7c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x92c81  endfinally
0x92c82  ldloc.1
0x92c83  ret
```
