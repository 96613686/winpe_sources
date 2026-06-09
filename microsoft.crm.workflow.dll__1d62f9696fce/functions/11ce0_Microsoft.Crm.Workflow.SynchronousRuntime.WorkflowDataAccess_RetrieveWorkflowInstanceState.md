# Microsoft.Crm.Workflow.SynchronousRuntime.WorkflowDataAccess::RetrieveWorkflowInstanceState

- ea: `0x11ce0`
- end: `0x11d8d`
- name: `Microsoft.Crm.Workflow.SynchronousRuntime.WorkflowDataAccess::RetrieveWorkflowInstanceState`
- size: `173`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x6900`
- `0xda40`
- `0xdee0`
- `0xe0b0`
- `0x11b70`
- `0x11ca0`
- `0x11ce0`

## string_xrefs

- `0x11d81`: `On Resume Bookmark compressed WorkflowState should not be null or empty.`

## pseudocode

```c

```

## disassembly

```asm
0x11ce0  ldnull
0x11ce1  stloc.0
0x11ce2  ldarg.0
0x11ce3  call     instance class Microsoft.Crm.Workflow.InteractiveWorkflowInputContext Microsoft.Crm.Workflow.SynchronousRuntime.WorkflowDataAccess::get_InteractiveWorkflowInputContext()
0x11ce8  callvirt instance string Microsoft.Crm.Workflow.InteractiveWorkflowContext::get_WorkflowStateXml()
0x11ced  stloc.1
0x11cee  ldloc.1
0x11cef  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x11cf4  brfalse.s loc_11D5A
0x11cf6  ldarg.0
0x11cf7  call     instance class Microsoft.Crm.Workflow.InteractiveWorkflowInputContext Microsoft.Crm.Workflow.SynchronousRuntime.WorkflowDataAccess::get_InteractiveWorkflowInputContext()
0x11cfc  callvirt instance class Microsoft.Crm.Workflow.PageResult Microsoft.Crm.Workflow.InteractiveWorkflowInputContext::get_PageResult()
0x11d01  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Workflow.InteractionActivityResult> Microsoft.Crm.Workflow.PageResult::get_InteractionActivitiesResults()
0x11d06  brfalse.s loc_11D5A
0x11d08  ldarg.0
0x11d09  call     instance class Microsoft.Crm.Workflow.InteractiveWorkflowInputContext Microsoft.Crm.Workflow.SynchronousRuntime.WorkflowDataAccess::get_InteractiveWorkflowInputContext()
0x11d0e  callvirt instance class Microsoft.Crm.Workflow.PageResult Microsoft.Crm.Workflow.InteractiveWorkflowInputContext::get_PageResult()
0x11d13  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Workflow.InteractionActivityResult> Microsoft.Crm.Workflow.PageResult::get_InteractionActivitiesResults()
0x11d18  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Workflow.InteractionActivityResult>::get_Count()
0x11d1d  ldc.i4.0
0x11d1e  ble.s    loc_11D5A
0x11d20  ldarg.0
0x11d21  ldfld    class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.SynchronousRuntime.WorkflowDataAccess::_context
0x11d26  ldc.i4.0
0x11d27  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Workflow.ICommonWorkflowContext::CreateSdkService(bool asAdminUser)
0x11d2c  ldstr    aProcesssession_0// "processsession"
0x11d31  ldarg.1
0x11d32  ldc.i4.1
0x11d33  newarr   [mscorlib]System.String
0x11d38  dup
0x11d39  ldc.i4.0
0x11d3a  ldstr    aProcessstate// "processstate"
0x11d3f  stelem.ref
0x11d40  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(string[])
0x11d45  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Retrieve(string, valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet)
0x11d4a  ldstr    aProcessstate// "processstate"
0x11d4f  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x11d54  castclass [mscorlib]System.String
0x11d59  stloc.1
0x11d5a  ldloc.1
0x11d5b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x11d60  brtrue.s loc_11D8B
0x11d62  ldarg.0
0x11d63  ldarg.1
0x11d64  ldloc.1
0x11d65  call     instance bool Microsoft.Crm.Workflow.SynchronousRuntime.WorkflowDataAccess::VerifyProcessStateData(valuetype [mscorlib]System.Guid processSessionId, string hashEmbeddedCompressedWorkflowStateData)
0x11d6a  brfalse.s loc_11D78
0x11d6c  ldloc.1
0x11d6d  ldc.i4   0x80
0x11d72  callvirt instance string [mscorlib]System.String::Substring(int32)
0x11d77  stloc.0
0x11d78  ldloc.0
0x11d79  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x11d7e  ldc.i4.0
0x11d7f  ceq
0x11d81  ldstr    aOnResumeBookma// "On Resume Bookmark compressed WorkflowS"...
0x11d86  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x11d8b  ldloc.0
0x11d8c  ret
```
