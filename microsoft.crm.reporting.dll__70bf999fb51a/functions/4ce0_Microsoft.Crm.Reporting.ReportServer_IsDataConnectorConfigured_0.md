# Microsoft.Crm.Reporting.ReportServer::IsDataConnectorConfigured_0

- ea: `0x4ce0`
- end: `0x4cf8`
- name: `Microsoft.Crm.Reporting.ReportServer::IsDataConnectorConfigured_0`
- size: `24`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4be0`

## callees

- `0x4ce0`
- `0x4dc0`

## pseudocode

```c

```

## disassembly

```asm
0x4ce0  ldarg.0
0x4ce1  ldarg.1
0x4ce2  call     instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSourceDefinition Microsoft.Crm.Reporting.ReportServer::GetDataSourceDefinition(string dataSourcePath)
0x4ce7  callvirt instance string [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSourceDefinition::get_Extension()
0x4cec  ldarg.2
0x4ced  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x4cf2  brfalse.s loc_4CF6
0x4cf4  ldc.i4.0
0x4cf5  ret
0x4cf6  ldc.i4.1
0x4cf7  ret
```
