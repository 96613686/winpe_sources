# Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::get_OrganizationContext

- ea: `0x3570`
- end: `0x3589`
- name: `Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::get_OrganizationContext`
- size: `25`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x3ec0`
- `0x4150`
- `0x44d0`
- `0x4660`
- `0x4790`
- `0x4a10`
- `0x4db0`
- `0x5090`
- `0x50e0`

## callees

- `0x3570`

## pseudocode

```c

```

## disassembly

```asm
0x3570  ldarg.0
0x3571  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::_organizationContext
0x3576  dup
0x3577  brtrue.s loc_3588
0x3579  pop
0x357a  ldarg.0
0x357b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x3580  dup
0x3581  stloc.0
0x3582  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::_organizationContext
0x3587  ldloc.0
0x3588  ret
```
