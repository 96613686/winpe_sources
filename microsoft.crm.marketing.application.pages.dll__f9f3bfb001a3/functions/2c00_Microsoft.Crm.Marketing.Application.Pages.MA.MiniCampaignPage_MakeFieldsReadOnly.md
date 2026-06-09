# Microsoft.Crm.Marketing.Application.Pages.MA.MiniCampaignPage::MakeFieldsReadOnly

- ea: `0x2c00`
- end: `0x2c35`
- name: `Microsoft.Crm.Marketing.Application.Pages.MA.MiniCampaignPage::MakeFieldsReadOnly`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x3920`

## callees

- `0x2c00`

## pseudocode

```c

```

## disassembly

```asm
0x2c00  ldnull
0x2c01  stloc.0
0x2c02  ldarg.1
0x2c03  stloc.1
0x2c04  ldc.i4.0
0x2c05  stloc.2
0x2c06  br.s     loc_2C2E
0x2c08  ldloc.1
0x2c09  ldloc.2
0x2c0a  ldelem.ref
0x2c0b  stloc.3
0x2c0c  ldarg.0
0x2c0d  ldloc.3
0x2c0e  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0x2c13  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmDataControl
0x2c18  stloc.0
0x2c19  ldloc.0
0x2c1a  brfalse.s loc_2C2A
0x2c1c  ldloc.0
0x2c1d  ldnull
0x2c1e  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmDataControl::set_Value(object)
0x2c23  ldloc.0
0x2c24  ldc.i4.1
0x2c25  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl::set_ReadOnly(bool)
0x2c2a  ldloc.2
0x2c2b  ldc.i4.1
0x2c2c  add
0x2c2d  stloc.2
0x2c2e  ldloc.2
0x2c2f  ldloc.1
0x2c30  ldlen
0x2c31  conv.i4
0x2c32  blt.s    loc_2C08
0x2c34  ret
```
