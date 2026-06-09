# Microsoft.Crm.Application.WebServices.WorkflowWebService::RefreshWorkflow

- ea: `0x2000`
- end: `0x2029`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::RefreshWorkflow`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x1ab0`
- `0x1e90`
- `0x2000`
- `0x8af0`

## pseudocode

```c

```

## disassembly

```asm
0x2000  ldc.i4.0
0x2001  stloc.0
0x2002  ldarg.3
0x2003  brtrue.s loc_200C
0x2005  ldarg.2
0x2006  call     bool Microsoft.Crm.Application.WebServices.WorkflowWebService::CanElevateToSystemUserForSystemJobRetrieve(string asyncId)
0x200b  stloc.0
0x200c  ldarg.0
0x200d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x2012  ldarg.1
0x2013  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x2018  ldloc.0
0x2019  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid, bool)
0x201e  stloc.1
0x201f  ldarg.0
0x2020  ldloc.1
0x2021  ldarg.2
0x2022  ldloc.0
0x2023  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflowWithoutSave(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string asyncId, bool useSystemUserContext)
0x2028  ret
```
