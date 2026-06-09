# Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::Render

- ea: `0x7e60`
- end: `0x7e98`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::Render`
- size: `56`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x5750`

## callees

- `0x7ea0`
- `0x7fe0`
- `0x8110`
- `0x8200`
- `0x8310`
- `0x84a0`

## pseudocode

```c

```

## disassembly

```asm
0x7e60  ldarg.0
0x7e61  call     instance void Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::InitializeAttributeMapTable()
0x7e66  ldarg.0
0x7e67  call     instance void Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::InitializeAttributeLists()
0x7e6c  ldarg.0
0x7e6d  call     instance void Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::InitializeSelectControls()
0x7e72  ldarg.0
0x7e73  call     instance void Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::PopulateAttributeMapTable()
0x7e78  ldarg.0
0x7e79  ldarg.1
0x7e7a  call     instance void Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::AddJavaScriptData(class [System.Web]System.Web.UI.HtmlTextWriter output)
0x7e7f  ldarg.0
0x7e80  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlTable Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_attributeMapTable
0x7e85  ldarg.1
0x7e86  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x7e8b  ldarg.0
0x7e8c  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::ReferencedEntities()
0x7e91  ldarg.1
0x7e92  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x7e97  ret
```
