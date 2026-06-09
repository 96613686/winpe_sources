# Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::ExecuteWorkflow

- ea: `0x12990`
- end: `0x12a9b`
- name: `Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::ExecuteWorkflow`
- size: `267`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x10900`
- `0x12350`
- `0x13290`

## callees

- `0x12990`
- `0x12aa0`

## pseudocode

```c

```

## disassembly

```asm
0x12990  ldarg.0
0x12991  brfalse  loc_12A9A
0x12996  ldarg.0
0x12997  ldstr    aWorkflowid// "workflowid"
0x1299c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x129a1  brfalse  loc_12A9A
0x129a6  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ExecuteWorkflowRequest::.ctor()
0x129ab  dup
0x129ac  ldarg.0
0x129ad  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0x129b2  ldstr    aWorkflowid// "workflowid"
0x129b7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0x129bc  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0x129c1  callvirt instance string [mscorlib]System.Object::ToString()
0x129c6  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x129cb  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ExecuteWorkflowRequest::set_WorkflowId(valuetype [mscorlib]System.Guid)
0x129d0  dup
0x129d1  ldarg.1
0x129d2  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ExecuteWorkflowRequest::set_EntityId(valuetype [mscorlib]System.Guid)
0x129d7  stloc.0
0x129d8  ldstr    aOnholdtime// "onholdtime"
0x129dd  ldtoken  [mscorlib]System.Int32
0x129e2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x129e7  ldc.i4.1
0x129e8  call     string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::ConstructIdentifierName(string, class [mscorlib]System.Type, bool)
0x129ed  stloc.1
0x129ee  ldstr    aInvokechildwfs// "invokechildwfs"
0x129f3  ldtoken  [mscorlib]System.Int32
0x129f8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x129fd  ldc.i4.1
0x129fe  call     string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::ConstructIdentifierName(string, class [mscorlib]System.Type, bool)
0x12a03  stloc.2
0x12a04  ldstr    aStatus// "status"
0x12a09  ldtoken  [mscorlib]System.Int32
0x12a0e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x12a13  ldc.i4.1
0x12a14  call     string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::ConstructIdentifierName(string, class [mscorlib]System.Type, bool)
0x12a19  stloc.3
0x12a1a  ldarg.0
0x12a1b  ldstr    aAllowpauseresu// "allowpauseresume"
0x12a20  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x12a25  brfalse.s loc_12A75
0x12a27  ldarg.0
0x12a28  ldstr    aAllowpauseresu// "allowpauseresume"
0x12a2d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x12a32  unbox.any [mscorlib]System.Boolean
0x12a37  brfalse.s loc_12A75
0x12a39  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.InputArgumentCollection::.ctor()
0x12a3e  stloc.s  4
0x12a40  ldloc.s  4
0x12a42  ldloc.1
0x12a43  ldarg.s  4
0x12a45  box      [mscorlib]System.Int32
0x12a4a  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.InputArgumentCollection::Add(string, object)
0x12a4f  ldloc.s  4
0x12a51  ldloc.3
0x12a52  ldarg.s  5
0x12a54  box      [mscorlib]System.Int32
0x12a59  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.InputArgumentCollection::Add(string, object)
0x12a5e  ldloc.s  4
0x12a60  ldloc.2
0x12a61  ldarg.s  6
0x12a63  box      [mscorlib]System.Int32
0x12a68  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.InputArgumentCollection::Add(string, object)
0x12a6d  ldloc.0
0x12a6e  ldloc.s  4
0x12a70  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ExecuteWorkflowRequest::set_InputArguments(class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.InputArgumentCollection)
0x12a75  ldarg.2
0x12a76  ldloc.0
0x12a77  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x12a7c  castclass [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ExecuteWorkflowResponse
0x12a81  brfalse.s loc_12A9A
0x12a83  ldarg.3
0x12a84  ldarg.0
0x12a85  ldstr    aSlaid// "slaid"
0x12a8a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x12a8f  ldarg.1
0x12a90  box      [mscorlib]System.Guid
0x12a95  call     void Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::ExecuteWithoutPipline(class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext context, object slaInvokedId, object incidentId)
0x12a9a  ret
```
