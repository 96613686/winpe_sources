# Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::SwitchProcess

- ea: `0xf490`
- end: `0xf4ed`
- name: `Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::SwitchProcess`
- size: `93`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xd6f0`
- `0xd960`
- `0xf3f0`

## callees

- `0xf490`
- `0xf4f0`

## string_xrefs

- `0xf4d0`: `Knowledge Article with Article Id {0} moved to {1} BPF.`

## pseudocode

```c

```

## disassembly

```asm
0xf490  ldarg.0
0xf491  ldarg.2
0xf492  ldarg.3
0xf493  call     instance bool Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::IsBusinessProcessFlowPublished(valuetype [mscorlib]System.Guid processGuid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xf498  brfalse.s loc_F4EC
0xf49a  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.WorkflowService::.ctor()
0xf49f  ldstr    aKnowledgeartic_6// "knowledgearticle"
0xf4a4  ldarg.1
0xf4a5  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0xf4aa  ldstr    aWorkflow_0// "workflow"
0xf4af  ldarg.2
0xf4b0  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0xf4b5  ldarg.3
0xf4b6  ldnull
0xf4b7  callvirt instance void class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.WorkflowServiceInternal`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.UpgradingOff>::SetProcess(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference)
0xf4bc  ldarg.3
0xf4bd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xf4c2  ldc.i4.0
0xf4c3  ldstr    a0// "{0}"
0xf4c8  ldc.i4.1
0xf4c9  newarr   [mscorlib]System.Object
0xf4ce  dup
0xf4cf  ldc.i4.0
0xf4d0  ldstr    aKnowledgeArtic// "Knowledge Article with Article Id {0} m"...
0xf4d5  ldarg.1
0xf4d6  box      [mscorlib]System.Guid
0xf4db  ldarg.2
0xf4dc  box      [mscorlib]System.Guid
0xf4e1  call     string [mscorlib]System.String::Format(string, object, object)
0xf4e6  stelem.ref
0xf4e7  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xf4ec  ret
```
