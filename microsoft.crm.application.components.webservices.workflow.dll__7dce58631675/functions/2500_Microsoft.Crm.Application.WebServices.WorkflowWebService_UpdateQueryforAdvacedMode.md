# Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateQueryforAdvacedMode

- ea: `0x2500`
- end: `0x25b5`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateQueryforAdvacedMode`
- size: `181`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x2340`

## callees

- `0x2500`
- `0x2630`
- `0x2700`

## pseudocode

```c

```

## disassembly

```asm
0x2500  ldarg.3
0x2501  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_InnerXml()
0x2506  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmXmlDecode(string)
0x250b  stloc.0
0x250c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2511  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.IFormatProvider)
0x2516  stloc.1
0x2517  ldloc.1
0x2518  ldc.i4.1
0x2519  call     class [System.Xml]System.Xml.XmlWriter [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlWriter(class [mscorlib]System.IO.TextWriter, bool)
0x251e  stloc.3
0x251f  ldloc.3
0x2520  ldstr    aSlugbody// "slugbody"
0x2525  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x252a  ldloc.3
0x252b  ldstr    aSlugelement// "slugelement"
0x2530  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x2535  ldloc.3
0x2536  ldstr    aType// "type"
0x253b  ldstr    aOperator// "operator"
0x2540  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x2545  ldloc.3
0x2546  ldstr    aValue// "value"
0x254b  ldstr    aQueryconcat// "QUERYCONCAT"
0x2550  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x2555  ldloc.3
0x2556  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x255b  ldarg.0
0x255c  ldarg.s  4
0x255e  call     instance class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Application.WebServices.WorkflowWebService::GetConditionsList(class [System.Xml]System.Xml.XPath.XPathNavigator conditionsNode)
0x2563  stloc.s  4
0x2565  ldarg.0
0x2566  ldloc.3
0x2567  ldloc.0
0x2568  ldloc.s  4
0x256a  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::ConstructSlugXml(class [System.Xml]System.Xml.XmlWriter xmlWriter, string modifiedFetch, class [mscorlib]System.Collections.Generic.List`1<string> conditionsXmls)
0x256f  ldloc.3
0x2570  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x2575  ldloc.3
0x2576  callvirt instance void [System.Xml]System.Xml.XmlWriter::Flush()
0x257b  leave.s  loc_2587
0x257d  ldloc.3
0x257e  brfalse.s loc_2586
0x2580  ldloc.3
0x2581  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2586  endfinally
0x2587  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x258c  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.PropertyExpressionBuilder::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2591  stloc.2
0x2592  ldarg.1
0x2593  ldloc.2
0x2594  ldarg.2
0x2595  ldc.i4.s 0xE
0x2597  ldloc.1
0x2598  callvirt instance string [mscorlib]System.Object::ToString()
0x259d  ldc.i4.0
0x259e  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.PropertyExpressionBuilder::CreateExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, string, bool)
0x25a3  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.QueryStep::set_FetchExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x25a8  leave.s  loc_25B4
0x25aa  ldloc.1
0x25ab  brfalse.s loc_25B3
0x25ad  ldloc.1
0x25ae  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x25b3  endfinally
0x25b4  ret
```
