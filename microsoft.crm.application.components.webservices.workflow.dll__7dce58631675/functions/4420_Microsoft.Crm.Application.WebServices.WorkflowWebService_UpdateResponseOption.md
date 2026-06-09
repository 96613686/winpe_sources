# Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateResponseOption

- ea: `0x4420`
- end: `0x44db`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateResponseOption`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x40b0`

## callees

- `0x4420`

## pseudocode

```c

```

## disassembly

```asm
0x4420  ldarg.2
0x4421  ldstr    aBinding// "binding"
0x4426  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x442b  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x4430  ldstr    a1// "1"
0x4435  call     bool [mscorlib]System.String::op_Equality(string, string)
0x443a  brfalse.s loc_445F
0x443c  ldarg.2
0x443d  ldstr    aValues// "values"
0x4442  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x4447  stloc.0
0x4448  ldarg.1
0x4449  ldloc.0
0x444a  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_OuterXml()
0x444f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4454  callvirt instance string [mscorlib]System.String::ToString(class [mscorlib]System.IFormatProvider)
0x4459  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep::set_StaticResponseValues(string)
0x445e  ret
0x445f  ldarg.2
0x4460  ldstr    aQuerystepid// "querystepid"
0x4465  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x446a  stloc.1
0x446b  ldloc.1
0x446c  brfalse.s loc_44B7
0x446e  ldarg.1
0x446f  ldloc.1
0x4470  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x4475  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep::set_QueryVariableName(string)
0x447a  ldarg.2
0x447b  ldstr    aColumnlist// "columnList"
0x4480  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x4485  stloc.3
0x4486  ldarg.1
0x4487  ldloc.3
0x4488  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x448d  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep::set_AttributeList(string)
0x4492  ldarg.1
0x4493  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Workflow()
0x4498  ldarg.1
0x4499  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep::get_QueryVariableName()
0x449e  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x44a3  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.QueryStep
0x44a8  stloc.s  4
0x44aa  ldarg.1
0x44ab  ldloc.s  4
0x44ad  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.QueryStep::get_EntityName()
0x44b2  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep::set_QueryEntityName(string)
0x44b7  ldarg.2
0x44b8  ldstr    aSeparator// "separator"
0x44bd  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x44c2  stloc.2
0x44c3  ldarg.1
0x44c4  ldloc.2
0x44c5  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x44ca  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep::set_AttributeDelimiter(string)
0x44cf  ldarg.1
0x44d0  ldsfld   string [mscorlib]System.String::Empty
0x44d5  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep::set_StaticResponseValues(string)
0x44da  ret
```
