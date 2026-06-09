# Microsoft.Crm.Dialogs.IncidentMessageDialogPage::ConfigureForm

- ea: `0x1160`
- end: `0x1201`
- name: `Microsoft.Crm.Dialogs.IncidentMessageDialogPage::ConfigureForm`
- size: `161`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1160`

## pseudocode

```c

```

## disassembly

```asm
0x1160  ldarg.0
0x1161  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0x1166  ldarg.0
0x1167  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x116c  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x1171  stloc.0
0x1172  ldarg.0
0x1173  ldarg.0
0x1174  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1179  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x117e  ldstr    aRequesttype// "requestType"
0x1183  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1188  stfld    string Microsoft.Crm.Dialogs.IncidentMessageDialogPage::requestType
0x118d  ldarg.0
0x118e  ldfld    string Microsoft.Crm.Dialogs.IncidentMessageDialogPage::requestType
0x1193  stloc.1
0x1194  ldloc.1
0x1195  ldstr    aMerge// "merge"
0x119a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x119f  brtrue.s loc_11B0
0x11a1  ldloc.1
0x11a2  ldstr    aAssociatechild// "associatechild"
0x11a7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x11ac  brtrue.s loc_11C8
0x11ae  br.s     loc_11DE
0x11b0  ldloc.0
0x11b1  ldarg.0
0x11b2  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x11b7  ldstr    aMultipleMergeT// "Multiple_Merge_Title"
0x11bc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x11c1  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x11c6  br.s     loc_11DE
0x11c8  ldloc.0
0x11c9  ldarg.0
0x11ca  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x11cf  ldstr    aAssociateChild// "Associate_Child_Title"
0x11d4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x11d9  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x11de  ldarg.0
0x11df  ldarg.0
0x11e0  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x11e5  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x11ea  ldstr    aMessagecontent// "messageContent"
0x11ef  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x11f4  stfld    string Microsoft.Crm.Dialogs.IncidentMessageDialogPage::messageContent
0x11f9  ldloc.0
0x11fa  ldc.i4.1
0x11fb  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ButtonStyle(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x1200  ret
```
