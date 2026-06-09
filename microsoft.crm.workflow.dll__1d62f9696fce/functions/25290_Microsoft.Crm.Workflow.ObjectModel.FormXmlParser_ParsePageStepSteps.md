# Microsoft.Crm.Workflow.ObjectModel.FormXmlParser::ParsePageStepSteps

- ea: `0x25290`
- end: `0x2534a`
- name: `Microsoft.Crm.Workflow.ObjectModel.FormXmlParser::ParsePageStepSteps`
- size: `186`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x25220`

## callees

- `0x25290`
- `0x25350`
- `0x25510`
- `0x25580`
- `0x255d0`
- `0x25700`

## pseudocode

```c

```

## disassembly

```asm
0x25290  ldarg.1
0x25291  ldstr    aColumnsColumnS// "columns/column/sections/section"
0x25296  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x2529b  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x252a0  stloc.1
0x252a1  br.s     loc_25312
0x252a3  ldloc.1
0x252a4  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x252a9  castclass [System.Xml]System.Xml.XmlNode
0x252ae  stloc.2
0x252af  ldarg.0
0x252b0  ldloc.2
0x252b1  call     instance bool Microsoft.Crm.Workflow.ObjectModel.FormXmlParser::IsDefaultSection(class [System.Xml]System.Xml.XmlNode sectionXmlNode)
0x252b6  brtrue.s loc_252F9
0x252b8  ldarg.0
0x252b9  ldloc.2
0x252ba  ldarg.2
0x252bb  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepStep Microsoft.Crm.Workflow.ObjectModel.FormXmlParser::ParseStepStep(class [System.Xml]System.Xml.XmlNode stepStepNode, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.PageStep currentPageStep)
0x252c0  stloc.s  4
0x252c2  ldarg.0
0x252c3  ldloc.2
0x252c4  ldloc.s  4
0x252c6  call     instance void Microsoft.Crm.Workflow.ObjectModel.FormXmlParser::ParseStepStepLabels(class [System.Xml]System.Xml.XmlNode stepXmlNode, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepStep currentStepStep)
0x252cb  ldarg.0
0x252cc  ldloc.s  4
0x252ce  call     instance void Microsoft.Crm.Workflow.ObjectModel.FormXmlParser::CreateSectionControlStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepStep currentStepStep)
0x252d3  ldarg.2
0x252d4  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Workflow()
0x252d9  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepDictionary [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_StepDictionary()
0x252de  ldloc.s  4
0x252e0  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Id()
0x252e5  ldloc.s  4
0x252e7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase>::set_Item(var<u1>, !!T0)
0x252ec  ldarg.2
0x252ed  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_Steps()
0x252f2  ldloc.s  4
0x252f4  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection::Add(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x252f9  ldloc.2
0x252fa  ldstr    aRowsRowCell// "rows/row/cell"
0x252ff  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x25304  stloc.3
0x25305  ldarg.0
0x25306  ldarg.2
0x25307  ldloc.3
0x25308  ldstr    aControl// "control"
0x2530d  call     instance void Microsoft.Crm.Workflow.ObjectModel.FormXmlParser::ParsePageStepSteps(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.PageStep currentPageStep, class [System.Xml]System.Xml.XmlNodeList rowXmlNodes, string childNodeName)
0x25312  ldloc.1
0x25313  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x25318  brtrue.s loc_252A3
0x2531a  leave.s  loc_25330
0x2531c  ldloc.1
0x2531d  isinst   [mscorlib]System.IDisposable
0x25322  stloc.s  5
0x25324  ldloc.s  5
0x25326  brfalse.s loc_2532F
0x25328  ldloc.s  5
0x2532a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2532f  endfinally
0x25330  ldarg.1
0x25331  ldstr    aHiddencontrols// "hiddencontrols"
0x25336  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x2533b  stloc.0
0x2533c  ldarg.0
0x2533d  ldarg.2
0x2533e  ldloc.0
0x2533f  ldstr    aData// "data"
0x25344  call     instance void Microsoft.Crm.Workflow.ObjectModel.FormXmlParser::ParsePageStepSteps(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.PageStep currentPageStep, class [System.Xml]System.Xml.XmlNodeList rowXmlNodes, string childNodeName)
0x25349  ret
```
