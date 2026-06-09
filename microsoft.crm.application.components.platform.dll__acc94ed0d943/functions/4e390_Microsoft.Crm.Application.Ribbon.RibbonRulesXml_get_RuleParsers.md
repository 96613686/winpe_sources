# Microsoft.Crm.Application.Ribbon.RibbonRulesXml::get_RuleParsers

- ea: `0x4e390`
- end: `0x4e837`
- name: `Microsoft.Crm.Application.Ribbon.RibbonRulesXml::get_RuleParsers`
- size: `1191`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x4e930`

## callees

- `0x4e390`
- `0xa5700`

## string_xrefs

- `0x4e3d1`: `CommandClientTypeRule`
- `0x4e3ff`: `CrmOfflineAccessStateRule`
- `0x4e444`: `EntityPrivilegeRule`
- `0x4e4b7`: `MiscellaneousPrivilegeRule`
- `0x4e558`: `RecordPrivilegeRule`
- `0x4e655`: `HideIfServiceMetadataAvailableRule`
- `0x4e66c`: `HideIfSharepointS2SConfigurationEnabledRule`
- `0x4e7f3`: `HideIfProductRecommendationsNotEnabledRule`
- `0x4e80a`: `HideIfSolutionNotInstalledRule`

## pseudocode

```c

