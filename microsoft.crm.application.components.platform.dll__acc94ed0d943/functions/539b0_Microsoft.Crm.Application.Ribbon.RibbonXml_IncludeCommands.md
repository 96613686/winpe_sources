# Microsoft.Crm.Application.Ribbon.RibbonXml::IncludeCommands

- ea: `0x539b0`
- end: `0x53d1c`
- name: `Microsoft.Crm.Application.Ribbon.RibbonXml::IncludeCommands`
- size: `876`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x537e0`
- `0x53d20`

## callees

- `0x4cbc0`
- `0x50c40`
- `0x512c0`
- `0x53950`
- `0x539b0`
- `0x53dc0`
- `0x99ad0`
- `0x9a670`
- `0x9a690`
- `0x9a6b0`
- `0x9b330`

## string_xrefs

- `0x539b3`: `Command`
- `0x53a83`: `Command`
- `0x53ab9`: `Command`
- `0x53b35`: `Command`
- `0x53b99`: `Command`
- `0x53bcd`: `Command`
- `0x53c01`: `Command`
- `0x53c35`: `Command`
- `0x53c81`: `Command`
- `0x53a4c`: `TemplateAlias`
- `0x53a6e`: `PopulateQueryCommand`
- `0x53a93`: `PopulateQueryCommand`
- `0x53acf`: `Mscrm.WordTemplate.CreateWordTemplate.Form`
- `0x53ae7`: `Mscrm.WordTemplate.CreateWordTemplate.Grid`
- `0x53aff`: `Mscrm.WordTemplate.TemplatesMenu.Form`
- `0x53b17`: `Mscrm.WordTemplate.TemplatesMenu.Grid`
- `0x53b4b`: `Mscrm.DocumentTemplate.TemplatesMenu`
- `0x53b63`: `Mscrm.DocumentTemplate.CreateDocumentTemplate`
- `0x53b7b`: `Mscrm.DocumentTemplate.OpenDocumentTemplateInExcelOnline`
- `0x53c17`: `Mscrm.SharePointOpenSource`
- `0x53ce6`: `QueryCommand`
- `0x53cf3`: `QueryCommand`

## pseudocode

```c

