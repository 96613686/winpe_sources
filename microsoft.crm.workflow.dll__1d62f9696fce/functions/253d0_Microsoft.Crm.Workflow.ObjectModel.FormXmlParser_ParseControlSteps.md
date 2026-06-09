# Microsoft.Crm.Workflow.ObjectModel.FormXmlParser::ParseControlSteps

- ea: `0x253d0`
- end: `0x2550c`
- name: `Microsoft.Crm.Workflow.ObjectModel.FormXmlParser::ParseControlSteps`
- size: `316`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x25350`

## callees

- `0xf2f0`
- `0x253d0`
- `0x25730`
- `0x25750`
- `0x257b0`
- `0x257e0`

## string_xrefs

- `0x2541c`: `classid`

## pseudocode

```c

```

## disassembly

```asm
0x253d0  ldarg.1
0x253d1  ldarg.3
0x253d2  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x253d7  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x253dc  stloc.0
0x253dd  br       loc_254EA
0x253e2  ldloc.0
0x253e3  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x253e8  castclass [System.Xml]System.Xml.XmlNode
0x253ed  stloc.1
0x253ee  ldarg.2
0x253ef  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Workflow()
0x253f4  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ControlStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x253f9  stloc.2
0x253fa  ldloc.2
0x253fb  ldarg.2
0x253fc  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::set_Parent(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x25401  ldloc.2
0x25402  ldarg.2
0x25403  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Workflow()
0x25408  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::set_Workflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x2540d  ldloc.2
0x2540e  ldarg.2
0x2540f  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepStep::get_StepStepName()
0x25414  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ControlStep::set_ControlDisplayName(string)
0x25419  ldloc.2
0x2541a  ldarg.0
0x2541b  ldloc.1
0x2541c  ldstr    aClassid// "classid"
0x25421  call     instance string Microsoft.Crm.Workflow.ObjectModel.FormXmlParser::TryGetIdAttributeValue(class [System.Xml]System.Xml.XmlNode xmlNode, string attributeName)
0x25426  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ControlStep::set_ClassId(string)
0x2542b  ldloc.2
0x2542c  ldarg.0
0x2542d  ldloc.1
0x2542e  ldstr    aDatafieldname// "datafieldname"
0x25433  call     instance string Microsoft.Crm.Workflow.ObjectModel.FormXmlParser::TryGetAttributeValue(class [System.Xml]System.Xml.XmlNode xmlNode, string attributeName)
0x25438  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ControlStep::set_DataFieldName(string)
0x2543d  ldloc.2
0x2543e  ldarg.0
0x2543f  ldloc.1
0x25440  ldstr    aIsunbound// "isunbound"
0x25445  call     instance bool Microsoft.Crm.Workflow.ObjectModel.FormXmlParser::TryGetBooleanAttributeValue(class [System.Xml]System.Xml.XmlNode xmlNode, string attributeName)
0x2544a  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ControlStep::set_IsUnbound(bool)
0x2544f  ldarg.0
0x25450  ldloc.2
0x25451  call     instance bool Microsoft.Crm.Workflow.ObjectModel.FormXmlParser::IsLabelControlStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ControlStep controlStep)
0x25456  brtrue.s loc_254A7
0x25458  ldloc.2
0x25459  ldloc.2
0x2545a  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ControlStep::get_DataFieldName()
0x2545f  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ControlStep::set_ControlId(string)
0x25464  ldloc.2
0x25465  ldc.i4.0
0x25466  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ControlStep::set_ControlType(int32)
0x2546b  ldarg.0
0x2546c  ldloc.1
0x2546d  ldstr    aRelationship// "relationship"
0x25472  call     instance string Microsoft.Crm.Workflow.ObjectModel.FormXmlParser::TryGetAttributeValue(class [System.Xml]System.Xml.XmlNode xmlNode, string attributeName)
0x25477  stloc.3
0x25478  ldloc.3
0x25479  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2547e  brfalse.s loc_25493
0x25480  ldloc.2
0x25481  ldarg.2
0x25482  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Workflow()
0x25487  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PrimaryEntity::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x2548c  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ControlStep::set_Entity(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase)
0x25491  br.s     loc_254C7
0x25493  ldloc.2
0x25494  ldarg.0
0x25495  ldfld    class Microsoft.Crm.Workflow.Utility.WorkflowRelationshipResolver Microsoft.Crm.Workflow.ObjectModel.FormXmlParser::_workflowRelationshipResolver
0x2549a  ldloc.3
0x2549b  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.RelatedEntityLinked Microsoft.Crm.Workflow.Utility.WorkflowRelationshipResolver::GetRelatedEntity(string relationshipName)
0x254a0  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ControlStep::set_Entity(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase)
0x254a5  br.s     loc_254C7
0x254a7  ldloc.2
0x254a8  ldc.i4.2
0x254a9  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ControlStep::set_ControlType(int32)
0x254ae  ldloc.2
0x254af  ldarg.0
0x254b0  ldloc.1
0x254b1  ldstr    aId_2// "id"
0x254b6  call     instance string Microsoft.Crm.Workflow.ObjectModel.FormXmlParser::TryGetAttributeValue(class [System.Xml]System.Xml.XmlNode xmlNode, string attributeName)
0x254bb  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ControlStep::set_ControlId(string)
0x254c0  ldloc.2
0x254c1  ldnull
0x254c2  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ControlStep::set_Entity(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase)
0x254c7  ldarg.2
0x254c8  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Workflow()
0x254cd  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepDictionary [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_StepDictionary()
0x254d2  ldloc.2
0x254d3  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Id()
0x254d8  ldloc.2
0x254d9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase>::set_Item(var<u1>, !!T0)
0x254de  ldarg.2
0x254df  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_Steps()
0x254e4  ldloc.2
0x254e5  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection::Add(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x254ea  ldloc.0
0x254eb  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x254f0  brtrue   loc_253E2
0x254f5  leave.s  loc_2550B
0x254f7  ldloc.0
0x254f8  isinst   [mscorlib]System.IDisposable
0x254fd  stloc.s  4
0x254ff  ldloc.s  4
0x25501  brfalse.s loc_2550A
0x25503  ldloc.s  4
0x25505  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2550a  endfinally
0x2550b  ret
```
