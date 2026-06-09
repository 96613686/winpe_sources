# Microsoft.Crm.Reporting.SetupReportServer::CreateHiddenProperty

- ea: `0x7a30`
- end: `0x7a4c`
- name: `Microsoft.Crm.Reporting.SetupReportServer::CreateHiddenProperty`
- size: `28`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x8030`
- `0x8160`

## pseudocode

```c

```

## disassembly

```asm
0x7a30  newobj   instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Property::.ctor()
0x7a35  dup
0x7a36  ldstr    aHidden// "Hidden"
0x7a3b  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Property::set_Name(string)
0x7a40  dup
0x7a41  ldsfld   string [mscorlib]System.Boolean::TrueString
0x7a46  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Property::set_Value(string)
0x7a4b  ret
```
