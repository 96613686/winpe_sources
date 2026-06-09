# Microsoft.Crm.Common.Application.Commands.ApplicationCommand::LeadQualify_0

- ea: `0x2540`
- end: `0x255f`
- name: `Microsoft.Crm.Common.Application.Commands.ApplicationCommand::LeadQualify_0`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x2520`

## callees

- `0x5ce0`
- `0x5d80`

## pseudocode

```c

```

## disassembly

```asm
0x2540  ldarg.0
0x2541  ldarg.1
0x2542  ldarg.2
0x2543  ldarg.3
0x2544  ldarg.s  4
0x2546  ldarg.s  5
0x2548  ldarg.s  6
0x254a  ldarg.s  7
0x254c  ldarg.s  8
0x254e  ldarg.s  9
0x2550  ldarg.s  0xA
0x2552  ldarg.s  0xB
0x2554  newobj   instance void Microsoft.Crm.Common.Application.Platform.ServiceCommands.QualifyLeadCommand::.ctor(valuetype [mscorlib]System.Guid entityId, bool createAccount, bool createContact, bool createOpportunity, int32 newStatus, string opportunityCurrencyId, string opportunityParentId, int32 opportunityParentType, string campaignId, bool showNew, bool suppressDuplicateDetection, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x2559  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference> Microsoft.Crm.Common.Application.Platform.ServiceCommands.QualifyLeadCommand::Execute()
0x255e  ret
```
