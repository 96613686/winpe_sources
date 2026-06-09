# Microsoft.Crm.Service.Web.Controls.Lookup.LookupSubjectPage::.ctor

- ea: `0x98e0`
- end: `0x9925`
- name: `Microsoft.Crm.Service.Web.Controls.Lookup.LookupSubjectPage::.ctor`
- size: `69`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## string_xrefs

- `0x98e1`: `var _fetchXml = new Array();`

## pseudocode

```c

```

## disassembly

```asm
0x98e0  ldarg.0
0x98e1  ldstr    aVarFetchxmlNew// "var _fetchXml = new Array();"
0x98e6  stfld    string Microsoft.Crm.Service.Web.Controls.Lookup.LookupSubjectPage::fetchArray
0x98eb  ldarg.0
0x98ec  ldstr    aVarObjectxslNe// "var _objectXsl = new Array();"
0x98f1  stfld    string Microsoft.Crm.Service.Web.Controls.Lookup.LookupSubjectPage::xslArray
0x98f6  ldarg.0
0x98f7  ldsfld   string [mscorlib]System.String::Empty
0x98fc  stfld    string Microsoft.Crm.Service.Web.Controls.Lookup.LookupSubjectPage::selectOptions
0x9901  ldarg.0
0x9902  ldsfld   string [mscorlib]System.String::Empty
0x9907  stfld    string Microsoft.Crm.Service.Web.Controls.Lookup.LookupSubjectPage::xml
0x990c  ldarg.0
0x990d  ldsfld   string [mscorlib]System.String::Empty
0x9912  stfld    string Microsoft.Crm.Service.Web.Controls.Lookup.LookupSubjectPage::returnObjectValues
0x9917  ldarg.0
0x9918  ldc.i4.1
0x9919  stfld    unsigned int32 Microsoft.Crm.Service.Web.Controls.Lookup.LookupSubjectPage::featureMask
0x991e  ldarg.0
0x991f  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::.ctor()
0x9924  ret
```
