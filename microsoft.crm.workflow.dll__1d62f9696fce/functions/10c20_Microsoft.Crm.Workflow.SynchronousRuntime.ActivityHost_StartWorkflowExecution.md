# Microsoft.Crm.Workflow.SynchronousRuntime.ActivityHost::StartWorkflowExecution

- ea: `0x10c20`
- end: `0x10e74`
- name: `Microsoft.Crm.Workflow.SynchronousRuntime.ActivityHost::StartWorkflowExecution`
- size: `596`
- prototype: ``
- caller_count: `0`
- callee_count: `22`
- tags: `broker_com_uri`

## callees

- `0x4fa0`
- `0x5060`
- `0x51a0`
- `0x5550`
- `0x5af0`
- `0x5b70`
- `0x6a70`
- `0x6b50`
- `0x9750`
- `0x97d0`
- `0x9840`
- `0x9850`
- `0x9b20`
- `0x10c20`
- `0x10e80`
- `0x10ed0`
- `0x110a0`
- `0x11b50`
- `0x14f40`
- `0x155a0`
- `0x16cc0`
- `0x2e6f0`

## string_xrefs

- `0x10e53`: `Thread synchronization completed for interactive workflow '{0}'.`

## pseudocode

```c

```

## disassembly

```asm
0x10c20  ldarg.2
0x10c21  newobj   instance void Microsoft.Crm.Workflow.WorkflowInstanceStore::.ctor(class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x10c26  stloc.0
0x10c27  ldnull
0x10c28  stloc.1
0x10c29  ldarg.0
0x10c2a  newobj   instance void SynchronousSynchronizationContext::.ctor()
0x10c2f  stfld    class [mscorlib]System.Threading.SynchronizationContext Microsoft.Crm.Workflow.SynchronousRuntime.ActivityHost::_syncContext
0x10c34  ldarg.0
0x10c35  ldarg.2
0x10c36  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x10c3b  call     instance class Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Workflow.ActivityHostBase::WorkflowResolveOrganizationConfiguration(valuetype [mscorlib]System.Guid organizationId)
0x10c40  ldarg.2
0x10c41  newobj   instance void Microsoft.Crm.Workflow.SynchronousRuntime.WorkflowDataAccess::.ctor(class Microsoft.Crm.Asynchronous.IOrganizationConfiguration config, class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x10c46  ldarg.2
0x10c47  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OperationId()
0x10c4c  callvirt instance string Microsoft.Crm.Workflow.IWorkflowDataAccess::RetrieveWorkflowInstanceState(valuetype [mscorlib]System.Guid instanceId)
0x10c51  stloc.2
0x10c52  ldarg.2
0x10c53  newobj   instance void Microsoft.Crm.Workflow.Services.ActivityReferenceService::.ctor(class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x10c58  call     void [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Services.WorkflowInitializationContext::set_ActivityReferenceService(class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Services.IActivityReferenceService)
0x10c5d  ldarg.2
0x10c5e  newobj   instance void Microsoft.Crm.Workflow.Services.WebActivityReferenceService::.ctor(class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x10c63  call     void [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Services.WorkflowInitializationContext::set_WebActivityReferenceService(class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Services.IActivityReferenceService)
0x10c68  ldarg.2
0x10c69  newobj   instance void Microsoft.Crm.Workflow.Services.SynchronousExpressionService::.ctor(class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x10c6e  call     void [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Services.WorkflowInitializationContext::set_ExpressionService(class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Services.IExpressionActivityService)
0x10c73  ldloc.2
0x10c74  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x10c79  brtrue.s loc_10CDB
0x10c7b  ldloc.0
0x10c7c  ldloc.2
0x10c7d  callvirt instance void Microsoft.Crm.Workflow.WorkflowInstanceStore::set_WorkflowState(string value)
0x10c82  ldarg.1
0x10c83  newobj   instance void [System.Activities]System.Activities.WorkflowApplication::.ctor(class [System.Activities]System.Activities.Activity)
0x10c88  stloc.1
0x10c89  ldloc.1
0x10c8a  ldarg.0
0x10c8b  ldfld    class [mscorlib]System.Threading.SynchronizationContext Microsoft.Crm.Workflow.SynchronousRuntime.ActivityHost::_syncContext
0x10c90  callvirt instance void [System.Activities]System.Activities.Hosting.WorkflowInstance::set_SynchronizationContext(class [mscorlib]System.Threading.SynchronizationContext)
0x10c95  ldloc.1
0x10c96  ldloc.0
0x10c97  callvirt instance void [System.Activities]System.Activities.WorkflowApplication::set_InstanceStore(class [System.Runtime.DurableInstancing]System.Runtime.DurableInstancing.InstanceStore)
0x10c9c  ldarg.0
0x10c9d  ldloc.1
0x10c9e  ldarg.2
0x10c9f  callvirt instance void Microsoft.Crm.Workflow.ActivityHostBase::AddHandlersAndExtensions(class [System.Activities]System.Activities.WorkflowApplication activityInstance, class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x10ca4  ldloc.1
0x10ca5  ldloc.0
0x10ca6  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.WorkflowInstanceStore::get_WorkflowApplicationId()
0x10cab  callvirt instance void [System.Activities]System.Activities.WorkflowApplication::Load(valuetype [mscorlib]System.Guid)
0x10cb0  ldarg.2
0x10cb1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x10cb6  ldc.i4.s 0x1E
0x10cb8  ldstr    aLoadingPersist// "Loading persisted workflow instance for"...
0x10cbd  ldc.i4.1
0x10cbe  newarr   [mscorlib]System.Object
0x10cc3  dup
0x10cc4  ldc.i4.0
0x10cc5  ldarg.2
0x10cc6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OperationId()
0x10ccb  box      [mscorlib]System.Guid
0x10cd0  stelem.ref
0x10cd1  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x10cd6  br       loc_10D9B
0x10cdb  ldnull
0x10cdc  stloc.3
0x10cdd  ldarg.0
0x10cde  ldarg.2
0x10cdf  call     instance bool Microsoft.Crm.Workflow.SynchronousRuntime.ActivityHost::NeedChildWorkflowInputParameters(class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x10ce4  brfalse.s loc_10D16
0x10ce6  ldarg.0
0x10ce7  ldarg.2
0x10ce8  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Workflow.SynchronousRuntime.ActivityHost::RetrieveChildWorkflowInputParameters(class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x10ced  stloc.3
0x10cee  ldarg.2
0x10cef  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x10cf4  ldc.i4.s 0x1E
0x10cf6  ldstr    aLoadedChildWor// "Loaded child workflow inputParameters f"...
0x10cfb  ldc.i4.1
0x10cfc  newarr   [mscorlib]System.Object
0x10d01  dup
0x10d02  ldc.i4.0
0x10d03  ldarg.2
0x10d04  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OperationId()
0x10d09  box      [mscorlib]System.Guid
0x10d0e  stelem.ref
0x10d0f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x10d14  br.s     loc_10D1C
0x10d16  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x10d1b  stloc.3
0x10d1c  ldarg.0
0x10d1d  ldarg.1
0x10d1e  isinst   [System.Activities]System.Activities.DynamicActivity
0x10d23  call     instance bool Microsoft.Crm.Workflow.ActivityHostBase::ContainsInputProperty(class [System.Activities]System.Activities.DynamicActivity dynamicActivity)
0x10d28  brfalse.s loc_10D46
0x10d2a  ldarg.2
0x10d2b  callvirt instance class Microsoft.Crm.Workflow.EntityDictionary Microsoft.Crm.Workflow.ICommonWorkflowContext::RetrieveEntityInstances()
0x10d30  stloc.s  4
0x10d32  ldloc.3
0x10d33  ldsfld   string Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::InputEntitiesVariableName
0x10d38  ldloc.s  4
0x10d3a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x10d3f  ldarg.0
0x10d40  ldloc.3
0x10d41  call     instance void Microsoft.Crm.Workflow.ActivityHostBase::AddCreatedEntitiesDictionary(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> inputDictionary)
0x10d46  ldarg.1
0x10d47  ldloc.3
0x10d48  newobj   instance void [System.Activities]System.Activities.WorkflowApplication::.ctor(class [System.Activities]System.Activities.Activity, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>)
0x10d4d  stloc.1
0x10d4e  ldloc.1
0x10d4f  ldarg.0
0x10d50  ldfld    class [mscorlib]System.Threading.SynchronizationContext Microsoft.Crm.Workflow.SynchronousRuntime.ActivityHost::_syncContext
0x10d55  callvirt instance void [System.Activities]System.Activities.Hosting.WorkflowInstance::set_SynchronizationContext(class [mscorlib]System.Threading.SynchronizationContext)
0x10d5a  ldloc.0
0x10d5b  ldloc.1
0x10d5c  callvirt instance valuetype [mscorlib]System.Guid [System.Activities]System.Activities.Hosting.WorkflowInstance::get_Id()
0x10d61  callvirt instance void Microsoft.Crm.Workflow.WorkflowInstanceStore::set_WorkflowApplicationId(valuetype [mscorlib]System.Guid value)
0x10d66  ldloc.1
0x10d67  ldloc.0
0x10d68  callvirt instance void [System.Activities]System.Activities.WorkflowApplication::set_InstanceStore(class [System.Runtime.DurableInstancing]System.Runtime.DurableInstancing.InstanceStore)
0x10d6d  ldarg.0
0x10d6e  ldloc.1
0x10d6f  ldarg.2
0x10d70  callvirt instance void Microsoft.Crm.Workflow.ActivityHostBase::AddHandlersAndExtensions(class [System.Activities]System.Activities.WorkflowApplication activityInstance, class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x10d75  ldarg.2
0x10d76  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x10d7b  ldc.i4.s 0x1E
0x10d7d  ldstr    aStartingANewIn// "Starting a new instance of interactive "...
0x10d82  ldc.i4.1
0x10d83  newarr   [mscorlib]System.Object
0x10d88  dup
0x10d89  ldc.i4.0
0x10d8a  ldarg.2
0x10d8b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OperationId()
0x10d90  box      [mscorlib]System.Guid
0x10d95  stelem.ref
0x10d96  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x10d9b  ldarg.0
0x10d9c  ldloc.1
0x10d9d  ldarg.2
0x10d9e  call     instance void Microsoft.Crm.Workflow.ActivityHostBase::OnWorkflowLoaded(class [System.Activities]System.Activities.WorkflowApplication activityInstance, class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x10da3  ldarg.0
0x10da4  ldloc.1
0x10da5  ldarg.2
0x10da6  call     instance void Microsoft.Crm.Workflow.ActivityHostBase::OnWorkflowStarted(class [System.Activities]System.Activities.WorkflowApplication activityInstance, class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x10dab  ldloc.0
0x10dac  callvirt instance bool Microsoft.Crm.Workflow.WorkflowInstanceStore::get_InstanceHasBookmarks()
0x10db1  brfalse.s loc_10DFE
0x10db3  ldarg.2
0x10db4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x10db9  ldc.i4.s 0x1E
0x10dbb  ldstr    aResumingBookma// "Resuming bookmark from persisted intera"...
0x10dc0  ldc.i4.1
0x10dc1  newarr   [mscorlib]System.Object
0x10dc6  dup
0x10dc7  ldc.i4.0
0x10dc8  ldarg.2
0x10dc9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OperationId()
0x10dce  box      [mscorlib]System.Guid
0x10dd3  stelem.ref
0x10dd4  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x10dd9  ldarg.0
0x10dda  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x10ddf  stfld    valuetype [mscorlib]System.DateTime Microsoft.Crm.Workflow.SynchronousRuntime.ActivityHost::_perfRuntimeInitTime
0x10de4  ldarg.0
0x10de5  ldfld    class [mscorlib]System.Threading.SynchronizationContext Microsoft.Crm.Workflow.SynchronousRuntime.ActivityHost::_syncContext
0x10dea  callvirt instance void [mscorlib]System.Threading.SynchronizationContext::OperationStarted()
0x10def  ldloc.1
0x10df0  call     string [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.BookmarkNames::get_Default()
0x10df5  ldnull
0x10df6  callvirt instance valuetype [System.Activities]System.Activities.BookmarkResumptionResult [System.Activities]System.Activities.WorkflowApplication::ResumeBookmark(string, object)
0x10dfb  pop
0x10dfc  br.s     loc_10E40
0x10dfe  ldarg.2
0x10dff  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x10e04  ldc.i4.s 0x1E
0x10e06  ldstr    aRunningInterac// "Running interactive workflow first time"...
0x10e0b  ldc.i4.1
0x10e0c  newarr   [mscorlib]System.Object
0x10e11  dup
0x10e12  ldc.i4.0
0x10e13  ldarg.2
0x10e14  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OperationId()
0x10e19  box      [mscorlib]System.Guid
0x10e1e  stelem.ref
0x10e1f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x10e24  ldarg.0
0x10e25  ldfld    class [mscorlib]System.Threading.SynchronizationContext Microsoft.Crm.Workflow.SynchronousRuntime.ActivityHost::_syncContext
0x10e2a  callvirt instance void [mscorlib]System.Threading.SynchronizationContext::OperationStarted()
0x10e2f  ldarg.0
0x10e30  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x10e35  stfld    valuetype [mscorlib]System.DateTime Microsoft.Crm.Workflow.SynchronousRuntime.ActivityHost::_perfRuntimeInitTime
0x10e3a  ldloc.1
0x10e3b  callvirt instance void [System.Activities]System.Activities.WorkflowApplication::Run()
0x10e40  leave.s  loc_10E72
0x10e42  pop
0x10e43  rethrow
0x10e45  ldarg.0
0x10e46  call     instance void Microsoft.Crm.Workflow.SynchronousRuntime.ActivityHost::SignalSyncThreadContext()
0x10e4b  ldarg.2
0x10e4c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x10e51  ldc.i4.s 0x1E
0x10e53  ldstr    aThreadSynchron// "Thread synchronization completed for in"...
0x10e58  ldc.i4.1
0x10e59  newarr   [mscorlib]System.Object
0x10e5e  dup
0x10e5f  ldc.i4.0
0x10e60  ldarg.2
0x10e61  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OperationId()
0x10e66  box      [mscorlib]System.Guid
0x10e6b  stelem.ref
0x10e6c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x10e71  endfinally
0x10e72  ldloc.1
0x10e73  ret
```
