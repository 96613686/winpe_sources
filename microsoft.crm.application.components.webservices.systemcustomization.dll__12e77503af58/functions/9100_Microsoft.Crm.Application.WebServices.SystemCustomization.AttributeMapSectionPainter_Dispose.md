# Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::Dispose

- ea: `0x9100`
- end: `0x913b`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::Dispose`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x5750`

## callees

- `0x9100`

## pseudocode

```c

```

## disassembly

```asm
0x9100  ldarg.0
0x9101  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlTable Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_attributeMapTable
0x9106  brfalse.s loc_913A
0x9108  ldarg.0
0x9109  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_sourceFieldsSelectControl
0x910e  brfalse.s loc_9122
0x9110  ldarg.0
0x9111  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_sourceFieldsSelectControl
0x9116  callvirt instance void [System.Web]System.Web.UI.Control::Dispose()
0x911b  ldarg.0
0x911c  ldnull
0x911d  stfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_sourceFieldsSelectControl
0x9122  ldarg.0
0x9123  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlTable Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_attributeMapTable
0x9128  callvirt instance void [System.Web]System.Web.UI.Control::Dispose()
0x912d  ldarg.0
0x912e  ldnull
0x912f  stfld    class [System.Web]System.Web.UI.HtmlControls.HtmlTable Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_attributeMapTable
0x9134  ldarg.0
0x9135  call     void [mscorlib]System.GC::SuppressFinalize(object)
0x913a  ret
```
