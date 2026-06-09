# Microsoft.Crm.Application.Ribbon.RibbonXml::GetCommandBarPieces

- ea: `0x52e80`
- end: `0x5316e`
- name: `Microsoft.Crm.Application.Ribbon.RibbonXml::GetCommandBarPieces`
- size: `750`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x53360`
- `0x533e0`

## callees

- `0x51620`
- `0x516d0`
- `0x52cc0`
- `0x52e80`
- `0x53170`
- `0x53270`
- `0x532c0`
- `0x537e0`
- `0x53950`
- `0x53d20`
- `0x53dc0`
- `0x544b0`
- `0x54b90`

## string_xrefs

- `0x5300d`: `Command`
- `0x53043`: `Command`
- `0x52e89`: `<CommandBar><Tabs></Tabs><ContextualTabs></ContextualTabs></CommandBar>`
- `0x52fcd`: `Mscrm.CommandBar`
- `0x52fd2`: `/CommandBar/Tabs`
- `0x530ce`: `/CommandBar/Tabs`
- `0x53079`: `Mscrm.ContextualCommandBar`
- `0x5307e`: `/CommandBar/ContextualTabs`
- `0x53125`: `/CommandBar/ContextualTabs`

## pseudocode

```c

```

## disassembly

```asm
0x52e80  ldarg.0
0x52e81  ldarg.3
0x52e82  ldarg.s  7
0x52e84  newobj   instance void Microsoft.Crm.Application.Ribbon.RibbonDescription::.ctor(class Microsoft.Crm.Application.Ribbon.RibbonPageContext pageContext, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context, class Microsoft.Crm.Application.Ribbon.IMenuBuilderFactory menuBuilderFactory)
0x52e89  ldstr    aCommandbarTabs// "<CommandBar><Tabs></Tabs><ContextualTab"...
0x52e8e  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x52e93  stloc.0
0x52e94  ldsfld   string [mscorlib]System.String::Empty
0x52e99  stloc.1
0x52e9a  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Ribbon.RibbonTabInformation> Microsoft.Crm.Application.Ribbon.RibbonDescription::get_TabList()
0x52e9f  ldsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Ribbon.RibbonTabInformation>, int32> <>c::<>9__11_0
0x52ea4  dup
0x52ea5  brtrue.s loc_52EBE
0x52ea7  pop
0x52ea8  ldsfld   class <>c <>c::<>9
0x52ead  ldftn    instance int32 <>c::<GetCommandBarPieces>b__11_0(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Ribbon.RibbonTabInformation> tab)
0x52eb3  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Ribbon.RibbonTabInformation>, int32>::.ctor(object, native int)
0x52eb8  dup
0x52eb9  stsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Ribbon.RibbonTabInformation>, int32> <>c::<>9__11_0
0x52ebe  call     T0x2B000081
0x52ec3  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Ribbon.RibbonTabInformation>>::GetEnumerator()
0x52ec8  stloc.2
0x52ec9  br       loc_53155
0x52ece  ldloc.2
0x52ecf  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Ribbon.RibbonTabInformation>>::get_Current()
0x52ed4  stloc.3
0x52ed5  ldarg.2
0x52ed6  brfalse.s loc_52EEE
0x52ed8  ldloca.s 3
0x52eda  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Ribbon.RibbonTabInformation>::get_Key()
0x52edf  ldstr    aMscrmBasichome// "Mscrm.BasicHomeTab"
0x52ee4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x52ee9  brtrue   loc_53155
0x52eee  ldloca.s 3
0x52ef0  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Ribbon.RibbonTabInformation>::get_Value()
0x52ef5  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Ribbon.RibbonTabInformation::get_IsEntityTab()
0x52efa  brtrue.s loc_52F03
0x52efc  ldstr    aNull// "null"
0x52f01  br.s     loc_52F18
0x52f03  ldloca.s 3
0x52f05  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Ribbon.RibbonTabInformation>::get_Value()
0x52f0a  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Ribbon.RibbonTabInformation::get_EntityLogicalName()
0x52f0f  dup
0x52f10  brtrue.s loc_52F18
0x52f12  pop
0x52f13  ldstr    aNull// "null"
0x52f18  stloc.1
0x52f19  ldloca.s 3
0x52f1b  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Ribbon.RibbonTabInformation>::get_Key()
0x52f20  ldloca.s 3
0x52f22  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Ribbon.RibbonTabInformation>::get_Value()
0x52f27  stloc.s  4
0x52f29  dup
0x52f2a  ldarg.1
0x52f2b  ldloc.s  4
0x52f2d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Ribbon.RibbonTabInformation::get_HierarchyLevel()
0x52f32  ldarg.2
0x52f33  ldarg.3
0x52f34  ldarg.s  7
0x52f36  ldarg.s  8
0x52f38  ldarg.s  9
0x52f3a  ldarg.0
0x52f3b  ldarg.s  0xA
0x52f3d  call     valuetype [Microsoft.Crm]Microsoft.Crm.RibbonLayout Microsoft.Crm.Application.Ribbon.RibbonXml::GetLayoutXmlForTabInternal(string tabId, int32 languageCode, valuetype [mscorlib]System.Guid hierarchyLocation, bool isForModern, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context, class Microsoft.Crm.Application.Ribbon.IMenuBuilderFactory menuBuilderFactory, class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Descriptors.LabelValue> requiredLocLabels, class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, string> columnNameToObjectId, class Microsoft.Crm.Application.Ribbon.RibbonPageContext pageContext, [opt] bool isReplaceLocalString)
0x52f42  stloc.s  5
0x52f44  ldloc.s  4
0x52f46  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Ribbon.RibbonTabInformation::get_HierarchyLevel()
0x52f4b  ldarg.3
0x52f4c  ldarg.0
0x52f4d  ldarg.s  7
0x52f4f  call     class Microsoft.Crm.Application.Ribbon.RibbonClientHandlers Microsoft.Crm.Application.Ribbon.RibbonXml::GetClientCommandsAndHandlers(string tabId, valuetype [mscorlib]System.Guid hierarchyLocation, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context, class Microsoft.Crm.Application.Ribbon.RibbonPageContext pageContext, class Microsoft.Crm.Application.Ribbon.IMenuBuilderFactory menuBuilderFactory)
0x52f54  stloc.s  6
0x52f56  ldloc.s  6
0x52f58  ldarg.s  0xB
0x52f5a  ldarg.s  0xC
0x52f5c  call     void Microsoft.Crm.Application.Ribbon.RibbonXml::ExtractUniqueDependenciesFromHandlers(class Microsoft.Crm.Application.Ribbon.RibbonClientHandlers rch, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<string>> jsDependencies, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype [mscorlib]System.Guid>>> resxDependencies)
0x52f61  ldloc.s  5
0x52f63  ldfld    string [Microsoft.Crm]Microsoft.Crm.RibbonLayout::LayoutXml
0x52f68  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x52f6d  stloc.s  7
0x52f6f  ldloc.s  4
0x52f71  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Ribbon.RibbonTabInformation::get_TabOriginalId()
0x52f76  ldstr    aMscrm// "Mscrm"
0x52f7b  ldc.i4.4
0x52f7c  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x52f81  brfalse  loc_530BB
0x52f86  ldloc.s  7
0x52f88  ldstr    aUiRibbonTabsTa// "/UI/Ribbon/Tabs/Tab"
0x52f8d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x52f92  stloc.s  8
0x52f94  ldloc.s  8
0x52f96  brfalse.s loc_52FF6
0x52f98  ldarg.2
0x52f99  ldarg.3
0x52f9a  ldarg.s  4
0x52f9c  ldarg.s  5
0x52f9e  ldarg.s  6
0x52fa0  ldloc.1
0x52fa1  ldloc.s  6
0x52fa3  ldloc.s  8
0x52fa5  call     class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition Microsoft.Crm.Application.Ribbon.RibbonXml::IncludeTabRules(bool isForModern, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition>> commands, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RuleDefinition>> rules, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RuleDefinition>> displayRules, string entityLogicalName, class Microsoft.Crm.Application.Ribbon.RibbonClientHandlers rch, class [System.Xml]System.Xml.XmlNode tabDefinition)
0x52faa  stloc.s  0xA
0x52fac  ldarg.2
0x52fad  brfalse.s loc_52FBB
0x52faf  ldloc.s  0xA
0x52fb1  call     bool Microsoft.Crm.Application.Ribbon.RibbonXml::IsOnFilteredListForModern(class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition command)
0x52fb6  brtrue   loc_53155
0x52fbb  ldloc.s  8
0x52fbd  ldstr    aGroups// "Groups"
0x52fc2  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x52fc7  stloc.s  0xB
0x52fc9  ldloc.s  0xB
0x52fcb  brfalse.s loc_52FF6
0x52fcd  ldstr    aMscrmCommandba// "Mscrm.CommandBar"
0x52fd2  ldstr    aCommandbarTabs_0// "/CommandBar/Tabs"
0x52fd7  ldloc.0
0x52fd8  call     class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Application.Ribbon.RibbonXml::BuildCommandBarTab(string tabId, string parentNode, class [System.Xml]System.Xml.XmlDocument commandBar)
0x52fdd  stloc.s  0xC
0x52fdf  ldloc.1
0x52fe0  ldloc.0
0x52fe1  ldloc.s  0xC
0x52fe3  ldarg.2
0x52fe4  ldarg.s  4
0x52fe6  ldarg.s  5
0x52fe8  ldarg.s  6
0x52fea  ldloc.s  6
0x52fec  ldloc.s  0xB
0x52fee  ldloc.s  0xA
0x52ff0  ldarg.3
0x52ff1  call     void Microsoft.Crm.Application.Ribbon.RibbonXml::ExtractCommandBarControls(string entityLogicalName, class [System.Xml]System.Xml.XmlDocument commandBar, class [System.Xml]System.Xml.XmlNode ribbonControls, bool isForModern, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition>> commands, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RuleDefinition>> rules, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RuleDefinition>> displayRules, class Microsoft.Crm.Application.Ribbon.RibbonClientHandlers rch, class [System.Xml]System.Xml.XmlNode groups, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition tabCommand, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x52ff6  ldloc.s  7
0x52ff8  ldstr    aUiRibbonContex// "UI/Ribbon/ContextualTabs/ContextualGrou"...
0x52ffd  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x53002  stloc.s  9
0x53004  ldloc.s  9
0x53006  brfalse  loc_53155
0x5300b  ldloc.s  9
0x5300d  ldstr    aCommand// "Command"
0x53012  call     string Microsoft.Crm.Application.Ribbon.RibbonXml::GetCommandId(class [System.Xml]System.Xml.XmlNode node, string commandAttribute)
0x53017  stloc.s  0xD
0x53019  ldarg.2
0x5301a  ldarg.3
0x5301b  ldarg.s  4
0x5301d  ldarg.s  5
0x5301f  ldarg.s  6
0x53021  ldloc.1
0x53022  ldloc.s  6
0x53024  ldloc.s  8
0x53026  call     class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition Microsoft.Crm.Application.Ribbon.RibbonXml::IncludeTabRules(bool isForModern, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition>> commands, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RuleDefinition>> rules, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RuleDefinition>> displayRules, string entityLogicalName, class Microsoft.Crm.Application.Ribbon.RibbonClientHandlers rch, class [System.Xml]System.Xml.XmlNode tabDefinition)
0x5302b  stloc.s  0xE
0x5302d  ldloc.s  9
0x5302f  ldstr    aTabGroups// "Tab/Groups"
0x53034  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x53039  stloc.s  0xF
0x5303b  ldloc.s  0xF
0x5303d  brfalse  loc_53155
0x53042  ldloc.0
0x53043  ldstr    aCommand// "Command"
0x53048  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x5304d  stloc.s  0x10
0x5304f  ldloc.s  0x10
0x53051  ldloc.s  0xD
0x53053  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x53058  ldloc.s  0xD
0x5305a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5305f  brtrue.s loc_53079
0x53061  ldloc.s  0xD
0x53063  ldloc.1
0x53064  ldarg.2
0x53065  ldarg.s  4
0x53067  ldarg.s  5
0x53069  ldarg.s  6
0x5306b  ldloc.s  6
0x5306d  ldnull
0x5306e  ldarg.3
0x5306f  call     bool Microsoft.Crm.Application.Ribbon.RibbonXml::IncludeCommandsForId(string commandId, string entityLogicalName, bool isForModern, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition>> commands, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RuleDefinition>> rules, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RuleDefinition>> displayRules, class Microsoft.Crm.Application.Ribbon.RibbonClientHandlers rch, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition tabCommand, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x53074  brfalse  loc_53155
0x53079  ldstr    aMscrmContextua// "Mscrm.ContextualCommandBar"
0x5307e  ldstr    aCommandbarCont// "/CommandBar/ContextualTabs"
0x53083  ldloc.0
0x53084  call     class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Application.Ribbon.RibbonXml::BuildCommandBarTab(string tabId, string parentNode, class [System.Xml]System.Xml.XmlDocument commandBar)
0x53089  stloc.s  0x11
0x5308b  ldloc.s  0x11
0x5308d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x53092  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x53097  ldloc.s  0x10
0x53099  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x5309e  pop
0x5309f  ldloc.1
0x530a0  ldloc.0
0x530a1  ldloc.s  0x11
0x530a3  ldarg.2
0x530a4  ldarg.s  4
0x530a6  ldarg.s  5
0x530a8  ldarg.s  6
0x530aa  ldloc.s  6
0x530ac  ldloc.s  0xF
0x530ae  ldloc.s  0xE
0x530b0  ldarg.3
0x530b1  call     void Microsoft.Crm.Application.Ribbon.RibbonXml::ExtractCommandBarControls(string entityLogicalName, class [System.Xml]System.Xml.XmlDocument commandBar, class [System.Xml]System.Xml.XmlNode ribbonControls, bool isForModern, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition>> commands, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RuleDefinition>> rules, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RuleDefinition>> displayRules, class Microsoft.Crm.Application.Ribbon.RibbonClientHandlers rch, class [System.Xml]System.Xml.XmlNode groups, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition tabCommand, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x530b6  br       loc_53155
0x530bb  ldloc.s  7
0x530bd  ldstr    aUiRibbonTabsTa// "/UI/Ribbon/Tabs/Tab"
0x530c2  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x530c7  stloc.s  0x12
0x530c9  ldloc.s  0x12
0x530cb  brfalse.s loc_53112
0x530cd  ldloc.0
0x530ce  ldstr    aCommandbarTabs_0// "/CommandBar/Tabs"
0x530d3  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x530d8  ldloc.0
0x530d9  ldloc.s  0x12
0x530db  ldc.i4.1
0x530dc  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlDocument::ImportNode(class [System.Xml]System.Xml.XmlNode, bool)
0x530e1  stloc.s  0x13
0x530e3  ldloc.s  0x13
0x530e5  ldloc.s  0x13
0x530e7  ldstr    aScaling// "Scaling"
0x530ec  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x530f1  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::RemoveChild(class [System.Xml]System.Xml.XmlNode)
0x530f6  pop
0x530f7  ldloc.s  0x13
0x530f9  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x530fe  pop
0x530ff  ldloc.1
0x53100  ldloc.s  7
0x53102  ldarg.2
0x53103  ldarg.s  4
0x53105  ldarg.s  5
0x53107  ldarg.s  6
0x53109  ldloc.s  6
0x5310b  ldnull
0x5310c  ldarg.3
0x5310d  call     void Microsoft.Crm.Application.Ribbon.RibbonXml::IncludeCommandsForNode(string entityLogicalName, class [System.Xml]System.Xml.XmlNode node, bool isForModern, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition>> commands, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RuleDefinition>> rules, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RuleDefinition>> displayRules, class Microsoft.Crm.Application.Ribbon.RibbonClientHandlers rch, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition tabCommand, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x53112  ldloc.s  7
0x53114  ldstr    aUiRibbonContex_0// "UI/Ribbon/ContextualTabs/ContextualGrou"...
0x53119  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x5311e  stloc.s  0x12
0x53120  ldloc.s  0x12
0x53122  brfalse.s loc_53155
0x53124  ldloc.0
0x53125  ldstr    aCommandbarCont// "/CommandBar/ContextualTabs"
0x5312a  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x5312f  ldloc.0
0x53130  ldloc.s  0x12
0x53132  ldc.i4.1
0x53133  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlDocument::ImportNode(class [System.Xml]System.Xml.XmlNode, bool)
0x53138  stloc.s  0x14
0x5313a  ldloc.s  0x14
0x5313c  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x53141  pop
0x53142  ldloc.1
0x53143  ldloc.s  7
0x53145  ldarg.2
0x53146  ldarg.s  4
0x53148  ldarg.s  5
0x5314a  ldarg.s  6
0x5314c  ldloc.s  6
0x5314e  ldnull
0x5314f  ldarg.3
0x53150  call     void Microsoft.Crm.Application.Ribbon.RibbonXml::IncludeCommandsForNode(string entityLogicalName, class [System.Xml]System.Xml.XmlNode node, bool isForModern, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition>> commands, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RuleDefinition>> rules, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RuleDefinition>> displayRules, class Microsoft.Crm.Application.Ribbon.RibbonClientHandlers rch, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition tabCommand, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x53155  ldloc.2
0x53156  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5315b  brtrue   loc_52ECE
0x53160  leave.s  loc_5316C
0x53162  ldloc.2
0x53163  brfalse.s loc_5316B
0x53165  ldloc.2
0x53166  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5316b  endfinally
0x5316c  ldloc.0
0x5316d  ret
```
