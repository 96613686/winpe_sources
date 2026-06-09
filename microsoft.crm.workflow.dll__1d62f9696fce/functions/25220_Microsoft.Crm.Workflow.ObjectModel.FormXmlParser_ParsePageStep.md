# Microsoft.Crm.Workflow.ObjectModel.FormXmlParser::ParsePageStep

- ea: `0x25220`
- end: `0x25282`
- name: `Microsoft.Crm.Workflow.ObjectModel.FormXmlParser::ParsePageStep`
- size: `98`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x251b0`

## callees

- `0x25220`
- `0x25290`
- `0x255f0`
- `0x25770`
- `0x257b0`
- `0x257e0`

## pseudocode

```c

```

## disassembly

```asm
0x25220  ldnull
0x25221  stloc.0
0x25222  ldarg.0
0x25223  ldarg.1
0x25224  ldstr    aId_2// "id"
0x25229  call     instance string Microsoft.Crm.Workflow.ObjectModel.FormXmlParser::TryGetIdAttributeValue(class [System.Xml]System.Xml.XmlNode xmlNode, string attributeName)
0x2522e  stloc.1
0x2522f  ldarg.0
0x25230  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.PageStep> Microsoft.Crm.Workflow.ObjectModel.FormXmlParser::_pages
0x25235  ldloc.1
0x25236  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.PageStep>::ContainsKey(var<u1>)
0x2523b  brfalse.s loc_25246
0x2523d  ldarg.0
0x2523e  ldarg.1
0x2523f  call     instance bool Microsoft.Crm.Workflow.ObjectModel.FormXmlParser::HasSteps(class [System.Xml]System.Xml.XmlNode pageXmlNode)
0x25244  brtrue.s loc_25247
0x25246  ret
0x25247  ldarg.0
0x25248  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.PageStep> Microsoft.Crm.Workflow.ObjectModel.FormXmlParser::_pages
0x2524d  ldloc.1
0x2524e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.PageStep>::get_Item(void)
0x25253  stloc.0
0x25254  ldloc.0
0x25255  ldarg.0
0x25256  ldarg.1
0x25257  ldstr    aName// "name"
0x2525c  call     instance string Microsoft.Crm.Workflow.ObjectModel.FormXmlParser::TryGetAttributeValue(class [System.Xml]System.Xml.XmlNode xmlNode, string attributeName)
0x25261  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.PageStep::set_PageUniqueName(string)
0x25266  ldloc.0
0x25267  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabelCollection [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_StepLabels()
0x2526c  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabelCollection::Clear()
0x25271  ldarg.0
0x25272  ldarg.1
0x25273  ldloc.0
0x25274  call     instance void Microsoft.Crm.Workflow.ObjectModel.FormXmlParser::ParsePageStepLabels(class [System.Xml]System.Xml.XmlNode pageXmlNode, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.PageStep currentPageStep)
0x25279  ldarg.0
0x2527a  ldarg.1
0x2527b  ldloc.0
0x2527c  call     instance void Microsoft.Crm.Workflow.ObjectModel.FormXmlParser::ParsePageStepSteps(class [System.Xml]System.Xml.XmlNode pageXmlNode, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.PageStep currentPageStep)
0x25281  ret
```