```

## disassembly

```asm
0x4e390  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ParseRuleDelegate> Microsoft.Crm.Application.Ribbon.RibbonRulesXml::_ruleParsers
0x4e395  brtrue   loc_4E831
0x4e39a  ldsfld   object Microsoft.Crm.Application.Ribbon.RibbonRulesXml::_ruleParsersLockObject
0x4e39f  stloc.0
0x4e3a0  ldc.i4.0
0x4e3a1  stloc.1
0x4e3a2  ldloc.0
0x4e3a3  ldloca.s 1
0x4e3a5  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x4e3aa  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ParseRuleDelegate> Microsoft.Crm.Application.Ribbon.RibbonRulesXml::_ruleParsers
0x4e3af  brtrue   loc_4E825
0x4e3b4  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ParseRuleDelegate>::.ctor()
0x4e3b9  dup
0x4e3ba  ldstr    aCrmclienttyper// "CrmClientTypeRule"
0x4e3bf  ldnull
0x4e3c0  ldftn    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RulePart Microsoft.Crm.Application.Ribbon.RibbonRulesXml::ParseCrmClientTypeRulePart(class [System.Xml]System.Xml.XPath.XPathNavigator rulePartXml, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4e3c6  newobj   instance void ParseRuleDelegate::.ctor(object object, native int method)
0x4e3cb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ParseRuleDelegate>::set_Item(var<u1>, !!T0)
0x4e3d0  dup
0x4e3d1  ldstr    aCommandclientt// "CommandClientTypeRule"
0x4e3d6  ldnull
0x4e3d7  ldftn    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RulePart Microsoft.Crm.Application.Ribbon.RibbonRulesXml::ParseCommandClientTypeRulePart(class [System.Xml]System.Xml.XPath.XPathNavigator rulePartXml, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4e3dd  newobj   instance void ParseRuleDelegate::.ctor(object object, native int method)
0x4e3e2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ParseRuleDelegate>::set_Item(var<u1>, !!T0)
0x4e3e7  dup
0x4e3e8  ldstr    aDevicetyperule// "DeviceTypeRule"
0x4e3ed  ldnull
0x4e3ee  ldftn    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RulePart Microsoft.Crm.Application.Ribbon.RibbonRulesXml::ParseDeviceTypeRulePart(class [System.Xml]System.Xml.XPath.XPathNavigator rulePartXml, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4e3f4  newobj   instance void ParseRuleDelegate::.ctor(object object, native int method)
0x4e3f9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ParseRuleDelegate>::set_Item(var<u1>, !!T0)
0x4e3fe  dup
0x4e3ff  ldstr    aCrmofflineacce// "CrmOfflineAccessStateRule"
0x4e404  ldnull
0x4e405  ldftn    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RulePart Microsoft.Crm.Application.Ribbon.RibbonRulesXml::ParseCrmOfflineAccessStateRulePart(class [System.Xml]System.Xml.XPath.XPathNavigator rulePartXml, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4e40b  newobj   instance void ParseRuleDelegate::.ctor(object object, native int method)
0x4e410  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ParseRuleDelegate>::set_Item(var<u1>, !!T0)
0x4e415  dup
0x4e416  ldstr    aCrmoutlookclie// "CrmOutlookClientTypeRule"
0x4e41b  ldnull
0x4e41c  ldftn    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RulePart Microsoft.Crm.Application.Ribbon.RibbonRulesXml::ParseCrmOutlookClientTypeRulePart(class [System.Xml]System.Xml.XPath.XPathNavigator rulePartXml, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4e422  newobj   instance void ParseRuleDelegate::.ctor(object object, native int method)
0x4e427  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ParseRuleDelegate>::set_Item(var<u1>, !!T0)
0x4e42c  dup
0x4e42d  ldstr    aCustomrule// "CustomRule"
0x4e432  ldnull
0x4e433  ldftn    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RulePart Microsoft.Crm.Application.Ribbon.RibbonRulesXml::ParseCustomRulePart(class [System.Xml]System.Xml.XPath.XPathNavigator rulePartXml, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4e439  newobj   instance void ParseRuleDelegate::.ctor(object object, native int method)
0x4e43e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ParseRuleDelegate>::set_Item(var<u1>, !!T0)
0x4e443  dup
0x4e444  ldstr    aEntityprivileg// "EntityPrivilegeRule"
0x4e449  ldnull
0x4e44a  ldftn    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RulePart Microsoft.Crm.Application.Ribbon.RibbonRulesXml::ParsePrivilegeRulePart(class [System.Xml]System.Xml.XPath.XPathNavigator rulePartXml, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4e450  newobj   instance void ParseRuleDelegate::.ctor(object object, native int method)
0x4e455  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ParseRuleDelegate>::set_Item(var<u1>, !!T0)
0x4e45a  dup
0x4e45b  ldstr    aEntityproperty// "EntityPropertyRule"
0x4e460  ldnull
0x4e461  ldftn    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RulePart Microsoft.Crm.Application.Ribbon.RibbonRulesXml::ParseEntityPropertyRulePart(class [System.Xml]System.Xml.XPath.XPathNavigator rulePartXml, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4e467  newobj   instance void ParseRuleDelegate::.ctor(object object, native int method)
0x4e46c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ParseRuleDelegate>::set_Item(var<u1>, !!T0)
0x4e471  dup
0x4e472  ldstr    aEntityrule// "EntityRule"
0x4e477  ldnull
0x4e478  ldftn    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RulePart Microsoft.Crm.Application.Ribbon.RibbonRulesXml::ParseEntityRulePart(class [System.Xml]System.Xml.XPath.XPathNavigator rulePartXml, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4e47e  newobj   instance void ParseRuleDelegate::.ctor(object object, native int method)
0x4e483  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ParseRuleDelegate>::set_Item(var<u1>, !!T0)
0x4e488  dup
0x4e489  ldstr    aFormentitycont// "FormEntityContextRule"
0x4e48e  ldnull
0x4e48f  ldftn    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RulePart Microsoft.Crm.Application.Ribbon.RibbonRulesXml::ParseFormEntityContextRulePart(class [System.Xml]System.Xml.XPath.XPathNavigator rulePartXml, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4e495  newobj   instance void ParseRuleDelegate::.ctor(object object, native int method)
0x4e49a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ParseRuleDelegate>::set_Item(var<u1>, !!T0)
0x4e49f  dup
0x4e4a0  ldstr    aFormstaterule// "FormStateRule"
0x4e4a5  ldnull
0x4e4a6  ldftn    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RulePart Microsoft.Crm.Application.Ribbon.RibbonRulesXml::ParseFormStateRulePart(class [System.Xml]System.Xml.XPath.XPathNavigator rulePartXml, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4e4ac  newobj   instance void ParseRuleDelegate::.ctor(object object, native int method)
0x4e4b1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ParseRuleDelegate>::set_Item(var<u1>, !!T0)
0x4e4b6  dup
0x4e4b7  ldstr    aMiscellaneousp// "MiscellaneousPrivilegeRule"
0x4e4bc  ldnull
0x4e4bd  ldftn    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RulePart Microsoft.Crm.Application.Ribbon.RibbonRulesXml::ParseMiscellaneousPrivilegeRulePart(class [System.Xml]System.Xml.XPath.XPathNavigator rulePartXml, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4e4c3  newobj   instance void ParseRuleDelegate::.ctor(object object, native int method)
0x4e4c8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ParseRuleDelegate>::set_Item(var<u1>, !!T0)
0x4e4cd  dup
0x4e4ce  ldstr    aOrganizationse// "OrganizationSettingRule"
0x4e4d3  ldnull
0x4e4d4  ldftn    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RulePart Microsoft.Crm.Application.Ribbon.RibbonRulesXml::ParseOrganizationSettingRulePart(class [System.Xml]System.Xml.XPath.XPathNavigator rulePartXml, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4e4da  newobj   instance void ParseRuleDelegate::.ctor(object object, native int method)
0x4e4df  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ParseRuleDelegate>::set_Item(var<u1>, !!T0)
0x4e4e4  dup
0x4e4e5  ldstr    aOrrule// "OrRule"
0x4e4ea  ldnull
0x4e4eb  ldftn    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RulePart Microsoft.Crm.Application.Ribbon.RibbonRulesXml::ParseOrRulePart(class [System.Xml]System.Xml.XPath.XPathNavigator rulePartXml, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4e4f1  newobj   instance void ParseRuleDelegate::.ctor(object object, native int method)
0x4e4f6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ParseRuleDelegate>::set_Item(var<u1>, !!T0)
0x4e4fb  dup
0x4e4fc  ldstr    aOutlookitemtra// "OutlookItemTrackingRule"
0x4e501  ldnull
0x4e502  ldftn    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RulePart Microsoft.Crm.Application.Ribbon.RibbonRulesXml::ParseOutlookItemTrackingRule(class [System.Xml]System.Xml.XPath.XPathNavigator rulePartXml, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4e508  newobj   instance void ParseRuleDelegate::.ctor(object object, native int method)
0x4e50d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ParseRuleDelegate>::set_Item(var<u1>, !!T0)
0x4e512  dup
0x4e513  ldstr    aOutlookrendert// "OutlookRenderTypeRule"
0x4e518  ldnull
0x4e519  ldftn    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RulePart Microsoft.Crm.Application.Ribbon.RibbonRulesXml::ParseOutlookRenderTypeRule(class [System.Xml]System.Xml.XPath.XPathNavigator rulePartXml, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4e51f  newobj   instance void ParseRuleDelegate::.ctor(object object, native int method)
0x4e524  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ParseRuleDelegate>::set_Item(var<u1>, !!T0)
0x4e529  dup
0x4e52a  ldstr    aOutlookversion_0// "OutlookVersionRule"
0x4e52f  ldnull
0x4e530  ldftn    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RulePart Microsoft.Crm.Application.Ribbon.RibbonRulesXml::ParseOutlookVersionRulePart(class [System.Xml]System.Xml.XPath.XPathNavigator rulePartXml, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4e536  newobj   instance void ParseRuleDelegate::.ctor(object object, native int method)
0x4e53b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ParseRuleDelegate>::set_Item(var<u1>, !!T0)
0x4e540  dup
0x4e541  ldstr    aPagerule// "PageRule"
0x4e546  ldnull
0x4e547  ldftn    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RulePart Microsoft.Crm.Application.Ribbon.RibbonRulesXml::ParsePageRulePart(class [System.Xml]System.Xml.XPath.XPathNavigator rulePartXml, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4e54d  newobj   instance void ParseRuleDelegate::.ctor(object object, native int method)
0x4e552  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ParseRuleDelegate>::set_Item(var<u1>, !!T0)
0x4e557  dup
0x4e558  ldstr    aRecordprivileg// "RecordPrivilegeRule"
0x4e55d  ldnull
0x4e55e  ldftn    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RulePart Microsoft.Crm.Application.Ribbon.RibbonRulesXml::ParsePrivilegeRulePart(class [System.Xml]System.Xml.XPath.XPathNavigator rulePartXml, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4e564  newobj   instance void ParseRuleDelegate::.ctor(object object, native int method)
0x4e569  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ParseRuleDelegate>::set_Item(var<u1>, !!T0)
0x4e56e  dup
0x4e56f  ldstr    aReferencingatt// "ReferencingAttributeRequiredRule"
0x4e574  ldnull
0x4e575  ldftn    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RulePart Microsoft.Crm.Application.Ribbon.RibbonRulesXml::ParseReferencingAttributeRequiredRulePart(class [System.Xml]System.Xml.XPath.XPathNavigator rulePartXml, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4e57b  newobj   instance void ParseRuleDelegate::.ctor(object object, native int method)
0x4e580  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ParseRuleDelegate>::set_Item(var<u1>, !!T0)
0x4e585  dup
0x4e586  ldstr    aRelationshipty// "RelationshipTypeRule"
0x4e58b  ldnull
0x4e58c  ldftn    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RulePart Microsoft.Crm.Application.Ribbon.RibbonRulesXml::ParseRelationshipTypeRulePart(class [System.Xml]System.Xml.XPath.XPathNavigator rulePartXml, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4e592  newobj   instance void ParseRuleDelegate::.ctor(object object, native int method)
0x4e597  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ParseRuleDelegate>::set_Item(var<u1>, !!T0)
0x4e59c  dup
0x4e59d  ldstr    aSelectioncount// "SelectionCountRule"
0x4e5a2  ldnull
0x4e5a3  ldftn    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RulePart Microsoft.Crm.Application.Ribbon.RibbonRulesXml::ParseSelectionCountRulePart(class [System.Xml]System.Xml.XPath.XPathNavigator rulePartXml, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4e5a9  newobj   instance void ParseRuleDelegate::.ctor(object object, native int method)
0x4e5ae  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ParseRuleDelegate>::set_Item(var<u1>, !!T0)
0x4e5b3  dup
0x4e5b4  ldstr    aSkurule// "SkuRule"
0x4e5b9  ldnull
0x4e5ba  ldftn    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RulePart Microsoft.Crm.Application.Ribbon.RibbonRulesXml::ParseSkuRulePart(class [System.Xml]System.Xml.XPath.XPathNavigator rulePartXml, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4e5c0  newobj   instance void ParseRuleDelegate::.ctor(object object, native int method)
0x4e5c5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ParseRuleDelegate>::set_Item(var<u1>, !!T0)
0x4e5ca  dup
0x4e5cb  ldstr    aValuerule// "ValueRule"
0x4e5d0  ldnull
0x4e5d1  ldftn    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RulePart Microsoft.Crm.Application.Ribbon.RibbonRulesXml::ParseValueRulePart(class [System.Xml]System.Xml.XPath.XPathNavigator rulePartXml, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4e5d7  newobj   instance void ParseRuleDelegate::.ctor(object object, native int method)
0x4e5dc  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ParseRuleDelegate>::set_Item(var<u1>, !!T0)
0x4e5e1  dup
0x4e5e2  ldstr    aCrmoutlookclie_0// "CrmOutlookClientVersionRule"
0x4e5e7  ldnull
0x4e5e8  ldftn    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RulePart Microsoft.Crm.Application.Ribbon.RibbonRulesXml::ParseCrmOutlookClientVersionRulePart(class [System.Xml]System.Xml.XPath.XPathNavigator rulePartXml, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4e5ee  newobj   instance void ParseRuleDelegate::.ctor(object object, native int method)
0x4e5f3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ParseRuleDelegate>::set_Item(var<u1>, !!T0)
0x4e5f8  dup
0x4e5f9  ldstr    aOptionsetrule// "OptionSetRule"
0x4e5fe  ldnull
0x4e5ff  ldftn    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RulePart Microsoft.Crm.Application.Ribbon.RibbonRulesXml::ParseOptionSetRulePart(class [System.Xml]System.Xml.XPath.XPathNavigator rulePartXml, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4e605  newobj   instance void ParseRuleDelegate::.ctor(object object, native int method)
0x4e60a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ParseRuleDelegate>::set_Item(var<u1>, !!T0)
0x4e60f  dup
0x4e610  ldstr    aFormtyperule// "FormTypeRule"
0x4e615  ldnull
0x4e616  ldftn    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RulePart Microsoft.Crm.Application.Ribbon.RibbonRulesXml::ParseFormTypeRulePart(class [System.Xml]System.Xml.XPath.XPathNavigator rulePartXml, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4e61c  newobj   instance void ParseRuleDelegate::.ctor(object object, native int method)
0x4e621  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ParseRuleDelegate>::set_Item(var<u1>, !!T0)
0x4e626  dup
0x4e627  ldstr    aHidefortablete// "HideForTabletExperienceRule"
0x4e62c  ldnull
0x4e62d  ldftn    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RulePart Microsoft.Crm.Application.Ribbon.RibbonRulesXml::HideForTabletExperienceRulePart(class [System.Xml]System.Xml.XPath.XPathNavigator rulePartXml, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4e633  newobj   instance void ParseRuleDelegate::.ctor(object object, native int method)
0x4e638  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ParseRuleDelegate>::set_Item(var<u1>, !!T0)
0x4e63d  dup
0x4e63e  ldstr    aHideifnetbreez// "HideIfNetBreezeNotAvailableRule"
0x4e643  ldnull
0x4e644  ldftn    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RulePart Microsoft.Crm.Application.Ribbon.RibbonRulesXml::HideIfNetBreezeNotAvailableRulePart(class [System.Xml]System.Xml.XPath.XPathNavigator rulePartXml, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4e64a  newobj   instance void ParseRuleDelegate::.ctor(object object, native int method)
0x4e64f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ParseRuleDelegate>::set_Item(var<u1>, !!T0)
0x4e654  dup
0x4e655  ldstr    aHideifservicem// "HideIfServiceMetadataAvailableRule"
0x4e65a  ldnull
0x4e65b  ldftn    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RulePart Microsoft.Crm.Application.Ribbon.RibbonRulesXml::HideIfServiceMetadataAvailableRulePart(class [System.Xml]System.Xml.XPath.XPathNavigator rulePartXml, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4e661  newobj   instance void ParseRuleDelegate::.ctor(object object, native int method)
0x4e666  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ParseRuleDelegate>::set_Item(var<u1>, !!T0)
0x4e66b  dup
0x4e66c  ldstr    aHideifsharepoi// "HideIfSharepointS2SConfigurationEnabled"...
0x4e671  ldnull
0x4e672  ldftn    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RulePart Microsoft.Crm.Application.Ribbon.RibbonRulesXml::HideIfSharepointS2SConfigurationEnabledRulePart(class [System.Xml]System.Xml.XPath.XPathNavigator rulePartXml, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4e678  newobj   instance void ParseRuleDelegate::.ctor(object object, native int method)
0x4e67d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ParseRuleDelegate>::set_Item(var<u1>, !!T0)
0x4e682  dup
0x4e683  ldstr    aHideifexportto// "HideIfExportToExcelNotEnabledRule"
0x4e688  ldnull
0x4e689  ldftn    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RulePart Microsoft.Crm.Application.Ribbon.RibbonRulesXml::HideIfExportToExcelNotEnabledRulePart(class [System.Xml]System.Xml.XPath.XPathNavigator rulePartXml, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4e68f  newobj   instance void ParseRuleDelegate::.ctor(object object, native int method)
0x4e694  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ParseRuleDelegate>::set_Item(var<u1>, !!T0)
0x4e699  dup
0x4e69a  ldstr    aIsexporttoexce// "IsExportToExcelOnlineEnabledRule"
0x4e69f  ldnull
0x4e6a0  ldftn    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RulePart Microsoft.Crm.Application.Ribbon.RibbonRulesXml::IsExportToExcelOnlineEnabledRulePart(class [System.Xml]System.Xml.XPath.XPathNavigator rulePartXml, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4e6a6  newobj   instance void ParseRuleDelegate::.ctor(object object, native int method)
0x4e6ab  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ParseRuleDelegate>::set_Item(var<u1>, !!T0)
0x4e6b0  dup
0x4e6b1  ldstr    aHideifdisabled// "HideIfDisabledForMobileRule"
0x4e6b6  ldnull
0x4e6b7  ldftn    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RulePart Microsoft.Crm.Application.Ribbon.RibbonRulesXml::HideIfDisabledForMobileRulePart(class [System.Xml]System.Xml.XPath.XPathNavigator rulePartXml, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4e6bd  newobj   instance void ParseRuleDelegate::.ctor(object object, native int method)
0x4e6c2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ParseRuleDelegate>::set_Item(var<u1>, !!T0)
0x4e6c7  dup
0x4e6c8  ldstr    aHideifhybridss// "HideIfHybridSSSNotEnabledRule"
0x4e6cd  ldnull
0x4e6ce  ldftn    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RulePart Microsoft.Crm.Application.Ribbon.RibbonRulesXml::HideIfHybridSSSNotEnabledRulePart(class [System.Xml]System.Xml.XPath.XPathNavigator rulePartXml, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4e6d4  newobj   instance void ParseRuleDelegate::.ctor(object object, native int method)
0x4e6d9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ParseRuleDelegate>::set_Item(var<u1>, !!T0)
0x4e6de  dup
0x4e6df  ldstr    aHideifreverseh// "HideIfReverseHybridSSSNotEnabledRule"
0x4e6e4  ldnull
0x4e6e5  ldftn    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RulePart Microsoft.Crm.Application.Ribbon.RibbonRulesXml::HideIfReverseHybridSSSNotEnabledRulePart(class [System.Xml]System.Xml.XPath.XPathNavigator rulePartXml, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4e6eb  newobj   instance void ParseRuleDelegate::.ctor(object object, native int method)
0x4e6f0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ParseRuleDelegate>::set_Item(var<u1>, !!T0)
0x4e6f5  dup
0x4e6f6  ldstr    aFeaturecontrol// "FeatureControlRule"
0x4e6fb  ldnull
0x4e6fc  ldftn    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RulePart Microsoft.Crm.Application.Ribbon.RibbonRulesXml::FeatureControlRulePart(class [System.Xml]System.Xml.XPath.XPathNavigator rulePartXml, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4e702  newobj   instance void ParseRuleDelegate::.ctor(object object, native int method)
0x4e707  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ParseRuleDelegate>::set_Item(var<u1>, !!T0)
0x4e70c  dup
0x4e70d  ldstr    aHideifdelvenot// "HideIfDelveNotAvailableRule"
0x4e712  ldnull
0x4e713  ldftn    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RulePart Microsoft.Crm.Application.Ribbon.RibbonRulesXml::HideIfDelveNotAvailableRulePart(class [System.Xml]System.Xml.XPath.XPathNavigator rulePartXml, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4e719  newobj   instance void ParseRuleDelegate::.ctor(object object, native int method)
0x4e71e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ParseRuleDelegate>::set_Item(var<u1>, !!T0)
0x4e723  dup
0x4e724  ldstr    aHideiftestexch// "HideIfTestExchangeServerNotEnabledRule"
0x4e729  ldnull
0x4e72a  ldftn    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RulePart Microsoft.Crm.Application.Ribbon.RibbonRulesXml::HideIfTestExchangeServerNotEnabledRulePart(class [System.Xml]System.Xml.XPath.XPathNavigator rulePartXml, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4e730  newobj   instance void ParseRuleDelegate::.ctor(object object, native int method)
0x4e735  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ParseRuleDelegate>::set_Item(var<u1>, !!T0)
0x4e73a  dup
0x4e73b  ldstr    aHideifssstroub// "HideIfSSSTroubleshootingNotEnabledRule"
0x4e740  ldnull
0x4e741  ldftn    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RulePart Microsoft.Crm.Application.Ribbon.RibbonRulesXml::HideIfSSSTroubleshootingNotEnabledRulePart(class [System.Xml]System.Xml.XPath.XPathNavigator rulePartXml, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4e747  newobj   instance void ParseRuleDelegate::.ctor(object object, native int method)
0x4e74c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ParseRuleDelegate>::set_Item(var<u1>, !!T0)
0x4e751  dup
0x4e752  ldstr    aHideifcurrentu// "HideIfCurrentUserIsNotSystemAdministrat"...
0x4e757  ldnull
0x4e758  ldftn    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RulePart Microsoft.Crm.Application.Ribbon.RibbonRulesXml::HideIfCurrentUserIsNotSystemAdministratorRulePart(class [System.Xml]System.Xml.XPath.XPathNavigator rulePartXml, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4e75e  newobj   instance void ParseRuleDelegate::.ctor(object object, native int method)
0x4e763  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ParseRuleDelegate>::set_Item(var<u1>, !!T0)
0x4e768  dup
0x4e769  ldstr    aHideifpowerbit// "HideIfPowerBITileNotAvailableRule"
0x4e76e  ldnull
0x4e76f  ldftn    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RulePart Microsoft.Crm.Application.Ribbon.RibbonRulesXml::HideIfPowerBITileNotAvailableRulePart(class [System.Xml]System.Xml.XPath.XPathNavigator rulePartXml, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4e775  newobj   instance void ParseRuleDelegate::.ctor(object object, native int method)
0x4e77a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ParseRuleDelegate>::set_Item(var<u1>, !!T0)
0x4e77f  dup
0x4e780  ldstr    aHideifemailsig// "HideIfEmailSignatureNotEnabledRule"
0x4e785  ldnull
0x4e786  ldftn    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RulePart Microsoft.Crm.Application.Ribbon.RibbonRulesXml::HideIfEmailSignatureNotEnabledRulePart(class [System.Xml]System.Xml.XPath.XPathNavigator rulePartXml, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4e78c  newobj   instance void ParseRuleDelegate::.ctor(object object, native int method)
0x4e791  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ParseRuleDelegate>::set_Item(var<u1>, !!T0)
0x4e796  dup
0x4e797  ldstr    aHideifo365user// "HideIfO365UserDoesNotHaveExchangeSubscr"...
0x4e79c  ldnull
0x4e79d  ldftn    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RulePart Microsoft.Crm.Application.Ribbon.RibbonRulesXml::HideIfO365UserDoesNotHaveExchangeSubscriptionsRulePart(class [System.Xml]System.Xml.XPath.XPathNavigator rulePartXml, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4e7a3  newobj   instance void ParseRuleDelegate::.ctor(object object, native int method)
0x4e7a8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ParseRuleDelegate>::set_Item(var<u1>, !!T0)
0x4e7ad  dup
0x4e7ae  ldstr    aHideifemailisa// "HideIfEmailIsApprovedByAdminRule"
0x4e7b3  ldnull
0x4e7b4  ldftn    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RulePart Microsoft.Crm.Application.Ribbon.RibbonRulesXml::HideIfEmailIsApprovedByAdminRulePart(class [System.Xml]System.Xml.XPath.XPathNavigator rulePartXml, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4e7ba  newobj   instance void ParseRuleDelegate::.ctor(object object, native int method)
0x4e7bf  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ParseRuleDelegate>::set_Item(var<u1>, !!T0)
0x4e7c4  dup
0x4e7c5  ldstr    aHideifuserisno// "HideIfUserIsNotTenantAdminRule"
0x4e7ca  ldnull
0x4e7cb  ldftn    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RulePart Microsoft.Crm.Application.Ribbon.RibbonRulesXml::HideIfUserIsNotTenantAdminRulePart(class [System.Xml]System.Xml.XPath.XPathNavigator rulePartXml, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4e7d1  newobj   instance void ParseRuleDelegate::.ctor(object object, native int method)
0x4e7d6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ParseRuleDelegate>::set_Item(var<u1>, !!T0)
0x4e7db  dup
0x4e7dc  ldstr    aHideifemailisa_0// "HideIfEmailIsApprovedByAdminBasedOnESPR"...
0x4e7e1  ldnull
0x4e7e2  ldftn    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RulePart Microsoft.Crm.Application.Ribbon.RibbonRulesXml::HideIfEmailIsApprovedByAdminBasedOnESPRulePart(class [System.Xml]System.Xml.XPath.XPathNavigator rulePartXml, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4e7e8  newobj   instance void ParseRuleDelegate::.ctor(object object, native int method)
0x4e7ed  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ParseRuleDelegate>::set_Item(var<u1>, !!T0)
0x4e7f2  dup
0x4e7f3  ldstr    aHideifproductr// "HideIfProductRecommendationsNotEnabledR"...
0x4e7f8  ldnull
0x4e7f9  ldftn    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RulePart Microsoft.Crm.Application.Ribbon.RibbonRulesXml::HideIfProductRecommendationsNotEnabledRulePart(class [System.Xml]System.Xml.XPath.XPathNavigator rulePartXml, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4e7ff  newobj   instance void ParseRuleDelegate::.ctor(object object, native int method)
0x4e804  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ParseRuleDelegate>::set_Item(var<u1>, !!T0)
  ... truncated ...
```
