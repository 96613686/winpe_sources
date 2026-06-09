# Microsoft.Crm.Application.Ribbon.XmlRendering.ToggleButton::RenderAttributes

- ea: `0x55930`
- end: `0x559d1`
- name: `Microsoft.Crm.Application.Ribbon.XmlRendering.ToggleButton::RenderAttributes`
- size: `161`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callees

- `0x55810`
- `0x55830`
- `0x55850`
- `0x55870`
- `0x55890`
- `0x558b0`
- `0x558d0`
- `0x558f0`
- `0x55910`
- `0x55d30`
- `0x55d60`
- `0x55da0`

## string_xrefs

- `0x55937`: `Command`
- `0x55948`: `QueryCommand`

## pseudocode

```c

```

## disassembly

```asm
0x55930  ldarg.0
0x55931  ldarg.1
0x55932  call     instance void Microsoft.Crm.Application.Ribbon.XmlRendering.RibbonXmlRenderer::RenderAttributes(class [System.Xml]System.Xml.XmlWriter writer)
0x55937  ldstr    aCommand// "Command"
0x5593c  ldarg.0
0x5593d  call     instance string Microsoft.Crm.Application.Ribbon.XmlRendering.ToggleButton::get_Command()
0x55942  ldarg.1
0x55943  call     void Microsoft.Crm.Application.Ribbon.XmlRendering.RibbonXmlRenderer::WriteOptionalAttribute(string name, string value, class [System.Xml]System.Xml.XmlWriter writer)
0x55948  ldstr    aQuerycommand// "QueryCommand"
0x5594d  ldarg.0
0x5594e  call     instance string Microsoft.Crm.Application.Ribbon.XmlRendering.ToggleButton::get_QueryCommand()
0x55953  ldarg.1
0x55954  call     void Microsoft.Crm.Application.Ribbon.XmlRendering.RibbonXmlRenderer::WriteOptionalAttribute(string name, string value, class [System.Xml]System.Xml.XmlWriter writer)
0x55959  ldstr    aSequence// "Sequence"
0x5595e  ldarg.0
0x5595f  call     instance valuetype [mscorlib]System.Nullable`1<int32> Microsoft.Crm.Application.Ribbon.XmlRendering.ToggleButton::get_Sequence()
0x55964  ldarg.1
0x55965  call     void Microsoft.Crm.Application.Ribbon.XmlRendering.RibbonXmlRenderer::WriteOptionalAttribute(string name, valuetype [mscorlib]System.Nullable`1<int32> value, class [System.Xml]System.Xml.XmlWriter writer)
0x5596a  ldstr    aTooltiptitle// "ToolTipTitle"
0x5596f  ldarg.0
0x55970  call     instance string Microsoft.Crm.Application.Ribbon.XmlRendering.ToggleButton::get_ToolTipTitle()
0x55975  ldarg.1
0x55976  call     void Microsoft.Crm.Application.Ribbon.XmlRendering.RibbonXmlRenderer::WriteOptionalAttribute(string name, string value, class [System.Xml]System.Xml.XmlWriter writer)
0x5597b  ldstr    aTooltipdescrip// "ToolTipDescription"
0x55980  ldarg.0
0x55981  call     instance string Microsoft.Crm.Application.Ribbon.XmlRendering.ToggleButton::get_ToolTipDescription()
0x55986  ldarg.1
0x55987  call     void Microsoft.Crm.Application.Ribbon.XmlRendering.RibbonXmlRenderer::WriteOptionalAttribute(string name, string value, class [System.Xml]System.Xml.XmlWriter writer)
0x5598c  ldstr    aAlt// "Alt"
0x55991  ldarg.0
0x55992  call     instance string Microsoft.Crm.Application.Ribbon.XmlRendering.ToggleButton::get_Alt()
0x55997  ldarg.1
0x55998  call     void Microsoft.Crm.Application.Ribbon.XmlRendering.RibbonXmlRenderer::WriteOptionalAttribute(string name, string value, class [System.Xml]System.Xml.XmlWriter writer)
0x5599d  ldstr    aLabeltext// "LabelText"
0x559a2  ldarg.0
0x559a3  call     instance string Microsoft.Crm.Application.Ribbon.XmlRendering.ToggleButton::get_LabelText()
0x559a8  ldarg.1
0x559a9  call     void Microsoft.Crm.Application.Ribbon.XmlRendering.RibbonXmlRenderer::WriteOptionalAttribute(string name, string value, class [System.Xml]System.Xml.XmlWriter writer)
0x559ae  ldstr    aImage16by16// "Image16by16"
0x559b3  ldarg.0
0x559b4  call     instance string Microsoft.Crm.Application.Ribbon.XmlRendering.ToggleButton::get_Image16by16()
0x559b9  ldarg.1
0x559ba  call     void Microsoft.Crm.Application.Ribbon.XmlRendering.RibbonXmlRenderer::WriteOptionalAttribute(string name, string value, class [System.Xml]System.Xml.XmlWriter writer)
0x559bf  ldstr    aImage32by32// "Image32by32"
0x559c4  ldarg.0
0x559c5  call     instance string Microsoft.Crm.Application.Ribbon.XmlRendering.ToggleButton::get_Image32by32()
0x559ca  ldarg.1
0x559cb  call     void Microsoft.Crm.Application.Ribbon.XmlRendering.RibbonXmlRenderer::WriteOptionalAttribute(string name, string value, class [System.Xml]System.Xml.XmlWriter writer)
0x559d0  ret
```
