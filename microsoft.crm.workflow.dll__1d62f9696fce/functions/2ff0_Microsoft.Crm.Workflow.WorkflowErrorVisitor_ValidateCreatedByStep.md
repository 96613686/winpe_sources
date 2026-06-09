# Microsoft.Crm.Workflow.WorkflowErrorVisitor::ValidateCreatedByStep

- ea: `0x2ff0`
- end: `0x3034`
- name: `Microsoft.Crm.Workflow.WorkflowErrorVisitor::ValidateCreatedByStep`
- size: `68`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1f90`
- `0x2060`
- `0x2130`

## callees

- `0x12f0`
- `0x1340`
- `0x13b0`
- `0x1d80`
- `0x2ff0`

## pseudocode

```c

```

## disassembly

```asm
0x2ff0  ldarg.1
0x2ff1  call     class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase Microsoft.Crm.Workflow.StepControlHelper::GetEntity(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase step)
0x2ff6  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep
0x2ffb  stloc.0
0x2ffc  ldloc.0
0x2ffd  brtrue.s loc_3001
0x2fff  ldc.i4.0
0x3000  ret
0x3001  ldarg.0
0x3002  call     instance class Microsoft.Crm.Workflow.IWorkflowErrorVisitorContext Microsoft.Crm.Workflow.WorkflowErrorVisitor::get_ErrorVisitorContext()
0x3007  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.IWorkflowErrorVisitorContext::get_OrganizationId()
0x300c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x3011  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3016  ldloc.0
0x3017  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase::get_EntityName()
0x301c  ldc.i4.1
0x301d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x3022  ldarg.2
0x3023  ldarg.0
0x3024  call     instance class Microsoft.Crm.Workflow.IWorkflowErrorVisitorContext Microsoft.Crm.Workflow.WorkflowErrorVisitor::get_ErrorVisitorContext()
0x3029  call     bool Microsoft.Crm.Workflow.StepControlHelper::IsValidEntityForControl(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entityMeta, valuetype Microsoft.Crm.Workflow.StepControlType stepType, class Microsoft.Crm.Workflow.IWorkflowUserPrivilegeCheck privilegeCheck)
0x302e  brtrue.s loc_3032
0x3030  ldc.i4.0
0x3031  ret
0x3032  ldc.i4.1
0x3033  ret
```
