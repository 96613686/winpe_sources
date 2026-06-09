# Microsoft.Crm.Workflow.ObjectModel.NullObjectsFactory::BuildEntity

- ea: `0x2cb30`
- end: `0x2cbba`
- name: `Microsoft.Crm.Workflow.ObjectModel.NullObjectsFactory::BuildEntity`
- size: `138`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x2cb30`
- `0x31f60`
- `0x3eb50`
- `0x3f240`
- `0x3f2e0`
- `0x3f4e0`

## string_xrefs

- `0x2cb57`: `RelatedEntityLinked:#Microsoft.Crm.Workflow.Expressions`
- `0x2cb64`: `EntityCreatedByStep:#Microsoft.Crm.Workflow.Expressions`

## pseudocode

```c

```

## disassembly

```asm
0x2cb30  ldstr    aAccount// "account"
0x2cb35  ldc.i4.0
0x2cb36  newobj   instance void Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::.ctor(string primaryEntityName, int32 category)
0x2cb3b  stloc.0
0x2cb3c  ldarg.0
0x2cb3d  ldstr    aPrimaryentityM// "PrimaryEntity:#Microsoft.Crm.Workflow.E"...
0x2cb42  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2cb47  brtrue.s loc_2CB72
0x2cb49  ldarg.0
0x2cb4a  ldstr    aRelatedentityM// "RelatedEntity:#Microsoft.Crm.Workflow.E"...
0x2cb4f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2cb54  brtrue.s loc_2CB79
0x2cb56  ldarg.0
0x2cb57  ldstr    aRelatedentityl// "RelatedEntityLinked:#Microsoft.Crm.Work"...
0x2cb5c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2cb61  brtrue.s loc_2CB8A
0x2cb63  ldarg.0
0x2cb64  ldstr    aEntitycreatedb// "EntityCreatedByStep:#Microsoft.Crm.Work"...
0x2cb69  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2cb6e  brtrue.s loc_2CBA0
0x2cb70  br.s     loc_2CBB8
0x2cb72  ldloc.0
0x2cb73  newobj   instance void Microsoft.Crm.Workflow.Expressions.PrimaryEntity::.ctor(class Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflow)
0x2cb78  ret
0x2cb79  ldloc.0
0x2cb7a  ldstr    aDummyproperty// "dummyProperty"
0x2cb7f  ldstr    aDummyentity// "dummyEntity"
0x2cb84  newobj   instance void Microsoft.Crm.Workflow.Expressions.RelatedEntity::.ctor(class Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflow, string relatedAttributeName, string relatedEntity)
0x2cb89  ret
0x2cb8a  ldloc.0
0x2cb8b  ldstr    aDummyproperty// "dummyProperty"
0x2cb90  ldstr    aDummyentity// "dummyEntity"
0x2cb95  ldstr    aDummyrelations// "dummyRelationshipName"
0x2cb9a  newobj   instance void Microsoft.Crm.Workflow.Expressions.RelatedEntityLinked::.ctor(class Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflow, string relatedAttributeName, string relatedEntity, string relationshipName)
0x2cb9f  ret
0x2cba0  ldloc.0
0x2cba1  ldnull
0x2cba2  ldstr    aDummy// "dummy"
0x2cba7  ldstr    aDummy// "dummy"
0x2cbac  ldstr    aDummy// "dummy"
0x2cbb1  ldc.i4.1
0x2cbb2  newobj   instance void Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep::.ctor(class Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflow, class Microsoft.Crm.Workflow.ObjectModel.StepBase step, string entityName, string entityIdentifier, string parameterName, bool isCustomOperationArgument)
0x2cbb7  ret
0x2cbb8  ldnull
0x2cbb9  ret
```
