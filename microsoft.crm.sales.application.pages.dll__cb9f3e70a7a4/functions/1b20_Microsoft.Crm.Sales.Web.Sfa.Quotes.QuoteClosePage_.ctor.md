# Microsoft.Crm.Sales.Web.Sfa.Quotes.QuoteClosePage::.ctor

- ea: `0x1b20`
- end: `0x1b4b`
- name: `Microsoft.Crm.Sales.Web.Sfa.Quotes.QuoteClosePage::.ctor`
- size: `43`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x1b20  ldarg.0
0x1b21  ldsfld   string [mscorlib]System.String::Empty
0x1b26  stfld    string Microsoft.Crm.Sales.Web.Sfa.Quotes.QuoteClosePage::_quoteId
0x1b2b  ldarg.0
0x1b2c  ldsfld   string [mscorlib]System.String::Empty
0x1b31  stfld    string Microsoft.Crm.Sales.Web.Sfa.Quotes.QuoteClosePage::_opportunityId
0x1b36  ldarg.0
0x1b37  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsOnline()
0x1b3c  ldc.i4.0
0x1b3d  ceq
0x1b3f  stfld    bool Microsoft.Crm.Sales.Web.Sfa.Quotes.QuoteClosePage::_offline
0x1b44  ldarg.0
0x1b45  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::.ctor()
0x1b4a  ret
```
