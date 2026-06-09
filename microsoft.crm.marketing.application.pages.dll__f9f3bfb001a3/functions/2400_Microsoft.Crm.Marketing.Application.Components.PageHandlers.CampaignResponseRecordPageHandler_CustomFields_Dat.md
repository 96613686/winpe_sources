# Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignResponseRecordPageHandler::CustomFields_DataBoundReady

- ea: `0x2400`
- end: `0x2430`
- name: `Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignResponseRecordPageHandler::CustomFields_DataBoundReady`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x2400`

## pseudocode

```c

```

## disassembly

```asm
0x2400  ldarg.2
0x2401  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CrmFormEventArgs::get_Form()
0x2406  ldstr    aRegardingobjec// "regardingobjectid"
0x240b  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0x2410  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmDataControl
0x2415  stloc.0
0x2416  ldloc.0
0x2417  brfalse.s loc_242F
0x2419  ldloc.0
0x241a  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmDataControl::get_Value()
0x241f  brfalse.s loc_242F
0x2421  ldloc.0
0x2422  ldc.i4.1
0x2423  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl::set_ReadOnly(bool)
0x2428  ldloc.0
0x2429  ldc.i4.1
0x242a  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl::set_Disabled(bool)
0x242f  ret
```
