# Microsoft.Crm.Marketing.Application.Pages.MA.MiniCampaignPage::ConfigureForm

- ea: `0x28d0`
- end: `0x29ba`
- name: `Microsoft.Crm.Marketing.Application.Pages.MA.MiniCampaignPage::ConfigureForm`
- size: `234`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0x2953`: `Title_Create_AMiniCampaign_Wizard`

## pseudocode

```c

```

## disassembly

```asm
0x28d0  ldarg.0
0x28d1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0x28d6  ldarg.0
0x28d7  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Marketing.Application.Pages.MA.MiniCampaignPage::ActivityLookup
0x28dc  ldstr    aSingle// "single"
0x28e1  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupStyle(string)
0x28e6  ldarg.0
0x28e7  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Marketing.Application.Pages.MA.MiniCampaignPage::ActivityLookup
0x28ec  ldc.i4.2
0x28ed  newarr   [mscorlib]System.Int32
0x28f2  dup
0x28f3  ldc.i4.0
0x28f4  ldc.i4.8
0x28f5  stelem.i4
0x28f6  dup
0x28f7  ldc.i4.1
0x28f8  ldc.i4.s 9
0x28fa  stelem.i4
0x28fb  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupTypes(int32[])
0x2900  ldarg.0
0x2901  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Marketing.Application.Pages.MA.MiniCampaignPage::ActivityLookup
0x2906  ldc.i4.1
0x2907  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0x290c  ldarg.0
0x290d  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Marketing.Application.Pages.MA.MiniCampaignPage::QueueLookup
0x2912  ldstr    aSingle// "single"
0x2917  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupStyle(string)
0x291c  ldarg.0
0x291d  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Marketing.Application.Pages.MA.MiniCampaignPage::QueueLookup
0x2922  ldc.i4.1
0x2923  newarr   [mscorlib]System.Int32
0x2928  dup
0x2929  ldc.i4.0
0x292a  ldc.i4   0x7E4
0x292f  stelem.i4
0x2930  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupTypes(int32[])
0x2935  ldarg.0
0x2936  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Marketing.Application.Pages.MA.MiniCampaignPage::QueueLookup
0x293b  ldc.i4.1
0x293c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0x2941  ldarg.0
0x2942  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x2947  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x294c  dup
0x294d  ldarg.0
0x294e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x2953  ldstr    aTitleCreateAmi// "Title_Create_AMiniCampaign_Wizard"
0x2958  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x295d  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x2962  dup
0x2963  ldc.i4.0
0x2964  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ButtonStyle(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x2969  dup
0x296a  ldstr    aButback// "butBack"
0x296f  ldstr    aMcButtonBack// "MC_Button_Back"
0x2974  ldstr    aBtnback// "btnBack();"
0x2979  ldc.i4.1
0x297a  ldc.i4   0x800
0x297f  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(string, string, string, bool, valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x2984  dup
0x2985  ldstr    aButnext// "butNext"
0x298a  ldstr    aMcButtonNext// "MC_Button_Next"
0x298f  ldstr    aBtnnextNewSysU// "btnNext(new Sys.UI.DomEvent(event));"
0x2994  ldc.i4.1
0x2995  ldc.i4   0x800
0x299a  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(string, string, string, bool, valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x299f  ldstr    aButcancel// "butCancel"
0x29a4  ldstr    aMcButtonCancel// "MC_Button_Cancel"
0x29a9  ldstr    aBtncancel// "btnCancel();"
0x29ae  ldc.i4.1
0x29af  ldc.i4   0x800
0x29b4  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(string, string, string, bool, valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x29b9  ret
```
