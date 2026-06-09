# Microsoft.Crm.Web.Sfa.SfaUtility::CanCloseOpportunity

- ea: `0x10`
- end: `0x19`
- name: `Microsoft.Crm.Web.Sfa.SfaUtility::CanCloseOpportunity`
- size: `9`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x160`
- `0x1840`
- `0x1a40`

## pseudocode

```c

```

## disassembly

```asm
0x10  ldarg.0
0x11  ldarg.1
0x12  ldarg.2
0x13  call     bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.SfaUtility::CanCloseOpportunity(string, string, valuetype [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.OpportunityState)
0x18  ret
```
