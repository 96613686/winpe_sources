# Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader

- ea: `0x23b60`
- end: `0x23b82`
- name: `Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader`
- size: `34`
- prototype: ``
- caller_count: `48`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x390`
- `0x9770`
- `0xa8f0`
- `0xad10`
- `0xaec0`
- `0xb7a0`
- `0xbdf0`
- `0xc960`
- `0xd750`
- `0xf3e0`
- `0xf9e0`
- `0x11cf0`
- `0x14600`
- `0x149e0`
- `0x15540`
- `0x15c90`
- `0x15e10`
- `0x169d0`
- `0x16a90`
- `0x16f30`
- `0x17900`
- `0x183a0`
- `0x19240`
- `0x194f0`
- `0x1ad90`
- `0x1bd00`
- `0x1ccf0`
- `0x1d7b0`
- `0x1f440`
- `0x1f720`
- `0x1ffc0`
- `0x20210`
- `0x20470`
- `0x20820`
- `0x20db0`
- `0x21190`
- `0x21f40`
- `0x22a30`
- `0x22f10`
- `0x236c0`
- `0x238a0`
- `0x238e0`
- `0x23f20`
- `0x24080`
- `0x24430`
- `0x25370`
- `0x26650`
- `0x281f0`

## callees

- `0x85b0`
- `0x23b10`
- `0x23b60`
- `0x23b90`
- `0x23be0`

## pseudocode

```c

```

## disassembly

```asm
0x23b60  call     class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_HeaderControl()
0x23b65  stloc.0
0x23b66  ldarg.0
0x23b67  call     instance bool Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_EnableOnDemandInit()
0x23b6c  brfalse.s loc_23B80
0x23b6e  ldloc.0
0x23b6f  castclass Microsoft.Crm.Controls.Header
0x23b74  ldarg.0
0x23b75  call     instance string Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_IdForControlHeader()
0x23b7a  callvirt instance class Microsoft.Crm.Controls.Header Microsoft.Crm.Controls.Header::GetControlHeader(string id)
0x23b7f  stloc.0
0x23b80  ldloc.0
0x23b81  ret
```
