# Microsoft.Crm.Reporting.ReportServer::GetDataExtensionName

- ea: `0x4f10`
- end: `0x4f2b`
- name: `Microsoft.Crm.Reporting.ReportServer::GetDataExtensionName`
- size: `27`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x47f0`
- `0x4900`
- `0x4be0`

## callees

- `0x4f10`

## pseudocode

```c

```

## disassembly

```asm
0x4f10  ldarg.1
0x4f11  brfalse.s loc_4F19
0x4f13  ldarg.1
0x4f14  ldc.i4.1
0x4f15  beq.s    loc_4F1F
0x4f17  br.s     loc_4F25
0x4f19  ldsfld   string Microsoft.Crm.Reporting.ReportServer::SqlExtensionName
0x4f1e  ret
0x4f1f  ldsfld   string Microsoft.Crm.Reporting.ReportServer::FetchExtensionName
0x4f24  ret
0x4f25  ldsfld   string [mscorlib]System.String::Empty
0x4f2a  ret
```
