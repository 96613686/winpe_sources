# Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignRecordPageHandler::CustomFields_DataBoundReady

- ea: `0x17a0`
- end: `0x17e7`
- name: `Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignRecordPageHandler::CustomFields_DataBoundReady`
- size: `71`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x15f0`
- `0x17a0`

## pseudocode

```c

```

## disassembly

```asm
0x17a0  ldarg.0
0x17a1  call     instance string Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignRecordPageHandler::get_IsTemplate()
0x17a6  ldstr    a1// "1"
0x17ab  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x17b0  brfalse.s loc_17E6
0x17b2  ldarg.0
0x17b3  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentForm()
0x17b8  callvirt instance valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormState [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_State()
0x17bd  ldc.i4.1
0x17be  bne.un.s loc_17E6
0x17c0  ldarg.2
0x17c1  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CrmFormEventArgs::get_Form()
0x17c6  ldstr    aExpectedrespon// "expectedresponse"
0x17cb  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0x17d0  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmDataControl
0x17d5  stloc.0
0x17d6  ldloc.0
0x17d7  brfalse.s loc_17E6
0x17d9  ldloc.0
0x17da  ldc.i4.s 0x64
0x17dc  box      [mscorlib]System.Int32
0x17e1  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmDataControl::set_Value(object)
0x17e6  ret
```
