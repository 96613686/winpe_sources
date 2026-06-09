# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::SetQuickEditAttributes

- ea: `0x1c8d0`
- end: `0x1c94c`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::SetQuickEditAttributes`
- size: `124`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1c890`

## callees

- `0x1c720`
- `0x1c7a0`
- `0x1c7c0`
- `0x1c8d0`
- `0x1e6a0`
- `0x1e6e0`
- `0x1e700`
- `0x1e760`

## pseudocode

```c

```

## disassembly

```asm
0x1c8d0  ldarg.0
0x1c8d1  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_IsStakeholdersGrid()
0x1c8d6  brfalse.s loc_1C8FE
0x1c8d8  ldarg.0
0x1c8d9  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_IsRefreshFCBEnabled()
0x1c8de  brfalse.s loc_1C8FE
0x1c8e0  ldarg.0
0x1c8e1  ldc.i4   0x3E8
0x1c8e6  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::set_ConnectionToCategory(unsigned int32 value)
0x1c8eb  ldarg.0
0x1c8ec  ldstr    aContact// "contact"
0x1c8f1  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::set_ConnectionToEntity(string value)
0x1c8f6  ldarg.0
0x1c8f7  ldc.i4.1
0x1c8f8  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::set_EnableInlineEdit(bool value)
0x1c8fd  ret
0x1c8fe  ldarg.0
0x1c8ff  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_IsSalesTeamGrid()
0x1c904  brfalse.s loc_1C92C
0x1c906  ldarg.0
0x1c907  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_IsRefreshFCBEnabled()
0x1c90c  brfalse.s loc_1C92C
0x1c90e  ldarg.0
0x1c90f  ldc.i4   0x3E9
0x1c914  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::set_ConnectionToCategory(unsigned int32 value)
0x1c919  ldarg.0
0x1c91a  ldstr    aSystemuser// "systemuser"
0x1c91f  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::set_ConnectionToEntity(string value)
0x1c924  ldarg.0
0x1c925  ldc.i4.1
0x1c926  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::set_EnableInlineEdit(bool value)
0x1c92b  ret
0x1c92c  ldarg.0
0x1c92d  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_IsCompetitorsGrid()
0x1c932  brfalse.s loc_1C944
0x1c934  ldarg.0
0x1c935  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_IsRefreshFCBEnabled()
0x1c93a  brfalse.s loc_1C944
0x1c93c  ldarg.0
0x1c93d  ldc.i4.1
0x1c93e  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::set_EnableInlineEdit(bool value)
0x1c943  ret
0x1c944  ldarg.0
0x1c945  ldc.i4.0
0x1c946  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::set_EnableInlineEdit(bool value)
0x1c94b  ret
```
