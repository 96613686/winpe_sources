# Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::InitializeAttributeMapTable

- ea: `0x8200`
- end: `0x829d`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::InitializeAttributeMapTable`
- size: `157`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x7e60`

## callees

- `0x82a0`

## pseudocode

```c

```

## disassembly

```asm
0x8200  ldarg.0
0x8201  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlTable Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_attributeMapTable
0x8206  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x820b  ldstr    aClass// "class"
0x8210  ldstr    aMscrmIwAmpAttr// "mscrm-iw-AMP-AttributeTable"
0x8215  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0x821a  ldarg.0
0x821b  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlTable Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_attributeMapTable
0x8220  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x8225  ldstr    aPkAttribute// "pk_attribute"
0x822a  ldarg.0
0x822b  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportEntity Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_targetEntity
0x8230  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportEntity::get_PrimaryKeyAttributeName()
0x8235  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0x823a  ldarg.0
0x823b  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlTable Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_attributeMapTable
0x8240  ldc.i4.0
0x8241  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlTable::set_CellSpacing(int32)
0x8246  ldarg.0
0x8247  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlTable Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_attributeMapTable
0x824c  ldc.i4.4
0x824d  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlTable::set_CellPadding(int32)
0x8252  ldarg.0
0x8253  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlTable Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_attributeMapTable
0x8258  callvirt instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableRowCollection [System.Web]System.Web.UI.HtmlControls.HtmlTable::get_Rows()
0x825d  ldarg.0
0x825e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8263  ldstr    aImportwizardAt_2// "ImportWizard.AttributeMapPage.Attribute"...
0x8268  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x826d  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableRow Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::CreateHeaderRow(string headerText)
0x8272  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableRowCollection::Add(class [System.Web]System.Web.UI.HtmlControls.HtmlTableRow)
0x8277  ldarg.0
0x8278  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlTable Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_attributeMapTable
0x827d  callvirt instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableRowCollection [System.Web]System.Web.UI.HtmlControls.HtmlTable::get_Rows()
0x8282  ldarg.0
0x8283  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8288  ldstr    aImportwizardAt_3// "ImportWizard.AttributeMapPage.Attribute"...
0x828d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8292  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableRow Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::CreateHeaderRow(string headerText)
0x8297  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableRowCollection::Add(class [System.Web]System.Web.UI.HtmlControls.HtmlTableRow)
0x829c  ret
```
