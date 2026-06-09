# Microsoft.Crm.Application.WebServices.ProcessWebService::DeserializeJsonWorkflowStep

- ea: `0x19b0`
- end: `0x19c9`
- name: `Microsoft.Crm.Application.WebServices.ProcessWebService::DeserializeJsonWorkflowStep`
- size: `25`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18a0`
- `0x1930`

## pseudocode

```c

```

## disassembly

```asm
0x19b0  newobj   instance void [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer::.ctor()
0x19b5  ldarg.1
0x19b6  callvirt T0x2B000009
0x19bb  stloc.0
0x19bc  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::.ctor()
0x19c1  dup
0x19c2  ldloc.0
0x19c3  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::InitializeFromDynamic(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>)
0x19c8  ret
```
