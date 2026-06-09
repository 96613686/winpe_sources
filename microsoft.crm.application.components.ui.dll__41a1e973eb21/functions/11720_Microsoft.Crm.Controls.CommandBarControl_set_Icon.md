# Microsoft.Crm.Controls.CommandBarControl::set_Icon

- ea: `0x11720`
- end: `0x1173c`
- name: `Microsoft.Crm.Controls.CommandBarControl::set_Icon`
- size: `28`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xd1e0`
- `0xd410`
- `0xd640`
- `0xe010`
- `0xe290`
- `0xe4d0`
- `0xf1e0`
- `0xf4a0`

## callees

- `0x11720`

## pseudocode

```c

```

## disassembly

```asm
0x11720  ldarg.0
0x11721  ldarg.1
0x11722  brtrue.s loc_11735
0x11724  ldstr    asc_3280A// ""
0x11729  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1172e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x11733  br.s     loc_11736
0x11735  ldarg.1
0x11736  stfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Controls.CommandBarControl::_icon
0x1173b  ret
```
