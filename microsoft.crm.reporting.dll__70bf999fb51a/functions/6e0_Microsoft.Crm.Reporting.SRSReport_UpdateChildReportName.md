# Microsoft.Crm.Reporting.SRSReport::UpdateChildReportName

- ea: `0x6e0`
- end: `0x708`
- name: `Microsoft.Crm.Reporting.SRSReport::UpdateChildReportName`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x6c0`

## callees

- `0x5e0`
- `0x86a0`
- `0x87e0`

## pseudocode

```c

```

## disassembly

```asm
0x6e0  newobj   instance void <>c__DisplayClass36_0::.ctor()
0x6e5  stloc.0
0x6e6  ldloc.0
0x6e7  ldarg.2
0x6e8  stfld    string <>c__DisplayClass36_0::originalName
0x6ed  ldloc.0
0x6ee  ldarg.3
0x6ef  stfld    string <>c__DisplayClass36_0::newName
0x6f4  ldarg.0
0x6f5  ldarg.1
0x6f6  ldloc.0
0x6f7  ldftn    instance bool <>c__DisplayClass36_0::<UpdateChildReportName>b__0(class [System.Xml]System.Xml.XmlNode referencedReport)
0x6fd  newobj   instance void ReferencedReportProcessor::.ctor(object object, native int method)
0x702  call     instance void Microsoft.Crm.Reporting.SRSReport::ProcessReferencedReports(string xPath, class ReferencedReportProcessor reportProcessor)
0x707  ret
```
