# Microsoft.Crm.Service.Dialogs.DeleteServiceRestrictionPage::ConfigureForm

- ea: `0x1800`
- end: `0x186e`
- name: `Microsoft.Crm.Service.Dialogs.DeleteServiceRestrictionPage::ConfigureForm`
- size: `110`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## string_xrefs

- `0x1819`: `Dialog_DeleteServiceRestriction_Title`
- `0x1834`: `Dialog_DeleteServiceRestriction_SubHeading`

## pseudocode

```c

```

## disassembly

```asm
0x1800  ldarg.0
0x1801  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0x1806  ldarg.0
0x1807  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x180c  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x1811  stloc.0
0x1812  ldloc.0
0x1813  ldarg.0
0x1814  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1819  ldstr    aDialogDeletese// "Dialog_DeleteServiceRestriction_Title"
0x181e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1823  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x1828  ldloc.0
0x1829  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x182e  ldarg.0
0x182f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1834  ldstr    aDialogDeletese_0// "Dialog_DeleteServiceRestriction_SubHead"...
0x1839  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x183e  ldc.i4.1
0x183f  newarr   [mscorlib]System.Object
0x1844  dup
0x1845  ldc.i4.0
0x1846  ldarg.0
0x1847  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x184c  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1851  ldstr    aN// "n"
0x1856  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x185b  stelem.ref
0x185c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1861  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x1866  ldloc.0
0x1867  ldc.i4.3
0x1868  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ButtonStyle(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x186d  ret
```
