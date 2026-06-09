# Microsoft.Crm.Workflow.SynchronousRuntime.WorkflowDataAccess::SaveWorkflowInstanceState

- ea: `0x11c00`
- end: `0x11ca0`
- name: `Microsoft.Crm.Workflow.SynchronousRuntime.WorkflowDataAccess::SaveWorkflowInstanceState`
- size: `160`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x6900`
- `0xda50`
- `0x11b90`

## string_xrefs

- `0x11c78`: `Interactive workflow {0} has been persisted; compressed workflow state is {1} bytes.`

## pseudocode

```c

```

## disassembly

```asm
0x11c00  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor()
0x11c05  stloc.0
0x11c06  ldloc.0
0x11c07  ldstr    aProcesssession_0// "processsession"
0x11c0c  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_LogicalName(string)
0x11c11  ldloc.0
0x11c12  ldarg.1
0x11c13  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Id(valuetype [mscorlib]System.Guid)
0x11c18  ldloc.0
0x11c19  ldstr    aProcessstate// "processstate"
0x11c1e  ldarg.2
0x11c1f  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x11c24  ldarg.0
0x11c25  ldfld    class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.SynchronousRuntime.WorkflowDataAccess::_context
0x11c2a  ldc.i4.1
0x11c2b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Workflow.ICommonWorkflowContext::CreateSdkService(bool asAdminUser)
0x11c30  dup
0x11c31  ldloc.0
0x11c32  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Update(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0x11c37  ldstr    aProcesssession_0// "processsession"
0x11c3c  ldarg.1
0x11c3d  ldc.i4.1
0x11c3e  newarr   [mscorlib]System.String
0x11c43  dup
0x11c44  ldc.i4.0
0x11c45  ldstr    aProcessstate// "processstate"
0x11c4a  stelem.ref
0x11c4b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(string[])
0x11c50  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Retrieve(string, valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet)
0x11c55  ldstr    aProcessstate// "processstate"
0x11c5a  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x11c5f  castclass [mscorlib]System.String
0x11c64  stloc.1
0x11c65  ldarg.0
0x11c66  call     instance class Microsoft.Crm.Workflow.InteractiveWorkflowOutputContext Microsoft.Crm.Workflow.SynchronousRuntime.WorkflowDataAccess::get_InteractiveWorkflowOutputContext()
0x11c6b  ldloc.1
0x11c6c  callvirt instance void Microsoft.Crm.Workflow.InteractiveWorkflowContext::set_WorkflowStateXml(string value)
0x11c71  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x11c76  ldc.i4.s 0x1E
0x11c78  ldstr    aInteractiveWor_0// "Interactive workflow {0} has been persi"...
0x11c7d  ldc.i4.2
0x11c7e  newarr   [mscorlib]System.Object
0x11c83  dup
0x11c84  ldc.i4.0
0x11c85  ldarg.1
0x11c86  box      [mscorlib]System.Guid
0x11c8b  stelem.ref
0x11c8c  dup
0x11c8d  ldc.i4.1
0x11c8e  ldarg.2
0x11c8f  callvirt instance int32 [mscorlib]System.String::get_Length()
0x11c94  box      [mscorlib]System.Int32
0x11c99  stelem.ref
0x11c9a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x11c9f  ret
```
