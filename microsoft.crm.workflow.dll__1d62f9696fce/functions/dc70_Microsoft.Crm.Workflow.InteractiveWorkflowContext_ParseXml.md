# Microsoft.Crm.Workflow.InteractiveWorkflowContext::ParseXml

- ea: `0xdc70`
- end: `0xdd95`
- name: `Microsoft.Crm.Workflow.InteractiveWorkflowContext::ParseXml`
- size: `293`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0xd910`
- `0xd9a0`
- `0xd9e0`
- `0xda00`
- `0xda50`
- `0xda70`
- `0xda90`
- `0xdc70`
- `0xdda0`

## string_xrefs

- `0xdcf7`: `WorkflowStateXml`

## pseudocode

```c

```

## disassembly

```asm
0xdc70  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0xdc75  stloc.0
0xdc76  ldarg.1
0xdc77  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0xdc7c  stloc.0
0xdc7d  leave.s  loc_DC82
0xdc7f  pop
0xdc80  rethrow
0xdc82  ldloc.0
0xdc83  brfalse  loc_DD94
0xdc88  ldloc.0
0xdc89  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0xdc8e  stloc.1
0xdc8f  ldloc.1
0xdc90  brfalse  loc_DD94
0xdc95  ldarg.0
0xdc96  ldloc.1
0xdc97  ldstr    aWorkflowactiva_0// "WorkflowActivationId"
0xdc9c  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xdca1  ldstr    aValue// "value"
0xdca6  call     string Microsoft.Crm.Workflow.InteractiveWorkflowContext::GetAttributeValue(class [System.Xml]System.Xml.XmlNode node, string attributeName)
0xdcab  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xdcb0  call     instance void Microsoft.Crm.Workflow.SynchronousWorkflowCommonContext::set_WorkflowActivationId(valuetype [mscorlib]System.Guid value)
0xdcb5  ldarg.0
0xdcb6  ldloc.1
0xdcb7  ldstr    aOriginatingwor// "OriginatingWorkflowInstanceId"
0xdcbc  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xdcc1  ldstr    aValue// "value"
0xdcc6  call     string Microsoft.Crm.Workflow.InteractiveWorkflowContext::GetAttributeValue(class [System.Xml]System.Xml.XmlNode node, string attributeName)
0xdccb  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xdcd0  call     instance void Microsoft.Crm.Workflow.SynchronousWorkflowCommonContext::set_OriginatingWorkflowInstanceId(valuetype [mscorlib]System.Guid value)
0xdcd5  ldarg.0
0xdcd6  ldloc.1
0xdcd7  ldstr    aWorkflowinstan// "WorkflowInstanceId"
0xdcdc  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xdce1  ldstr    aValue// "value"
0xdce6  call     string Microsoft.Crm.Workflow.InteractiveWorkflowContext::GetAttributeValue(class [System.Xml]System.Xml.XmlNode node, string attributeName)
0xdceb  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xdcf0  call     instance void Microsoft.Crm.Workflow.SynchronousWorkflowCommonContext::set_WorkflowInstanceId(valuetype [mscorlib]System.Guid value)
0xdcf5  ldarg.0
0xdcf6  ldloc.1
0xdcf7  ldstr    aWorkflowstatex// "WorkflowStateXml"
0xdcfc  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xdd01  ldstr    aValue// "value"
0xdd06  call     string Microsoft.Crm.Workflow.InteractiveWorkflowContext::GetAttributeValue(class [System.Xml]System.Xml.XmlNode node, string attributeName)
0xdd0b  call     instance void Microsoft.Crm.Workflow.InteractiveWorkflowContext::set_WorkflowStateXml(string value)
0xdd10  ldloca.s 2
0xdd12  ldloc.1
0xdd13  ldstr    aPrimaryentityi// "PrimaryEntityId"
0xdd18  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xdd1d  ldstr    aValue// "value"
0xdd22  call     string Microsoft.Crm.Workflow.InteractiveWorkflowContext::GetAttributeValue(class [System.Xml]System.Xml.XmlNode node, string attributeName)
0xdd27  call     instance void [mscorlib]System.Guid::.ctor(string)
0xdd2c  ldloc.1
0xdd2d  ldstr    aPrimaryentityt// "PrimaryEntityTypeCode"
0xdd32  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xdd37  ldstr    aValue// "value"
0xdd3c  call     string Microsoft.Crm.Workflow.InteractiveWorkflowContext::GetAttributeValue(class [System.Xml]System.Xml.XmlNode node, string attributeName)
0xdd41  ldloca.s 3
0xdd43  call     bool [mscorlib]System.Int32::TryParse(string, int32&)
0xdd48  brtrue.s loc_DD4D
0xdd4a  ldc.i4.m1
0xdd4b  br.s     loc_DD4E
0xdd4d  ldloc.3
0xdd4e  stloc.3
0xdd4f  ldarg.0
0xdd50  ldloc.2
0xdd51  call     instance void Microsoft.Crm.Workflow.InteractiveWorkflowContext::set_PrimaryEntityId(valuetype [mscorlib]System.Guid value)
0xdd56  ldarg.0
0xdd57  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup::.ctor()
0xdd5c  dup
0xdd5d  ldloc.3
0xdd5e  ldc.i4.m1
0xdd5f  beq.s    loc_DD7E
0xdd61  ldarg.0
0xdd62  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.SynchronousWorkflowCommonContext::get_OrganizationId()
0xdd67  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0xdd6c  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xdd71  ldloc.3
0xdd72  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0xdd77  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xdd7c  br.s     loc_DD83
0xdd7e  ldsfld   string [mscorlib]System.String::Empty
0xdd83  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmReference::set_type(string)
0xdd88  dup
0xdd89  ldloc.2
0xdd8a  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmReference::set_Value(valuetype [mscorlib]System.Guid)
0xdd8f  call     instance void Microsoft.Crm.Workflow.InteractiveWorkflowContext::set_RegardingObject(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup value)
0xdd94  ret
```
