# Microsoft.Crm.Application.Controls.RefreshCommandBarControlsContainer::get_SaveButton

- ea: `0x93b70`
- end: `0x93bd4`
- name: `Microsoft.Crm.Application.Controls.RefreshCommandBarControlsContainer::get_SaveButton`
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

- `0x93b70`

## string_xrefs

- `0x93bba`: `ms-crm-Menu-ReadForm`
- `0x93b75`: `RefreshCommandBar.Create`
- `0x93b84`: `RefreshCommandBar.Create`
- `0x93b9a`: `/_imgs/RefreshCommandbar/Create_16.png`

## pseudocode

```c

```

## disassembly

```asm
0x93b70  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x93b75  ldstr    aRefreshcommand_9// "RefreshCommandBar.Create"
0x93b7a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x93b7f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x93b84  ldstr    aRefreshcommand_9// "RefreshCommandBar.Create"
0x93b89  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x93b8e  ldstr    aSavebutton// "saveButton"
0x93b93  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::.ctor(string, string, string)
0x93b98  stloc.0
0x93b99  ldloc.0
0x93b9a  ldstr    aImgsRefreshcom_8// "/_imgs/RefreshCommandbar/Create_16.png"
0x93b9f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x93ba4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x93ba9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Icon(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x93bae  ldloc.0
0x93baf  ldc.i4   0xDA
0x93bb4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::set_ActionId(int32)
0x93bb9  ldloc.0
0x93bba  ldstr    aMsCrmMenuReadf// "ms-crm-Menu-ReadForm"
0x93bbf  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::set_CssClass(string)
0x93bc4  ldloc.0
0x93bc5  stloc.1
0x93bc6  leave.s  loc_93BD2
0x93bc8  ldloc.0
0x93bc9  brfalse.s loc_93BD1
0x93bcb  ldloc.0
0x93bcc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x93bd1  endfinally
0x93bd2  ldloc.1
0x93bd3  ret
```