```

## disassembly

```asm
0x539b0  ldc.i4.0
0x539b1  stloc.0
0x539b2  ldarg.1
0x539b3  ldstr    aCommand// "Command"
0x539b8  call     string Microsoft.Crm.Application.Ribbon.RibbonXml::GetCommandId(class [System.Xml]System.Xml.XmlNode node, string commandAttribute)
0x539bd  stloc.1
0x539be  ldarg.2
0x539bf  brfalse.s loc_53A05
0x539c1  ldarg.s  6
0x539c3  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition> Microsoft.Crm.Application.Ribbon.RibbonClientHandlers::get_CommandDefinitions()
0x539c8  ldloc.1
0x539c9  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition>::ContainsKey(var<u1>)
0x539ce  brfalse.s loc_53A05
0x539d0  ldarg.s  6
0x539d2  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition> Microsoft.Crm.Application.Ribbon.RibbonClientHandlers::get_CommandDefinitions()
0x539d7  ldloc.1
0x539d8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition>::get_Item(void)
0x539dd  stloc.2
0x539de  ldloc.2
0x539df  brfalse.s loc_53A05
0x539e1  ldloc.2
0x539e2  ldfld    string[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition::DisplayRules
0x539e7  brfalse.s loc_53A05
0x539e9  ldloc.2
0x539ea  ldfld    string[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition::DisplayRules
0x539ef  ldstr    aMscrmHideonmod// "Mscrm.HideOnModern"
0x539f4  call     T0x2B000048
0x539f9  brfalse.s loc_53A05
0x539fb  ldarg.s  9
0x539fd  ldarg.1
0x539fe  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [System.Xml]System.Xml.XmlNode>::Add(var<u1>)
0x53a03  ldc.i4.0
0x53a04  ret
0x53a05  ldloc.1
0x53a06  ldarg.0
0x53a07  ldarg.2
0x53a08  ldarg.3
0x53a09  ldarg.s  4
0x53a0b  ldarg.s  5
0x53a0d  ldarg.s  6
0x53a0f  ldarg.s  7
0x53a11  ldarg.s  8
0x53a13  call     bool Microsoft.Crm.Application.Ribbon.RibbonXml::IncludeCommandsForId(string commandId, string entityLogicalName, bool isForModern, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition>> commands, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RuleDefinition>> rules, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RuleDefinition>> displayRules, class Microsoft.Crm.Application.Ribbon.RibbonClientHandlers rch, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition tabCommand, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x53a18  stloc.0
0x53a19  ldarg.2
0x53a1a  brfalse.s loc_53A57
0x53a1c  ldarg.1
0x53a1d  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x53a22  brfalse.s loc_53A57
0x53a24  ldarg.1
0x53a25  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x53a2a  ldstr    aImage16by16// "Image16by16"
0x53a2f  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::RemoveNamedItem(string)
0x53a34  pop
0x53a35  ldarg.1
0x53a36  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x53a3b  ldstr    aImage32by32// "Image32by32"
0x53a40  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::RemoveNamedItem(string)
0x53a45  pop
0x53a46  ldarg.1
0x53a47  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x53a4c  ldstr    aTemplatealias// "TemplateAlias"
0x53a51  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::RemoveNamedItem(string)
0x53a56  pop
0x53a57  ldarg.1
0x53a58  brfalse  loc_53CD5
0x53a5d  ldarg.1
0x53a5e  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x53a63  brfalse  loc_53CD5
0x53a68  ldarg.1
0x53a69  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x53a6e  ldstr    aPopulatequeryc// "PopulateQueryCommand"
0x53a73  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x53a78  brfalse  loc_53CD5
0x53a7d  ldarg.1
0x53a7e  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x53a83  ldstr    aCommand// "Command"
0x53a88  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x53a8d  brfalse  loc_53CD5
0x53a92  ldarg.1
0x53a93  ldstr    aPopulatequeryc// "PopulateQueryCommand"
0x53a98  call     string Microsoft.Crm.Application.Ribbon.RibbonXml::GetCommandId(class [System.Xml]System.Xml.XmlNode node, string commandAttribute)
0x53a9d  stloc.3
0x53a9e  ldloc.0
0x53a9f  ldloc.3
0x53aa0  ldarg.0
0x53aa1  ldarg.2
0x53aa2  ldarg.3
0x53aa3  ldarg.s  4
0x53aa5  ldarg.s  5
0x53aa7  ldarg.s  6
0x53aa9  ldnull
0x53aaa  ldarg.s  8
0x53aac  call     bool Microsoft.Crm.Application.Ribbon.RibbonXml::IncludeCommandsForId(string commandId, string entityLogicalName, bool isForModern, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition>> commands, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RuleDefinition>> rules, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RuleDefinition>> displayRules, class Microsoft.Crm.Application.Ribbon.RibbonClientHandlers rch, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition tabCommand, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x53ab1  or
0x53ab2  stloc.0
0x53ab3  ldarg.1
0x53ab4  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x53ab9  ldstr    aCommand// "Command"
0x53abe  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x53ac3  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x53ac8  call     bool Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.WordTemplatesMenuBuilder::IsWordTemplateMenuCommand(string command)
0x53acd  brfalse.s loc_53B2F
0x53acf  ldstr    aMscrmWordtempl// "Mscrm.WordTemplate.CreateWordTemplate.F"...
0x53ad4  ldarg.0
0x53ad5  ldarg.2
0x53ad6  ldarg.3
0x53ad7  ldarg.s  4
0x53ad9  ldarg.s  5
0x53adb  ldarg.s  6
0x53add  ldarg.s  7
0x53adf  ldarg.s  8
0x53ae1  call     bool Microsoft.Crm.Application.Ribbon.RibbonXml::IncludeCommandsForId(string commandId, string entityLogicalName, bool isForModern, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition>> commands, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RuleDefinition>> rules, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RuleDefinition>> displayRules, class Microsoft.Crm.Application.Ribbon.RibbonClientHandlers rch, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition tabCommand, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x53ae6  pop
0x53ae7  ldstr    aMscrmWordtempl_0// "Mscrm.WordTemplate.CreateWordTemplate.G"...
0x53aec  ldarg.0
0x53aed  ldarg.2
0x53aee  ldarg.3
0x53aef  ldarg.s  4
0x53af1  ldarg.s  5
0x53af3  ldarg.s  6
0x53af5  ldarg.s  7
0x53af7  ldarg.s  8
0x53af9  call     bool Microsoft.Crm.Application.Ribbon.RibbonXml::IncludeCommandsForId(string commandId, string entityLogicalName, bool isForModern, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition>> commands, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RuleDefinition>> rules, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RuleDefinition>> displayRules, class Microsoft.Crm.Application.Ribbon.RibbonClientHandlers rch, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition tabCommand, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x53afe  pop
0x53aff  ldstr    aMscrmWordtempl_1// "Mscrm.WordTemplate.TemplatesMenu.Form"
0x53b04  ldarg.0
0x53b05  ldarg.2
0x53b06  ldarg.3
0x53b07  ldarg.s  4
0x53b09  ldarg.s  5
0x53b0b  ldarg.s  6
0x53b0d  ldarg.s  7
0x53b0f  ldarg.s  8
0x53b11  call     bool Microsoft.Crm.Application.Ribbon.RibbonXml::IncludeCommandsForId(string commandId, string entityLogicalName, bool isForModern, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition>> commands, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RuleDefinition>> rules, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RuleDefinition>> displayRules, class Microsoft.Crm.Application.Ribbon.RibbonClientHandlers rch, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition tabCommand, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x53b16  pop
0x53b17  ldstr    aMscrmWordtempl_2// "Mscrm.WordTemplate.TemplatesMenu.Grid"
0x53b1c  ldarg.0
0x53b1d  ldarg.2
0x53b1e  ldarg.3
0x53b1f  ldarg.s  4
0x53b21  ldarg.s  5
0x53b23  ldarg.s  6
0x53b25  ldarg.s  7
0x53b27  ldarg.s  8
0x53b29  call     bool Microsoft.Crm.Application.Ribbon.RibbonXml::IncludeCommandsForId(string commandId, string entityLogicalName, bool isForModern, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition>> commands, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RuleDefinition>> rules, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RuleDefinition>> displayRules, class Microsoft.Crm.Application.Ribbon.RibbonClientHandlers rch, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition tabCommand, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x53b2e  pop
0x53b2f  ldarg.1
0x53b30  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x53b35  ldstr    aCommand// "Command"
0x53b3a  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x53b3f  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x53b44  call     bool Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.DocumentTemplatesMenuBuilder::IsDocumentTemplateMenuCommand(string command)
0x53b49  brfalse.s loc_53B93
0x53b4b  ldstr    aMscrmDocumentt// "Mscrm.DocumentTemplate.TemplatesMenu"
0x53b50  ldarg.0
0x53b51  ldarg.2
0x53b52  ldarg.3
0x53b53  ldarg.s  4
0x53b55  ldarg.s  5
0x53b57  ldarg.s  6
0x53b59  ldarg.s  7
0x53b5b  ldarg.s  8
0x53b5d  call     bool Microsoft.Crm.Application.Ribbon.RibbonXml::IncludeCommandsForId(string commandId, string entityLogicalName, bool isForModern, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition>> commands, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RuleDefinition>> rules, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RuleDefinition>> displayRules, class Microsoft.Crm.Application.Ribbon.RibbonClientHandlers rch, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition tabCommand, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x53b62  pop
0x53b63  ldstr    aMscrmDocumentt_0// "Mscrm.DocumentTemplate.CreateDocumentTe"...
0x53b68  ldarg.0
0x53b69  ldarg.2
0x53b6a  ldarg.3
0x53b6b  ldarg.s  4
0x53b6d  ldarg.s  5
0x53b6f  ldarg.s  6
0x53b71  ldarg.s  7
0x53b73  ldarg.s  8
0x53b75  call     bool Microsoft.Crm.Application.Ribbon.RibbonXml::IncludeCommandsForId(string commandId, string entityLogicalName, bool isForModern, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition>> commands, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RuleDefinition>> rules, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RuleDefinition>> displayRules, class Microsoft.Crm.Application.Ribbon.RibbonClientHandlers rch, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition tabCommand, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x53b7a  pop
0x53b7b  ldstr    aMscrmDocumentt_1// "Mscrm.DocumentTemplate.OpenDocumentTemp"...
0x53b80  ldarg.0
0x53b81  ldarg.2
0x53b82  ldarg.3
0x53b83  ldarg.s  4
0x53b85  ldarg.s  5
0x53b87  ldarg.s  6
0x53b89  ldarg.s  7
0x53b8b  ldarg.s  8
0x53b8d  call     bool Microsoft.Crm.Application.Ribbon.RibbonXml::IncludeCommandsForId(string commandId, string entityLogicalName, bool isForModern, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition>> commands, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RuleDefinition>> rules, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RuleDefinition>> displayRules, class Microsoft.Crm.Application.Ribbon.RibbonClientHandlers rch, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition tabCommand, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x53b92  pop
0x53b93  ldarg.1
0x53b94  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x53b99  ldstr    aCommand// "Command"
0x53b9e  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x53ba3  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x53ba8  call     bool Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.MenuBuilderForSharePointDocument::IsChangeLocationCommand(string command)
0x53bad  brfalse.s loc_53BC7
0x53baf  ldstr    aMscrmSharepoin// "Mscrm.SharePointChangeLocation"
0x53bb4  ldarg.0
0x53bb5  ldarg.2
0x53bb6  ldarg.3
0x53bb7  ldarg.s  4
0x53bb9  ldarg.s  5
0x53bbb  ldarg.s  6
0x53bbd  ldarg.s  7
0x53bbf  ldarg.s  8
0x53bc1  call     bool Microsoft.Crm.Application.Ribbon.RibbonXml::IncludeCommandsForId(string commandId, string entityLogicalName, bool isForModern, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition>> commands, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RuleDefinition>> rules, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RuleDefinition>> displayRules, class Microsoft.Crm.Application.Ribbon.RibbonClientHandlers rch, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition tabCommand, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x53bc6  pop
0x53bc7  ldarg.1
0x53bc8  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x53bcd  ldstr    aCommand// "Command"
0x53bd2  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x53bd7  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x53bdc  call     bool Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.MenuBuilderForSharePointDocument::IsEditLocationCommand(string command)
0x53be1  brfalse.s loc_53BFB
0x53be3  ldstr    aMscrmSharepoin_0// "Mscrm.SharePointEditLocation"
0x53be8  ldarg.0
0x53be9  ldarg.2
0x53bea  ldarg.3
0x53beb  ldarg.s  4
0x53bed  ldarg.s  5
0x53bef  ldarg.s  6
0x53bf1  ldarg.s  7
0x53bf3  ldarg.s  8
0x53bf5  call     bool Microsoft.Crm.Application.Ribbon.RibbonXml::IncludeCommandsForId(string commandId, string entityLogicalName, bool isForModern, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition>> commands, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RuleDefinition>> rules, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RuleDefinition>> displayRules, class Microsoft.Crm.Application.Ribbon.RibbonClientHandlers rch, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition tabCommand, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x53bfa  pop
0x53bfb  ldarg.1
0x53bfc  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x53c01  ldstr    aCommand// "Command"
0x53c06  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x53c0b  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x53c10  call     bool Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.MenuBuilderForSharePointDocument::IsOpenSourceLocationCommand(string command)
0x53c15  brfalse.s loc_53C2F
0x53c17  ldstr    aMscrmSharepoin_1// "Mscrm.SharePointOpenSource"
0x53c1c  ldarg.0
0x53c1d  ldarg.2
0x53c1e  ldarg.3
0x53c1f  ldarg.s  4
0x53c21  ldarg.s  5
0x53c23  ldarg.s  6
0x53c25  ldarg.s  7
0x53c27  ldarg.s  8
0x53c29  call     bool Microsoft.Crm.Application.Ribbon.RibbonXml::IncludeCommandsForId(string commandId, string entityLogicalName, bool isForModern, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition>> commands, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RuleDefinition>> rules, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RuleDefinition>> displayRules, class Microsoft.Crm.Application.Ribbon.RibbonClientHandlers rch, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition tabCommand, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x53c2e  pop
0x53c2f  ldarg.1
0x53c30  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x53c35  ldstr    aCommand// "Command"
0x53c3a  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x53c3f  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x53c44  call     bool Microsoft.Crm.Application.Ribbon.MicrosoftFlowsMenuBuilder::IsFlowsMenuCommand(string command)
0x53c49  brfalse.s loc_53C7B
0x53c4b  ldstr    aMscrmFlowsTrig// "Mscrm.Flows.TriggerFlow"
0x53c50  ldarg.0
0x53c51  ldarg.2
0x53c52  ldarg.3
0x53c53  ldarg.s  4
0x53c55  ldarg.s  5
0x53c57  ldarg.s  6
0x53c59  ldarg.s  7
0x53c5b  ldarg.s  8
0x53c5d  call     bool Microsoft.Crm.Application.Ribbon.RibbonXml::IncludeCommandsForId(string commandId, string entityLogicalName, bool isForModern, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition>> commands, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RuleDefinition>> rules, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RuleDefinition>> displayRules, class Microsoft.Crm.Application.Ribbon.RibbonClientHandlers rch, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition tabCommand, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x53c62  pop
0x53c63  ldstr    aMscrmFlowsTrig_0// "Mscrm.Flows.TriggerWorkflow"
0x53c68  ldarg.0
0x53c69  ldarg.2
0x53c6a  ldarg.3
0x53c6b  ldarg.s  4
0x53c6d  ldarg.s  5
0x53c6f  ldarg.s  6
0x53c71  ldarg.s  7
0x53c73  ldarg.s  8
0x53c75  call     bool Microsoft.Crm.Application.Ribbon.RibbonXml::IncludeCommandsForId(string commandId, string entityLogicalName, bool isForModern, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition>> commands, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RuleDefinition>> rules, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RuleDefinition>> displayRules, class Microsoft.Crm.Application.Ribbon.RibbonClientHandlers rch, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition tabCommand, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x53c7a  pop
0x53c7b  ldarg.1
0x53c7c  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x53c81  ldstr    aCommand// "Command"
0x53c86  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x53c8b  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x53c90  ldloca.s 4
0x53c92  call     bool Microsoft.Crm.Application.Ribbon.ReportsMenuBuilder::IsReportMenuCommand(string command, [out] int32& visibility)
0x53c97  brfalse.s loc_53CD5
0x53c99  ldloc.s  4
0x53c9b  ldc.i4.2
0x53c9c  bne.un.s loc_53CB8
0x53c9e  ldstr    aMscrmReportsme_0// "Mscrm.ReportsMenu.RunReport.Form"
0x53ca3  ldarg.0
0x53ca4  ldarg.2
0x53ca5  ldarg.3
0x53ca6  ldarg.s  4
0x53ca8  ldarg.s  5
0x53caa  ldarg.s  6
0x53cac  ldarg.s  7
0x53cae  ldarg.s  8
0x53cb0  call     bool Microsoft.Crm.Application.Ribbon.RibbonXml::IncludeCommandsForId(string commandId, string entityLogicalName, bool isForModern, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition>> commands, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RuleDefinition>> rules, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RuleDefinition>> displayRules, class Microsoft.Crm.Application.Ribbon.RibbonClientHandlers rch, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition tabCommand, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x53cb5  pop
0x53cb6  br.s     loc_53CD5
0x53cb8  ldloc.s  4
0x53cba  ldc.i4.3
0x53cbb  bne.un.s loc_53CD5
0x53cbd  ldstr    aMscrmReportsme_1// "Mscrm.ReportsMenu.RunReport.Grid"
0x53cc2  ldarg.0
0x53cc3  ldarg.2
0x53cc4  ldarg.3
  ... truncated ...
```
