# Microsoft.Crm.Application.WebServices.WorkflowWebService::SetStopWorkflowStatus

- ea: `0x5ef0`
- end: `0x5f1c`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::SetStopWorkflowStatus`
- size: `44`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x5e20`

## callees

- `0x5ef0`

## pseudocode

```c

```

## disassembly

```asm
0x5ef0  ldarg.1
0x5ef1  ldstr    aValue// "value"
0x5ef6  ldsfld   string [mscorlib]System.String::Empty
0x5efb  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::GetAttribute(string, string)
0x5f00  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5f05  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x5f0a  brtrue.s loc_5F14
0x5f0c  ldarg.0
0x5f0d  ldc.i4.0
0x5f0e  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StopWorkflowStep::set_Status(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Workflow.Activities.WorkflowCompletionStatus)
0x5f13  ret
0x5f14  ldarg.0
0x5f15  ldc.i4.1
0x5f16  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StopWorkflowStep::set_Status(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Workflow.Activities.WorkflowCompletionStatus)
0x5f1b  ret
```
