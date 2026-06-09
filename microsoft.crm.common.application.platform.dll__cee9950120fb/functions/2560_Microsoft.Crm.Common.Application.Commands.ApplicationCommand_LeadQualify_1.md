# Microsoft.Crm.Common.Application.Commands.ApplicationCommand::LeadQualify_1

- ea: `0x2560`
- end: `0x256f`
- name: `Microsoft.Crm.Common.Application.Commands.ApplicationCommand::LeadQualify_1`
- size: `15`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x5d80`
- `0x5e60`

## pseudocode

```c

```

## disassembly

```asm
0x2560  ldarg.0
0x2561  ldarg.2
0x2562  ldarg.1
0x2563  ldarg.3
0x2564  newobj   instance void Microsoft.Crm.Common.Application.Platform.ServiceCommands.QualifyLeadCommand::.ctor(valuetype [mscorlib]System.Guid entityId, string campaignId, int32 newStatus, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x2569  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference> Microsoft.Crm.Common.Application.Platform.ServiceCommands.QualifyLeadCommand::Execute()
0x256e  ret
```
