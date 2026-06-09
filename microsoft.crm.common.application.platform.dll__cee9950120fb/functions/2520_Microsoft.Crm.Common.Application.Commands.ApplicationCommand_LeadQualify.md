# Microsoft.Crm.Common.Application.Commands.ApplicationCommand::LeadQualify

- ea: `0x2520`
- end: `0x2539`
- name: `Microsoft.Crm.Common.Application.Commands.ApplicationCommand::LeadQualify`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x2540`

## pseudocode

```c

```

## disassembly

```asm
0x2520  ldarg.0
0x2521  ldarg.1
0x2522  ldarg.2
0x2523  ldarg.3
0x2524  ldarg.s  4
0x2526  ldarg.s  5
0x2528  ldarg.s  6
0x252a  ldarg.s  7
0x252c  ldarg.s  8
0x252e  ldarg.s  9
0x2530  ldc.i4.0
0x2531  ldarg.s  0xA
0x2533  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference> Microsoft.Crm.Common.Application.Commands.ApplicationCommand::LeadQualify(valuetype [mscorlib]System.Guid entityId, bool createAccount, bool createContact, bool createOpportunity, int32 newStatus, string opportunityCurrencyId, string opportunityParentId, int32 opportunityParentType, string campaignId, bool showNew, bool suppressDuplicateDetection, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x2538  ret
```
