# Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateMetadataBinding

- ea: `0x4150`
- end: `0x41c4`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateMetadataBinding`
- size: `116`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x40b0`

## callees

- `0x4150`

## pseudocode

```c

```

## disassembly

```asm
0x4150  ldarg.2
0x4151  ldstr    aResponsemetada// "responseMetadataBound"
0x4156  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x415b  stloc.0
0x415c  ldloc.0
0x415d  brfalse.s loc_41C3
0x415f  ldarg.1
0x4160  ldloc.0
0x4161  callvirt instance bool [System.Xml]System.Xml.XPath.XPathItem::get_ValueAsBoolean()
0x4166  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep::set_IsResponseMetadataBound(bool)
0x416b  ldloc.0
0x416c  callvirt instance bool [System.Xml]System.Xml.XPath.XPathItem::get_ValueAsBoolean()
0x4171  brfalse.s loc_41C3
0x4173  ldarg.2
0x4174  ldstr    aResponsemetada_0// "responseMetadataBinding"
0x4179  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x417e  dup
0x417f  ldstr    aEntity// "entity"
0x4184  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x4189  stloc.1
0x418a  dup
0x418b  ldstr    aAttribute_0// "attribute"
0x4190  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x4195  stloc.2
0x4196  brfalse.s loc_41A1
0x4198  ldloc.1
0x4199  brfalse.s loc_41A1
0x419b  ldloc.2
0x419c  ldnull
0x419d  cgt.un
0x419f  br.s     loc_41A2
0x41a1  ldc.i4.0
0x41a2  ldstr    aInvalidInput_0// "Invalid Input"
0x41a7  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x41ac  ldarg.1
0x41ad  ldloc.1
0x41ae  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x41b3  ldloc.2
0x41b4  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x41b9  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.MetadataSource::.ctor(string, string)
0x41be  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep::set_ResponseMetadataSource(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.MetadataSource)
0x41c3  ret
```
