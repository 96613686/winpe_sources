# Microsoft.Crm.Marketing.Application.Pages.MA.MiniCampaignPage::MakeCrmControlDisabled

- ea: `0x2c40`
- end: `0x2c69`
- name: `Microsoft.Crm.Marketing.Application.Pages.MA.MiniCampaignPage::MakeCrmControlDisabled`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x3920`

## callees

- `0x2c40`

## pseudocode

```c

```

## disassembly

```asm
0x2c40  ldnull
0x2c41  stloc.0
0x2c42  ldarg.1
0x2c43  stloc.1
0x2c44  ldc.i4.0
0x2c45  stloc.2
0x2c46  br.s     loc_2C62
0x2c48  ldloc.1
0x2c49  ldloc.2
0x2c4a  ldelem.ref
0x2c4b  stloc.3
0x2c4c  ldarg.0
0x2c4d  ldloc.3
0x2c4e  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0x2c53  stloc.0
0x2c54  ldloc.0
0x2c55  brfalse.s loc_2C5E
0x2c57  ldloc.0
0x2c58  ldc.i4.1
0x2c59  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl::set_Disabled(bool)
0x2c5e  ldloc.2
0x2c5f  ldc.i4.1
0x2c60  add
0x2c61  stloc.2
0x2c62  ldloc.2
0x2c63  ldloc.1
0x2c64  ldlen
0x2c65  conv.i4
0x2c66  blt.s    loc_2C48
0x2c68  ret
```
