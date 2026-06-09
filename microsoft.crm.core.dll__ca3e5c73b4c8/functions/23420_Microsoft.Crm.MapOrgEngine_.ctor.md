# Microsoft.Crm.MapOrgEngine::.ctor

- ea: `0x23420`
- end: `0x2345b`
- name: `Microsoft.Crm.MapOrgEngine::.ctor`
- size: `59`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x23431`: `/MSCRMServices/OfflineSync.ashx`
- `0x23439`: `/MSCRMServices/2007/CrmService.asmx?WSDL`
- `0x23441`: `/MSCRMServices/2007/MetadataService.asmx?WSDL`
- `0x23449`: `/MSCRMServices/2007/CrmServiceWsdl.aspx`

## pseudocode

```c

```

## disassembly

```asm
0x23420  ldarg.0
0x23421  ldc.i4.5
0x23422  newarr   [mscorlib]System.String
0x23427  dup
0x23428  ldc.i4.0
0x23429  ldstr    aCrmreportsRsvi// "/CRMReports/rsviewer/"
0x2342e  stelem.ref
0x2342f  dup
0x23430  ldc.i4.1
0x23431  ldstr    aMscrmservicesO// "/MSCRMServices/OfflineSync.ashx"
0x23436  stelem.ref
0x23437  dup
0x23438  ldc.i4.2
0x23439  ldstr    aMscrmservices2// "/MSCRMServices/2007/CrmService.asmx?WSD"...
0x2343e  stelem.ref
0x2343f  dup
0x23440  ldc.i4.3
0x23441  ldstr    aMscrmservices2_0// "/MSCRMServices/2007/MetadataService.asm"...
0x23446  stelem.ref
0x23447  dup
0x23448  ldc.i4.4
0x23449  ldstr    aMscrmservices2_1// "/MSCRMServices/2007/CrmServiceWsdl.aspx"
0x2344e  stelem.ref
0x2344f  stfld    string[] Microsoft.Crm.MapOrgEngine::exemptions
0x23454  ldarg.0
0x23455  call     instance void [mscorlib]System.Object::.ctor()
0x2345a  ret
```
