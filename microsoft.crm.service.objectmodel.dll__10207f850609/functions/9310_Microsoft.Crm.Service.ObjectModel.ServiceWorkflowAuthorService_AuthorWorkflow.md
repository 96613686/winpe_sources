# Microsoft.Crm.Service.ObjectModel.ServiceWorkflowAuthorService::AuthorWorkflow

- ea: `0x9310`
- end: `0x9460`
- name: `Microsoft.Crm.Service.ObjectModel.ServiceWorkflowAuthorService::AuthorWorkflow`
- size: `336`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x9310`
- `0x9460`
- `0x9480`
- `0x15540`
- `0x15560`
- `0x17e70`
- `0x17e90`
- `0x1a0e0`
- `0x1a100`

## pseudocode

```c

```

## disassembly

```asm
0x9310  ldarg.0
0x9311  ldfld    bool Microsoft.Crm.Service.ObjectModel.ServiceWorkflowAuthorService::_useReflection
0x9316  brfalse.s loc_936E
0x9318  ldarg.0
0x9319  call     instance class [mscorlib]System.Type Microsoft.Crm.Service.ObjectModel.ServiceWorkflowAuthorService::GetWorkflowAuthorType()
0x931e  stloc.0
0x931f  ldloc.0
0x9320  ldc.i4.2
0x9321  newarr   [mscorlib]System.Object
0x9326  dup
0x9327  ldc.i4.0
0x9328  ldarg.0
0x9329  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.WorkflowAuthorServiceBase::get_Context()
0x932e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x9333  box      [mscorlib]System.Guid
0x9338  stelem.ref
0x9339  dup
0x933a  ldc.i4.1
0x933b  ldc.i4.1
0x933c  box      [mscorlib]System.Boolean
0x9341  stelem.ref
0x9342  call     object [mscorlib]System.Activator::CreateInstance(class [mscorlib]System.Type, object[])
0x9347  stloc.1
0x9348  ldloc.0
0x9349  ldstr    aAuthorworkflow// "AuthorWorkflow"
0x934e  ldc.i4   0x100
0x9353  ldnull
0x9354  ldloc.1
0x9355  ldarg.0
0x9356  callvirt instance object[] Microsoft.Crm.Service.ObjectModel.ServiceWorkflowAuthorService::GetAuthorWorkflowArgs()
0x935b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9360  callvirt instance object [mscorlib]System.Type::InvokeMember(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, object, object[], class [mscorlib]System.Globalization.CultureInfo)
0x9365  pop
0x9366  leave    loc_945F
0x936b  pop
0x936c  rethrow
0x936e  ldarg.0
0x936f  call     instance valuetype [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.WorkflowAuthorType [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.WorkflowAuthorServiceBase::get_WorkflowAuthorType()
0x9374  stloc.2
0x9375  ldloc.2
0x9376  switch   loc_9388, loc_9418, loc_93D0
0x9387  ret
0x9388  ldarg.0
0x9389  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.WorkflowAuthorServiceBase::get_Context()
0x938e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x9393  ldc.i4.1
0x9394  newobj   instance void Microsoft.Crm.Service.ObjectModel.SLAWorkflowAuthoringHelper::.ctor(valuetype [mscorlib]System.Guid organizationId, bool isSdkContext)
0x9399  ldarg.0
0x939a  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.WorkflowAuthorServiceBase::get_Moniker()
0x939f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x93a4  stloc.3
0x93a5  ldloca.s 3
0x93a7  constrained. [mscorlib]System.Guid
0x93ad  callvirt instance string [mscorlib]System.Object::ToString()
0x93b2  ldarg.0
0x93b3  ldfld    string Microsoft.Crm.Service.ObjectModel.ServiceWorkflowAuthorService::_entityName
0x93b8  ldarg.0
0x93b9  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.WorkflowAuthorServiceBase::get_Context()
0x93be  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.WorkflowErrorVisitorContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x93c3  ldarg.0
0x93c4  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.WorkflowAuthorServiceBase::get_Context()
0x93c9  callvirt instance string Microsoft.Crm.Service.ObjectModel.SLAWorkflowAuthoringHelper::AuthorWorkflow(string entityId, string primaryEntityName, class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.IWorkflowErrorVisitorContext workflowErrorVisitorContext, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x93ce  pop
0x93cf  ret
0x93d0  ldarg.0
0x93d1  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.WorkflowAuthorServiceBase::get_Context()
0x93d6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x93db  ldc.i4.1
0x93dc  newobj   instance void Microsoft.Crm.Service.ObjectModel.ConvertRuleWorkflowAuthoringHelper::.ctor(valuetype [mscorlib]System.Guid organizationId, bool isSdkContext)
0x93e1  ldarg.0
0x93e2  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.WorkflowAuthorServiceBase::get_Moniker()
0x93e7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x93ec  stloc.3
0x93ed  ldloca.s 3
0x93ef  constrained. [mscorlib]System.Guid
0x93f5  callvirt instance string [mscorlib]System.Object::ToString()
0x93fa  ldarg.0
0x93fb  ldfld    string Microsoft.Crm.Service.ObjectModel.ServiceWorkflowAuthorService::_entityName
0x9400  ldarg.0
0x9401  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.WorkflowAuthorServiceBase::get_Context()
0x9406  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.WorkflowErrorVisitorContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x940b  ldarg.0
0x940c  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.WorkflowAuthorServiceBase::get_Context()
0x9411  callvirt instance string Microsoft.Crm.Service.ObjectModel.ConvertRuleWorkflowAuthoringHelper::AuthorWorkflow(string entityId, string primaryEntityName, class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.IWorkflowErrorVisitorContext workflowErrorVisitorContext, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x9416  pop
0x9417  ret
0x9418  ldarg.0
0x9419  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.WorkflowAuthorServiceBase::get_Context()
0x941e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x9423  ldc.i4.1
0x9424  newobj   instance void Microsoft.Crm.Service.ObjectModel.RoutingWorkflowAuthoringHelper::.ctor(valuetype [mscorlib]System.Guid organizationId, bool isSdkContext)
0x9429  ldarg.0
0x942a  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.WorkflowAuthorServiceBase::get_Moniker()
0x942f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x9434  stloc.3
0x9435  ldloca.s 3
0x9437  constrained. [mscorlib]System.Guid
0x943d  callvirt instance string [mscorlib]System.Object::ToString()
0x9442  ldarg.0
0x9443  ldfld    string Microsoft.Crm.Service.ObjectModel.ServiceWorkflowAuthorService::_entityName
0x9448  ldarg.0
0x9449  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.WorkflowAuthorServiceBase::get_Context()
0x944e  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.WorkflowErrorVisitorContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x9453  ldarg.0
0x9454  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.WorkflowAuthorServiceBase::get_Context()
0x9459  callvirt instance string Microsoft.Crm.Service.ObjectModel.RoutingWorkflowAuthoringHelper::AuthorWorkflow(string entityId, string primaryEntityName, class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.IWorkflowErrorVisitorContext workflowErrorVisitorContext, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x945e  pop
0x945f  ret
```
