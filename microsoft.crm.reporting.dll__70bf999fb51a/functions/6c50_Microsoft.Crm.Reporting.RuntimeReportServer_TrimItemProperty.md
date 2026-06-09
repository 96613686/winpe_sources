# Microsoft.Crm.Reporting.RuntimeReportServer::TrimItemProperty

- ea: `0x6c50`
- end: `0x6c64`
- name: `Microsoft.Crm.Reporting.RuntimeReportServer::TrimItemProperty`
- size: `20`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x5d40`
- `0x6cd0`

## callees

- `0x6c50`

## pseudocode

```c

```

## disassembly

```asm
0x6c50  ldarg.0
0x6c51  callvirt instance int32 [mscorlib]System.String::get_Length()
0x6c56  ldarg.1
0x6c57  bgt.s    loc_6C5B
0x6c59  ldarg.0
0x6c5a  ret
0x6c5b  ldarg.0
0x6c5c  ldc.i4.0
0x6c5d  ldarg.1
0x6c5e  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x6c63  ret
```
