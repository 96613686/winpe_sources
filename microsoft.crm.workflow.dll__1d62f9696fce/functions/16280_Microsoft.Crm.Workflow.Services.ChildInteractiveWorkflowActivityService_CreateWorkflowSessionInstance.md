# Microsoft.Crm.Workflow.Services.ChildInteractiveWorkflowActivityService::CreateWorkflowSessionInstance

- ea: `0x16280`
- end: `0x1638a`
- name: `Microsoft.Crm.Workflow.Services.ChildInteractiveWorkflowActivityService::CreateWorkflowSessionInstance`
- size: `266`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x2e9a0`

## callees

- `0xd9d0`
- `0xd9f0`
- `0x14480`
- `0x16000`

## string_xrefs

- `0x16294`: `processid`
- `0x162fd`: `comments`
- `0x162dd`: `previouslinkedsessionid`
- `0x16349`: `Linked Child Workflow got created. Originating Workflow Session '{0}', Parent workflow session '{1}', Linked child workflow session '{2}'.`

## pseudocode

```c

```

## disassembly

```asm
0x16280  ldarg.s  5
0x16282  call     string Microsoft.Crm.Workflow.Services.InputParametersSerializerDeSerializer::GetDictionaryXml(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> inputParametersDictionary)
0x16287  stloc.0
0x16288  ldstr    aProcesssession_0// "processsession"
0x1628d  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x16292  stloc.1
0x16293  ldloc.1
0x16294  ldstr    aProcessid// "processid"
0x16299  ldstr    aWorkflow// "workflow"
0x1629e  ldarg.s  4
0x162a0  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x162a5  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x162aa  ldloc.1
0x162ab  ldstr    aRegardingobjec_0// "regardingobjectid"
0x162b0  ldarg.2
0x162b1  ldarg.3
0x162b2  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x162b7  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x162bc  ldloc.1
0x162bd  ldstr    aOriginatingses// "originatingsessionid"
0x162c2  ldstr    aProcesssession_0// "processsession"
0x162c7  ldarg.0
0x162c8  call     instance class Microsoft.Crm.Workflow.InteractiveWorkflowInputContext Microsoft.Crm.Workflow.Services.ChildInteractiveWorkflowActivityService::get_InteractiveWorkflowInputContext()
0x162cd  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.SynchronousWorkflowCommonContext::get_OriginatingWorkflowInstanceId()
0x162d2  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x162d7  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x162dc  ldloc.1
0x162dd  ldstr    aPreviouslinked// "previouslinkedsessionid"
0x162e2  ldstr    aProcesssession_0// "processsession"
0x162e7  ldarg.0
0x162e8  call     instance class Microsoft.Crm.Workflow.InteractiveWorkflowInputContext Microsoft.Crm.Workflow.Services.ChildInteractiveWorkflowActivityService::get_InteractiveWorkflowInputContext()
0x162ed  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.SynchronousWorkflowCommonContext::get_WorkflowInstanceId()
0x162f2  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x162f7  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x162fc  ldloc.1
0x162fd  ldstr    aComments// "comments"
0x16302  ldsfld   string [mscorlib]System.String::Empty
0x16307  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x1630c  ldloc.1
0x1630d  ldstr    aInputarguments_0// "inputarguments"
0x16312  ldloc.0
0x16313  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x16318  ldloc.1
0x16319  ldstr    aStatecode// "statecode"
0x1631e  ldc.i4.0
0x1631f  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0x16324  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x16329  ldloc.1
0x1632a  ldstr    aStatuscode// "statuscode"
0x1632f  ldc.i4.2
0x16330  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0x16335  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x1633a  ldarg.1
0x1633b  ldloc.1
0x1633c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Create(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0x16341  stloc.2
0x16342  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x16347  ldc.i4.s 0x1E
0x16349  ldstr    aLinkedChildWor// "Linked Child Workflow got created. Orig"...
0x1634e  ldc.i4.3
0x1634f  newarr   [mscorlib]System.Object
0x16354  dup
0x16355  ldc.i4.0
0x16356  ldarg.0
0x16357  call     instance class Microsoft.Crm.Workflow.InteractiveWorkflowInputContext Microsoft.Crm.Workflow.Services.ChildInteractiveWorkflowActivityService::get_InteractiveWorkflowInputContext()
0x1635c  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.SynchronousWorkflowCommonContext::get_OriginatingWorkflowInstanceId()
0x16361  box      [mscorlib]System.Guid
0x16366  stelem.ref
0x16367  dup
0x16368  ldc.i4.1
0x16369  ldarg.0
0x1636a  call     instance class Microsoft.Crm.Workflow.InteractiveWorkflowInputContext Microsoft.Crm.Workflow.Services.ChildInteractiveWorkflowActivityService::get_InteractiveWorkflowInputContext()
0x1636f  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.SynchronousWorkflowCommonContext::get_WorkflowInstanceId()
0x16374  box      [mscorlib]System.Guid
0x16379  stelem.ref
0x1637a  dup
0x1637b  ldc.i4.2
0x1637c  ldloc.2
0x1637d  box      [mscorlib]System.Guid
0x16382  stelem.ref
0x16383  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x16388  ldloc.2
0x16389  ret
```
