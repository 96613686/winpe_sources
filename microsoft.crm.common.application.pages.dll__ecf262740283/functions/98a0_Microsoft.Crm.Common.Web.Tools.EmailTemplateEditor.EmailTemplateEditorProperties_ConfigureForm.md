# Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorProperties::ConfigureForm

- ea: `0x98a0`
- end: `0x9996`
- name: `Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorProperties::ConfigureForm`
- size: `246`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x99a0`

## string_xrefs

- `0x98f9`: `PickList_EmailTemplate_Global`

## pseudocode

```c

```

## disassembly

```asm
0x98a0  ldarg.0
0x98a1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0x98a6  ldarg.0
0x98a7  ldarg.0
0x98a8  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentForm()
0x98ad  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x98b2  stfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorProperties::form
0x98b7  ldarg.0
0x98b8  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorProperties::form
0x98bd  ldarg.0
0x98be  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x98c3  ldstr    aEmailTmplDlgTi// "Email_Tmpl_Dlg_Title"
0x98c8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x98cd  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x98d2  ldarg.0
0x98d3  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorProperties::form
0x98d8  ldarg.0
0x98d9  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x98de  ldstr    aEmailTmplDlgDe// "Email_Tmpl_Dlg_Desc"
0x98e3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x98e8  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x98ed  ldarg.0
0x98ee  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorProperties::templateType
0x98f3  ldarg.0
0x98f4  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x98f9  ldstr    aPicklistEmailt// "PickList_EmailTemplate_Global"
0x98fe  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9903  ldc.i4.8
0x9904  stloc.0
0x9905  ldloca.s 0
0x9907  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x990c  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x9911  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddItem(string, string)
0x9916  ldarg.0
0x9917  ldc.i4.4
0x9918  call     instance void Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorProperties::AddTypeOption(int32 typeCode)
0x991d  ldarg.0
0x991e  ldc.i4.3
0x991f  call     instance void Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorProperties::AddTypeOption(int32 typeCode)
0x9924  ldarg.0
0x9925  ldc.i4.1
0x9926  call     instance void Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorProperties::AddTypeOption(int32 typeCode)
0x992b  ldarg.0
0x992c  ldc.i4.2
0x992d  call     instance void Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorProperties::AddTypeOption(int32 typeCode)
0x9932  ldarg.0
0x9933  ldc.i4   0x43C
0x9938  call     instance void Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorProperties::AddTypeOption(int32 typeCode)
0x993d  ldarg.0
0x993e  ldc.i4   0x440
0x9943  call     instance void Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorProperties::AddTypeOption(int32 typeCode)
0x9948  ldarg.0
0x9949  ldc.i4   0x442
0x994e  call     instance void Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorProperties::AddTypeOption(int32 typeCode)
0x9953  ldarg.0
0x9954  ldc.i4.s 0x70
0x9956  call     instance void Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorProperties::AddTypeOption(int32 typeCode)
0x995b  ldarg.0
0x995c  ldc.i4   0x3F2
0x9961  call     instance void Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorProperties::AddTypeOption(int32 typeCode)
0x9966  ldarg.0
0x9967  ldc.i4   0x1076
0x996c  call     instance void Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorProperties::AddTypeOption(int32 typeCode)
0x9971  ldarg.0
0x9972  ldc.i4   0x125C
0x9977  call     instance void Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorProperties::AddTypeOption(int32 typeCode)
0x997c  ldarg.0
0x997d  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorProperties::templateType
0x9982  ldc.i4.8
0x9983  stloc.0
0x9984  ldloca.s 0
0x9986  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x998b  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x9990  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::set_Selected(string)
0x9995  ret
```
