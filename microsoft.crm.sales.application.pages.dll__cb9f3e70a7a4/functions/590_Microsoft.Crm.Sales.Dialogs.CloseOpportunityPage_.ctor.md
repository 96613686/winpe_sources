# Microsoft.Crm.Sales.Dialogs.CloseOpportunityPage::.ctor

- ea: `0x590`
- end: `0x5ce`
- name: `Microsoft.Crm.Sales.Dialogs.CloseOpportunityPage::.ctor`
- size: `62`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x590  ldarg.0
0x591  ldsfld   string [mscorlib]System.String::Empty
0x596  stfld    string Microsoft.Crm.Sales.Dialogs.CloseOpportunityPage::EstimatedRevenue
0x59b  ldarg.0
0x59c  ldsfld   string [mscorlib]System.String::Empty
0x5a1  stfld    string Microsoft.Crm.Sales.Dialogs.CloseOpportunityPage::EstimatedCloseDate
0x5a6  ldarg.0
0x5a7  ldsfld   string [mscorlib]System.String::Empty
0x5ac  stfld    string Microsoft.Crm.Sales.Dialogs.CloseOpportunityPage::JScriptHeader
0x5b1  ldarg.0
0x5b2  ldsfld   string [mscorlib]System.String::Empty
0x5b7  stfld    string Microsoft.Crm.Sales.Dialogs.CloseOpportunityPage::OpportunityId
0x5bc  ldarg.0
0x5bd  ldsfld   string [mscorlib]System.String::Empty
0x5c2  stfld    string Microsoft.Crm.Sales.Dialogs.CloseOpportunityPage::OpportunityIsWon
0x5c7  ldarg.0
0x5c8  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::.ctor()
0x5cd  ret
```
