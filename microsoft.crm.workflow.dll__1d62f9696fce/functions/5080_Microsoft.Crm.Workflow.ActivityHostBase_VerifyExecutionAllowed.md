# Microsoft.Crm.Workflow.ActivityHostBase::VerifyExecutionAllowed

- ea: `0x5080`
- end: `0x5184`
- name: `Microsoft.Crm.Workflow.ActivityHostBase::VerifyExecutionAllowed`
- size: `260`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4ee0`
- `0x10ad0`
- `0x11df0`

## callees

- `0x4f90`
- `0x5080`
- `0x9310`

## string_xrefs

- `0x50cc`: `Server settings do not allow running XAML workflows not created by the CRM application.`

## pseudocode

```c

```

## disassembly

```asm
0x5080  ldarg.3
0x5081  ldnull
0x5082  stind.ref
0x5083  ldarg.1
0x5084  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.WorkflowActivationData::get_IsCrmUIWorkflow()
0x5089  brtrue.s loc_50D9
0x508b  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x5090  ldstr    aAllowdeclarati// "AllowDeclarativeWorkflows"
0x5095  ldc.i4.0
0x5096  callvirt T0x2B000003
0x509b  brtrue.s loc_50D9
0x509d  ldarg.0
0x509e  callvirt instance string Microsoft.Crm.Workflow.ActivityHostBase::GetXamlWorkflowsResource()
0x50a3  stloc.0
0x50a4  ldarg.3
0x50a5  ldc.i4   0x80045041
0x50aa  ldloc.0
0x50ab  ldc.i4.0
0x50ac  newarr   [mscorlib]System.Object
0x50b1  newobj   instance void Microsoft.Crm.Workflow.WorkflowOperationFailedResult::.ctor(int32 errorCode, string errorFormat, object[] args)
0x50b6  stind.ref
0x50b7  ldnull
0x50b8  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x50bd  ldc.i4.s 0x1E
0x50bf  ldstr    a0// "{0}"
0x50c4  ldc.i4.1
0x50c5  newarr   [mscorlib]System.Object
0x50ca  dup
0x50cb  ldc.i4.0
0x50cc  ldstr    aServerSettings// "Server settings do not allow running XA"...
0x50d1  stelem.ref
0x50d2  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x50d7  ldc.i4.0
0x50d8  ret
0x50d9  ldarg.2
0x50da  ldc.i4.1
0x50db  bne.un.s loc_5129
0x50dd  ldarg.1
0x50de  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.WorkflowActivationData::get_WorkflowCategory()
0x50e3  brfalse.s loc_5129
0x50e5  ldarg.1
0x50e6  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.WorkflowActivationData::get_WorkflowCategory()
0x50eb  ldc.i4.2
0x50ec  beq.s    loc_5129
0x50ee  ldstr    aCategoryNotSet// "Category not set to AsynchronousWorkflo"...
0x50f3  stloc.0
0x50f4  ldarg.3
0x50f5  ldc.i4   0x80040315
0x50fa  ldloc.0
0x50fb  ldc.i4.0
0x50fc  newarr   [mscorlib]System.Object
0x5101  newobj   instance void Microsoft.Crm.Workflow.WorkflowOperationFailedResult::.ctor(int32 errorCode, string errorFormat, object[] args)
0x5106  stind.ref
0x5107  ldnull
0x5108  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x510d  ldc.i4.s 0x1E
0x510f  ldstr    a0// "{0}"
0x5114  ldc.i4.1
0x5115  newarr   [mscorlib]System.Object
0x511a  dup
0x511b  ldc.i4.0
0x511c  ldstr    aOnlyAsynchrono// "Only AsynchronousWorkflow BPF-PBL can b"...
0x5121  stelem.ref
0x5122  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5127  ldc.i4.0
0x5128  ret
0x5129  ldarg.2
0x512a  ldc.i4.2
0x512b  bne.un.s loc_5182
0x512d  ldarg.1
0x512e  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.WorkflowActivationData::get_WorkflowCategory()
0x5133  ldc.i4.1
0x5134  beq.s    loc_5182
0x5136  ldarg.1
0x5137  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.WorkflowActivationData::get_WorkflowCategory()
0x513c  brfalse.s loc_5182
0x513e  ldarg.1
0x513f  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.WorkflowActivationData::get_WorkflowCategory()
0x5144  ldc.i4.3
0x5145  beq.s    loc_5182
0x5147  ldstr    aCategoryNotSet_0// "Category not set to InteractiveWorkflow"...
0x514c  stloc.0
0x514d  ldarg.3
0x514e  ldc.i4   0x80040315
0x5153  ldloc.0
0x5154  ldc.i4.0
0x5155  newarr   [mscorlib]System.Object
0x515a  newobj   instance void Microsoft.Crm.Workflow.WorkflowOperationFailedResult::.ctor(int32 errorCode, string errorFormat, object[] args)
0x515f  stind.ref
0x5160  ldnull
0x5161  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x5166  ldc.i4.s 0x1E
0x5168  ldstr    a0// "{0}"
0x516d  ldc.i4.1
0x516e  newarr   [mscorlib]System.Object
0x5173  dup
0x5174  ldc.i4.0
0x5175  ldstr    aOnlyInteractiv// "Only InteractiveWorkflow or Synchronous"...
0x517a  stelem.ref
0x517b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5180  ldc.i4.0
0x5181  ret
0x5182  ldc.i4.1
0x5183  ret
```
