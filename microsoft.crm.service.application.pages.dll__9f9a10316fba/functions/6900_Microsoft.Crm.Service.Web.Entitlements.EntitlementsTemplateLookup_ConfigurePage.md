# Microsoft.Crm.Service.Web.Entitlements.EntitlementsTemplateLookup::ConfigurePage

- ea: `0x6900`
- end: `0x6985`
- name: `Microsoft.Crm.Service.Web.Entitlements.EntitlementsTemplateLookup::ConfigurePage`
- size: `133`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x6900`

## string_xrefs

- `0x6923`: `<entitlementtemplates morerecords="0"></entitlementtemplates>`
- `0x693b`: `EntitlementsLookupTemplate.xsl`
- `0x6957`: `Web.entitlements.lookup_template.aspx_123`

## pseudocode

```c

```

## disassembly

```asm
0x6900  ldarg.0
0x6901  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigurePage()
0x6906  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x690b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.ServiceDataSource::RetrieveEntitlementsTemplates(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6910  stloc.0
0x6911  ldloc.0
0x6912  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x6917  ldc.i4.0
0x6918  ble.s    loc_6923
0x691a  ldloc.0
0x691b  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection::Serialize(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection)
0x6920  stloc.1
0x6921  br.s     loc_6929
0x6923  ldstr    aEntitlementtem// "<entitlementtemplates morerecords=\"0\""...
0x6928  stloc.1
0x6929  ldarg.0
0x692a  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.XmlRenderer Microsoft.Crm.Service.Web.Entitlements.EntitlementsTemplateLookup::xmlRenderer
0x692f  ldloc.1
0x6930  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.XmlRenderer::set_XmlData(string)
0x6935  ldarg.0
0x6936  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.XmlRenderer Microsoft.Crm.Service.Web.Entitlements.EntitlementsTemplateLookup::xmlRenderer
0x693b  ldstr    aEntitlementslo// "EntitlementsLookupTemplate.xsl"
0x6940  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.XmlRenderer::set_XslFileId(string)
0x6945  ldarg.0
0x6946  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x694b  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x6950  dup
0x6951  ldarg.0
0x6952  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6957  ldstr    aWebEntitlement_1// "Web.entitlements.lookup_template.aspx_1"...
0x695c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6961  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x6966  dup
0x6967  ldc.i4.0
0x6968  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ButtonStyle(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x696d  dup
0x696e  ldc.i4.1
0x696f  ldstr    aButtonLabelSel// "Button_Label_Select"
0x6974  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0x6979  ldc.i4.2
0x697a  ldstr    aButtonLabelCan// "Button_Label_Cancel"
0x697f  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0x6984  ret
```
