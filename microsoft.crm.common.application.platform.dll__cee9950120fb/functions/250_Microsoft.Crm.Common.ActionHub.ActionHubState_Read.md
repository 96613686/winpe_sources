# Microsoft.Crm.Common.ActionHub.ActionHubState::Read

- ea: `0x250`
- end: `0x274`
- name: `Microsoft.Crm.Common.ActionHub.ActionHubState::Read`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x220`
- `0x240`
- `0x250`

## pseudocode

```c

```

## disassembly

```asm
0x250  newobj   instance void Microsoft.Crm.Common.ActionHub.ActionHubState::.ctor()
0x255  stloc.0
0x256  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x25b  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.ActionCardUtil::IsPreviewEnabledForActionCard(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x260  brtrue.s loc_26B
0x262  ldloc.0
0x263  ldc.i4.0
0x264  callvirt instance void Microsoft.Crm.Common.ActionHub.ActionHubState::set_IsActionHubFeatureEnabled(bool value)
0x269  br.s     loc_272
0x26b  ldloc.0
0x26c  ldc.i4.1
0x26d  callvirt instance void Microsoft.Crm.Common.ActionHub.ActionHubState::set_IsActionHubFeatureEnabled(bool value)
0x272  ldloc.0
0x273  ret
```
