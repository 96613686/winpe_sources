# Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateResponseSection

- ea: `0x40b0`
- end: `0x414e`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateResponseSection`
- size: `158`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x3f00`

## callees

- `0x40b0`
- `0x4150`
- `0x41d0`
- `0x4420`

## string_xrefs

- `0x413d`: `Invalid XML`

## pseudocode

```c

```

## disassembly

```asm
0x40b0  ldarg.2
0x40b1  ldstr    aResponsecontai// "responsecontainer"
0x40b6  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x40bb  stloc.0
0x40bc  ldarg.1
0x40bd  ldloc.0
0x40be  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x40c3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x40c8  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x40cd  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep::set_ResponseContainerType(int32)
0x40d2  ldarg.0
0x40d3  ldarg.1
0x40d4  ldarg.2
0x40d5  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateMetadataBinding(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep interactionStep, class [System.Xml]System.Xml.XPath.XPathNavigator responseNode)
0x40da  ldarg.1
0x40db  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep::get_ResponseContainerType()
0x40e0  stloc.1
0x40e1  ldloc.1
0x40e2  switch   loc_414D, loc_4109, loc_4114, loc_4114, loc_4109, loc_4132, loc_4132, loc_4127
0x4107  br.s     loc_413D
0x4109  ldarg.0
0x410a  ldarg.1
0x410b  ldarg.2
0x410c  ldc.i4.1
0x410d  ldarg.3
0x410e  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateResponseDetails(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep interactionStep, class [System.Xml]System.Xml.XPath.XPathNavigator responseNode, bool isDefaultValueValid, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x4113  ret
0x4114  ldarg.0
0x4115  ldarg.1
0x4116  ldarg.2
0x4117  ldc.i4.0
0x4118  ldarg.3
0x4119  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateResponseDetails(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep interactionStep, class [System.Xml]System.Xml.XPath.XPathNavigator responseNode, bool isDefaultValueValid, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x411e  ldarg.0
0x411f  ldarg.1
0x4120  ldarg.2
0x4121  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateResponseOption(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep interactionStep, class [System.Xml]System.Xml.XPath.XPathNavigator responseNode)
0x4126  ret
0x4127  ldarg.0
0x4128  ldarg.1
0x4129  ldarg.2
0x412a  ldc.i4.0
0x412b  ldarg.3
0x412c  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateResponseDetails(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep interactionStep, class [System.Xml]System.Xml.XPath.XPathNavigator responseNode, bool isDefaultValueValid, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x4131  ret
0x4132  ldarg.0
0x4133  ldarg.1
0x4134  ldarg.2
0x4135  ldc.i4.1
0x4136  ldarg.3
0x4137  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateResponseDetails(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep interactionStep, class [System.Xml]System.Xml.XPath.XPathNavigator responseNode, bool isDefaultValueValid, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x413c  ret
0x413d  ldstr    aInvalidXml// "Invalid XML"
0x4142  ldc.i4   0x80004005
0x4147  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x414c  throw
0x414d  ret
```
