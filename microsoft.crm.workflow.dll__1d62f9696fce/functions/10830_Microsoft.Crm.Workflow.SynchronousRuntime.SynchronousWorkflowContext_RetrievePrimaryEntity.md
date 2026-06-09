# Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowContext::RetrievePrimaryEntity

- ea: `0x10830`
- end: `0x10944`
- name: `Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowContext::RetrievePrimaryEntity`
- size: `276`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callees

- `0x7330`
- `0x7390`
- `0x73b0`
- `0x73d0`
- `0x7610`
- `0x8340`
- `0xf070`
- `0x10830`

## string_xrefs

- `0x108ed`: `Delete`
- `0x1086e`: `Create`

## pseudocode

```c

```

## disassembly

```asm
0x10830  ldarg.0
0x10831  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowContext::pluginContext
0x10836  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext::get_Stage()
0x1083b  stloc.0
0x1083c  ldloc.0
0x1083d  ldc.i4.s 0x1E
0x1083f  bgt.s    loc_10853
0x10841  ldloc.0
0x10842  ldc.i4.s 0x14
0x10844  beq.s    loc_10868
0x10846  ldloc.0
0x10847  ldc.i4.s 0x1E
0x10849  beq      loc_1091B
0x1084e  br       loc_10923
0x10853  ldloc.0
0x10854  ldc.i4.s 0x23
0x10856  beq      loc_1091B
0x1085b  ldloc.0
0x1085c  ldc.i4.s 0x28
0x1085e  beq      loc_108E7
0x10863  br       loc_10923
0x10868  ldarg.0
0x10869  call     instance string Microsoft.Crm.Workflow.WorkflowContextBase::get_MessageName()
0x1086e  ldstr    aCreate// "Create"
0x10873  call     bool [mscorlib]System.String::op_Equality(string, string)
0x10878  brfalse.s loc_10895
0x1087a  ldarg.0
0x1087b  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowContext::pluginContext
0x10880  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_InputParameters()
0x10885  ldstr    aTarget// "Target"
0x1088a  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x1088f  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity
0x10894  ret
0x10895  ldarg.0
0x10896  callvirt instance int32 Microsoft.Crm.Workflow.WorkflowContextBase::get_WorkflowCategory()
0x1089b  ldc.i4.2
0x1089c  bne.un.s loc_108D6
0x1089e  ldarg.0
0x1089f  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityImageCollection Microsoft.Crm.Workflow.WorkflowContextBase::get_PreEntityImages()
0x108a4  ldstr    aPrebusinessent// "PreBusinessEntity"
0x108a9  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Item(void)
0x108ae  ldarg.0
0x108af  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowContext::pluginContext
0x108b4  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_InputParameters()
0x108b9  ldstr    aTarget// "Target"
0x108be  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x108c3  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity
0x108c8  stloc.1
0x108c9  ldloc.1
0x108ca  ldarg.0
0x108cb  call     instance string Microsoft.Crm.Workflow.WorkflowContextBase::get_PrimaryEntityName()
0x108d0  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Workflow.Utility.WorkflowUtility::Coalesce(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity baseEntity, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity overrideEntity, string primaryEntityName)
0x108d5  ret
0x108d6  ldarg.0
0x108d7  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityImageCollection Microsoft.Crm.Workflow.WorkflowContextBase::get_PreEntityImages()
0x108dc  ldstr    aPrebusinessent// "PreBusinessEntity"
0x108e1  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Item(void)
0x108e6  ret
0x108e7  ldarg.0
0x108e8  call     instance string Microsoft.Crm.Workflow.WorkflowContextBase::get_MessageName()
0x108ed  ldstr    aDelete// "Delete"
0x108f2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x108f7  brfalse.s loc_1090A
0x108f9  ldarg.0
0x108fa  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityImageCollection Microsoft.Crm.Workflow.WorkflowContextBase::get_PreEntityImages()
0x108ff  ldstr    aPrebusinessent// "PreBusinessEntity"
0x10904  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Item(void)
0x10909  ret
0x1090a  ldarg.0
0x1090b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityImageCollection Microsoft.Crm.Workflow.WorkflowContextBase::get_PostEntityImages()
0x10910  ldstr    aPostbusinessen// "PostBusinessEntity"
0x10915  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Item(void)
0x1091a  ret
0x1091b  ldarg.0
0x1091c  ldarg.1
0x1091d  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Workflow.WorkflowContextBase::RetrievePrimaryEntity(class [Microsoft.Crm.Sdk]Microsoft.Crm.Workflow.EntityDependencyBase entityDependency)
0x10922  ret
0x10923  ldstr    aStage0NotSuppo// "Stage {0} not supported"
0x10928  ldarg.0
0x10929  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowContext::pluginContext
0x1092e  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext::get_Stage()
0x10933  box      [mscorlib]System.Int32
0x10938  call     string [mscorlib]System.String::Format(string, object)
0x1093d  ldnull
0x1093e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmNotSupportedException::.ctor(string, class [mscorlib]System.Exception)
0x10943  throw
```
