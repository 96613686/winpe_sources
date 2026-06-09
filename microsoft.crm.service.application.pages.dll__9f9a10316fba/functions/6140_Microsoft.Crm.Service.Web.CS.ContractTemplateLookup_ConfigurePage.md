# Microsoft.Crm.Service.Web.CS.ContractTemplateLookup::ConfigurePage

- ea: `0x6140`
- end: `0x61c5`
- name: `Microsoft.Crm.Service.Web.CS.ContractTemplateLookup::ConfigurePage`
- size: `133`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x6140`

## string_xrefs

- `0x6163`: `<contracttemplates morerecords="0"></contracttemplates>`
- `0x617b`: `contractsLookupTemplate.xsl`
- `0x6197`: `Web.CS.contracts.lookup_template.aspx_123`

## pseudocode

```c

```

## disassembly

```asm
0x6140  ldarg.0
0x6141  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigurePage()
0x6146  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x614b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.ServiceDataSource::RetrieveContractTemplates(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6150  stloc.0
0x6151  ldloc.0
0x6152  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x6157  ldc.i4.0
0x6158  ble.s    loc_6163
0x615a  ldloc.0
0x615b  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection::Serialize(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection)
0x6160  stloc.1
0x6161  br.s     loc_6169
0x6163  ldstr    aContracttempla// "<contracttemplates morerecords=\"0\"></"...
0x6168  stloc.1
0x6169  ldarg.0
0x616a  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.XmlRenderer Microsoft.Crm.Service.Web.CS.ContractTemplateLookup::xmlRenderer
0x616f  ldloc.1
0x6170  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.XmlRenderer::set_XmlData(string)
0x6175  ldarg.0
0x6176  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.XmlRenderer Microsoft.Crm.Service.Web.CS.ContractTemplateLookup::xmlRenderer
0x617b  ldstr    aContractslooku// "contractsLookupTemplate.xsl"
0x6180  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.XmlRenderer::set_XslFileId(string)
0x6185  ldarg.0
0x6186  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x618b  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x6190  dup
0x6191  ldarg.0
0x6192  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6197  ldstr    aWebCsContracts_1// "Web.CS.contracts.lookup_template.aspx_1"...
0x619c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x61a1  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x61a6  dup
0x61a7  ldc.i4.0
0x61a8  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ButtonStyle(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x61ad  dup
0x61ae  ldc.i4.1
0x61af  ldstr    aButtonLabelSel// "Button_Label_Select"
0x61b4  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0x61b9  ldc.i4.2
0x61ba  ldstr    aButtonLabelCan// "Button_Label_Cancel"
0x61bf  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0x61c4  ret
```
