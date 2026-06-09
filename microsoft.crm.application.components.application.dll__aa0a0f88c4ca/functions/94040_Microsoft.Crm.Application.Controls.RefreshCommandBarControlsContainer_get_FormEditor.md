# Microsoft.Crm.Application.Controls.RefreshCommandBarControlsContainer::get_FormEditor

- ea: `0x94040`
- end: `0x940a4`
- name: `Microsoft.Crm.Application.Controls.RefreshCommandBarControlsContainer::get_FormEditor`
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

- `0x94040`

## string_xrefs

- `0x9408a`: `ms-crm-Menu-ReadForm`
- `0x94045`: `RefreshCommandBar.FormEditor`
- `0x94054`: `RefreshCommandBar.FormEditor`
- `0x9406a`: `/_imgs/RefreshCommandbar/FormEditor_16.png`

## pseudocode

```c

```

## disassembly

```asm
0x94040  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x94045  ldstr    aRefreshcommand_21// "RefreshCommandBar.FormEditor"
0x9404a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9404f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x94054  ldstr    aRefreshcommand_21// "RefreshCommandBar.FormEditor"
0x94059  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9405e  ldstr    aFormeditorbutt// "formEditorButton"
0x94063  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::.ctor(string, string, string)
0x94068  stloc.0
0x94069  ldloc.0
0x9406a  ldstr    aImgsRefreshcom_19// "/_imgs/RefreshCommandbar/FormEditor_16."...
0x9406f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x94074  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x94079  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Icon(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x9407e  ldloc.0
0x9407f  ldc.i4   0xD6
0x94084  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::set_ActionId(int32)
0x94089  ldloc.0
0x9408a  ldstr    aMsCrmMenuReadf// "ms-crm-Menu-ReadForm"
0x9408f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::set_CssClass(string)
0x94094  ldloc.0
0x94095  stloc.1
0x94096  leave.s  loc_940A2
0x94098  ldloc.0
0x94099  brfalse.s loc_940A1
0x9409b  ldloc.0
0x9409c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x940a1  endfinally
0x940a2  ldloc.1
0x940a3  ret
```
