# Microsoft.Crm.Marketing.Application.Pages.MA.ActivityFormPage::ConfigurePage

- ea: `0x38c0`
- end: `0x391e`
- name: `Microsoft.Crm.Marketing.Application.Pages.MA.ActivityFormPage::ConfigurePage`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x38c0`

## pseudocode

```c

```

## disassembly

```asm
0x38c0  ldarg.0
0x38c1  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x38c6  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x38cb  ldstr    aObjecttypecode_0// "objectTypeCode"
0x38d0  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x38d5  ldc.i4   0x106A
0x38da  stloc.0
0x38db  ldloca.s 0
0x38dd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x38e2  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x38e7  ldc.i4.5
0x38e8  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x38ed  brtrue.s loc_38FC
0x38ef  ldarg.0
0x38f0  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EmailActivityForm::.ctor()
0x38f5  stfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x38fa  br.s     loc_3907
0x38fc  ldarg.0
0x38fd  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.ActivityForm::.ctor()
0x3902  stfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x3907  ldarg.0
0x3908  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Marketing.Application.Pages.MA.ActivityFormPage::formDiv
0x390d  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x3912  ldarg.0
0x3913  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x3918  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x391d  ret
```
