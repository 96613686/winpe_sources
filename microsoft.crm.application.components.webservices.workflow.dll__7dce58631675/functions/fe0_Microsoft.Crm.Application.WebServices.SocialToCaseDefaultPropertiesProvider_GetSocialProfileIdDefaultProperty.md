# Microsoft.Crm.Application.WebServices.SocialToCaseDefaultPropertiesProvider::GetSocialProfileIdDefaultProperty

- ea: `0xfe0`
- end: `0xff6`
- name: `Microsoft.Crm.Application.WebServices.SocialToCaseDefaultPropertiesProvider::GetSocialProfileIdDefaultProperty`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xeb0`

## callees

- `0x1490`
- `0x14c0`

## pseudocode

```c

```

## disassembly

```asm
0xfe0  ldstr    aSocialprofilei// "socialprofileid"
0xfe5  ldstr    aPostfromprofil// "postfromprofileid"
0xfea  ldarg.1
0xfeb  newobj   instance void Microsoft.Crm.Application.WebServices.PrimaryEntityAttributePropertyProvider::.ctor(string targetAttributeName, string sourceAttributeName, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0xff0  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification Microsoft.Crm.Application.WebServices.PrimaryEntityAttributePropertyProvider::GetProperty()
0xff5  ret
```
