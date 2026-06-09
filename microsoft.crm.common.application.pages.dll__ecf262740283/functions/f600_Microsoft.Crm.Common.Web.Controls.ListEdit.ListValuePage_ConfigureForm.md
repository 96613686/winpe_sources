# Microsoft.Crm.Common.Web.Controls.ListEdit.ListValuePage::ConfigureForm

- ea: `0xf600`
- end: `0xf724`
- name: `Microsoft.Crm.Common.Web.Controls.ListEdit.ListValuePage::ConfigureForm`
- size: `292`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0xf600`

## string_xrefs

- `0xf683`: `minValueForSystemPicklists`

## pseudocode

```c

```

## disassembly

```asm
0xf600  ldarg.0
0xf601  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0xf606  ldarg.0
0xf607  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xf60c  stloc.0
0xf60d  ldarg.0
0xf60e  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentForm()
0xf613  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0xf618  stloc.1
0xf619  ldarg.0
0xf61a  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xf61f  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xf624  ldstr    aMode// "mode"
0xf629  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xf62e  stloc.2
0xf62f  ldarg.0
0xf630  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf635  ldstr    aMode// "mode"
0xf63a  ldloc.2
0xf63b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xf640  ldarg.0
0xf641  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xf646  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xf64b  ldstr    aIsattribute// "isAttribute"
0xf650  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xf655  stloc.3
0xf656  ldarg.0
0xf657  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf65c  ldstr    aIsattribute// "isAttribute"
0xf661  ldloc.3
0xf662  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xf667  ldarg.0
0xf668  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf66d  ldstr    aMaxvalueforpic// "maxValueForPicklists"
0xf672  ldc.i4   0x7FFFFFFE
0xf677  conv.i8
0xf678  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0xf67d  ldarg.0
0xf67e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf683  ldstr    aMinvalueforsys// "minValueForSystemPicklists"
0xf688  ldc.i4.0
0xf689  conv.i8
0xf68a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0xf68f  ldarg.0
0xf690  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf695  ldstr    aMinvalueforcus// "minValueForCustomPicklists"
0xf69a  ldc.i4.0
0xf69b  conv.i8
0xf69c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0xf6a1  ldloc.1
0xf6a2  ldc.i4.1
0xf6a3  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ShowHeader(bool)
0xf6a8  ldloc.2
0xf6a9  ldstr    aAdd// "add"
0xf6ae  call     bool [mscorlib]System.String::op_Equality(string, string)
0xf6b3  brfalse.s loc_F6D9
0xf6b5  ldloc.1
0xf6b6  ldloc.0
0xf6b7  ldstr    aWebControlsLis_0// "Web._controls.listedit.dialogs.AddValue"...
0xf6bc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf6c1  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0xf6c6  ldloc.1
0xf6c7  ldloc.0
0xf6c8  ldstr    aWebControlsLis_1// "Web._controls.listedit.dialogs.AddValue"...
0xf6cd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf6d2  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0xf6d7  br.s     loc_F6FB
0xf6d9  ldloc.1
0xf6da  ldloc.0
0xf6db  ldstr    aWebControlsLis_2// "Web._controls.listedit.dialogs.EditValu"...
0xf6e0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf6e5  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0xf6ea  ldloc.1
0xf6eb  ldloc.0
0xf6ec  ldstr    aWebControlsLis_3// "Web._controls.listedit.dialogs.EditValu"...
0xf6f1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf6f6  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0xf6fb  ldarg.0
0xf6fc  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Number Microsoft.Crm.Common.Web.Controls.ListEdit.ListValuePage::numValue
0xf701  ldc.i4.0
0xf702  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Number::set_Precision(int32)
0xf707  ldarg.0
0xf708  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.TextBox Microsoft.Crm.Common.Web.Controls.ListEdit.ListValuePage::txtLabel
0xf70d  ldc.i4   0xFF
0xf712  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.TextBox::set_MaxLength(int32)
0xf717  ldarg.0
0xf718  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.TextBox Microsoft.Crm.Common.Web.Controls.ListEdit.ListValuePage::txtColor
0xf71d  ldc.i4.7
0xf71e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.TextBox::set_MaxLength(int32)
0xf723  ret
```
