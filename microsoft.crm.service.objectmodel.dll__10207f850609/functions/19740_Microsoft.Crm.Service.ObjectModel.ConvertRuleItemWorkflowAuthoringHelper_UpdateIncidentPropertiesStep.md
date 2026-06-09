# Microsoft.Crm.Service.ObjectModel.ConvertRuleItemWorkflowAuthoringHelper::UpdateIncidentPropertiesStep

- ea: `0x19740`
- end: `0x197e7`
- name: `Microsoft.Crm.Service.ObjectModel.ConvertRuleItemWorkflowAuthoringHelper::UpdateIncidentPropertiesStep`
- size: `167`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x197f0`

## callees

- `0x19740`
- `0x19890`
- `0x19a30`

## pseudocode

```c

```

## disassembly

```asm
0x19740  ldarg.3
0x19741  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x19746  brfalse.s loc_19749
0x19748  ret
0x19749  ldarg.3
0x1974a  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x1974f  stloc.0
0x19750  ldloc.0
0x19751  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x19756  brfalse  loc_197E6
0x1975b  ldloc.0
0x1975c  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x19761  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x19766  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x1976b  stloc.1
0x1976c  br.s     loc_197C8
0x1976e  ldloc.1
0x1976f  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x19774  castclass [System.Xml]System.Xml.XmlNode
0x19779  stloc.2
0x1977a  ldarg.0
0x1977b  ldarg.1
0x1977c  ldloc.2
0x1977d  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification Microsoft.Crm.Service.ObjectModel.ConvertRuleItemWorkflowAuthoringHelper::CreateSetPropertiesExpressionFromNode(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflow, class [System.Xml]System.Xml.XmlNode propertyNode)
0x19782  stloc.3
0x19783  ldloc.3
0x19784  ldnull
0x19785  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x1978a  brtrue.s loc_197C8
0x1978c  ldarg.2
0x1978d  ldloc.3
0x1978e  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification::get_Name()
0x19793  call     int32 Microsoft.Crm.Service.ObjectModel.ConvertRuleItemWorkflowAuthoringHelper::IfPropertyPresent(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep createStep, string propertyName)
0x19798  stloc.s  4
0x1979a  ldloc.s  4
0x1979c  ldc.i4.m1
0x1979d  beq.s    loc_197B1
0x1979f  ldarg.2
0x197a0  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep::get_Entity()
0x197a5  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification> [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification::get_Properties()
0x197aa  ldloc.s  4
0x197ac  callvirt instance void class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification>::RemoveAt(int32)
0x197b1  ldarg.2
0x197b2  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep::get_Entity()
0x197b7  ldloc.3
0x197b8  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification::get_Name()
0x197bd  ldloc.3
0x197be  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification::get_Value()
0x197c3  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification::AddProperty(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x197c8  ldloc.1
0x197c9  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x197ce  brtrue.s loc_1976E
0x197d0  leave.s  loc_197E6
0x197d2  ldloc.1
0x197d3  isinst   [mscorlib]System.IDisposable
0x197d8  stloc.s  5
0x197da  ldloc.s  5
0x197dc  brfalse.s loc_197E5
0x197de  ldloc.s  5
0x197e0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x197e5  endfinally
0x197e6  ret
```
