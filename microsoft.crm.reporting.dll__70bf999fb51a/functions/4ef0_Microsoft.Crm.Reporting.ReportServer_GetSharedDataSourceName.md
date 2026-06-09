# Microsoft.Crm.Reporting.ReportServer::GetSharedDataSourceName

- ea: `0x4ef0`
- end: `0x4f0b`
- name: `Microsoft.Crm.Reporting.ReportServer::GetSharedDataSourceName`
- size: `27`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4900`
- `0x4be0`
- `0x8030`

## callees

- `0x4ef0`

## pseudocode

```c

```

## disassembly

```asm
0x4ef0  ldarg.1
0x4ef1  brfalse.s loc_4EF9
0x4ef3  ldarg.1
0x4ef4  ldc.i4.1
0x4ef5  beq.s    loc_4EFF
0x4ef7  br.s     loc_4F05
0x4ef9  ldsfld   string Microsoft.Crm.Reporting.ReportServer::SharedSqlDataSourceName
0x4efe  ret
0x4eff  ldsfld   string Microsoft.Crm.Reporting.ReportServer::SharedFetchDataSourceName
0x4f04  ret
0x4f05  ldsfld   string [mscorlib]System.String::Empty
0x4f0a  ret
```
