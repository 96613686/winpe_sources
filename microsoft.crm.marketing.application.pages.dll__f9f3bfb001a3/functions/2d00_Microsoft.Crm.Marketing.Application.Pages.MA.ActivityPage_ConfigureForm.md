# Microsoft.Crm.Marketing.Application.Pages.MA.ActivityPage::ConfigureForm

- ea: `0x2d00`
- end: `0x2d7c`
- name: `Microsoft.Crm.Marketing.Application.Pages.MA.ActivityPage::ConfigureForm`
- size: `124`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x3190`

## pseudocode

```c

```

## disassembly

```asm
0x2d00  ldarg.0
0x2d01  ldstr    aMcMsgHeaderAct_0// "MC_MSG_Header_ActivityAndAssignment"
0x2d06  ldstr    aMcMsgChooseact// "MC_MSG_ChooseActivity"
0x2d0b  call     instance void Microsoft.Crm.Marketing.Application.Pages.MA.MiniCampaignBasePage::SetTitleAndDescription(string titleId, string descriptionId)
0x2d10  ldarg.0
0x2d11  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Marketing.Application.Pages.MA.ActivityPage::ActivityLookup
0x2d16  ldstr    aSingle// "single"
0x2d1b  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupStyle(string)
0x2d20  ldarg.0
0x2d21  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Marketing.Application.Pages.MA.ActivityPage::ActivityLookup
0x2d26  ldc.i4.2
0x2d27  newarr   [mscorlib]System.Int32
0x2d2c  dup
0x2d2d  ldc.i4.0
0x2d2e  ldc.i4.8
0x2d2f  stelem.i4
0x2d30  dup
0x2d31  ldc.i4.1
0x2d32  ldc.i4.s 9
0x2d34  stelem.i4
0x2d35  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupTypes(int32[])
0x2d3a  ldarg.0
0x2d3b  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Marketing.Application.Pages.MA.ActivityPage::ActivityLookup
0x2d40  ldc.i4.1
0x2d41  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0x2d46  ldarg.0
0x2d47  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Marketing.Application.Pages.MA.ActivityPage::QueueLookup
0x2d4c  ldstr    aSingle// "single"
0x2d51  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupStyle(string)
0x2d56  ldarg.0
0x2d57  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Marketing.Application.Pages.MA.ActivityPage::QueueLookup
0x2d5c  ldc.i4.1
0x2d5d  newarr   [mscorlib]System.Int32
0x2d62  dup
0x2d63  ldc.i4.0
0x2d64  ldc.i4   0x7E4
0x2d69  stelem.i4
0x2d6a  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupTypes(int32[])
0x2d6f  ldarg.0
0x2d70  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Marketing.Application.Pages.MA.ActivityPage::QueueLookup
0x2d75  ldc.i4.1
0x2d76  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0x2d7b  ret
```
